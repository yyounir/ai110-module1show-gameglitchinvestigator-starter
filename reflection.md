# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
The game ran normally the first time I was running it.
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").
  - Some of the bugs that I encountered was that entering a number higher than the target would instruct you to enter a number "higher" instead of entering a number lower than the target. Likewise, when enter a number lower than the target, would instruct the user to enter a number lower than the target.
  - When entering a number lower than 1 or higher than 100, the game would continue to run normally but doesnt instruct the user to enter a number within the range
  - Clicking on the "New Game" button only works when you havent beaten the game yet, so if you lose or win the game, you can't play it again. You can only play a new game when you havent finished it.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| Entered "1" or any appropriate number below the target | "Go higher" | "Go lower!" | none |
| Entered "100" or any appropriate number above the target | "Go Lower!" | "Go higher!" | none |
| Clicked "New Game" | The game is expected to allow the user to guess a different number | Game is unplayable despite winning or losing, making the button itself useless | none |

- The program runs as expected when I guess the number correctly
--- 

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.

- I used Claude Code for this project to help me debug the errors that the other AI model made.
- One AI suggestion that was correct was to ask the AI why the error is happening in the first place before asking it to debug, that way, I would understand what exactly is going on with the program at I was entering the numbers trying to guess the answer wihtin the attempts
- An example of an AI suggestion that I didnt accept and had to ask again was when I noticed the AI changing the pytest cases which the app was running normally but the assertions wouldnt pass. For example, one such assertion was when the guess is 50 however the program outputted "Go Higher" instead of "You win".
- The game runs normally as expected now, with the correct hints that doesnt lead the player to nowhere, making it easier to win
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

- I found out the bug was fixed when I entered the maximum value "100" and it outputs "GO LOWER", correctly indicating that the guess above the correct answer work
- Another bug that was fixed when entering "1" which is the lowest value within the range, and it outputs "GO HIGHER" correctly indicating the guess below the correct answer works
- The AI helped me understand the tests and what was going on because it was to prepare me and make sure what the code actually does to prevent me from producing bad output that wouldnt pass assertions
- Using pytest, I made the guess 50 and tested any value above 50 and below 50 to make sure that the output is showing as expected, which had worked.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- Streamlit is like a program that acts as a whiteboard, every time your program reruns, someone erases the whole thing and redraw it from top to bottom. It reruns your whole script on every interation, and ession state is the memory that survives those reruns so your app wont crash.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
- One habit that I need to reuse is to be more descriptive with the AI chatbot so that I would narrow down on my requests, after that, I would ask follow up questions if I'm confused about that code that is outputted.
- One thing I needed to do next time would be to ask the AI about what a certain piece of code does and how it functions.
- This project made me think about AI generated code is that the code wont always be right and it is imported to look after the code and  monitor the AI code generation closely to avoid syntax errors.