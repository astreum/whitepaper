
# Astreuos Whitepaper

# A New Autonomous Blockchain that manages Transaction Fees, Block Limits and Currency Volume to Maintain Network Stability & Maximize Network Utilization.

## History

### Blockchain
### Bitcoin
### Ethereum


## Astreuos

### Blocks

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

### Accounts

Structure:

1. Counter
2. Balance
3. Code ID
4. Storage ID


Balance:

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

Special Addresses

| Service | Address |
|---|---|
| Nova | 0x0000nova |
| Nebula | 0x0000nebula |
| Burn | 0x0000burn |

### Transactions

Structure:

1. Data
    1. Recipient
    2. Value
    3. Counter
    4. Solar Price
    5. Solar Limit
2. Sender Signature

### Receipts

Structure:

1. Transaction Hash
2. Status
3. Solar Used

### Pulsar - Peer to Peer Network

### Fusion - Decentralized Application Platform

#### Reactor - Stack Machine
#### Plasma - Compiler
#### Helium - App Manager

### Nova - Proof of Stake Consensus

### Nebula - Decentralized Storage

## Roadmap
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

2021-11-05