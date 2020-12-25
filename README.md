# NNUE-Nets 

## for SF NNUE

These are nets compatible with version 0x7AF32F16u of SF NNUE implementation. Minic versions 2.47 to 2.53 can use those nets (not Minic version >=3.00)

- **napping nexus** (09/2020) : a Stockfish data based net build in many steps from 2 billions depth 10 data. Data are from Stockfish genfen. Learner used is the Nodchip repository one. Validation data are 1M depth 16 and 20 Stockfish data. With this net, MinicNNUE is around 100Elo weaker than with SV net.  
- **nascent nutrient** (10/2020) : a Minic data based net build from 400M random positions evaluated by Minic at depth 12. Data were generated using the Minic genfen feature and Minic random mover. The learner merged inside Minic is used in order to ensure Minic evaluation is used. Validation data are 1M depth 16 Minic data extracted from Minic2.48 games in pgn format. No RL with game outcome for this net. With this net, MinicNNUE is around 100Elo weaker than with napping nexus.

## for Seer like NNUE

These nets are compatible with Minic >=3.00 

- **nefarious nucleus** for Minic 3.00 or 3.01 (11/2020): same data as nascent nutrient. With this net, Minic3.01 is 60Elo weaker than HCE at short TC.
- **narcotized nightshift** for Minic 3.02 (12/2020): this net is generated with data from Minic search at depth 8 using positions seen during game at root. At the beginning of each game, 2 to 8 plies are play randomly. Around 500M positions were used, Minic was trained for 12 epoch. This net is **not compatible** with previous release because a *clipped relu* is now used in the training and inference code. With this net, Minic3.02 is around 90Elo stronger than Minic3.01 with nefarious nucleus.
- **nettling nemesis** for Minic 3.02 (12/2020): this net is built using 2B Stockfish (master) data at depth d5. This one is **not** for use in rating list of course ! just for fun. Minic is of course a lot stronger using this net. Architecture is the same as previous net. It was trained during 1 epoch only... and is somehow near +200Elo versus "narcotized nightshift"...
