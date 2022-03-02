
# Astreuos

### A Next Generation Blockchain for Apps, Storage and Compute that's Decentralized, Secure and Sustainable.

## Elements

### Accounts

Account.
- address
- details hash

Account Details.
- balance
- counter
- storage hash

The standard unit of value is an Astre while the smallest unit is a Quark.
Value magnitudes:
- 10^24: Yottaquark / Astre (AST)
- 10^21: Zettaquark (ZQ)
- 10^18: Exaquark (EQ)
- 10^15: Petaquark (PQ)
- 10^12: Teraquark (TQ)
- 10^9: Gigaquark (GQ)
- 10^6: Megaquark (MQ)
- 10^3: Kiloquark (KQ)
- 10^0: Quark (Q)


### Blocks

Block.
- body
- signature

Body.
- accounts hash
- chain
- number
- previous block hash
- receipts hash
- solar limit
- solar price
- solar used
- time
- transactions hash
- validator

### Transactions

Transaction.
- body
- signature

Body.
- chain
- counter
- recipient
- sender
- solar limit
- solar price
- value

### Receipts

Receipt.
- solar used
- status

### Nova, Proof of Stake Consensus Protocol.
- The consensus protocol is the mechanism for creating new blocks and validating the blockchain.
- A validator must be staked to participate in the protocol.
- Staking is done by sending astre to the nova account.
- The nova account address is 0x 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 6E 6F 76 61.
- An epoch lasts approximately one week.
- The block time target is three seconds.
- A slot is a three seconds period when new blocks are created.
- Slots are allocated pro rata with a validator's stake every epoch and are removed after slot selection.
- A slot miss occurs when a validator does not create a new block or created a malicious block when selected.
- Slot selection determines the validator for the next block at any time:-
    - Get validator addresses with slot allocations.
    - Check slot misses from the last block to the current time.
    - If no slot miss, the nearest address xor to the last block hash is selected.
    - If slot misses, the nearest address xor to the linear-feedback shift register, shifted to the number of slot misses, of the lastest block hash is selected.
- All transactions in a block are ordered ascending by the xor distance of the transaction hash and the previuos block transactions hash.
- A validator that misses all of their slots in an epoch will be refunded their stake.
- The base solar limit is set at 1,000,000.
- The base block reward is set at 1 astre.


### Solar Pricing Protocol
- The solar price is fixed for every block.
- The solar price varies by 0.01%.
- The solar price increases when more than 90%, and decreases when less than 10%, of the previous solar limit was used.
- The base solar price is set at 1 exaquark / 0.000001 astre.

## Roadmap

### v1: Genesis
- Value Transactions.
- Nova, Proof of Stake Consensus Protocol.
- Solar Pricing Protocol.
- Nova Deposit Contract.

### v2: Fusion Upgrade
- Fusion, Application System.
- Language.
- Virtual Machine.
- Compiler & Code Manager.
- App Creation & Call Transactions.

### v2+: Standards Upgrade
- Token Standards.
- Oracle Standards.
- DAO Standards.
- Insurance Standards.

### v3: Nebula Upgrade
- Nebula, Distributed File System.
- Proof of Storage Staking Protocol.
- Storage Pricing Protocol.
- Storage Contract.
- Retrieval Contract.
- Removal Contract.
- Nebula File Tree for storing Account Details, Blocks & Transactions.

### v4: Reactor Upgrade
- Reactor, Distributed Compute System.
- Proof of Work Staking Mechanism.
- Compute Pricing Protocol.
- Compute Contract.
- Automation Contract.

### v5: Governance Upgrade
- Nova Reserve System.
- Nova Governance Protocol.

### Projects
| Project | Description | Delivery |
|---|---|---|
| [Astro Notation](https://github.com/stelar-software/rust-astro-notation) | Encoding Format | ✅ |
| [NeutronDB](https://github.com/stelar-software/rust-neutrondb) | Key Value Store | ✅ |
| [Opis](https://github.com/stelar-software/rust-opis) | Integer Arithmetic | ✅ |
| [Fides](https://github.com/stelar-software/rust-fides) | Hashing & Asymmetric/Symmetric Cryptography | ✅ |
| [Pulsar Network](https://github.com/stelar-software/rust-pulsar-network) | P2P Messaging Protocol | ✅ |
| [Rust Astreuos](https://github.com/astreuos/rust-astreuos) | Blockchain Node | ✅ |
| V1 Testnet Launch | | MAR 2022 |
| V1 Mainnet Launch | | 2022-04-01 |

2022-03-02