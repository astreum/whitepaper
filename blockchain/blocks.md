
# Blocks

Key: Hash, String

Value: Stellar Group,
1. Data: Stellar Group,
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
    11. Miner
    12. Reward
    13. Nonce
2. Signature, String

## Block Transactions

Key: String;
- Hash of Value(Transactions Root Hash)

Value: Stellar Objects;
1. Index
2. [Transaction Hash](https://github.com/astreuos/astreuos-specifications/blob/main/blockchain/transactions.md)

## Block Receipts

Key: String;
- Hash of Value(Receipts Root Hash)

Value: Stellar Objects
1. Transaction Hash
2. [Receipt Hash](https://github.com/astreuos/astreuos-specifications/blob/main/blockchain/receipts.md)