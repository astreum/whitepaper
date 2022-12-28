# Accounts

## Structure

Key: String;
- Address (256 bits)

Value: String;
- Account Hash (256 bits)

## Account

Key: String;
- Account Hash (256 bits)

Value: Stellar Objects;
    1. Counter: u64
    2. Balance: u128


### Balance

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
