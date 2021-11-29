
# Astreuos Whitepaper

### A Next Generation Blockchain that adjusts Transaction Fees, Block Limits and Storage Fees to Maintain Network Sustainability & Maximize Network Utilization.

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

## Fusion - Blockchain Application Platform

Main Components:-
1. Fusion Language, Postfix Programming Language.
2. Reactor, Virtual Stack Machine.
3. Plasma, Fusion Language to Reactor Code Compiler.
4. Helium, Code Manager.

### Reactor - Virtual Stack Machine

#### Op Codes

1. General
    1. Stop
2. Memory
    1. Put
    2. Get
3. Account
    1. Create
    2. Balance
    3. Storage Put
    4. Storage Get
    5. Storage Delete
4. Arithmetic
    1. Addition
    2. Subtraction
    3. Multiplication
    4. Division
    5. Remainder
    6. Modulo
    7. Exponentiation
    8. Modular Inverse
5. Comparison
    1. Less Than
    2. Greater Than
    3. Equal To
6. Bitwise
    1. Not
    2. And
    3. Or
    4. Xor

## Nova - Proof of Stake Consensus Protocol

### Block Time

### Slot Allocation

### Validator Selection

### Block Reward
The block reward is proportianal to the Solar Limit of the block.
Every 1 Billon Solar Limit earns the validator 1 Quanta.

## Nebula - Storage Platform

### Storage Fee
Applies to the storage of 256Kb chunks of data. 
The Initial Storage Fee is 130 Yottaquarks for 3 Months.

### Standard Storage Contract
Features
1. 3 Month Period

### Retrieval Fee
Applies to the transfer of 256Kb chunks of data. 
The Initial Retrieval Fee is 21.6 Yottaquarks.

# Applications

## Smart Contracts

## Digital Tokens (Virtual Currencies & NFTs)

## Oracles

## DAOs

## Distributed Storage

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

2021-11-29