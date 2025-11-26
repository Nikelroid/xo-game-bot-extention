# XO-Game-Bot

![Java](https://img.shields.io/badge/Java-11%2B-ED8B00?logo=openjdk&logoColor=white)
![JSON](https://img.shields.io/badge/org.json-2016-lightgrey)
![Bot](https://img.shields.io/badge/Type-Game_Bot-blueviolet)

## Project Description

**XO-Game-Bot** is a fun, interactive extension for the **Nwitter-Backend-Server**. It functions as a gaming bot that enables users to play Tic-Tac-Toe (XO) via direct messages. Unlike text-only bots, this project utilizes Java's graphics libraries to dynamically generate and send image files (`.png`) representing the current state of the game board after every move, providing a rich visual experience.

## Features

  * **Interactive Gameplay:** Manages game sessions, turns, and move validation (`operateGround.java`).
  * **Visual Feedback:** Dynamically draws the game board (X's and O's) into an image file using `makePicture.java` and `groundPrinter.java`.
  * **Win Detection:** Automated logic to check for winning conditions (rows, columns, diagonals) via `checkWin.java`.
  * **State Management:** Tracks active games using `gameObj` to ensure multiple users can play simultaneously without state collision.
  * **Server Integration:** Connects to the main Nwitter infrastructure to receive commands and send back image assets.

## System Requirements

  * **Java Development Kit (JDK):** Version 11 or higher.
  * **Nwitter Server:** Must be running to handle the message routing.
  * **Dependencies:**
      * `json-20160212.jar`

## Detailed File Analysis

The source code is contained within `XO_game/src/`.

  * **`Main.java`**: The entry point. Connects to the server socket and listens for "start game" or "move" commands.
  * **`launchGame.java`**: Initializes a new game instance for a user.
  * **`operateGround.java`**: The core controller for handling user input (e.g., placing an 'X' at position 5).
  * **`checkWin.java`**: Algorithmic logic to determine if the current board state results in a win, loss, or draw.
  * **`makePicture.java` / `groundPrinter.java`**: Uses `java.awt` (Abstract Window Toolkit) to draw the grid and symbols onto a buffered image, saving it as a PNG to be sent to the user.
  * **`gameObj.java`**: A model class holding the data for a specific match (player IDs, current board array).

## Installation & Running

### 1\. Setup

Clone the repository:

```bash
git clone https://github.com/nikelroid/xo_game.git
cd xo_game
```

### 2\. Configuration

Ensure the bot is configured to connect to the correct Nwitter Server IP and Port. Check `Main.java` or associated config files (if extracted) for connection strings.

### 3\. Dependencies

Ensure `json-20160212.jar` located in the `lib` folder is added to your project classpath.

### 4\. Execution

Run the `Main` class to start the bot:

```bash
java -cp "XO_game/lib/*:XO_game/src" Main
```

## Usage

Users on the Nwitter Client can interact with the bot using chat commands.

1.  **Start:** Send a message to the bot to initiate a match.
2.  **Play:** Send a number (1-9) or coordinate to place your mark.
3.  **View:** The bot replies with an image of the updated board.

## Contributing

Pull requests are welcome. If improving the image generation (e.g., adding skins or themes), please ensure the output file size remains optimized for network transmission.

## License

Distributed under the MIT License.

## Contact

Project Maintainer - [GitHub Profile](https://www.google.com/search?q=https://github.com/nikelroid)

