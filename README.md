# Tic-Tac-Toe Game with OpenGL

![About](https://github.com/GabrielFrazz/TicTacToe-OpenGL/assets/118780538/b4e57a7d-9f08-4146-957a-f0eafe0780d7)

## Table of Contents

- [Introduction](#introduction)
- [Software Architecture](#software-architecture)
- [System Modules](#system-modules)
- [Abstract Data Type (ADT) - Tree and Minimax Algorithm](#abstract-data-type-adt---tree-and-minimax-algorithm)
- [Graphical User Interface Design](#graphical-user-interface-design)
  - [Design Principles](#design-principles)
  - [Menus and Options](#menus-and-options)
    - [Main Menu](#main-menu)
    - [Submenus](#sub-menus)
  - [Rendering the Board and X/O Symbols](#rendering-the-board-and-xo-symbols)
- [How to Run](#how-to-run)

## Introduction

This repository documents the development process of a Tic-Tac-Toe game implemented in the C language using the OpenGL library.

## Software Architecture

In this section, we'll delve into the underlying software architecture of the Tic-Tac-Toe game. It includes the definition of Abstract Data Types (ADTs) that represent essential game structures and details on interconnected modules, each focusing on specific tasks.

### System Modules

The architecture of the Tic-Tac-Toe game is divided into independent modules, each representing specific functionalities. These modules are:

- **Board**: Defines the TBoard data structure to represent the state of the game board and provides functions for board manipulation and checking game conditions, such as determining if the board is full or if a player has won.
- **Computer**: Implements the logic for the computer player using the Minimax algorithm, responsible for calculating the most strategic move based on the current board state.
- **Game**: Manages the game flow, including win detection, game reset, and scorekeeping. It also handles user interaction, such as responding to keyboard commands and mouse clicks.
- **UI (User Interface)**: Takes care of the graphical rendering of the game, including menus, game options, and visual elements of the board. It offers functions to display information on the screen, such as main menus, game mode selection, scoreboards, and submenus.
- **Util (Utilities)**: Provides utility functions to process keyboard and mouse inputs, map screen coordinates to board cells, and handle keyboard events.

These modules communicate through function calls and shared data structures, promoting code modularity and reusability. The code structure follows the C library convention, with header files (.h) and implementation files (.c) for each module, enhancing code modularity and reusability.

![Relations](https://github.com/GabrielFrazz/TicTacToe-OpenGL/assets/118780538/8ab20744-7dbc-4c7f-b639-7a384939712c)

### Abstract Data Type (ADT) - Tree and Minimax Algorithm

To implement the computer player's logic, we employed the Abstract Data Type (ADT) of a tree, combined with the Minimax algorithm. The tree ADT was represented using the TCell structure, which holds information about the board state (TBoard), the node's parent, and its possible children.

The Minimax algorithm is an exhaustive search technique that evaluates all possible moves in a two-player zero-sum game, such as Tic-Tac-Toe. It aims to maximize the current player's score while minimizing the opponent's score. The Minimax algorithm works as follows:

1. If the current move leads to a winning state, the algorithm returns a positive score. If it leads to a losing state, the score is negative.
2. If the current move leads to a draw, the score is zero.
3. Otherwise, the Minimax algorithm generates all possible future moves from the current state and recursively calls Minimax for each opponent's move. The score for the current state is the maximum of the opponent's scores (in the current player's turn) or the minimum (in the opponent's turn).
4. The Minimax algorithm returns the score for the current state.

In the context of the Tic-Tac-Toe game, the Minimax algorithm is used by the computer player to determine the best possible move. The `minimax` function, implemented in the Computer module, calculates scores for all possible moves and returns the move that results in the best score for the computer player.

![Minimax](https://github.com/GabrielFrazz/TicTacToe-OpenGL/assets/118780538/c5d1c34f-11c9-4de5-a1d7-a07bc0237847)

## Graphical User Interface Design

This section outlines the design and layout of the game's graphical user interface, implemented using the OpenGL library.

### Design Principles

The graphical interface of the Tic-Tac-Toe game emphasizes clarity, simplicity, and ease of navigation. The initial layout features a grid representing the game board, where players can place their symbols. Additionally, the interface includes elements such as menus, buttons, and score indicators.

### Menus and Options

The graphical interface provides menus and options that allow players to interact with the game and customize their gaming experience. The menus are organized intuitively, enabling players to navigate between different screens and choose their preferred options.

#### Main Menu

The main menu offers options for players to select different game modes, such as "Player vs. Player" or "Player vs. Computer." Additionally, the main menu provides access to other screens, including game instructions, developer information, and exit options.

![MainMenu](https://github.com/GabrielFrazz/TicTacToe-OpenGL/assets/118780538/73012ab7-7aaa-4d69-84c5-d174fa64463f)

#### Submenus

During gameplay, players have the option to access submenus that offer choices such as selecting the game mode, viewing controls, returning to the main menu, restarting the game, checking the current score, and more. These additional options provide flexibility and control to players during the match.

![SubMenu](https://github.com/GabrielFrazz/TicTacToe-OpenGL/assets/118780538/49d8fbff-7146-4cc4-b380-2cd579b8d3c9)

### Rendering the Board and X/O Symbols

The OpenGL library was utilized to render the game board using simple geometric shapes and lines. The rendering is optimized to ensure sharp edges and an organized layout, contributing to the visual clarity of the game. Furthermore, the "X" and "O" symbols are dynamically drawn using OpenGL functions, resulting in clean and well-defined visual elements.

![GameBoard](https://github.com/GabrielFrazz/TicTacToe-OpenGL/assets/118780538/33b4a434-42f6-4536-9f5b-718e3b7639b6)

## How to Run

Follow these steps to compile and run the Tic-Tac-Toe game on your local machine:

### Prerequisites

Before you begin, ensure that you have the following prerequisites installed on your system:

- [OpenGL](https://www.opengl.org/) - Graphics library used for rendering.
- C compiler.

### Clone the Repository

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/GabrielFrazz/TicTacToe-OpenGL.git

### Compile the Game

1. Navigate to the repository directory:
    ```bash
    cd TicTacToe-OpenGL

2. Compile the game using your preferred C compiler (e.g., GCC):
    ```bash
    gcc -o tic_tac_toe main.c board.c computer.c game.c ui.c util.c -lGL -lGLU -lglut -lm

### Run the Game

1. run the compiled exectable:
    ```bash
    ./tic_tac_toe

    
