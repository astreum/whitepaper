
# Astreuos

### A Next Generation Blockchain for Apps, Storage and Compute that's Decentralized, Secure and Sustainable.

## Introduction

An accounts based blockchain with storage and compute protocols is presented in this paper. A motivation for such a blockchain is to build a better crypto experience with standards for building trusted smart contracts and price mechanisms for currency stability. 

As a blockchain, we benefit from trustless consensus and from the use of cryptography with permissionless access and great security for users. This empowers anyone in the world with uncensored access and benefit from the blockchain.

The blockchain primarily works by keeping track of all the accounts and details such as the balance, number of transactions and storage.

Astreuos aims to be a competitive and viable platform for powerful web3 services by offering a combined value, storage and compute on a single blockchain priced in a single currency.

Astreuos empowers web3 developers to:
- create powerful experiences that interface with blockchain node apis for transactions, storage and compute.
- host applications, static sites and media content on Nebula.
- perform compute intensive applications using Reactor Private & Open Compute.

## Contents

1. Accounts
2. Blocks
3. Transactions
4. Nova Consensus
5. Fusion Upgrade
6. Nebula Upgrade
7. Reactor Upgrade
8. Roadmap

### Accounts

An Astreuos Account is a makeup of an address and details associated to that account. Each account has a balance, a counter and storage.

`Accounts State`

```

                                        + - - - - - - - - - - - +
                                        |     Accounts Hash     |
                                        + - - - - - - - - - - - +
                                                    ^
                                . - - - - - - - - - - - - - - - - - - - .
                                ^                                       ^
                        + - - - - - - - - +                   + - - - - - - - - - +
                        | Account 1 Hash  |                   |   Account 2 Hash  |
                        + - - - - - - - - +                   + - - - - - - - - - +
                                ^
                  . - - - - - - - - - - - - - .
                  ^                           ^
        + - - - - - - - - - +       + - - - - - - - - - +
        |   Address Hash    |       |   Details Hash    |
        + - - - - - - - - - +       + - - - - - - - - - +
                                              ^
                  . - - - - - - - - - - - - - + - - - - - - - - - - - - - .
                  ^                           ^                           ^
          + - - - - - - - - +       + - - - - - - - - - +       + - - - - - - - - - +
          |  Balance Hash   |       |   Counter Hash    |       |   Storage Hash    |
          + - - - - - - - - +       + - - - - - - - - - +       + - - - - - - - - - +

```

`Account Storage`


```

                                                + - - - - - - - +
                                                |  Storage Hash |
                                                + - - - - - - - +
                                                        ^
                                    . - - - - - - - - - + - - - - - - - - - .
                                    ^                                       ^
                        + - - - - - - - - - - - +               + - - - - - - - - - - - +
                        |      Store 1 Hash     |               |      Store 2 Hash     |
                        + - - - - - - - - - - - +               + - - - - - - - - - - - +
                                    ^
                  . - - - - - - - - + - - - - - - - - - .
                  ^                                     ^
        + - - - - - - - - - +               + - - - - - - - - - - - +
        |   Store ID Hash   |               |   Store Records Hash  |
        + - - - - - - - - - +               + - - - - - - - - - - - +
                                                        ^
                                        . - - - - - - - + - - - - - - - .
                                        ^                               ^
                            + - - - - - - - - - - - +       + - - - - - - - - - - - +
                            |     Record 1 Hash     |       |     Record 2 Hash     |
                            + - - - - - - - - - - - +       + - - - - - - - - - - - +
                                        ^
                        . - - - - - - - + - - - - - - - .
                        ^                               ^
                + - - - - - - - +               + - - - - - - - +
                |  Key 1 Hash   |               |  Value 1 Hash |
                + - - - - - - - +               + - - - - - - - +

```

`Accounts State Transition`

```

            Block #1                                Block #2
        + - - - - - - - +                       + - - - - - - - +
        |               |                       |               | 
        |   Previous    |      Transactions     |     Latest    |
        |   Accounts    |   ----------------->  |    Accounts   |
        |     State     |                       |     State     |
        |               |                       |               |
        + - - - - - - - +                       + - - - - - - - +

```



The account balance is in the native unit of value which is an `Astre` while the smallest unit of value is a `Quark`.

Value magnitudes are:-
- 10^24: YottaQuark (YQ) / Astre (AST)
- 10^21: ZettaQuark (ZQ)
- 10^18: ExaQuark (EQ)
- 10^15: PetaQuark (PQ)
- 10^12: TeraQuark (TQ)
- 10^9: GigaQuark (GQ)
- 10^6: MegaQuark (MQ)
- 10^3: KiloQuark (KQ)
- 10^0: Quark (Q)

### Blocks

A Block consists of the block body and the validator's ed25519 signature of the body's merkle tree hash.

The block body has:-
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

A Transaction consists of the transaction body and the sender's ed25519 signature of the body's merkle tree hash.

The transaction body has:-
1. chain
2. counter
3. recipient
4. sender
5. solar limit
6. solar price
7. value

`Solar` is the currency for work done on the blockchain, in contrast with `Astre` with is the currency for value.

The solar limit of a block is 1,000,000,000.

| Fee | Solar |
|---|---|
| Transaction Processing | 1,000 |
| Account Creation | 1,000,000 |

### Nova Consensus

`Nova` is the consensus protocol for creating new blocks and validating the blockchain.

A validator must staked, by sending `Astre` to the nova account, to participate in the protocol.

The nova account address is 0x 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 6E 6F 76 61.

An epoch lasts approximately one week. The block time target is three seconds. A slot is a three seconds period when new blocks are created.

Slots are allocated pro rata with a validator's stake every epoch and are removed after slot selection.

A slot miss occurs when a validator does not create a new block or created a malicious block when selected.

A validator that misses all of their slots in an epoch will be refunded their stake.

Slot selection determines the validator for the next block at any time:-
- Get validator addresses with slot allocations in the nova account storage.
- Check slot misses from the last block to the current time.
- If no slot miss, the nearest address xor to the last block hash is selected.
- If slot misses, the nearest address xor to the linear-feedback shift register, shifted to the number of slot misses, of the lastest block hash is selected.

All transactions in a block are ordered ascending by the xor distance of the transaction hash and the previuos block transactions hash.

The reward for creating a new block is 1 `Astre`.

Solar pricing mechanism:-
- The solar price is fixed for every block.
- The solar price varies by 1 `Quark`.
- The solar price increases when more than 75%, and decreases when less than 25%, of the previous solar limit was used.
- The base solar price is set at 1 `Quark`.

### V2: Fusion Upgrade

Fusion is an application platform running on the Astreuos Blockchain.

The Fusion Language is a functional postfix programming language for developing Fusion Applications.

The Fusion Virtual Machine(FVM) is the native runtime for Fusion Machine Code(FMC) and has an interface to Astreuos Accounts.

Helium is the Fusion package manager. Helium downloads your Fusion Application's dependencies, runs tests and compiles your Fusion Script into FMC.

New transaction types will be added for App Creation and App Calls.

#### Syntax
- Types: boolean, integers, floating point, string, list, records, custom
- Modules
- Functions
- Conditionals: if, while
- Operators

#### Standard Library
- Math: modulo, modulars
- Crypto: hash, asymmetric verify, bulletproofs verify
- Integer
- Floating Point
- String
- List
- Records
- Custom Types

`Custom Types`

```

type Language { Rust, Erlang, Javascript, Python }

type Coder { language: Language }

```

Standards to help developers create trusted Fusion Applications.

- Fungible & Non Fungible Tokens.
- Oracles.
- Governance.
- Token Custody.
- Token Insurance.

### V3: Nebula Upgrade

This upgrade will add a distributed file protocol called Nebula.

Puslar network will also be upgraded with index and storage routes with complementary Nebula Object message types for get and put.

Nebula is a protocol for storing and retrieving Nebula Objects.

Nebula Objects are a clone of IPFS objects. The benefit from cloning is having two files with different names and the same content with the same Nebula object representation and hence the same hash, reducing duplication.

A Nebula Object is a data structure with two fields:

- Data — a blob of binary data of size < 256 KB.
- Links — A List of Links.

A Link structure has three data fields:

- Hash — the hash of the linked Nebula Object.
- Name — the name of the Link.
- Size — the cumulative size of the link.

The index route stores the index of the object hash and the storage provider's id.

The route is updated every five minutes to remove deleted objects and redistribute indexes adding new object indices.

An indexer must prove they are storing their part of the index.

A node can use the returned id to query the storage route for the storage provider to retrieve the object.

The storage provider is paid storage fees for the storage period and retrival fees for serving an object.

A stoage provider must prove they are storing their assigned objects.

Indexers are incentivized to cache objects by earning retrival fees for returning objects instead of storage provider's id.

An indexer also earns a commission for facilitating a put contract and indexing the underlying data.

A delete contract can be made directly to the validator route and refunded the contract's remainder period.

The Retrieval Fees for 256KB is 1,600,000 Solar.

Storage Fees for 256KB.

| Time | Solar |
|---|---|
| 1mo | 3,200,000|
| 1yr | 32,000,000 |

### V4: Reactor Upgrade

This upgrade adds a distributed compute protocol called Reactor with proof of work staking.

Reactor allows for Private & Open Compute.

Open Compute is calling Fusion Applications stored on Nebula and are callable by anyone on the blockchain.

Private Compute is confidential computing enabling users to use private data and protect software ip on the protocol while allowing for open or restricted access to app calls.

### V5: Governance Upgrade
- nova withdrawl contract
- improvement protocol system

### Roadmap

| Projects | Description | Status |
|---|---|---|
| [Astro Notation](https://github.com/stelar-software/rust-astro-notation) | Encoding Format | ✅ |
| [NeutronDB](https://github.com/stelar-software/rust-neutrondb) | Key Value Store | ✅ |
| [Opis](https://github.com/stelar-software/rust-opis) | Integer Arithmetic | ✅ |
| [Fides](https://github.com/stelar-software/rust-fides) | Hashing & Asymmetric/Symmetric Cryptography | ✅ |
| [Pulsar Network](https://github.com/stelar-software/rust-pulsar-network) | DHT P2P Messaging Protocol | ✅ |
| [Rust Astreuos](https://github.com/astreuos/rust-astreuos) | Blockchain Node | ✅ |
| V1 Testnet Launch | | Q2 2022 |
| V1 Mainnet Launch | | Q2 2022 |

2022-03-26