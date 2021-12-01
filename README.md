
# Astreuos Whitepaper

### A Next Generation Blockchain that delivers on Decentralization, Security and Sustainability.

Strategies: -
1. All users earn quanta by providing validation or storage for the network.
2. Auto-adjustments on transaction fees, block limits and storage fees for sustainability & maximum network utilization.
3. Secure the network through digital signatures, proof of work on messages and proof of stake on blocks.

# History

## Blockchain

## Bitcoin

## Ethereum

## Web 3.0

# Astreuos

## Blocks

Structure:
1. Data
    - Number
    - Previous Block Hash
    - Timestamp
    - Solar Limit
    - Solar Used
    - Solar Price
    - Solar Fees
    - Accounts Root Hash
    - Transactions Root Hash
    - Receipts Root Hash
    - Storage Root Hash
    - Reward
2. Validator Signature

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
    - Type
    - Recipient
    - Value
    - Counter
    - Solar Price
    - Solar Limit
    - Data
2. Sender Signature

## Receipts

Structure:
1. Transaction Hash
2. Status
3. Solar Used

## Pulsar - Peer to Peer Messaging Protocol

### Access Port
UDP PORT 7577

## Fusion - Blockchain Application Platform

Main Components:-
1. Fusion Language, Functional Programming Language.
2. Reactor, Virtual Stack Machine.
3. Plasma, Fusion Language to Reactor Code Compiler.
4. Helium, Code Manager.

### Fusion Language

Types :-
1. Integer -> 10
2. Floating Point -> 10.0
3. Boolean -> true/false
4. String -> "string"
5. List -> [ 1,2,3 ]
6. Tuple -> ("number", 10)
7. Record -> { "key_1": 1, "key_2": 2 }

Assignments :-
1. let -> let a = 10;
2. const -> let A = 10;

Operators :-
1. Equal (=)
2. And (&)
3. Or (||)

Control Flow :-
1. Conditional
    - If
    - Case
2. Loop
    - While
    - For

Standard Library (std) :-
1. Mathematics (math)
    - From String -> from_str(string, radix)
    - Into String -> into_str(number, radix)
    - Addition -> add(a, b)
    - Subtraction -> sub(a, b)
    - Multiplication -> mul(a, b)
    - Division -> div(a, b)
    - Remainder -> rem(a, b)
    - Modulo -> mod(a, b)
    - Exponentiation -> pow(a, e)

2. String (string) :-
    - Bytes -> bytes(string)
    - Hexadecimal -> hex(string)
    - Lowercase -> lower(string)
    - Merge -> merge(string, string)
    - Replace -> replace(string, old string, new string)
    - Uppercase -> upper(string)

3. List (list) :-
    - Any -> any(list, condition)
    - Dedup -> dedup(list)
    - Delete -> del(list, value)
    - Each -> each(list, assign, lambda)
    - Filter -> filter(list, assign, condition)
    - Get -> get(list, index)
    - Length -> len(list)
    - Map -> map(list, assign, lambda)
    - Merge -> merge(list, list)
    - Pop -> pop(list, index)
    - Put -> put(list, value)
    - Reverse -> reverse(list)
    - Slice -> slice(list, start index, stop index)

4. Record (record) :-
    - Delete -> del(record, key)
    - Get -> get(record, key)
    - Merge -> merge(record, record)
    - Pop -> pop(record, key)
    - Put -> put(record, key value pair)

4. Accounts (account) :-
    - Create -> create(0xFFFF)
    - Balance -> balance(0xFFFF)
    - Storage (storage)
        - Put -> put(0xFFFF, "key", "value")
        - Get -> get(0xFFFF, "key")
        - Delete -> delete(0xFFFF, "key")

### Reactor - Virtual Stack Machine

Op Codes :-
1. General
    - Stop
2. Memory
    - Put
    - Get
3. Account
    - Create
    - Balance
    - Storage Put
    - Storage Get
    - Storage Delete
4. Arithmetic
    - Addition
    - Subtraction
    - Multiplication
    - Division
    - Remainder
    - Modulo
    - Exponentiation
    - Modular Inverse
5. Comparison
    - Less Than
    - Greater Than
    - Equal To
6. Bitwise
    - Not
    - And
    - Or
    - Xor

## Nova - Proof of Stake Consensus Protocol

### Block Time
1 second.

### Slot Allocation

### Validator Selection

### Block Reward
1 quanta for every billion solar limit on the block.

## Nebula - Storage Platform

### Storage Fee
The initial storage fee is 130 yottaquarks for 3 months per 256Kb chunk of data.

### Standard Storage Contract
3 month period storage contract.

### Retrieval Fee 
The initial retrieval fee is 21.6 yottaquarks per 256Kb chunk of data.

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

2021-12-01