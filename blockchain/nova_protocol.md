 
# Nova Protocol

## Requirments
1. Consensus
2. Penalties

### Stake Ranking

The Ranking formula is Staked Amount x Time Staked. Ranking is evaluated by accumulating the staked amount at every Epoch (60,480 blocks).

Withdrawls reduce Ranking proportionally to the address total stake. Rankings are then reset at every Era (3,144,960 blocks).

### Block Time

There are 60,480 block times, distributed proportionally to the ranking of stakers, at every Epoch.

The nearest address to the previous block hash with available block times is choosen as the next minter.

### Validation Time

Validation Time is 15 blocks long where validators mint blocks and unify the chain.

### Penalties

| Activity | Cost |
|---|---|
| Non Participation | 100 QTA/Epoch |
| Malicious | 1000 QTA |

Malicious Activity:-
1. Minting an Improper Block