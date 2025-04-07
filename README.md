# AlphaZero Tic-Tac-Toe

This repository contains an re-implementation of AlphaZero's self-play algorithm to create a super-human tic-tac-toe AI.

## Table of Contents

- [Introduction](#introduction)
- [Project Structure](#project-structure)
- [Algorithm Overview](#algorithm-overview)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

AlphaZero is a reinforcement learning algorithm that uses self-play to train a neural network to play games at a super-human level. This project implements AlphaZero specifically for the game of tic-tac-toe.

## Project Structure

The project structure is as follows:

```
Tictactoe-AlphaZero/
├── models/                 # Directory containing model versions
├── src/                    # Source code directory
│   ├── alphazero.py        # Main AlphaZero algorithm implementation
│   ├── game.py             # Game logic for tic-tac-toe
│   ├── mcts.py             # Monte Carlo Tree Search implementation
│   ├── neural_net.py       # Neural network for policy and value predictions
│   └── utils.py            # Utility functions
├── notebooks/              # Jupyter notebooks for experimentation
├── data/                   # Directory for storing training data
├── requirements.txt        # Python dependencies
└── README.md               # Project README
```

## Algorithm Overview

### AlphaZero Algorithm

The AlphaZero algorithm consists of the following key components:

1. **Neural Network**: Predicts the policy (move probabilities) and the value (expected outcome) for the current board state.
2. **Monte Carlo Tree Search (MCTS)**: Simulates games to improve the neural network's predictions and select the best move.
3. **Self-Play**: The AI plays games against itself to generate training data.
4. **Training Loop**: The neural network is trained on the self-play data using supervised learning.

### Neural Network

The neural network is implemented in `src/neural_net.py` and consists of convolutional layers followed by fully connected layers. It outputs a policy vector and a value scalar for the given board state.

### Monte Carlo Tree Search (MCTS)

The MCTS algorithm is implemented in `src/mcts.py`. It uses the neural network's predictions to guide the search and select the most promising moves based on the visit counts of the nodes in the search tree.

### Game Logic

The tic-tac-toe game logic is implemented in `src/game.py`. It includes functions for making moves, checking for win conditions, and representing the game state.

### Training and Self-Play

The self-play and training process is implemented in `src/alphazero.py`. The AI plays games against itself to generate training data, which is then used to train the neural network.

## Installation

To install and run the project, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/moosemorse/Tictactoe-AlphaZero.git
    cd Tictactoe-AlphaZero
    ```

2. Create a virtual environment:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

To start training the AlphaZero model, run the following command:
```bash
python src/alphazero.py
```

You can also experiment with the model using the Jupyter notebooks in the `notebooks/` directory.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
