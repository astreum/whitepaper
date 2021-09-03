# Astreuos Virtual Machine

## Opcodes

### Stack Manipulation(0-9)

| Name | Code | Solar |
|---|---|---|
| STOP | 0X00 |
| START | 0X01 |
| PUSH | 0X02 |
| POP | 0X03 |
| mPUSH | 0X04 |
| mGET | 0X05 |
| sPUSH | 0X06 |
| sGET | 0X07 |

### Basic Arithmetic(10-19)

| Name | Code | Arguments | Solar |
|---|---|---|---|
| iADD | 10 | [AMOUNT] [AMOUNT] |
| iSUB | 11 | [AMOUNT] [AMOUNT] |

### Accounts Interface(20-29)

| Mnemonic | Code | Arguments | Solar |
|---|---|---|---|
| SHOW BAL | 0X0A | [ADDRESS] |
| EDIT BAL | 0X0B | [ADDRESS] [AMOUNT] |
| SHOW CNTR | 0X0A | [ADDRESS] |
| INCR CNTR| 0X0B | [ADDRESS] |