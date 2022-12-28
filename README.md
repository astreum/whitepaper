
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
- A validator must be staked to participate.
- Staking is done by sending astre to the nova account. 
- The nova account address is 0x 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 6E 6F 76 61.
- The validation process of creating new blocks is detailed below,
- An epoch lasts approximately one week.
- The block time target is three seconds.
- A slot is a three seconds period when new blocks are created.
- Slots are allocated pro rata with a validator's stake every epoch and are removed after slot selection.
- A slot miss occurs when a validator does not create a new block or created a malicious block when selected.
- Slot selection determines the validator for the next block at any time:-
    - Get validator addresses with slot allocations.
    - Check slot misses from the last block to the current time.
    - If no slot miss, the nearest address XOR to the last block hash is selected.
    - If slot misses, the nearest address XOR to the linear-feedback shift register, shifted to the number of slot misses, of the lastest block hash is selected.
- All transactions in a block are ordered ascending by the XOR distance of the transaction hash and the previuos block transactions hash.
- A validator that misses all of their slots in an epoch will be refunded their stake.
- The base solar limit is set at 1,000,000.
- The base block reward is set at 1 astre.


### Solar Stability Mechanism
- The solar price is fixed for every block.
- The solar price varies by 0.01%.
- The solar price increases when more than 90%, and decreases when less than 10%, of the previous solar limit was used.
- The base solar price is set at 1 exaquark / 0.000001 astre.

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
- Nova Withdrawl Contract.

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

2022-02-24