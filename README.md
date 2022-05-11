
# Astreuos: A Next Generation Blockchain for Apps, Storage and Compute that's Distributed, Secure and Sustainable

Roy Okello
royokello@protonmail.com

## Introduction

Astreuos is an accounts based blockchain which primarily works by keeping track of all the accounts and their details such as the balance, number of transactions and storage.

The motivation for building Astreuos is to build a better blockchain for creating trusted smart contracts and price mechanisms for currency stability.

Blockchains benefit from trust-less consensus, permission-less access and great security for users.

The Astreuos blockchain intergrates distributed layers for storage and compute.

Astreuos aims to be a competitive platform for digital services by:

- offering native value, storage and compute on the blockchain
- pricing services in a dynamic currency
- implementing a pricing mechanism that promotes currency stability

## Components

### Libraries

- [Astro Format](https://github.com/stelar-labs/astro-format-rs) - Data Encoding Format
- [NeutronDB](https://github.com/stelar-labs/neutrondb-rs) - Key Value Store
- [Opis](https://github.com/stelar-labs/opis-rs) - Integer Arithmetic
- [Fides](https://github.com/stelar-labs/fides-rs) - Cryptography
- [Pulsar Network](https://github.com/stelar-labs/pulsar-network-rs) - Messaging
- [Rust Astreuos](https://github.com/astreuos/node-rs) - Official Node

### Accounts

An Astreuos Account is a data structure of an address and details associated to that account. Each account has a balance, a counter and storage.

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
                  . - - - - - - - - - - - - - + - - - - - - - - - - - - - .
                  ^                           ^                           ^
          + - - - - - - - - +       + - - - - - - - - - +       + - - - - - - - - - +
          |  balance hash   |       |   counter hash    |       |   storage hash    |
          + - - - - - - - - +       + - - - - - - - - - +       + - - - - - - - - - +

```

`Account Storage`

```text

                                                  + - - - - - - - +
                                                  |  storage hash |
                                                  + - - - - - - - +
                                                          ^
                                        . - - - - - - - - + - - - - - - - - - .
                                        ^                                     ^
                                + - - - - - - - - - +               + - - - - - - - - - - - +
                                |  key-value 1 hash |               |   key-value 2 hash    |
                                + - - - - - - - - - +               + - - - - - - - - - - - +
                                        ^
                        . - - - - - - - + - - - - - - - .
                        ^                               ^
                + - - - - - - - +               + - - - - - - - +
                |  key 1 hash   |               |  value 1 hash |
                + - - - - - - - +               + - - - - - - - +

```

`Accounts State Transition`

```text

            Block #1                                Block #2
        + - - - - - - - +                       + - - - - - - - +
        |               |                       |               | 
        |   Previous    |      Transactions     |     Latest    |
        |   Accounts    |   - - - - - - - - ->  |    Accounts   |
        |     State     |                       |     State     |
        |               |                       |               |
        + - - - - - - - +                       + - - - - - - - +

```

The account balance is in the native unit of value which is a `Quark`.

Value magnitudes are:

- 10^24 `YottaQuark` `[YQ]`
- 10^21 `ZettaQuark` `[ZQ]`
- 10^18 `ExaQuark` `[EQ]`
- 10^15 `PetaQuark` `[PQ]`
- 10^12 `TeraQuark` `[TQ]`
- 10^9  `GigaQuark` `[GQ]`
- 10^6  `MegaQuark` `[MQ]`
- 10^3  `KiloQuark` `[KQ]`
- 10^0  `Quark` `[Q]`

### Blocks

A Block consists of the block body and the validator's ed25519 signature of the body's merkle tree root.

The block body has:

1. accounts hash
2. chain
3. number
4. previous block hash
5. receipts hash
6. solar price
7. solar used
8. time
9. transactions hash
10. validator

The Receipt is the result from the application of a transaction to the Astreuos Account State.

A receipt consists of the solar used and status of the transaction application procedure.

### Transactions

A Transaction consists of the transaction body and the sender's ed25519 signature of the body's merkle tree root.

The transaction body has:

1. chain
2. counter
3. recipient
4. sender
5. solar limit
6. solar price
7. value

### Solar

`Solar` is the currency for work done on the blockchain, in contrast with `Quark` with is the currency for value.

The solar limit of a block is set at 10^12 `Solar`.

Transaction Processing costs 10^6 `Solar`.

Solar pricing mechanism:

- The solar price is fixed for every block.
- The solar price varies by 1 `Quark`.
- The solar price increases when more than 0.9, and decreases when less than 0.1, of the previous solar limit was used.
- The base solar price is set at 1 `Quark`.

### Nova Consensus

Nova is the consensus protocol for creating new blocks and validating the blockchain.

A validator must be staked, by sending `Quarks` to the nova account, to participate in the protocol.

The nova account address is 0x 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 6E 6F 76 61.

The block time target is five seconds. A slot is the five seconds period when new blocks are created.

Slots are allocated pro-rata to a validator's stake.

A slot miss occurs when a validator does not create a new block or created a malicious block when selected.

Slot selection determines the validator for the next block at any time:

- Get validator addresses with slot allocations in the nova account storage.
- Check slot misses from the last block to the current time.
- If no slot miss, the latest block hash is used as the seed in the weighted random address selector.
- If slot misses, the linear-feedback shift register, shifted to the number of slot misses, of the lastest block hash is used as the seed in the weighted random address selector.

Transactions are ordered by their hash.

The creator of a new block is payed a fee of 10^12 `Solar` at the current block's solar price.

### Fusion

Fusion is the applications platform running on the Astreuos Blockchain.

Contracts are applications that run through Transaction Calls on-chain.

Reactions are applications that run through Computation Contracts off-chain.

The Fusion Language is a dialect of the Lisp programming language for developing Fusion Applications.

The Fusion Machine is a stack based native runtime for Fusion Machine Code interfacing with the Astreuos Accounts State.

Helium is the Fusion code manager.

- runs automated tests
- compiles your fusion script into fusion machine code

New transaction types:

- app creation
- app calls

### Nebula

Nebula is a protocol for storing and retrieving Nebula Objects.

Users can negotiate the `Solar` price for Get and Put contracts.

A Nebula Object is a data structure with three fields:

- Leaf: True/False
- Data: a blob of binary data of size < 32KB
- Size: the cumulative number of leaves

Puslar Network Upgrade:

- nebula route
- message contexts for get and put

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

The index route stores the index of the object hash and the storage provider's id.

The route is updated every five minutes to remove deleted objects and redistribute indexes adding new objects.

An indexer must prove they are storing their part of the index.

A node can use the returned id to query the storage route for the storage provider to retrieve the object.

The storage provider is paid storage fees for the storage period and retrival fees for serving an object.

A stoage provider must prove they are storing their assigned objects.

Indexers are incentivized to cache objects by earning retrival fees for returning objects instead of storage provider's id.

An indexer also earns a commission for facilitating a put contract and indexing the underlying data.

The Retrieval Fees for 32KB is 1,000 Solar.

The Storage Fees for 32KB/mo is 2,000 Solar.

### Reactor

Reactor is a protocol for distributed serverless computation with proof of work staking.

Fusion Applications running on Reactor are referred to as Reactions.

Reactions can be Open or Private.

Open Reactions work by processing apps stored on Nebula and are callable by anyone on the blockchain.

Private Reaction is confidential computing enabling users to use private data and protect software intellectual property on the protocol while allowing for restricted access to calls.

## Applications

### Global Payments

### Local Exchanges

### Smart Contracts

### User Powered

### Transparency

### Content Addressing

### Self Hosting

### Serverless

### Indexing

## References

1. Bitcoin: A Peer-to-Peer Electronic Cash System - Satoshi Nakamoto
2. Ethereum White Paper - Vitalik Buterin
3. Ethereum Yellow Paper - Gavin Wood
4. Kademlia: A Peer-to-Peer Information System Based on the XOR Metric - Petar Maymounkov & David Mazières
5. Recursive Functions of Symbolic Expressions and Their Computation by Machine - John McCarthy
6. High-speed high-security signatures - Daniel J. Bernstein, Niels Duif, Tanja Lange, Peter Schwabe and Bo-Yin Yang

2022-05-11
