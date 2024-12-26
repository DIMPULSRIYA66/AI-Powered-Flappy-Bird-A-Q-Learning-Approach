# AI-Powered Flappy Bird: A Q-Learning Approach

This repository contains an implementation of Flappy Bird, enhanced with AI capabilities using Q-Learning, a popular Reinforcement Learning (RL) algorithm. The project demonstrates how an agent learns to play the game by updating its policy based on rewards and penalties.

## Features

- **AI Gameplay**: The bird is controlled by a Q-Learning-based AI agent that learns optimal strategies.
- **Dynamic Graphics**: Smooth animations using Pygame for the bird, pipes, and background.
- **Real-Time Training Visualization**: Observe how the AI improves over multiple generations.
- **Game Elements**:
  - Bird: The player character.
  - Pipes: Obstacles with randomized positions.
  - Score: Increments whenever the bird successfully passes a pipe.

## Prerequisites

To run this project, ensure you have the following installed:

- Python 3.x
- Pygame
- NumPy
- Matplotlib

You can install the dependencies using pip:

```bash
pip install pygame numpy matplotlib
```

## How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/ai-flappy-bird.git
   cd ai-flappy-bird
   ```

2. Place the required game assets in an `imgs/` directory:
   - `bird1.png`: The bird sprite
   - `bg.png`: Background image
   - `pipe.png`: Pipe image
   - `base.png`: Ground image

3. Run the game:
   ```bash
   python flappy_bird_ai.py
   ```

## How It Works

### Game Logic
- The bird navigates through a series of pipes, avoiding collisions with the ground or pipes.
- The game dynamically updates based on user input or AI actions.

### Q-Learning Algorithm
- The Q-table is represented as a 3D NumPy array (`Q`), where states are defined by:
  - Horizontal distance to the next pipe (`x`).
  - Vertical distance between the bird and the next pipe opening (`y`).
- Actions:
  - Jump (`1`): Make the bird flap upwards.
  - Do Nothing (`0`): Let the bird fall naturally.
- Rewards:
  - +15 for passing a pipe.
  - -1000 for a collision.
- Update Rule:
  ```
  Q[state][action] = alpha * Q[state][action] + (1-alpha) * (reward + gamma * max(Q[next_state]))
  ```

### Visualization
- The game displays the current generation, score, and a live plot showing AI performance improvement over generations.

## Controls

- Press `Space` or `Up Arrow` to make the bird jump during manual play.
- The AI takes over automatically once the game starts.

## File Structure

```
|-- imgs/
|   |-- bird1.png       # Bird sprite
|   |-- bg.png          # Background image
|   |-- pipe.png        # Pipe image
|   |-- base.png        # Ground image
|-- flappy_bird_ai.py    # Main game script with AI logic
|-- README.md           # Project documentation


## Future Improvements

- Add advanced algorithms like Deep Q-Learning for better AI performance.
- Introduce new game mechanics (e.g., variable pipe speeds, different bird dynamics).
- Create a user interface for selecting AI or manual play mode.


