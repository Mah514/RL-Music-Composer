# Music Composer Agent Using Reinforcement Learning

## Overview
This project implements a reinforcement learning agent, **MusicComposerAgent**, designed to compose music. The agent uses Q-learning with an LSTM network to generate sequences of musical chords, each with specified durations. The implementation leverages the `musicpy` library for musical chord representation and manipulation.

## Features
- **LSTM-Based Learning**: Utilizes Long Short-Term Memory (LSTM) networks to handle the sequential nature of musical composition.
- **Dynamic Action Space**: Each action chosen by the agent corresponds to a combination of a musical chord and its duration.
- **Epsilon-Greedy Strategy**: Balances exploration and exploitation for efficient learning.
- **Reward-Based Learning**: The agent's learning is guided by a reward system based on musical theory.

## Implementation Details

### MusicComposerAgent Class
- **State Size**: Represents the length of the chord sequence (32 chords).
- **Action Size**: Determined by the number of unique chord-duration combinations.
- **Memory**: Stores experiences for replay, aiding in learning from past decisions.
- **Learning Rate, Gamma, Epsilon**: Parameters to control learning speed, discounting of future rewards, and balance between exploration and exploitation.

### Key Methods
- **_build_lstm_model**: Constructs the LSTM model used for predicting actions.
- **choose_action**: Selects the next action based on the current state, using the epsilon-greedy strategy.
- **remember**: Stores experiences in memory.
- **replay**: Samples from memory to train the model, updating the policy based on past experiences.
- **calculate_reward**: Determines the reward for a given action, based on predefined musical theory rules.
- **train**: Orchestrates the training process, utilizing replay for model updates.

### External Function: action_to_chord_duration
- Maps action indices to specific chord and duration combinations.
- Based on a predefined list of chords and durations, this function translates numerical actions into musical decisions.

## How to Run
- Ensure you have `musicpy`, `numpy`, and `keras` installed in your Python environment.
- Run the main script to initialize and train the **MusicComposerAgent**.

## TODO
- Implementation of the reward system to better align with complex musical theory.
- Expansion of the chord and duration choices for more diverse musical outputs. (Optional)
- Exploration of different neural network architectures for improved learning efficiency. (Optional)
