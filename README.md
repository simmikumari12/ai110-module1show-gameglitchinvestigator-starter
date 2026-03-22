# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- 🎯 Purpose of the Game
The game is a number guessing game where the user tries to guess a randomly generated number within a limited number of attempts. The game provides hints (higher/lower) and tracks score and history.

- 🐞 Bugs Found
Reversed hint logic: The game told users to go LOWER when the guess was already lower than the secret number
Type inconsistency bug: The secret number was sometimes treated as a string, causing incorrect comparisons
Attempts mismatch: UI attempts and internal attempts were inconsistent
Score issues: Score could go negative and did not reward correct guesses properly
State reset bug: New game did not reset score, history, or status
Unclear history format: Guess history was difficult to read

- 🔧 Fixes Applied
Fixed hint logic to correctly guide the player (higher/lower)
Removed string conversion of the secret number to ensure consistent comparisons
Initialized attempts correctly and fixed UI display
Updated scoring logic to prevent negative scores
Reset all session state variables when starting a new game
Improved history formatting for better readability
Refactored all core logic into logic_utils.py for better structure and testability

## 📸 Demo

- C:\Users\Simmi\ai110-module1show-gameglitchinvestigator-starter\winning_game_screenshot.png 

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]
