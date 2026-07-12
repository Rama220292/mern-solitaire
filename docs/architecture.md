# Architecture

## 1. Purpose

This document describes the overall architecture of the **MERN Solitaire** application. It provides a high-level overview of how the frontend, backend, database, and external services interact to deliver a secure and responsive Klondike Solitaire experience.

The objective of this document is to define the application's structure before implementation begins, ensuring that development follows a clear and maintainable architecture.

---

# 2. Functional Overview

The application consists of three primary functional areas.

## Gameplay

* Play a complete game of Klondike Solitaire.
* Follow the standard Klondike Solitaire rules.
* Move cards between tableau columns.
* Build foundation piles from Ace to King by suit.
* Draw cards from the stock pile.
* Automatically reveal face-down cards.
* Detect game completion.
* Track moves, elapsed time, and score.

## User Management

* Register a new account.
* Verify account ownership through email authentication.
* Log in securely.
* Reset forgotten passwords through email.
* Maintain authenticated user sessions using JSON Web Tokens (JWT).

## Game Persistence

* Save an unfinished game.
* Resume previously saved games.
* Store player statistics.
* View historical performance.

---

# 3. High-Level Architecture

The application follows a traditional three-tier architecture.

```text
                Internet
                    │
      ┌─────────────┴─────────────┐
      │                           │
   Netlify                    Render
(React Frontend)         (Express Backend)
                                  │
                           MongoDB Atlas
```

### Frontend

* Built using React and Vite.
* Hosted on Netlify.
* Responsible for rendering the user interface and communicating with the backend API.

### Backend

* Built using Express and Node.js.
* Hosted on Render.
* Responsible for authentication, game management, and data persistence.

### Database

* MongoDB Atlas stores user information, saved games, and player statistics.

---

# 4. System Components

## React Frontend

### Responsibilities

* Render the game interface.
* Manage client-side state.
* Handle drag-and-drop interactions.
* Communicate with backend APIs.
* Display authentication screens.
* Display player statistics.

---

## Express Backend

### Responsibilities

* Expose REST API endpoints.
* Authenticate users.
* Validate requests.
* Manage game data.
* Send authentication and password reset emails.
* Communicate with MongoDB.

---

## MongoDB

### Responsibilities

* Store user accounts.
* Store saved games.
* Store player statistics.

---

## Netlify

### Responsibilities

* Host the frontend application.
* Deploy automatically from GitHub.

---

## Render

### Responsibilities

* Host the backend API.
* Connect securely to MongoDB Atlas.
* Manage environment variables.

---

# 5. Frontend Architecture

The frontend is organised into reusable React components.

```text
App
│
├── Routes
│
├── Pages
│   ├── Login
│   ├── Register
│   ├── Game
│   └── Profile / Statistics
│
├── Components
│   ├── Card
│   ├── Tableau
│   ├── Foundation
│   ├── Stock
│   ├── Waste
│   ├── Header
│   └── Timer
│
└── Services
    └── API Client
```

Each component should have a single responsibility and remain reusable wherever possible.

---

# 6. Backend Architecture

The backend follows a layered architecture.

```text
Client Request
        │
        ▼
     Routes
        │
        ▼
   Controllers
        │
        ▼
    Services
        │
        ▼
     Models
        │
        ▼
    MongoDB Atlas
```

Separating responsibilities into layers improves maintainability, readability, and scalability.

---

# 7. Game Engine Architecture

The game engine manages all Klondike Solitaire logic independently of the user interface.

Its responsibilities include:

* Generate and shuffle a standard 52-card deck.
* Deal cards according to Klondike Solitaire rules.
* Validate legal moves.
* Manage the tableau, stock, waste, and foundation piles.
* Reveal hidden cards when appropriate.
* Detect game completion.
* Maintain the current game state.

The frontend is responsible for rendering the game state, while the game engine determines whether player actions are valid.

---

# 8. Database Architecture

The application initially consists of three primary MongoDB collections.

## Users

Stores:

* User profile
* Email address
* Password hash
* Email verification status

## Saved Games

Stores:

* Current game state
* Stock pile
* Waste pile
* Foundation piles
* Tableau
* Timer
* Move count
* Score

## Statistics

Stores:

* Games played
* Games won
* Win percentage
* Fastest completion time
* Average completion time

The detailed schema for each collection is documented in `database-schema.md`.

---

# 9. Authentication Flow

Authentication follows a standard email verification workflow.

```text
Register
    │
    ▼
Backend validates user
    │
    ▼
Verification email sent
    │
    ▼
User clicks verification link
    │
    ▼
Account activated
    │
    ▼
Login
    │
    ▼
JWT issued
    │
    ▼
Authenticated API requests
```

Password resets follow a similar process using secure, time-limited reset tokens delivered via email.

---

# 10. Data Flow

Typical gameplay follows this sequence.

```text
Player Action
      │
      ▼
React updates UI
      │
      ▼
Game Engine validates move
      │
      ▼
Game state updated
      │
      ▼
(Optional)
Save Game
      │
      ▼
Backend API
      │
      ▼
MongoDB Atlas
```

Only authenticated users can persist game data.

---

# 11. Project Structure

```text
mern-solitaire/

├── docs/
├── frontend/
├── backend/
├── README.md
├── LICENSE
└── .gitignore
```

* **docs/** contains project documentation and design artefacts.
* **frontend/** contains the React application.
* **backend/** contains the Express API and database logic.

---

# 12. Design Decisions

| Decision           | Rationale                                                                                            |
| ------------------ | ---------------------------------------------------------------------------------------------------- |
| MERN Stack         | Uses JavaScript across the full application, simplifying development and reducing context switching. |
| React              | Enables a reusable, component-based user interface suitable for interactive games.                   |
| Vite               | Provides fast development and efficient production builds.                                           |
| MongoDB            | Stores complex game state naturally using document-based data structures.                            |
| Express            | Lightweight framework for building RESTful APIs.                                                     |
| JWT Authentication | Provides secure, stateless authentication for API requests.                                          |
| Netlify            | Hosts the frontend with automatic deployments from GitHub.                                           |
| Render             | Hosts the backend with straightforward deployment and environment variable management.               |

---

# 13. Future Architecture Considerations

Potential future enhancements include:

* Daily Challenge mode
* Achievement system
* Leaderboards
* Multiple visual themes
* Sound effects
* Hint system
* Undo functionality
* Progressive Web App (PWA)
* Automated testing
* CI/CD pipeline
* Docker containerisation
* Real-time multiplayer support

These features are outside the scope of the initial MVP but have been considered when designing the overall architecture.
