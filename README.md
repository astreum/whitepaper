
# Astreum: A Next Generation Blockchain for Computing, Storage and Networking

## Author

Roy R. O. Okello

[Email](mailto:royokello@protonmail.com)

[Github](https://github.com/royokello)

[Twitter](https://twitter.com/RealOkello)

## Content

- Introduction

- Why Another Blockchain
  - Security
  - Privacy
  - Usability
  - Extensibility
  - Decentralization

- Astreum
  - Accounts
  - Blocks
  - Transactions
  - Relay Protocol
  - Consensus Protocol

- Roadmap
  - Programmable Accounts
  - Account Abstraction
  - Relay Privacy
  - Zero Knowledge Validation
  - Storage Protocol
  - Compute Protocol
  - Gateway Protocol
  - Account & Transaction Privacy
  - Treasury Protocol

- Applications
  - User Powered Applications
  - Terminals
  - Media Streaming
  - Perpetual Storage

- Conclusion

- References

## Introduction

## Why Another Blockchain

### Security

### Privacy

### Usability

### Extensibility

### Decentralization

## Astreum

### Accounts

                + - - - - - - - +
                |    account    |
                + - - - - - - - +
                        ^
                . - - - - - - - - - - - .
                ^                       ^
        + - - - - - - - +       + - - - - - - - +
        |    address    |       |    details    |
        + - - - - - - - +       + - - - - - - - +
                                        ^
                                . - - - - - - - - - - - - - - - - - - - - - - - .
                                ^                       ^                       ^
                        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
                        |    balance    |       |    counter    |       |    storage    |
                        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +

### Blocks

                + - - - - - - - +
                |     block     |
                + - - - - - - - +
                        ^
                . - - - - - - - - - - - .
                ^                       ^
        + - - - - - - - +       + - - - - - - - +
        |    details    |       |   signature   |
        + - - - - - - - +       + - - - - - - - +
                ^
                |
                |       + - - - - - - - +
                | - - - |    accounts   |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |     chain     |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |     data      |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |     delay     |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |    number     |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |    previous   |
                |       + - - - - - - - +
                |       
                |       + - - - - - - - +
                | - - - |    receipts   |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |     solar     |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |     time      |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |  transactions |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                + - - - |   validator   |
                        + - - - - - - - +

### Transactions

                        + - - - - - - - +
                        |  transaction  |
                        + - - - - - - - +
                                ^
                        . - - - - - - - - - - - .
                        ^                       ^
                + - - - - - - - +       + - - - - - - - +
                |    details    |       |   signature   |
                + - - - - - - - +       + - - - - - - - +
                        ^
                        |
                        |       + - - - - - - - +
                        | - - - |     chain     |
                        |       + - - - - - - - +
                        |
                        |       + - - - - - - - +
                        | - - - |    counter    |
                        |       + - - - - - - - +
                        |
                        |       + - - - - - - - +
                        | - - - |     data      |
                        |       + - - - - - - - +
                        |
                        |       + - - - - - - - +
                        | - - - |   recipient   |
                        |       + - - - - - - - +
                        |
                        |       + - - - - - - - +
                        | - - - |    sender     |
                        |       + - - - - - - - +
                        |
                        |       + - - - - - - - +
                        + - - - |     value     |
                                + - - - - - - - +


### Relay Protocol

                        + - - - - - - - +
                        |   Envelope    |
                        + - - - - - - - +
                                ^
                        . - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - .
                        ^                       ^                       ^                       ^
                + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
                |    Message    |       |     Nonce     |       |     Sender    |       |     Time      |
                + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
                        ^
                . - - - - - - - - - - - .
                ^                       ^
        + - - - - - - - +       + - - - - - - - +
        |     Body      |       |     Topic     |
        + - - - - - - - +       + - - - - - - - +

`Routes`

1. Consensus

`Topics`

1. Join
2. Route Request
3. Route Response
4. Transaction
5. New Block
6. Block Request
7. Block Response
8. Account Request
9. Account Response

### Consensus Protocol

Astreum uses a proof of stake consensus protocol for executing transactions and creating new blocks by validators.

A validators must be staked, by sending `Solar` to the `Consensus Account`, to participate in the protocol.

The block time target is three seconds. A slot is the three seconds period when new blocks are created.

Slots are allocated pro-rata to a validator's stake.

A slot miss occurs when a validator does not create a new block or creates a malicious block when selected.

Slot selection determines the validator for the next block at any time:

- Check slot misses from the latest block
- If no slot miss, the latest block delay output is used as the seed in the weighted random address selector
- If slot misses, the linear-feedback shift register, shifted to the number of slot misses, of the latest block delay output is used as the seed in the weighted random address selector

Validators who miss a slot get half their stake returned until 1 `Solar` is left.

Transactions are ordered by the validator.

Validators spend ~1 sec computing a delay output from a verifiable delay function.

The creator of a new block is payed a fee of 10^12 `Solar`.

The valid chain has the most blocks and with the most solar spent in the latest block.

## Roadmap

### Programmable Accounts

### Account Abstraction

### Relay Privacy

### Zero Knowledge Validation

### Storage Protocol

### Compute Protocol

### Gateway Protocol

### Account & Transaction Privacy

### Treasury Protocol

## Applications

## Final

Astreum aims to fully realize an ideal cryptographic network with the following features:

- Permissionless: Astreum Accounts and Services, such as financial intermediation, data storage, serverless computation and networking are open and censorship-free to all users, creators and developers.
- Trustless: Astreum Validation is performed by all nodes on the network efficiently through zero knowledge allowing billions of nodes to synchronize the state of the blockchain in seconds.
- Private: Relay Protocol is protected by encrypting all data including message topics to protect against eavesdropping and mix routing to prevent fingerprinting through metadata analysis.
- Secure: Astreum Accounts and communication through Relay Protocol are protected from future attacks from quantum computers by using post quantum secure digital signature algorithm dilithium and public key exchange algorithm kyber.
- Extensible: the Fusion Language and Machine provide developers with the ability to build any kind of template and application.

## References

- Bitcoin: A Peer-to-Peer Electronic Cash System - Satoshi Nakamoto
- Ethereum White Paper - Vitalik Buterin
- Ethereum Yellow Paper - Gavin Wood
- Kademlia: A Peer-to-Peer Information System Based on the XOR Metric - Petar Maymounkov & David Mazières
- Recursive Functions of Symbolic Expressions and Their Computation by Machine - John McCarthy
- PostScript Language Reference Manual - John Warnock, Charles Geschke, Doug Brotz, Ed Taft and Bill Paxton
- High-speed high-security signatures - Daniel J. Bernstein, Niels Duif, Tanja Lange, Peter Schwabe and Bo-Yin Yang
- CRYSTALS-Dilithium Algorithm Specifications and Supporting Documentation - Shi Bai, Léo Ducas, Eike Kiltz, Tancrède Lepoint,Vadim Lyubashevsky, Peter Schwabe, Gregor Seiler and Damien Stehlé
- Efficient verifiable delay functions - Benjamin Wesolowski
- PLONK: Permutations over Lagrange-bases for Oecumenical Noninteractive arguments of Knowledge - Ariel Gabizon, Zachary J. Williamson and Oana Ciobotaru
- Aurora: Transparent Succinct Arguments for R1CS - Eli Ben-Sasson, Alessandro Chiesa, Michael Riabzev, Nicholas Spooner, Madars Virza and Nicholas P. Ward
