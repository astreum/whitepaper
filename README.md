
# Astreum: A Next Generation Blockchain for Zero Knowledge Apps, Perpetual Storage and Serverless Compute

## Author

Roy R. O. Okello

[Email](mailto:0xR3y@protonmail.com)

[Github](https://github.com/0xR3y)

[Twitter](https://twitter.com/0xR3y)

## Introduction

This paper introduces a blockchain for zero knowledge apps, perpetual storage and serverless compute that's decentralized and secure.

Features: 

- trustless and permissionless access
- value transactions
- programmable accounts
- distributed & perpetual storage
- distributed, no config & confidential compute
- a language for developing zero knowledge apps
- rewards for providing storage and compute

Astreum primarily works by keeping track of all the accounts and their details such as the balance, code, number of transactions and storage in a block and changes through applying transactions.

Astreum has a standard model for pricing and verification of transactions, storage and compute.

Applications are written in the Fusion Language, which is a Lisp dialect whose lists are addressable from Nebula, the Distributed Storage Protocol.

Applications can run through Transactions or Reactor, the Distributed Compute Protocol.

## Protocols

### Pulsar

Pulsar Network is the distributed hash table peer-to-peer communication protocol for the Astreum Blockchain.

Nodes communicate by passing envelopes with messages.

Envelope:

- kyber public key
- message(empty for key exchange)
- nonce
- time
- x25519 public key

Message:

- body
- topic

#### Topics

Standard Topics:

- Join Request
- Join Response
- Ping Request
- Ping Response
- Bootstrap

Nova Topics:

- Cancel Transaction
- Transaction
- Transactions
- Block
- Block Request

Storage Topics:

- Get Request
- Get Response
- Put Request
- Put Response

Reactor Topics:

- Compute Request
- Compute Response


### Nova

Nova is the proof of stake consensus protocol for executing transactions and creating new blocks through provers and verifiers.

A verifier must be staked, by sending `Solar` to the nova account, to participate in the protocol.

The nova account address is 0x 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 6E 6F 76 61.

The block time target is three seconds. A slot is the three seconds period when new blocks are created.

Slots are allocated pro-rata to a verifier's stake.

A slot miss occurs when a verifiers does not create a new block or creates a malicious block when selected.

Slot selection determines the verifier for the next block at any time:

- Check slot misses from the latest block
- If no slot miss, the latest block time output is used as the seed in the weighted random address selector
- If slot misses, the linear-feedback shift register, shifted to the number of slot misses, of the latest block time output is used as the seed in the weighted random address selector

Verifiers who miss a slot get half their stake returned until 1 `Solar` is left.

Transactions are ordered by the prover.

Transactions proofs enable other nodes to efficiently verify the accounts transition.

Verifiers spend ~1 sec computing a time output from a verifiable delay function.

The creator of a new block is payed a fee of 10^12 `Solar`.

The latest block is the highest and most solar spent.

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

Applications can be confidential enabling users to use private data, preserve privacy and protect intellectual property.

## Components

### Nodes

| Type | Role | Fees Paid |
|---|---|---|
| Clients | - | - |
| Provers | Execute transactions and generate transactions proofs | Transaction |
| Verifiers | Verify transaction execution and create blocks | Block |
| Nebula | Store and provide access to accounts and contracted data | Storage |
| Reactor | Provide compute resources on-demand  | Compute |

### Terminals

Terminal is a specification for building user interfaces.

A terminal provides:

- querying capabilities for hashes of nebula objects and text from name services
- account management

Terminals can natively run Fusion applications and render templates stored on Nebula.

### Accounts

An Astreum Account is a data structure of an address and details associated to that account.

Each account has:

1. balance
2. channels
3. code
4. counter
5. storage

`Accounts State`

```text

                                                        + - - - - - - - - - - - +
                                                        |       accounts        |
                                                        + - - - - - - - - - - - +
                                                                    ^
                                                    . - - - - - - - - - - - - - - - .
                                                    ^                               ^
                                        + - - - - - - - - - - - +       + - - - - - - - - - - - +
                                        |       account 1       |       |       account 2       |
                                        + - - - - - - - - - - - +       + - - - - - - - - - - - +
                                                    ^
                                        . - - - - - - - - - - - .
                                        ^                       ^
                                + - - - - - - - +       + - - - - - - - +
                                |    address    |       |    details    |
                                + - - - - - - - +       + - - - - - - - +
                                                                ^
                . - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - .
                ^                       ^                       ^                       ^                       ^
        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +   
        |    balance    |       |    channels   |       |     code      |       |    counter    |       |    storage    |
        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +

```

### Blocks

A Block has the following fields:

1. accounts hash
2. chain
3. number
4. previous block hash
5. prover
6. receipts hash
7. solar spent
8. time
9. time output
10. time proof
11. transactions hash
12. transactions proof
13. verifier

### Transactions

A Transaction consists of:

1. body
2. dilithium3 public keys
3. dilithium3 signatures
4. ed25519 public keys
5. ed25519 signatures

The transaction body has:

1. chain
2. counter
3. data
4. recipient
5. solar limit
6. type
7. value

The Transaction types are:

- app call
- app creation
- value transfer

### Solar

`Solar` is the unit of value in the Astreum Blockchain.

The account balance, storage and compute costs are denominated in `Solar`.

Value magnitudes are:

- 10^24: Yotta Solar
- 10^21: Zetta Solar
- 10^18: Exa Solar
- 10^15: Peta Solar
- 10^12: Tera Solar
- 10^9:  Giga Solar
- 10^6:  Mega Solar
- 10^3:  Kilo Solar
- 10^0:  Solar

Solar costs for operations on 256 bits:

| Type | Words | Solar |
|---|---|---|
| storage | 1 | 1 |
| compute | 1 | 3 |
| | 2 | 4 |

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

2022-08-03
