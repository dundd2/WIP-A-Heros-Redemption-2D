# A Hero's Redemption 2D

A Hero's Redemption 2D is a simple RPG battle game built using the LÖVE 12 Beta game Framework.
It serves as a personal proof-of-concept and learning exercise to better understand the mechanics, systems, and potential complexities involved in game development, specifically in preparation for a larger Unity 3D group project for later this year. This 2D project aims to provide insights into code volume, game architecture, and overall development effort. Ultimately, it helps assess the feasibility of achieving our ambitious 3D game goals within a few months of part-time development.

## ScreenShot (V0.01)
![ScreenShot1](https://github.com/dundd2/A-Heros-Redemption-2D/blob/main/assets/Screenshot/SC(1).gif)
![ScreenShot1](https://github.com/dundd2/A-Heros-Redemption-2D/blob/main/assets/Screenshot/SC(2).png)
![ScreenShot1](https://github.com/dundd2/A-Heros-Redemption-2D/blob/main/assets/Screenshot/SC(3).png)

## Project Overview

This demo focuses on implementing a turn-based battle system and core RPG elements. Therefore, this 2D version intentionally simplifies the scope and concentrates on:

*   **Turn-Based Combat:** Implementing a system where the player and enemy take turns to perform actions.
*   **Basic Skills:** Creating a skill system with different actions like attack, defend, special attack, and heal.
*   **Enemy AI:** Developing a basic AI for enemies to make decisions in combat.
*   **Story System:** Adding a basic dialogue system to give the game context and narrative.
*   **Game States:** Managing different game states (menu, level select, story, battle, victory, defeat, ending).

## Scope and Excluded Features

This 2D demo is intentionally simplified and **does not include** features planned for our future 3D project, such as:

- **Movement**: This 2D game restricts player movement to direct transitions into duel states after the story mode, lacking free-roam exploration. A movement script is not included.  
- **Weapon Switching**  
- **Leveling System**: Character progression and EXP management  
- **Small Monsters for Leveling (Grinding)**  
- **Respawn System**  
- **Room Event Triggers**: Events within rooms, such as traps, treasure, or monster encounters.  
- **Inventory System**  
- **Equipment System**  
- **Item Pickup (Collectible Object)**  
- **Treasure/Loot System**  
- **NPC Quest and Trading System**  
- **Map Display**  
- **Mini-Map**  
- **Play Status UI**:Current HP, MP, EXP, LV.  MC’s statistics, 
- **Quest Page** : Show players’ mission

Despite these simplifications, the 2D game codebase already consists of approximately **3500+ lines of code**. This provides a tangible reference point for understanding the scale and complexity even of a reduced-scope game and highlights potential challenges in developing a more feature-rich 3D project within our timeframe.

For more detailed features and information about our current (Jan 2025) plans for the 3D project, please check the [A Hero's Redemption Game Plan](A%20Hero's%20Redemption%20Game%20Plan.pdf)
 file.

## Built With

*   [LÖVE2D 12.0](https://love2d.org/): A free, open-source 2D game Framework .

## How to Play

### Option 1: Download the Executable (Windows)
1. Go to the [Releases](https://github.com/dundd2/A-Heros-Redemption-2D/releases) page
2. Download the latest .exe file
3. Run the downloaded executable to play the game

### Option 2: Run with LÖVE
1.  **Download Love:** Download and install LÖVE from [https://love2d.org/](https://love2d.org/).
2.  **Download or Clone the Project:** Clone or download this repository to your local machine.
3.  **Run the Game:** Drag and drop the project folder (the folder containing `main.lua`) onto the `love.exe` executable (on Windows) or run from the terminal.

### Controls:

*   **Menu:**
    *   **Up/Down Arrow Keys:** Navigate menu options.
    *   **Enter/Space:** Select menu option.
*   **Level Select:**
    *   **Up/Down Arrow Keys:** Choose a level.
    *   **Enter:** Start the story and begin a battle for the selected level.
    *   **Esc:** Return to the main menu.
*   **Story Mode:**
    *   **Enter:** Continue to the next dialogue line.
    *   **Esc:** Skip the dialogue and go directly to the battle.
*   **Battle:**
    *   **Up/Down Arrow Keys:** Navigate skill options.
    *   **Enter/Space:** Select a skill.
    *   **Esc:** Pause the game.
    *   **Tab/I:** Toggle skill information screen.
    *   **Up/Down Arrow Keys (Skill Screen):** Select a skill from the skill information screen
*   **Pause Menu**
     *   **Mouse Click:** Click the button to continue,restart or return to menu
*   **Victory/Defeat Screen**
    *   **Mouse Click:** Click the button to restart or return to menu

### Game Mechanics

*   **Main Menu:** You can choose to start a level or exit the game.
*   **Level Select:** Select the level you want to play.
*   **Story Mode:** Before each battle, there will be a story dialogue. Press Enter to continue, or Esc to skip.
*   **Battle System:**
    *   The battle is turn-based. The player and enemy alternate their turns.
    *   On your turn, you can choose between Attack, Defend, Special Attack and Heal skill.
    *  Each skill has a cooldown period.
    *   The enemy uses a simple AI to decide whether to attack or defend.
    *   The battle ends when either the player's or the enemy's HP reaches 0.
*  **Pause Menu:**
    *   Press ESC in battle to pause the game
    *   You can chose to continue the game, restart the game or return to main menu
* **Victory/Defeat:**
    * After a battle ends, you can restart the game or return to main menu

## Skills Used

This project utilizes the following skills and concepts:

*   **Lua Programming:** The entire game logic is written in Lua.
*   **Love2D API:** Utilizes Love2D's core functionalities for:
    *   **Graphics:** Drawing images, text, and shapes.
    *   **Audio:** Playing sound effects and background music.
    *   **Input:** Handling keyboard and mouse input.
    *   **Timer:** Implementing delay and cooldown systems.
    *   **Particle System:** Creating simple visual effects.
*   **Game Design:** Implementing core game concepts such as:
    *   Turn-based combat mechanics
    *   Skill and cooldown systems
    *   Basic enemy AI
    *   UI/UX design
    *   Level design
*   **Data Structures:** Using Lua tables to manage game data.
*   **Object-Oriented Concepts:** Implemented in Lua using tables and functions.
*   **Game Logic:** Implementing game state logic, battle logic, and story progression logic.

## External Resources

This project utilizes various free resources from the game development community, including artwork, sound effects, and music. I'm grateful to all the creators who make their work available for others to use. For a detailed list of all resources used and their respective credits, please check the [Resource Credits List.md](Resource%20Credits%20List.md) file.

## Thanks

I would like to express my gratitude to the Love2D team for providing such a fantastic, free, and open-source game Framework.
