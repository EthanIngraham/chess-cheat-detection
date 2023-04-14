
# Detecting Cheating due to Machine Intelligence in the game of Chess

## Explanation of Files 

The directories 'test' 'train' and 'valid' contains the dataset of key sequences used for training and evaluating the model.
The directory 'random' contains an alternative dataset of random sequences that can be used to train the model if 'PATH' is adjusted in the neuralnet.ipynb file.
The directory 'experiment_sequences' contains the sequences from the games where players had cheated in the experiment outlined in the paper.
The directory 'pgns' contains all of the game files used to generate the game sequences. Individual pgn files contained in this directory may consist of more than one game.
The directory 'runs' is a recording of the model's performances (loss, accuracy, P/R Curve) which can be viewed with TensorBoard

'extract_pgns.ipynb' was used to examine the pgn files, including the process of deciding AvH and HvA games as outlined in section 3.2 of the paper.
'stockfish_analyze_pgn.ipynb' is the moment extractor algorithm. PGN files within the pgns directory will be translated into key sequences and stored in the 'train' folder. You will need to have a local version of stockfish15, which can be downloaded here: https://stockfishchess.org/download/. Put the contents into this directory.
'neuralnet.ipynb' contains the implementation of the DL classifier.

## Excerpt from the Paper Abstract

Today, cheating in online games is extremely common. There is no better example than the game of Chess because of it’s rapidly growing online playerbase combined with widely available game engines (such as Stockfish 15, Komodo and Leela) that can act as world-class consultants for the best move to play in any given position. This research proposes an alternative angle to cheat detection for the game of Chess - the detection of behavioural differences between human and computer play - which is now possible due to the recent advances in deep learning. This differs from the statistical methods of the day which rely on move accuracy and prior information about someone’s playing ability. Additionally, a deep learning solution is aided by large databases of chess games that provide the information needed to discover the nuances in human and computer play. To discover the identity of playing agents we propose a novel two staged solution. The Moment Extractor (ME) will retrieve sequences of play within games which would be more likely to provide a rich source of information concerning the player’s identity. This is done through examining the evaluations of Stockfish 15 for a given position. After this the sequences are processed into a custom convolutional neural network which will classify both playing agents as either computer or human. We show that this cheat detection approach is viable for the game of Chess, with an accuracy of 86\% for our system when classifying games as computer-played or human-played.


