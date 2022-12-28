
# Astreum: A Next Generation Blockchain for Apps, Storage and Compute

## Author

Roy R. O. Okello

[Email](mailto:royokello@protonmail.com)

[Github](https://github.com/royokello)

[Twitter](https://twitter.com/RealOkello)

## Introduction

This paper introduces an accounts based blockchain for zero knowledge apps, perpetual storage and confidential compute that's decentralized and secure.

Features: 

- permissionless accounts access
- trustless consensus
- post quantum secure
- value transactions
- programmable accounts
- Nebula, a distributed storage protocol
- Fusion, a language for developing zero knowledge and confidential applications
- Reactor, a distributed computation protocol for Fusion Applications
- Pulsar, an open peer-to-peer communication protocol for Astreum Nodes

Astreum primarily works by keeping track of all the accounts and their details such as the balance, code, number of transactions and storage in a block and changes through applying transactions.

Astreum introduces a standard model for pricing and verification of transactions, storage, compute and networking.

Applications are written in the Fusion Language, which is a Lisp dialect whose lists are addressable from Nebula, the Distributed Storage Protocol.

Applications can run through Transactions or Reactor, the Distributed Compute Protocol.

Astreum Nodes communicate through the Pulsar Network.

`Overview`

```text
        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
        |  Fusion       |       |  Nebula       |       |  Reactor      |
        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +

        + - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +
        |  Accounts                                                     |
        + - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +

        + - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +
        |  Pulsar Routes                                                |
        + - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +

        + - - - - - - - - - - - - - - +   + - - - - - - - - - - - - - - +
        |  Pulsar Gateways            |   |  Internet                   |
        + - - - - - - - - - - - - - - +   + - - - - - - - - - - - - - - +
```

## Protocols

### Pulsar

Pulsar Network is the distributed hash table peer-to-peer communication protocol for the Astreum Blockchain.

Nodes communicate by passing envelopes with messages through routes.

An Envelope has four fields:

- message
- nonce
- sender
- time

A message contains two fields:

- body
- topic

#### Pings

Pings are used for initial communication setup and updating peer liveness.

The initiating node (Node A) sends an envelope without a message and the kyber & x25519 public keys in the sender field.

`ping: ip address -> Envelope`

The receiving node (Node B) responds if Node A is in its init list or not in its peer list. 

```

ping_response: Envelope ->

        if sender is in init list: add to peer list and send handshake

        elif sender is in peer list: maybe update keys and timestamp

        else: send handshake

```

#### Routing Messages

- Join Request
- Routing Request
- Routing Response

#### Execution Messages

- Cancel Transaction
- Transaction
- Transaction Proof

#### Consensus Messages

- Transactions
- Block
- Block Request

#### Nebula Messages

- Get Request
- Get Response
- Put Request
- Put Response

#### Reactor Messages

- Compute Request
- Compute Response

#### Gateway

Pulsar Gateway Protocol provides an open protocol for routing data through out the Pulsar Network as an alternative to the Internet.

Openness is in reference to the transparency of the cost of transmitting data through data paths and the permissionless ability to create a gateway.

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

The valid chain has the most blocks and with the most solar spent in the latest block.

### Nebula

Nebula is a protocol for storing and retrieving Nebula Objects.

Users pay the present value of the perpetual storage cost of the object.

Astreum pays storage providers in perpetuity for proofs of storage.

A Nebula Object is a data structure with two fields:

- Leaf; True/False
- Data; a blob of binary data of size < 32KB

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

Users use account channels to pay for services.

## Components

### Nodes

Nodes are the primary components of the Astreum Network which all participants operate.

A Node's roles are:

- Connect and Message on the Pulsar Network
- Create, Execute and Transmit Transactions
- Create and Verify Blocks

### Terminals

Terminal is a specification for building user interfaces on top of the Astreum Node.

A terminal provides:

- querying capabilities for hashes of nebula objects and text from name services
- account management
- run Fusion Applications
- render Fusion Templates

### Accounts

An Astreum Account is a data structure of an address and details associated to that account.

Each account has:

1. balance
2. channels
3. code
4. counter
5. storage

Account Types:

- private; controlled by private keys
- contract; controlled by account code

`Accounts`

```text

                                                        + - - - - - - - +
                                                        |   accounts    |
                                                        + - - - - - - - +
                                                                ^
                                                    . - - - - - - - - - - - .
                                                    ^                       ^
                                            + - - - - - - - +       + - - - - - - - +
                                            |   account 1   |       |   account 2   |
                                            + - - - - - - - +       + - - - - - - - +
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
        |    balance    |       |   channels    |       |     code      |       |    counter    |       |   storage     |
        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +

```

### Channels

A channel provides a way of making micropayments for storage, compute and networking off-chain.

A channel consists of a counterparty address, balance, counter and timelock.

`Channel Transactions`

```text

+ - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +
|               | fund          | approve       | withdraw      | close         |
+ - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +

| chain         | XX            | XX            | XX            | XX            |

| counter       | XX            | CH. COUNTER   | XX            | XX            |

| data          | CH. TIMELOCK  | 00            | CH. APPROVE   | 00            |
|               |               |               | TX HASH       |               |

| recipient     | COUNTERPARTY  | COUNTERPARTY  | PRIMARY       | COUNTERPARTY  |

| solar limit   | XX            | 00            | XX            | XX            |

| type          | CH. FUND      | CH. APPROVE   | CH. WITHDRAW  | CH. CLOSE     |

| value         | ADDITIONAL    | WITHDRAWL     | 00            | 00            |
|               | BALANCE       | AMOUNT        |               |               |

+ - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +

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

Transaction types:

- value transfer
- channel fund
- channel approve
- channel withdraw
- channel close
- contract create
- contract call

### Solar

`Solar` is the unit of value in the Astreum Blockchain.

The account balance, storage, compute and networking costs are denominated in `Solar`.

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

Solar costs for basic operations on 256 bits:

```text

+ - - - - - - - - - - - - - - - +
|               | words | solar |
+ - - - - - - - - - - - - - - - +
| storage       | 1     | 1     |
| compute       | 1     | 3     |
|               | 2     | 4     |
+ - - - - - - - - - - - - - - - +

```

### Fusion

Fusion is the applications platform running on the Astreum Blockchain.

Applications can run through transactions, compute contracts and natively on Astreum Nodes.

The Fusion Language is a dialect of the Lisp programming language for developing Fusion Applications and Templates.

Developers create Fusion Scripts that are compiled into Fusion Machine Code.

The Fusion Machine is the stack based native runtime for Fusion Machine Code. 

The Astreum Machine is a Fusion Machine that interfaces with Astreum Blocks and Accounts.

## Conclusion

Astreum offers the following benefits:

- distribution and decentralization of digital services such as financial intermediation, data storage, serverless computation and networking through its trust-less models
- permission-less and pseudonymous or anonymous access to digital services
- open and censorship free platform for content creators and application developers
- one language for developing applications and templates, while still extensible to any use case

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

2022-10-08
