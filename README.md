# EpicGame

A 2-player Java arcade game where **Taz** and **Coyote** (Looney Tunes characters) race to grab food items on screen — with animations, sound effects, and a score system.

## Screenshots

**Start Menu**
![Start Menu](screenshots/start_menu.png)

**Gameplay**
![Gameplay](screenshots/gameplay.png)

**Game Over**
![Game Over](screenshots/game_over.png)

## Features

- **2-player local multiplayer** — Player 1 controls Taz (`A` key), Player 2 controls Coyote (`K` key)
- **Animated characters** — Frame-by-frame sprite animations for both characters
- **Food items** — Good food, Super Juice, Bad Food and Bombs randomly spawned
- **Sound effects** — Background music, eat sounds, bomb sounds, and a win jingle
- **Score tracking** — Live score display for both players
- **Win / Tie screens** — End-game screens showing the winner or a tie
- **Menu & rules screen** — Start menu with controls and food legend shown before the game

## Tech Stack

| | |
|---|---|
| Language | Java |
| Graphics | SimpleGraphics library |
| Audio | `javax.sound.sampled` |
| IDE | IntelliJ IDEA |
| Build | Ant (`build.xml`) |

## Project Structure

```
epicgame/
├── src/org/academiadecodigo/loopeytunes/EpicGame/
│   ├── Main.java              # Entry point
│   ├── Game.java              # Core game loop, input, scoring, audio
│   ├── Field.java             # Game field and visual layout
│   ├── Menu.java              # Start menu
│   ├── Factorys/
│   │   └── FoodFactory.java   # Randomly spawns food or bombs
│   └── GameObjects/
│       ├── Character.java     # Player character logic and key input
│       ├── Food.java          # Food item representation
│       ├── FoodType.java      # Enum: GOOD / BOMB
│       └── GameObjects.java   # Base game object
├── lib/
│   └── simple-graphics-0.2.1-SNAPSHOT.jar
├── screenshots/
└── build.xml
```

## Setup

### Prerequisites

- Java 8+

### 1. Clone the repo

```bash
git clone git@github.com:jovbcorreia/epicgame.git
cd epicgame
```

### 2. Compile

```bash
mkdir -p build/classes
javac -cp lib/simple-graphics-0.2.1-SNAPSHOT.jar \
      -d build/classes \
      $(find src -name "*.java")
```

### 3. Run

```bash
java -cp "build/classes:lib/simple-graphics-0.2.1-SNAPSHOT.jar" \
     org.academiadecodigo.loopeytunes.EpicGame.Main
```

> **Note:** The game must be run from the project root folder so it can find its resource files (images and sounds).

### Alternative — IntelliJ IDEA

Open the project folder in IntelliJ IDEA. The `lib/simple-graphics-0.2.1-SNAPSHOT.jar` is already included — add it to the module classpath and run `Main.java` directly.

## How to Play

| Player | Character | Key |
|--------|-----------|-----|
| Player 1 | Taz | `A` |
| Player 2 | Coyote | `K` |

- Press `Space` on the start menu to begin.
- Press your key when food appears on screen to grab it and score points.
- **Good Food** = +20 points
- **Super Juice** = +60 points
- **Bad Food** = -10 points
- **Bomb** = score resets to 0
- After 10 rounds, the player with the highest score wins.

## Contributors

This was a group project developed by 4 students:

| Name | GitHub |
|------|--------|
| João Vilas-Boas Correia | [@jovbcorreia](https://github.com/jovbcorreia) |
| Rita Febra | — |
| Miguel Morais | — |
| Francisco Soares | — |
