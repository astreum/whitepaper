
# Astreuos Whitepaper

## A Next Generation Autonomous Blockchain that manages Transaction Fees, Block Limits and Currency Volume to Maintain Network Stability & Maximize Network Utilization.

# History

## Blockchain

## Bitcoin

## Ethereum

## Web 3.0

# Astreuos

## Blocks

Structure:
1. Data
    1. Number
    2. Previous Block Hash
    3. Timestamp
    4. Solar Limit
    5. Solar Used
    6. Solar Price
    7. Solar Fees
    8. Accounts Root Hash
    9. Transactions Root Hash
    10. Receipts Root Hash
    11. Storage Root Hash
    12. Reward
2. Minter Signature

## Accounts

Types:
1. User
2. Application

Structure:
1. Counter
2. Balance
3. Code ID
4. Storage ID

#### Special Accounts

| Account | Address |
|---|---|
| Nova | 0x0000nova |
| Nebula | 0x0000nebula |
| Burn | 0x0000burn |


#### Balance

The standard unit of value is a Quanta while the smallest unit is a Quark.

Value magnitudes:-

- 10^24: Yottaquark / Quanta
- 10^21: Zettaquark
- 10^18: Exaquark
- 10^15: Petaquark
- 10^12: Teraquark
- 10^9: Gigaquark
- 10^6: Megaquark
- 10^3: Kiloquark
- 10^0: Quark

## Transactions

Types:
1. Standard
2. App Creation
3. App Call

Structure:
1. Data
    1. Type
    2. Recipient
    3. Value
    4. Counter
    5. Solar Price
    6. Solar Limit
    7. Data
2. Sender Signature

## Receipts

Structure:
1. Transaction Hash
2. Status
3. Solar Used

## Pulsar

A Peer to Peer Messaging Protocol

## Fusion

A Decentralized Application Platform

### Reactor

The Stack Machine

#### Arithmetic
| Instructions | Code |
|---|---|
| Add | |
| Sub | |

#### Account Manipulation

#### Memory & Storage Manipulation


- Plasma - Compiler
- Helium - App Manager

## Nova

A Proof of Stake Consensus Protocol

## Nebula

A Decentralized Storage Platform

# Applications

## Smart Contracts

## Digital Tokens (Virtual Currencies & NFTs)

## Oracles

## DAOs

## Distributed Storage

## Decentralized Containers

# Roadmap
| Project | Description | Delivery |
|---|---|---|
| [Stellar Notation](https://github.com/seg-software/rust-stellar-notation) | Data Encoding | ✅ |
| [NeutronDB](https://github.com/seg-software/rust-neutrondb) | Key Value Store | ✅ |
| [Opis](https://github.com/seg-software/rust-opis) | Integer Arithmetic | ✅ |
| [Fides](https://github.com/seg-software/rust-fides) | Digital Signature Library | 🚧 |
| Pulsar Network | Messaging System |  TBD |
| Fusion | Decentralized Applications | TBD |
| Nova Protocol| Proof of Stake | TBD |
| Nebula | Storage Protocol | TBD |
| [Terminal](https://github.com/astreuos/astreuos-terminal) | Network Interface | TBD |
| Testnet Launch | | Q4 2021 |
| Mainnet Launch | | Q1 2022 |

2021-11-23