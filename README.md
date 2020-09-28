# NNUE-Nets

- **napping nexus** : a Stockfish data based net build in many steps from 2 billions depth 10 data. Data are from Stockfish genfen. Learner used is the Nodchip repository one. Validation data are 1M depth 16 and 20 Stockfish data.  
- **nascent nutrient** : a Minic data based net build from 400M random positions evaluated by Minic at depth 12. Data were generated using the Minic genfen feature and Minic random mover. The learner merged inside Minic is used in order to ensure Minic evaluation is used. Validation data are 1M depth 16 Minic data extracted from Minic2.48 games in pgn format. No RL with game outcome yet for this net ... coming soon ...
