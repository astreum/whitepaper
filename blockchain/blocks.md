
# Blocks

Key: String;
- Hash of Value(Block Hash)

Value: Stellar Objects;
1. Number
2. Previous Block Hash
3. Timestamp
4. Nonce
5. Difficulty
6. Solar Limit
7. Solar Used
8. Solar Price
9. Solar Fees
10. Accounts Root Hash
11. Transactions Root Hash
12. Receipts Root Hash
13. Miner

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