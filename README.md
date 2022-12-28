
# Astreuos

### A Next Generation Blockchain for Apps, Storage and Compute that's Decentralized, Secure and Sustainable.

- Astreuos is a general purpose account based blockchain with protocols for consensus, distributed file & compute.

## Components

### Accounts

Account.
- address
- details hash

Account Details.
- balance
- counter
- storage hash

The standard unit of value is an astre while the smallest unit is a quark.
- Value magnitudes:
    - 10^24: yottaquark / astre (AST)
    - 10^21: zettaquark (ZQ)
    - 10^18: exaquark (EQ)
    - 10^15: petaquark (PQ)
    - 10^12: teraquark (TQ)
    - 10^9: gigaquark (GQ)
    - 10^6: megaquark (MQ)
    - 10^3: kiloquark (KQ)
    - 10^0: quark (Q)


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

### Nova, Consensus Protocol.
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
- The reward for creating a new block is 1 astre.

### Solar, Work Currency.
- Solar is the unit for paying for work done on the astreuos blockchain
- The solar limit in every block is 1,000,000,000.

| Fee | Cost |
|---|---|
| Transaction Processing | 1,000 |
| Account Creation | 1,000 |
costs in solar


### solar pricing mechanism
- The solar price is fixed for every block.
- The solar price varies by 0.01%.
- The solar price increases when more than 90%, and decreases when less than 10%, of the previous solar limit was used.
- The base solar price is set at 1 exaquark / 0.000001 astre.

## Roadmap

### v1: Genesis
- Nova, Consensus Protocol
- value transactions
- proof of value staking
- solar pricing mechanism
- nova deposit contract

### v2: Fusion Upgrade
- Fusion, Application Platform
- language
- virtual machine
- compiler & code manager
- app creation & call transactions

### v2+: Standards Upgrade
- token standards
- oracle standards
- governance standards
- insurance standards

### v3: Nebula Upgrade
- Nebula, Distributed File Protocol
- proof of storage staking
- storage pricing mechanism
- put contract
- get contract
- delete contract

### v4: Reactor Upgrade
- Reactor, Distributed Compute Protocol
- proof of work staking
- compute pricing mechanism
- compute contract
- automation contract

### v5: Governance Upgrade
- nova reserve system
- nova governance mechanism

### Projects
| Project | Description | Delivery |
|---|---|---|
| [Astro Notation](https://github.com/stelar-software/rust-astro-notation) | Encoding Format | ✅ |
| [NeutronDB](https://github.com/stelar-software/rust-neutrondb) | Key Value Store | ✅ |
| [Opis](https://github.com/stelar-software/rust-opis) | Integer Arithmetic | ✅ |
| [Fides](https://github.com/stelar-software/rust-fides) | Hashing & Asymmetric/Symmetric Cryptography | ✅ |
| [Pulsar Network](https://github.com/stelar-software/rust-pulsar-network) | P2P Messaging Protocol | ✅ |
| [Rust Astreuos](https://github.com/astreuos/rust-astreuos) | Blockchain Node | ✅ |
| V1 Testnet Launch | | Q2 2022 |
| V1 Mainnet Launch | | Q2 2022 |

2022-03-05