
# AI Bots and Schnapsen

This project explores intelligent agents for the card game **Schnapsen**, using machine learning, heuristic strategies, and Minimax search.

The repository contains a collection of hybrid-playing bots, training scripts, and experiments comparing different strategies against a baseline agent.

## Project Overview

The main approach combines machine-learning-based decision-making with search-based strategies.

The hybrid bot uses:
- **Phase One:** Machine-learning-based move selection.
- **Phase Two:** Minimax search for more strategic decision-making.

Several variants extend this approach with additional heuristics and strategies.

## Bot Implementations

| File | Description |
|---|---|
| `HybridBot.py` | Main hybrid agent, combining ML-based play in Phase One with Minimax in Phase Two. |
| `HybridBotProb.py` | Includes functionality for estimating an opponent's possible hand by sampling unknown cards while retaining known cards. |
| `HybridBotTrump.py` | Introduces trump-card priorities into the playing strategy. |
| `HybridBotEndgame.py` | Adds an endgame heuristic based on high-card values when five or fewer cards remain in Phase One. |

## Model Training

`train_HybridBot.py` implements the model-training workflow.

The script:
1. Collects game data by playing against BullyBot.
2. Runs 200 games while alternating player order.
3. Uses the collected data to train a model through `train_ML_model`.
4. Uses Logistic Regression (`model_class="LR"`).
5. Saves the trained model for use by the bot.

## Evaluation

`cli.py` provides commands for comparing the different bot implementations against BullyBot.

The available experiment commands include:

- `baseline-comparison`
- `hybridbot-mod1`
- `hybridbot-mod2`
- `hybridbot-mod3`

The comparisons run 100 games and alternate the starting player to reduce the effect of player order.

## Repository Structure

```text
AI-Bots-and-Schnapsen/
├── HybridBot.py
├── HybridBotProb.py
├── HybridBotTrump.py
├── HybridBotEndgame.py
├── train_HybridBot.py
├── cli.py
└── server.py
```

## Technologies and Concepts

- Python
- Schnapsen game framework
- Machine Learning
- Logistic Regression
- Minimax Search
- Heuristic Evaluation
- Card Sampling and Opponent-Hand Estimation
- Click CLI

## Running the Project

1. Clone the repository.
2. Set up the Schnapsen framework and its dependencies.
3. Run the relevant training or evaluation scripts using the project's configured environment.
4. Use the CLI commands to run bot comparisons.

Refer to the individual scripts for implementation details and experiment configuration.
