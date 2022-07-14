
# Astreum: A Next Generation Blockchain for Apps, Storage and Compute

## Author

Roy R. O. Okello

[Email](mailto:0xR3y@protonmail.com)

[Github](https://github.com/0xR3y)

[Twitter](https://twitter.com/0xR3y)

## Introduction

This paper expresses my vision for a blockchain that embodies the ethos set forth by pioneers of decentralized systems for permissionless and trustless access to value transactions, data storage and confidential computation.

Astreum introduces a new model for pricing, verification and payment for transactions, storage and compute.

Astreum primarily works by keeping track of all the accounts and their details such as the balance, code, number of transactions and storage in a block and changes through applying transactions.

Applications are written in the Fusion Language, which is a Lisp dialect whose lists are addressable from Nebula, the Distributed Storage Protocol.

Applications can run through Transactions or Reactor, the Distributed Compute Protocol.

## Protocols

### Pulsar

Pulsar Network is the distributed hash table peer-to-peer communication protocol for the Astreum Blockchain.

### Nova

Nova is the proof of stake consensus protocol for executing transactions and creating new blocks through provers and verifiers.

A Verifier must be staked, by sending `Astre` to the nova account, to participate in the protocol.

The nova account address is 0x 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 6E 6F 76 61.

The block time target is three seconds. A slot is the three seconds period when new blocks are created.

Slots are allocated pro-rata to a Verifier's stake.

A slot miss occurs when a Verifiers does not create a new block or creates a malicious block when selected.

Slot selection determines the Verifier for the next block at any time:

- Check slot misses from the latest block
- If no slot miss, the latest block time output is used as the seed in the weighted random address selector
- If slot misses, the linear-feedback shift register, shifted to the number of slot misses, of the latest block time output is used as the seed in the weighted random address selector

Verifiers who miss a slot get half their stake returned until 1 `Astre` is left.

Transactions are ordered by their hash.

Transactions proof enable other nodes to efficiently verify the accounts transition.

Verifiers spend ~1 sec computing a Time Output from a Verifiable Delay Function.

The creator of a new block is payed a fee of 10^18 `Solar`.

### Nebula

Nebula is a protocol for storing and retrieving Nebula Objects.

Users pay the present value of the perpetual storage cost of the object.

Astreum pays storage providers in perpetuity for proofs of storage.

A Nebula Object is a data structure with two fields:

- Leaf: True/False
- Data: a blob of binary data of size < 32KB

Nebula supports storage for:

- Lists(Data and Fusion Applications)
- Files(Plain, Encrypted and Erasure Coded)

`Object Get Flow`

```text

        Client                                          Nebula
        + - - - +                                       
        |       |             object hash               + - - - - - - - +
        |       | - - - - - - - - - - - - - - - - - - > |    nearest    |
        |       | < - - - - - - - - - - - - - - - - - - |     node      |
        |       |       nearer node or object           + - - - - - - - +
        |       |
        |       |
        |       |             object hash               + - - - - - - - +
        |       | - - - - - - - - - - - - - - - - - - > |    nearer     |
        |       | < - - - - - - - - - - - - - - - - - - |     node      |
        |       |         index node or object          + - - - - - - - +
        |       |
        |       |
        |       |               object hash             + - - - - - - - +
        |       | - - - - - - - - - - - - - - - - - - > |    index      |
        |       | < - - - - - - - - - - - - - - - - - - |     node      |
        |       |        storage node or object         + - - - - - - - +
        |       |
        |       |
        |       |             object hash               + - - - - - - - +
        |       | - - - - - - - - - - - - - - - - - - > |    storage    |
        |       | < - - - - - - - - - - - - - - - - - - |     node      |
        |       |               object                  + - - - - - - - +
        |       |
        + - - - +

```

Storage Nodes store the distributed index of the object hashes and their storage provider's address.

The storage provider is paid by providing proofs of storage.

### Reactor

Reactor is a protocol for distributed computation.

Applications can be confidential enabling users to use private data, preserving privacy and use proprietary software, protecting intellectual property.

The compute cost is derived from the current supply and demand.

## Components

### Nodes

| Type | Role | Fees Paid |
|---|---|---|
| Clients | - | - |
| Provers | Execute Transactions and generate proofs | Transaction |
| Verifiers | Verify Transaction execution and create blocks | Block |
| Nebula | Store and provide access to accounts and contracted data | Storage |
| Reactor | Provide compute resources on-demand  | Compute |

### Terminals

The Terminal is a specification for building user interfaces.

A terminal provides querying capabilities for hashes of Nebula Objects and text from name services.

Terminals can natively run Fusion Applications stored as Lists on Nebula.

### Accounts

An Astreum Account is a data structure of an address and details associated to that account. Each account has a balance, code, counter and storage.

`Accounts State`

```text

                                                        + - - - - - - - - - - - +
                                                        |     accounts hash     |
                                                        + - - - - - - - - - - - +
                                                                     ^
                                                . - - - - - - - - - - - - - - - - - - - .
                                                ^                                       ^
                                        + - - - - - - - - +                   + - - - - - - - - - +
                                        | account 1 hash  |                   |   account 2 hash  |
                                        + - - - - - - - - +                   + - - - - - - - - - +
                                                ^
                                . - - - - - - - - - - - - - .
                                ^                           ^
                      + - - - - - - - - - +       + - - - - - - - - - +
                      |   address hash    |       |   details hash    |
                      + - - - - - - - - - +       + - - - - - - - - - +
                                                            ^
                  . - - - - - - - - - - - - - . - - - - - - + - - - - - - . - - - - - - - - - - - - - .
                  ^                           ^                           ^                           ^
          + - - - - - - - - +       + - - - - - - - - - +       + - - - - - - - - - +       + - - - - - - - - - +
          |  balance hash   |       |     code hash     |       |   counter hash    |       |   storage hash    |
          + - - - - - - - - +       + - - - - - - - - - +       + - - - - - - - - - +       + - - - - - - - - - +

```

### Blocks

A Block has the following fields:

1. accounts hash
2. chain
3. number
4. previous block hash
5. prover
6. receipts hash
7. solar price
8. solar used
9. time
10. time output
11. time proof
12. transactions hash
13. transactions proof
14. verifier

### Transactions

A Transaction consists of:

1. body
2. dilithium3 public key
3. dilithium3 signature
4. ed25519 public key
5. ed25519 signature

The transaction body has:

1. chain
2. counter
3. data
4. recipient
5. solar limit
6. type
7. value

### Solar

`Solar` is the unit of value in the Astreum Blockchain.

The account balance, storage and compute costs are denominated in `Solar`.

Value magnitudes are:

- 10^24: YottaSolar
- 10^21: ZettaSolar
- 10^18: ExaSolar
- 10^15: PetaSolar
- 10^12: TeraSolar
- 10^9:  GigaSolar
- 10^6:  MegaSolar
- 10^3:  KiloSolar
- 10^0:  Solar

Solar costs for operations on 256 bits:

| Operation | Solar |
|---|---|
| storage per word per block | 1 |
| 1 word arithmetic | 3 |
| 2 words arithmetic | 5 |

### Fusion

Fusion is the applications platform running on the Astreum Blockchain.

Applications can run through transactions, compute contracts and natively on nodes.

The Fusion Language is a dialect of the Lisp programming language for developing Fusion applications and templates.

The Fusion Machine is a stack based native runtime for Fusion Machine Code interfacing with the Astreum Accounts State.

## Conclusion

With Astreum we create a system that offers the following benefits:

- distribution of financial intermediary and cloud service fees
- permissionless and pseudonymous(anonymous through private payment channels such as mixers) access to financial services
- open and censorship free platform for creators and developers
- one language for developing applications and templates, extensible to any current and future use case

## References

1. Bitcoin: A Peer-to-Peer Electronic Cash System - Satoshi Nakamoto
2. Ethereum White Paper - Vitalik Buterin
3. Ethereum Yellow Paper - Gavin Wood
4. Kademlia: A Peer-to-Peer Information System Based on the XOR Metric - Petar Maymounkov & David Mazières
5. Recursive Functions of Symbolic Expressions and Their Computation by Machine - John McCarthy
6. High-speed high-security signatures - Daniel J. Bernstein, Niels Duif, Tanja Lange, Peter Schwabe and Bo-Yin Yang
7. CRYSTALS-Dilithium Algorithm Specifications and Supporting Documentation - Shi Bai, Léo Ducas, Eike Kiltz, Tancrède Lepoint,Vadim Lyubashevsky, Peter Schwabe, Gregor Seiler and Damien Stehlé
8. Efficient verifiable delay functions - Benjamin Wesolowski
9. PLONK: Permutations over Lagrange-bases for Oecumenical Noninteractive arguments of Knowledge - Ariel Gabizon, Zachary J. Williamson and Oana Ciobotaru

2022-07-15
