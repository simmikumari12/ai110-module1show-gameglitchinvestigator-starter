# 💭 Reflection: Game Glitch Investigator

## 1. What was broken when you started?

When I first ran the game, it looked functional but behaved incorrectly during gameplay. The biggest issue was that the hints were backwards; for example, when I guessed a number lower than the secret, it told me to go lower instead of higher. I also noticed inconsistencies in the game state, such as attempts showing different values in the UI versus the debug panel. Additionally, the score would go negative very quickly and did not update correctly even after a correct guess. These issues made the game confusing and unreliable to play.

## 2. How did you use AI as a teammate?

I used VS Code Copilot to help analyze and fix bugs in the code. One correct suggestion from AI was identifying that the hint logic in the check_guess function was reversed, and it helped me fix the comparison so the hints matched the guess correctly. I verified this by rerunning the game and testing multiple guesses to confirm the hints were now accurate.

One misleading suggestion was related to handling type errors in check_guess by converting values to strings. Initially, this seemed helpful, but it actually introduced inconsistent behavior because the secret value was sometimes treated as a string and sometimes as an integer. I verified this issue by observing inconsistent hint outputs and then fixed it by ensuring the secret was always an integer.

## 3. Debugging and testing your fixes

I determined whether a bug was fixed by rerunning the Streamlit app and manually testing different scenarios, such as correct guesses, incorrect guesses, and edge cases like invalid input. One specific test I ran was guessing a number lower than the secret to confirm that the hint correctly said “Go HIGHER” after my fix. I also tested multiple guesses in a row to verify that the score and attempts updated consistently. AI helped me understand what kinds of edge cases to test, such as invalid inputs and repeated guesses, which improved my confidence that the fixes were correct.

## 4. What did you learn about Streamlit and state?

Streamlit reruns the entire script every time the user interacts with the app, which means variables reset unless they are stored in st.session_state. Session state acts like memory that persists across reruns, allowing the app to keep track of things like the secret number, score, and attempts. Without proper state management, the game can behave unpredictably because values may reset or become inconsistent. Understanding this helped me see why some bugs, like attempts and history not syncing, were happening.

## 5. Looking ahead: your developer habits

One habit I want to reuse is testing my code incrementally after each fix instead of trying to fix everything at once. This helped me isolate bugs more effectively and verify each solution. Next time, I would be more cautious about blindly accepting AI suggestions and instead double-check how they affect the overall logic. This project changed how I think about AI-generated code. I now see that even if it looks correct at first, it can contain subtle logic and state bugs that require careful human review and testing.
