# NNUE-Nets 

## for SF NNUE

These are nets compatible with version 0x7AF32F16u of SF NNUE implementation. Minic versions 2.47 to 2.53 can use those nets (not Minic version >=3.00)

- **napping nexus** (09/2020) : a Stockfish data based net build in many steps from 2 billions depth 10 data. Data are from Stockfish genfen. Learner used is the Nodchip repository one. Validation data are 1M depth 16 and 20 Stockfish data. With this net, MinicNNUE is around 100Elo weaker than with SV net.  
- **nascent nutrient** (10/2020) : a Minic data based net build from 400M random positions evaluated by Minic at depth 12. Data were generated using the Minic genfen feature and Minic random mover. The learner merged inside Minic is used in order to ensure Minic evaluation is used. Validation data are 1M depth 16 Minic data extracted from Minic2.48 games in pgn format. No RL with game outcome for this net. With this net, MinicNNUE is around 100Elo weaker than with napping nexus.

## for Seer like NNUE

These nets are compatible with Minic >=3.00 

- **nefarious nucleus** for Minic 3.00 or 3.01 (11/2020): same data as nascent nutrient. With this net, Minic3.01 is 60Elo weaker than HCE at short TC.
- **narcotized nightshift** for Minic >=3.02 && <=3.06 (12/2020): this net is generated with data from Minic HCE search at depth 8 using positions seen during game at root. At the beginning of each game, 2 to 8 plies are play randomly. Around 500M positions were used, Minic was trained for 12 epoch. This net is **not compatible** with previous release because a *clipped relu* is now used in the training and inference code. With this net, Minic3.02 is around 90Elo stronger than Minic3.01 with nefarious nucleus.
- **nettling nemesis** for Minic >=3.02 && <=3.06 (12/2020): this net is built using 2B Stockfish (master) data at depth 5. This one is **not** for use in rating list of course ! just for fun. Minic is of course a lot stronger using this net. Architecture is the same as previous net. It was trained during 2 epoch only... and is somehow near +150Elo versus "narcotized nightshift"...
- **niggling nymph** for Minic >=3.02 && <=3.06 (01/2020): this net is built using 600M FRC data at depth 8 from Minic HCE. It plays better FRC games than HCE (this was not the case of previous nets...). It is something like 20Elo stronger than "narcotized nightshift".  
- **noisy notch** for Minic >=3.02 && <=3.06 (02/2020): this net is built using 2B standard data at depth 8 from Minic HCE. It plays something like +50Elo better than previous net at short TC. My net generation process is now involving a massive testing process of more than 150 nets after generating them during the training phase. Noisy Notch was the better with a performance of 66+/-10Elo versus previous net (https://raw.githubusercontent.com/tryingsomestuff/NNUE-Nets/master/images/noisy_notch_testing.png).
- **nibbled nutshell** for Minic ==3.05 (03/2020): an unreleased smaller net that performs well at STC but not good enough at LTC (data used where the same as for "noisy notch").
- **nocturnal nadir** for Minic >=3.06 (05/2020): a net built using new 2B Minic HCE data where depth depend on game phase (depth 8 in opening, depth 12 in end-game) and including some FRC generated positions. This net seems at least 20Elo stronger than "noisy notch". Again here, this net is extracted from 200 others good ones thanks to a long testing process.
- **naive nostalgia** for Minic >=3.06 (05/2020): a net built using 1B Minic noisy notch data with depth depending on game phase (depth 8 in opening, depth 12 in end-game). This net is stronger in classical chess and a little bit weaker in FRC than the previous one. This net is *embeded* in Minic 3.07.
- **negligible nystagmus** for Minic >=3.06 (06/2020): this net is built using the same data as "naive nostalgia" but with some FRC position added and was selected based on its FRC performance. It looks as strong as "naive nostalgia" for classical chess but is much stronger at FRC. This net is *embeded* in Minic 3.08.
