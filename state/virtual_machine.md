# Astreuos Virtual Machine

## Opcodes

### Stack Manipulation(0-9)

| Name | Code | Solar |
|---|---|---|
| STOP | 0 |
| START | 1 |
| PUSH | 2 |
| POP | 3 |
| mPUSH | 4 |
| mGET | 5 |
| sPUSH | 6 |
| sGET | 7 |

### Basic Arithmetic(10-19)

| Name | Code | Arguments | Solar |
|---|---|---|---|
| ADD | 10 | [AMOUNT] [AMOUNT] |
| SUB | 11 | [AMOUNT] [AMOUNT] |

### Accounts Interface(20-29)

| Mnemonic | Code | Arguments | Solar |
|---|---|---|---|
| SHOW BAL | 20 | [ADDRESS] | |