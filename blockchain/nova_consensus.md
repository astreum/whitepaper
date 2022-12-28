 
# Nova Consensus

### Stake Ranking

The Ranking formula is Staked Amount x Time Staked. Ranking is evaluated by accumulating the staked amount at every Epoch (60,480 blocks).

Withdrawls reduce Ranking proportionally to the address total stake. Rankings are then reset at every Era (3,144,960 blocks).

### Slot Allocation

60,480 slots are distributed proportionally to the ranking of stakers at every Epoch.

### Minter Selection

The nearest address to the previous block hash with available slots is choosen as the next minter.

### Penalties

| Activity | Quanta |
|---|---|
| Non Participation | 100 QTA/Epoch |
| Malicious | 1000 QTA |

Malicious Activity:-
1. Minting Improper Blocks
2. Validating a Chain with Improper Blocks