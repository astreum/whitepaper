
# Astreuos

### A Next Generation Blockchain Platform for Apps, Storage and Compute that's Decentralized, Secure and Sustainable.

## Structure

### Accounts
- Structure: Address & Details Hash.
- Details: Counter, Balance & Storage Hash.
- The Standard Unit of Value is an Astre while the Smallest Unit is a Quark.
- Value magnitudes:
    - 10^24: Yottaquark / Astre
    - 10^21: Zettaquark
    - 10^18: Exaquark
    - 10^15: Petaquark
    - 10^12: Teraquark
    - 10^9: Gigaquark
    - 10^6: Megaquark
    - 10^3: Kiloquark
    - 10^0: Quark
- Nova Special Account Address is 0xNOVA.

### Blocks
- Spec 1 Structure:
    - Spec
    - Number
    - Previous Block Hash
    - Time
    - Solar Limit
    - Solar Used
    - Solar Price
    - Solar Fees
    - Accounts Hash
    - Transactions Hash
    - Receipts Hash
    - Reward
- Current Solar Limit is 1,000,000.

### Transactions
- Spec 1 Structure: Spec, Body & Signature.
- Transaction Body
    - Spec 1 Structure: Recipient, Value, Counter, Solar Price & Solar Limit.

### Receipts
- Spec 1 Structure: Spec, Transaction Hash, Status & Solar Used.

### Nova

### Solar Stability Mechanism
- Maximum Daily Solar Price Deviation is 10%.

## Roadmap

### Astreuos v1
- Value Transactions.
- Nova, Proof of Stake Consensus Mechanism.
- Nova Deposit Contract.
- Solar Stability Mechanism.

### Astreuos v2
- Fusion, Blockchain Application Platform.
- Language.
- Virtual Machine.
- Compiler & Code Manager.
- App Creation & Call Transactions.

### Astreuos v3
- Nebula, Distributed File Storage System.
- Storage Contract.
- Retrieval Contract.

### Astreuos v4
- Reactor, Distributed Compute System.
- Compute Contract.

### Astreuos v5
- Token Standards.
- Oracle Standards.
- Nova Reserve System.

### Projects
| Project | Description | Delivery |
|---|---|---|
| [Astro Notation](https://github.com/stelar-software/rust-astro-notation) | Data Transcoding | ✅ |
| [NeutronDB](https://github.com/stelar-software/rust-neutrondb) | Key Value Store | ✅ |
| [Opis](https://github.com/stelar-software/rust-opis) | Integer Arithmetic | ✅ |
| [Fides](https://github.com/stelar-software/rust-fides) | Digital Security | 🚧 |
| [Pulsar Network](https://github.com/stelar-software/rust-pulsar-network)  | Distributed Messaging |  🚧 |
| Nova | Proof of Stake Consensus Mechanism | FEB 12022 |
| [Node](https://github.com/astreuos/rust-astreuos) | Network Interface | FEB 12022 |
| Testnet Launch | | Q1 12022 |
| Mainnet Launch | | Q2 12022 |

12022-02-01