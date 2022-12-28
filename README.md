
# Astreuos

### A Next Generation Blockchain for Apps, Storage and Compute that's Decentralized, Secure and Sustainable.

## Specification(V1)

### Accounts
- Structure
    - Address
    - Details
- Details
    - Balance
    - Counter
    - Storage
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
- Structure
    - Body
    - Signature
- Body
    - Accounts Hash
    - Number
    - Previous Block Hash
    - Receipts Hash
    - Reward
    - Solar Limit
    - Solar Price
    - Solar Used
    - Time
    - Transactions Hash

### Transactions
- Structure
    - Body
    - Signature
- Body
    - Counter
    - Recipient
    - Solar Price
    - Solar Limit
    - Value

### Receipts
- Structure
    - Solar Used
    - Status

### Nova, Proof of Stake Consensus Mechanism.
- An Epoch lasts One Week.
- The Block Time Target is Three Seconds.
- A Slot is a three seconds period when new Blocks are created.
- Slots are allocated pro rata with Stake every Epoch and removed after Slot Selection.
- A Slot Miss occurs when a validator does not create a new Block or creates a malicious Block when selected.
- Slot Selection determines the Validator of the next Block at any time:-
    - Get Addresses with Slot Allocations.
    - Check Slot Misses from the last Block to the current time.
    - If no Slot Miss, the nearest Address XOR to the last Block hash is selected.
    - If Slot Misses, the nearest Address XOR to the Linear-feedback shift register, shifted to the number of Slot Misses, of the last Block hash is selected.
- The Base Solar Limit is 1,000,000.
- The Base Block Reward is 1 Astre.


### Solar Stability Mechanism
- The Solar price is fixed for every Block.
- The Solar price varies by 0.01%.
- The Solar price increases when more than 90%, and decreases when less than 10%, of the previous Solar Limit was used.
- The Base Solar Price is set at 1 Exaquark / 0.000001 Astre.

## Roadmap

### Astreuos V1
- Value Transactions.
- Nova, Proof of Stake Consensus Mechanism.
- Nova Deposit Contract.
- Solar Stability Mechanism.
- Nebula File Tree for storing Account Details, Blocks & Transactions.

### Astreuos V2
- Fusion, Application Platform.
- Language.
- Virtual Machine.
- Compiler & Code Manager.
- App Creation & Call Transactions.

### Astreuos V2+
- Token Standards.
- Oracle Standards.
- DAO Standards.

### Astreuos V3
- Nebula, Distributed File System.
- Proof of Storage Staking Mechanism.
- Storage Contract.
- Retrieval Contract.
- Removal Contract.

### Astreuos V4
- Reactor, Distributed Compute System.
- Proof of Work Staking Mechanism.
- Compute Contract.
- Automation Contract.

### Astreuos V5
- Nova Reserve System.
- Nova Governance Protocol.

### Projects
| Project | Description | Delivery |
|---|---|---|
| [Astro Notation](https://github.com/stelar-software/rust-astro-notation) | Encoding Format | ✅ |
| [NeutronDB](https://github.com/stelar-software/rust-neutrondb) | Key Value Store | ✅ |
| [Opis](https://github.com/stelar-software/rust-opis) | Integer Arithmetic | ✅ |
| [Fides](https://github.com/stelar-software/rust-fides) | Hashing & Asymmetric/Symmetric Cryptography | 🚧 |
| [Pulsar Network](https://github.com/stelar-software/rust-pulsar-network) | P2P Messaging Protocol |  🚧 |
| [Rust Astreuos](https://github.com/astreuos/rust-astreuos) | Blockchain Node | FEB 2022 |
| V1 Testnet Launch | | FEB 2022 |
| Stelar Terminal | Browser Interface | MAR 2022 |
| V1 Mainnet Launch | | APR 2022 |

2022-02-21