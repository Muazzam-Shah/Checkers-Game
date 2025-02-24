# Checkers Game in C++

## Overview

This project is a console-based implementation of the classic Checkers game using C++. The game uses a static 8x8 board and supports two players with basic Checkers rules, including normal moves, jump moves, multi-jump sequences, and piece promotion to king when reaching the opposite end of the board.

## Features

- **Board Representation:**  
  Uses an 8x8 static board represented by a `Piece` class. Each board cell holds a `Piece` that keeps track of its owner (player 1 or player 2), its location, and whether it has been promoted to a king.

- **Move Validation:**  
  Implements validation for both simple (diagonal, one-step) moves and jump moves. The rules enforce forward movement for non-king pieces and require that jump moves capture an opponent's piece.

- **Multi-Jump Support:**  
  After a successful jump, the game checks if additional jumps are available from the new position and gives the player an option to continue jumping.

- **Piece Promotion:**  
  Automatically promotes a piece to a king if it reaches the opponent's back row. King pieces are displayed with a capital letter.

- **Text-Based Interface:**  
  A simple command-line interface allows players to input moves by specifying the row and column of the piece to move and its destination.

- **Win Condition:**  
  The game continuously checks for a winner by counting the remaining pieces for each player. The game ends when one player loses all pieces.

## How to Compile and Run

### Prerequisites

- A C++ compiler (e.g., g++)

### Compilation

Open a terminal in the project directory and compile the code with the following command:

```bash
g++ -o CheckersGame Checkers.cpp
```

### Execution

Run the compiled executable:

```bash
./CheckersGame
```

## Game Instructions

1. **Initial Setup:**  
   - Player 1's pieces are positioned on the top three rows.
   - Player 2's pieces are positioned on the bottom three rows.
   - The board is displayed with rows and columns indexed from 0 to 7.
   - Regular pieces are denoted by lowercase letters (`r` for player 1 and `w` for player 2). When promoted to king, the piece is represented by a capital letter (`R` for player 1 and `W` for player 2).

2. **Player Turns:**  
   - The game alternates turns between player 1 and player 2.
   - On each turn, the current player is prompted to enter the coordinates (row and column) of the piece they wish to move and the destination coordinates.
   - The program validates the move (simple move or jump move) based on Checkers rules.
   - If a jump move is made, the game will check if additional jumps are available from the landing position and ask the player if they want to continue jumping.

3. **Winning the Game:**  
   - The game continuously checks if one of the players has lost all their pieces.
   - Once a player has no remaining pieces, the game declares the other player as the winner.

## Code Structure

- **Piece Class:**  
  - **Attributes:**  
    - `Player`: Indicates which player owns the piece.
    - `LocationX` and `LocationY`: The piece's coordinates on the board.
    - `IsKing`: Boolean flag indicating whether the piece is a king.
  - **Static Members:**  
    - `board[8][8]`: A static 2D array representing the game board.
  - **Methods:**  
    - `DisplayBoard()`: Prints the current state of the board.
    - `PromoteIfNeeded()`: Promotes a piece to a king if it reaches the opponent's back row.

- **Utility Functions:**  
  - `inBounds()`: Checks if given coordinates are within the board.
  - `isValidSimpleMove()`: Validates a simple diagonal move.
  - `isValidJumpMove()`: Validates a jump move (captures an opponent's piece).
  - `executeSimpleMove()` and `executeJumpMove()`: Execute moves after successful validation.
  - `canJump()`: Checks if a piece can perform any jump moves.
  - `CheckWinner()`: Determines if a player has won the game.

- **Main Function:**  
  - Initializes the board with pieces for both players.
  - Manages the game loop, processing player moves and updating the board.
  - Switches turns and checks for win conditions after each move.

## Additional Notes

- **Input Coordinates:**  
  All coordinates are 0-indexed. When prompted, enter the row and column separated by a space.
  
- **Error Handling:**  
  The game validates user input and prompts for re-entry if an invalid move or position is provided.

- **Gameplay:**  
  Enjoy the game by following the on-screen prompts, and make strategic moves to capture your opponent’s pieces!

