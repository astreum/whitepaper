
# Astreuos: A Next Generation Blockchain for Apps, Storage and Compute

Roy Okello

royokello@protonmail.com

## Introduction

Bitcoin is the first decentralized blockchain which was pseudonymously created by Satoshi Nakamoto.

It was created as a peer-to-peer electronic cash system built on cryptographic functions.

Bitcoin introduced a privacy model for financial transactions, blockchain proof-of-work mechanism and a node incentive model for decentralized systems.

This allowed for decentralized and secure electronic funds transfers that is permissionless and trustless. 

Etheruem, a next generation smart contract and decentralized application platform, was introduced in 2014 by Vitalik Buterin.

Etheruem introduces a new state model and turing complete scripting capability to transactions.

Etheruem's scripting capabilities allowed for the creation of decentralized applications that are trustless.

Astreuos is a next generation blockchain for apps, storage and compute.

- apps: decentralized applications
- storage: distributed storage
- compute: distributed compute

Astreuos consensus protocol, Nova Protocol, is Proof of Stake for security and sustainability.

Astreuos primarily works by keeping track of all the accounts and their details such as the balance, code, number of transactions and storage that change with every transaction.

Users are able to :-
- transfer value & validation
- storage query & supply
- compute queries & supply

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

Nodes connected to the Nebula route store the distributed index of the object hashes and their storage provider's id.

Every index is updated every five minutes to remove deleted objects.

An indexer must prove they are storing their part of the index.

The storage provider is paid storage fees for the storage period and retrival fees for serving an object.

A stoage provider must prove they are storing their objects.

Indexers are incentivized to cache objects by earning retrival fees for returning cached objects.

An indexer earns a commission for facilitating a put contract and indexing the underlying data.

### Reactor

Reactor is a protocol for distributed serverless computation with proof of work staking.

Fusion Applications running on Reactor are referred to as Reactions.

Reactions can be Open or Private.

Open Reactions work by processing apps stored on Nebula and are callable by anyone on the blockchain.

Private Reactions is confidential computing enabling users to use private data and protect software intellectual property on the protocol while allowing for restricted access to calls.

## Applications

### Global Payments

### Local Exchanges

### Smart Contracts

### User Powered

### Transparency

### Content Addressing

### Self Hosting

### Serverless

## References

1. Bitcoin: A Peer-to-Peer Electronic Cash System - Satoshi Nakamoto
2. Ethereum White Paper - Vitalik Buterin
3. Ethereum Yellow Paper - Gavin Wood
4. Kademlia: A Peer-to-Peer Information System Based on the XOR Metric - Petar Maymounkov & David Mazières
5. Recursive Functions of Symbolic Expressions and Their Computation by Machine - John McCarthy
6. High-speed high-security signatures - Daniel J. Bernstein, Niels Duif, Tanja Lange, Peter Schwabe and Bo-Yin Yang

2022-05-25
