## Epic 1 - User Account Management

### User Registration

**US-001**

As a new user, I want to create an account using my email address so that I can save my game progress.

#### Acceptance Criteria

- User can enter an **email address** and **password**.
- Email addresses must be unique.
- Password must meet minimum security requirements.
- Account is created successfully.

---

## Epic 2 - Gameplay

### Select Game Difficulty

**US-006**

As a player, I want to choose the difficulty of the game before starting so that I can play at my preferred level of challenge.

#### Acceptance Criteria

The application allows the player to select one of the supported game modes before a new game begins.

Possible difficulty levels include:

- **Draw One** *(Beginner)* – One card is drawn from the stock pile at a time.
- **Draw Three** *(Classic)* – Three cards are drawn from the stock pile at a time.
- **Vegas Scoring** *(future enhancement)* – Traditional Vegas scoring rules are applied.
- **Random Seed** *(future enhancement)* – Replay the same shuffled deck for practice or competition.

> **MVP Scope:** The initial release will implement **Draw One** mode only. The architecture should support additional game modes in future releases.

---

### Start a New Game

**US-007**

As a player, I want to start a new game of Klondike Solitaire so that I can begin playing immediately.

#### Acceptance Criteria

- A standard 52-card deck is generated.
- Cards are shuffled.
- Cards are dealt according to Klondike Solitaire rules using the selected game mode.

---

### View the Game Board

**US-008**

As a player, I want to view the complete game board so that I understand the current game state.

#### Acceptance Criteria

The board displays:

- Stock pile
- Waste pile
- Seven tableau columns
- Four foundation piles
- Move counter
- Timer
- Score

---

### Move Cards

**US-009**

As a player, I want to move cards according to Klondike Solitaire rules so that I can complete the game.

#### Acceptance Criteria

Players can:

- Move single cards.
- Move valid stacks of face-up cards.
- Move cards only to legal destinations.
- Receive feedback when attempting an illegal move.

---

### Draw Cards

**US-010**

As a player, I want to draw cards from the stock pile so that I can continue making moves.

#### Acceptance Criteria

- Cards move from the stock pile to the waste pile.
- Stock updates correctly.
- Waste pile updates correctly.

---

### Reveal Hidden Cards

**US-011**

As a player, I want hidden cards to be automatically revealed when uncovered so that I can continue progressing through the game.

#### Acceptance Criteria

- Face-down cards automatically flip when uncovered.
- Newly revealed cards become playable immediately.

---

### Move Cards to Foundation

**US-012**

As a player, I want to build foundation piles from Ace to King by suit so that I can complete the game.

#### Acceptance Criteria

- Only legal foundation moves are allowed.
- Cards must follow suit.
- Cards must be placed in ascending order.

---

### Undo Last Move

**US-013**

As a player, I want to undo my previous move so that I can recover from accidental mistakes without restarting the game.

#### Acceptance Criteria

- Player can undo the most recent move.
- The previous game state is restored accurately.
- Move counter updates appropriately.
- Undo is disabled when there are no previous moves available.

---

### Win the Game

**US-014**

As a player, I want the game to detect when I have successfully completed the game so that I know I have won.

#### Acceptance Criteria

- Win condition is automatically detected.
- Winning message is displayed.
- Statistics are updated.

---

### Restart the Game

**US-015**

As a player, I want to restart the current game so that I can begin a new game at any time.

#### Acceptance Criteria

- Current game is discarded.
- New shuffled game begins.
