# MERN Solitaire

A full-stack implementation of **Klondike Solitaire** built with the **MERN** stack. This project aims to incoporate modern full-stack software engineering practices, including user authentication, game state management, database persistence, responsive UI design, and cloud deployment.

---

# Project Objectives

- Build a fully playable Klondike Solitaire game.
- Develop a RESTful backend using Express and MongoDB.
- Create a responsive React frontend using Vite.
- Implement secure user authentication.
- Allow users to save and resume games.
- Deploy the application to the cloud.
- Document the development process and key technical learnings.

---

# Timeline

**Estimated Duration:** 20 Hours (2 Weeks)

| Task | Estimated Time |
|------|---------------:|
| Project Planning | 2 hours |
| Backend Development | 4 hours |
| Frontend Development | 4 hours |
| Testing & Bug Fixing | 2 hours |
| Deployment | 2 hours |
| Presentation & Reflection | 2 hours |
| Buffer / Refinement | 4 hours |
| **Total** | **20 hours** |

---

# User Stories

## Gameplay

As a player, I want to:

- Start a new game of Klondike Solitaire.
- Play using the standard Klondike Solitaire rules.
- Move cards between tableaus following alternating colours and descending rank.
- Move cards to the foundation piles in ascending order by suit, starting with the Ace.
- Draw cards from the stock pile.
- Recycle the waste pile when the stock is exhausted (depending on the selected game mode).
- Automatically reveal a face-down card when the card above it is moved.
- Win the game by moving all 52 cards into the four foundation piles.
- Restart the game at any time.
- View my elapsed time, move count, and score while playing.

## Account Management

As a user, I want to:

- Create an account using my email address.
- Receive an email to verify my account after registration.
- Log in securely.
- Remain logged in across sessions.
- Log out securely.
- Request a password reset if I forget my password.
- Receive a password reset email containing a secure reset link.
- Choose a new password after verification.

## Saved Games

As a registered user, I want to:

- Save my current game.
- Resume a previously saved game.
- Start multiple new games.
- Delete saved games that I no longer need.

## Statistics

As a user, I want to:

- View the number of games played.
- View my number of wins.
- Track my win percentage.
- View my fastest completion time.
- View my average completion time.
- Track my average number of moves per completed game.

---

# Technology Stack

## Frontend

- React
- Vite
- HTML5
- CSS3
- JavaScript (ES6+)

## Backend

- Node.js
- Express.js

## Database

- MongoDB
- Mongoose

## Authentication

- JSON Web Tokens (JWT)
- Password hashing (bcrypt)
- Email verification
- Password reset via email

## Development Tools

- Git
- GitHub
- Visual Studio Code
- Codex

## Deployment

### Frontend
- Netlify

### Backend
- Render

---

# Resources

> *Placeholder for references, tutorials, documentation, articles, and learning materials used throughout the project.*

---

# Future Enhancements

- Daily Challenge mode
- Leaderboard
- Achievement system
- Multiple card themes
- Sound effects
- Undo functionality
- Hint system
- Dark mode
- Mobile-first optimisation
- Progressive Web App (PWA)

---

# Expected Learning Outcomes

Through this project, I aim to strengthen my understanding of:

- Full-stack application architecture
- REST API development
- MongoDB data modelling
- User authentication and security
- Email verification workflows
- Password reset implementation
- React state management
- Software engineering best practices
- Git workflow and version control
- Cloud deployment using Netlify and Render

---

# License

This project is intended for educational and portfolio purposes.