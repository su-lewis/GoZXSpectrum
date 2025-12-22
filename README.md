# Go (Baduk) for ZX Spectrum

A fully functional implementation of the board game **Go** (Japanese) also known as Baduk (Korean) or Weiqi (Chinese) for the Sinclair ZX Spectrum. Written in Sinclair BASIC.

## Features

* **2-Player Mode:** Play against a friend 
* **9x9 Board:** Optimized for the Spectrum screen layout.
* **Japanese Rules:** Standard Japanese scoring (Territory + Captures) and mechanics.
* **No Komi:** A traditional handicap-free game where White receives no compensation points.
* **Full Rules Implementation:**
    * Capture logic (removing stones with no liberties).
    * **Ko Rule:** Prevents infinite loop repetition.
    * **Suicide Rule:** Prevents moves that result in immediate self-capture (unless it captures the opponent).
* **Automatic Scoring:** Calculates territory and captures at the end of the game using Japanese scoring rules.

## How to Play

### Loading the Game
**Using an Emulator (Recommended):**
1.  Download the `Lewis_go_baduk.tap` file from this repository.
2.  Open your ZX Spectrum emulator (e.g., Fuse, Spectaculator, ZXSpin).
3.  Open/Load the `.tap` file.
4.  The game should auto-load.

**Using Real Hardware:**
1.  Transfer the `Lewis_go_baduk.tap` file to a cassette tape or load it via an audio interface (e.g., TZXDuino, or playing the audio from a PC/Phone into the Spectrum's "EAR" port).
2.  Type `LOAD ""` on your Spectrum and press Enter.
3.  Play the tape/audio.

### Controls
The game is played using keyboard coordinates.

* **Placing a Stone:** Type the coordinate of the intersection where you want to play.
    * Format: `Letter` followed by `Number`.
    * Example: `D3`, `E5`, `A1`.
    * (You can type in lowercase; the game will convert it automatically).
* **Pass Turn:** Press `P`.
* **End Game:** The game ends when **both** players pass consecutively.

### ⚠️ Important Performance Tip
Because the game logic is written in BASIC, calculations for captures and scoring can take a moment.
* **Recommendation:** If you are playing on an emulator, it is highly recommended to **increase the emulation speed** (often called "Warp Mode" or "Turbo Speed"). This makes the move validation and scoring much faster.

## Game Rules
This implementation generally follows **Japanese Rules**:
1.  **Black** plays first.
2.  Stones are placed on the intersections of the grid.
3.  Stones are captured if they lose all their "liberties" (empty adjacent points).
4.  Territory is counted at the end of the game (empty points surrounded by a player).
5.  **Score** = (Territory Controlled) + (Prisoners Captured).

## Building from Source

If you want to modify the BASIC code (`test_go15.txt`) and create a new playable tape file, you can use the included `bas2tap` utility.
Read Instructions.txt for use.
