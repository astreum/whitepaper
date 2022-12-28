
# Astreuos

### A Next Generation Blockchain Platform for Apps, Storage and Compute that's Decentralized, Secure and Sustainable.

## Specification(v1)

### Accounts
- Structure: Address & Details Hash.
- Details: Astro Notation List Format.
    - Spec
    - Counter
    - Balance
    - Storage Hash
- The Standard Unit of Value is an Astr while the Smallest Unit is a Quark.
- Value magnitudes:
    - 10^24: Yottaquark / Astr
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
- Structure: Astro Notation List Format.
    - Spec
    - Body
    - Signature
- Body: Astro Notation List Format.
    - Number
    - Previous Block Hash
    - Time
    - Solar Limit
    - Solar Used
    - Solar Price
    - Accounts Hash
    - Transactions Hash
    - Receipts Hash
    - Reward

### Transactions
- Structure: Astro Notation List Format.
    - Spec
    - Body
    - Signature
- Body: Astro Notation List Format.
    - Recipient
    - Value
    - Counter
    - Solar Price
    - Solar Limit

### Receipts
- Structure: Astro Notation List Format.
    - Spec
    - Status
    - Solar Used

### Nova, Proof of Stake Consensus Mechanism.
- An Epoch lasts One Week.
- The Block Time Target is Three Seconds.
- A Slot is a three seconds period when new Blocks are created.
- Slots are allocated pro rata with Stake every Epoch and removed after Slot Selection.
- A Validator can miss using their Slot when they do not create a new Block or create a malicious Block when selected.
- Slot Selection determines the Validator of the next Block at any time:-
    - Get Addresses with Slot Allocations.
    - Check missed Slots from the last Block to the current time.
    - If no Slots were missed the nearest Address XOR to the last Block hash is selected.
    - If Slots were missed the nearest Address XOR to the Linear-feedback shift register, shifted to the number of slots missed, of the last Block hash is selected.
- The Base Solar Limit is 1,000,000.
- The Base Block Reward is 1 Astr.


### Solar Stability Mechanism
- The Solar price is fixed for every Block.
- The Solar price varies by 0.01%.
- The Solar price increases when more than 90% and decreases when less than 10% of the Solar Limit of the previous Block was used.
- The Base Solar Price is set at 1 Exaquark / 0.000001 Astr.

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
- Removal Contract.

### Astreuos v4
- Reactor, Distributed Compute System.
- Compute Contract.

### Astreuos v5
- Token Standards.
- Oracle Standards.
- Nova Reserve System.
- Nova Governance Protocol.

### Projects
| Project | Description | Delivery |
|---|---|---|
| [Astro Notation](https://github.com/stelar-software/rust-astro-notation) | Data Transcoding | ✅ |
| [NeutronDB](https://github.com/stelar-software/rust-neutrondb) | Key Value Store | ✅ |
| [Opis](https://github.com/stelar-software/rust-opis) | Integer Arithmetic | ✅ |
| [Fides](https://github.com/stelar-software/rust-fides) | Digital Security | 🚧 |
| [Pulsar Network](https://github.com/stelar-software/rust-pulsar-network)  | Distributed Messaging |  🚧 |
| Nova | Proof of Stake Consensus Mechanism | FEB 2022 |
| [Node](https://github.com/astreuos/rust-astreuos) | Network Interface | FEB 2022 |
| Testnet Launch | | Q1 2022 |
| Mainnet Launch | | Q2 2022 |

2022-02-03