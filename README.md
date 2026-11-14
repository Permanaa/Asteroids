# Asteroids

A classic **Asteroids-inspired arcade game** built with Python and Pygame. Pilot a spaceship, dodge incoming asteroids, and destroy them with projectiles. Larger asteroids split into smaller pieces when hit, making survival increasingly challenging.

## Features

- **Player Movement** – Rotate and move your spaceship in any direction.
- **Projectile System** – Shoot projectiles in the direction your spaceship is facing.
- **Dynamic Asteroid Spawning** – Asteroids spawn from random screen edges with randomized movement.
- **Asteroid Splitting** – Larger asteroids split into two smaller asteroids when destroyed.
- **Collision Detection** – Circle-based collision detection for game objects.
- **Game State Logging** – Automatically records game state snapshots and gameplay events in JSONL format.

## Tech Stack

- **Language:** Python 3.13+
- **Game Framework:** Pygame 2.6.1
- **Package Manager:** uv

## Getting Started

### Prerequisites

Make sure you have the following installed:

- Python 3.13 or later
- [uv](https://docs.astral.sh/uv/getting-started/installation/)

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Permanaa/Asteroids.git
   ```

2. Navigate to the project directory:

   ```bash
   cd Asteroids
   ```

3. Install project dependencies:

   ```bash
   uv sync
   ```

### Running the Game

Start the game using:

```bash
uv run main.py
```

Alternatively, install Pygame manually and run the application:

```bash
pip install pygame==2.6.1
python main.py
```

## Controls

| Key | Action |
|---|---|
| `W` | Move forward |
| `S` | Move backward |
| `A` | Rotate left |
| `D` | Rotate right |
| `SPACE` | Shoot |
| `ESC` / Window Close | Close the game |

## Project Structure

```text
Asteroids/
├── asteroid.py          # Asteroid behavior and splitting mechanics
├── asteroidfield.py     # Asteroid spawning and field management
├── circleshape.py       # Base class for circular game objects
├── constants.py         # Game configuration and constants
├── logger.py            # Game state and event logging
├── main.py              # Main game loop and initialization
├── player.py            # Player movement and shooting mechanics
├── shot.py              # Projectile behavior
├── pyproject.toml       # Project metadata and dependencies
├── uv.lock              # Dependency lockfile
└── README.md
```

## Architecture

The project follows a modular, object-oriented design, separating game logic into individual classes.

### Core Components

- **CircleShape:** Provides shared properties and collision detection for circular game objects.
- **Player:** Handles spaceship movement, rotation, rendering, and shooting.
- **Asteroid:** Manages asteroid movement, rendering, and splitting behavior.
- **AsteroidField:** Controls asteroid spawning from random screen boundaries.
- **Shot:** Represents projectiles fired by the player.
- **Logger:** Captures game state snapshots and gameplay events for debugging and analysis.

## Game Configuration

Game parameters can be customized in `constants.py`.

| Parameter | Default Value |
|---|---:|
| Screen Width | 1280 |
| Screen Height | 720 |
| Player Speed | 200 |
| Player Turn Speed | 300 |
| Asteroid Spawn Interval | 0.8 seconds |
| Asteroid Minimum Radius | 20 |
| Asteroid Kinds | 3 |
| Projectile Speed | 500 |
| Shooting Cooldown | 0.3 seconds |
