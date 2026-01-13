# Cinematic Mafia • Social Deduction Game

A single-file, offline-first web application for playing **Mafia** (also known as Werewolf). This project features a cinematic UI, atmospheric sound design, and an automated narrative engine that generates unique stories for every game phase—all contained within one HTML file.

> **🤖 AI Development Note:** This project was architected, coded, and debugged in collaboration with AI. 
> *   **Claude (Anthropic):** Primary logic generation, CSS styling, narrative engine, and bug fixing.
> *   **Gemini (Google):** Contextual search, planning, and tool integration.

---

## 🎲 How to Play

This app acts as the **Game Master (GM)**. You do not need a server or internet connection after loading the page.

### 1. Setup
1.  Open `mafia_game.html` on a shared device (tablet, laptop, or phone).
2.  **Game Master:** Enter the names of all players (5-12 people).
3.  Select a **Scene** (e.g., *Noir City, Space Station, Haunted Manor*) to set the visual theme and story flavor.
4.  Click **Create Game**.

### 2. Role Reveal
The device is passed around (or players approach the screen one by one).
*   **Player taps their name.**
*   The screen reveals their secret role (Mafia, Doctor, Detective, or Villager).
*   Player taps "Continue" to hide the role before the next person looks.

### 3. The Loop
*   **Night Phase:** The app asks for actions. The device is passed to specific roles (Mafia to kill, Doctor to save, Detective to investigate).
*   **Day Phase:** The app narrates what happened (e.g., *"Bob was found in the alley..."*). Players discuss and debate.
*   **Voting:** Players vote on who to eliminate.
*   **Repeat:** The cycle continues until the Village wins (all Mafia gone) or Mafia wins (Mafia outnumber Villagers).

### 🔗 Rules of Mafia
New to the game? [Read the official rules on Wikipedia](https://en.wikipedia.org/wiki/Mafia_(party_game)).

---

## 📱 Supported Devices

This application is responsive and works on any modern web browser.

*   **Smartphones (iOS/Android):** Optimized for touch. Great for passing around during the "Night" phase.
*   **Tablets (iPad/Android):** The ideal form factor for the "Game Master" board.
*   **Laptops/Desktops:** Best if you want to cast the screen to a TV for the "Day" phase narration.

**Browser Compatibility:** Chrome, Safari, Edge, Firefox.

---

## 💻 Technologies Used

This project was built with a philosophy of "Zero Dependencies"—everything needed to run the game is contained in a single text file.

*   **HTML5:** Semantic structure and single-file architecture.
*   **CSS3:** Advanced styling using CSS Variables, Glassmorphism (backdrop-filter), Grid/Flexbox layouts, and keyframe animations.
*   **JavaScript (ES6+):** Core game logic, state management, and narrative generation.
*   **Web APIs:**
    *   `localStorage`: Persists game state across page reloads and crashes.
    *   `AudioContext`: Generates real-time sound effects (synthesized beeps and tones) without needing external mp3 files.
*   **SVG:** All icons and background graphics are inline Scalable Vector Graphics, keeping the file size small and resolution-independent.

---

## 🛠 Development Journey

**Total Development Time:** ~1 Hour

This project serves as a case study in rapid AI-assisted prototyping. We moved from a concept to a polished, bug-free application in a very short timeframe.

### Iteration History
1.  **MVP Logic:** Established the core `Game` object, role randomization, and the `localStorage` state management to ensure the game survives page reloads.
2.  **Cinematic UI:** Replaced standard HTML buttons with a CSS-heavy, translucent "Glassmorphism" design, adding dynamic SVG backgrounds and vector icons.
3.  **Narrative Engine:** Implemented a string-template system that changes the story text based on the selected scene (e.g., "A airlock opens" in Space vs. "A gunshot in the rain" in Noir).
4.  **Debugging:** identified and fixed a critical bug where player names containing quotes (e.g., "O'Reilly") broke the inline JavaScript handlers.

### Test Plan
To ensure stability without a backend, we used the following testing strategy:
*   **Input Sanitization Test:** Deliberately inputting "Nasty" strings (names with `'`, `"`, `<`, `>`) to ensure the `JSON.stringify` patch prevented code injection or crashes.
*   **State Persistence:** Reloading the browser tab in the middle of a "Night" phase to verify the game resumed exactly where it left off.
*   **Win Condition Logic:** Simulating games where Mafia equals Villagers (Mafia Win) and games where all Mafia die (Village Win) to ensure the Game Over screen triggers correctly.
*   **Browser Console Self-Test:** A custom hook `window.mafiaSelfTest()` was injected to verify all DOM elements exist before the game starts.

---

## 📥 Installation

1.  Download the `mafia_game.html` file.
2.  Double-click it to open in your default browser.
3.  Enjoy!
