
# Astreuos

### A Next Generation Blockchain for Apps, Storage and Compute that's Decentralized, Secure and Sustainable.

## Contents

1. Why?
2. About
3. Vision
4. Upgrades
5. Open Source

### Why?

- To build a trusted and secure crypto experience by providing solid standards for tokens, oracles, governance and insurance.
- To be a viable backbone to web 3 services by offering combined value, storage and compute in a single blockchain and priced in the stable `Solar`.

### About

Astreuos is an account based blockchain with scripting capabilities and protocols for distributed file and distributed compute.

The blockchain keeps track of an account's details such as the balance, number of transactions and storage.

The standard unit of value is an `Astre` while the smallest unit is a `quark`.

Value magnitudes are:-
- 10^24: yottaquark / astre (AST)
- 10^21: zettaquark (ZQ)
- 10^18: exaquark (EQ)
- 10^15: petaquark (PQ)
- 10^12: teraquark (TQ)
- 10^9: gigaquark (GQ)
- 10^6: megaquark (MQ)
- 10^3: kiloquark (KQ)
- 10^0: quark (Q)

A Block consists of the block body and the validator's ed25519 signature of the body's tree hash.

The block body has:-
- accounts hash
- chain
- number
- previous block hash
- receipts hash
- solar price
- solar used
- time
- transactions hash
- validator

A Transaction consists of the transaction body and the sender's ed25519 signature of the body's tree hash.

The transaction body has:-
- chain
- counter
- recipient
- sender
- solar limit
- solar price
- value

The Receipt is the result from the application of a transaction to the Astreuos Account State.

A receipt consists of the solar used and status of the application procedure.

`Solar` is the currency for work done on the blockchain. The solar limit in a block is 1,000,000.

| Fee | Solar |
|---|---|
| Transaction Processing | 1,000 |
| Account Creation | 1,000 |

#### V1: Genesis

`Nova` is the consensus protocol for creating new blocks and validating the blockchain. A validator must stake value to participate in the protocol. Staking is done by sending `Astre` to the nova account. The nova account address is 0x 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 6E 6F 76 61.

An epoch lasts approximately one week. The block time target is three seconds. A slot is a three seconds period when new blocks are created.

Slots are allocated pro rata with a validator's stake every epoch and are removed after slot selection. A slot miss occurs when a validator does not create a new block or created a malicious block when selected. A validator that misses all of their slots in an epoch will be refunded their stake.

Slot selection determines the validator for the next block at any time:-
- Get validator addresses with slot allocations in the nova account storage.
- Check slot misses from the last block to the current time.
- If no slot miss, the nearest address xor to the last block hash is selected.
- If slot misses, the nearest address xor to the linear-feedback shift register, shifted to the number of slot misses, of the lastest block hash is selected.

All transactions in a block are ordered ascending by the xor distance of the transaction hash and the previuos block transactions hash. The reward for creating a new block is 1 `Astre`.

Solar pricing mechanism:-
- The solar price is fixed for every block.
- The solar price varies by 0.01%.
- The solar price increases when more than 75%, and decreases when less than 25%, of the previous solar limit was used.
- The base solar price is set at 1 `exaquark` / 0.000001 `Astre` to incentivise validators to fill a block and at the least double their reward.

### Vision

Empower web 3 builders:-
- create browser extensions that interface with an astreuos node to enhance user experiences
- create blockchain applications
- host web app and data on Nebula
- create compute applications on Reactor

### Upgrades

#### V2: Fusion Upgrade

This upgrade will add an application platform called Fusion.

The Fusion Language is a multi-paradigm statically-typed programming language for building Fusion Applications.

The Fusion Virtual Machine is the native runtime for Fusion Bytecode and has a direct interface to the Astreuos Account State.

Helium is the Fusion package manager. Helium downloads your Fusion Application's dependencies and compiles your application into Fusion Bytecode.

New transaction types will be added for App Creation and App Calls.

#### V2+: Standards Upgrade

This upgrade adds a series of standards to help builders create trusted Fusion Applications.

Fungible and Non-Fungible Token standards.

Oracle standards

Governance standards

Insurance standards

#### V3: Nebula Upgrade

This upgrade will add a distributed file protocol called Nebula.

Puslar network will also be upgraded with index and storage routes with complementary object message types for get and put.

An object is a node or leaf of a merkle tree of a file or folder.

The index route stores the index of the object hash and the storage provider's id.

The route is updated every five minutes to remove deleted objects and redistribute indexes adding new object indices.

An indexer must prove they are storing their part of the index.

A node can use the returned id to query the storage route for the storage provider to retrieve the object.

The storage provider is paid storage fees for the storage period and retrival fees for serving an object.

A stoage provider must prove they are storing their assigned objects.

Indexers are incentivized to cache objects by earning retrival fees for returning objects instead of storage provider's id.

An indexer also earns a commission for facilitating a put contract and indexing the underlying data.

The standard put contract is for a period of 3 months. 

A delete contract can be made directly to the validator route and refunded the contract's remainder period.

Storage `Solar` cost will involve the available protocol storage space.

Proof of Space-Time staking.

#### V4: Reactor Upgrade

This upgrade adds a distributed compute protocol called Reactor with proof of work staking.

#### V5: Governance Upgrade
- nova withdrawl contract
- nova reserve system
- token index
- nova governance mechanism

### Open Source

The Astreuos Blockchain is a fully open source project and is powered by several open source libraries.

| Library | Description | Status |
|---|---|---|
| [Astro Notation](https://github.com/stelar-software/rust-astro-notation) | Encoding Format | ✅ |
| [NeutronDB](https://github.com/stelar-software/rust-neutrondb) | Key Value Store | ✅ |
| [Opis](https://github.com/stelar-software/rust-opis) | Integer Arithmetic | ✅ |
| [Fides](https://github.com/stelar-software/rust-fides) | Hashing & Asymmetric/Symmetric Cryptography | ✅ |
| [Pulsar Network](https://github.com/stelar-software/rust-pulsar-network) | P2P Messaging Protocol | ✅ |
| [Rust Astreuos](https://github.com/astreuos/rust-astreuos) | Blockchain Node | ✅ |
| V1 Testnet Launch | | Q2 2022 |
| V1 Mainnet Launch | | Q2 2022 |

2022-03-06