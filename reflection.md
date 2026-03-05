# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").
The game looked clean on the surface, but a bunch of bugs became apparent when I started playing, and opened the debug panel.
The hints point in the wrong direction
the 'new game' button will reset the attempts left, but the game over message doesn't leave, and I still can't play
When I have one attempt left, the website locks me out of guessing.
Attempts starts at 1, and updates 1 guess behind - score changes on the second guess.
Score seems to ping-pong in a range of 5 after a few guesses... Needs more investigation.
---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
I used Claude Code to fix my bugs.
My first attempt to fix the hint bug left the hints alternating between higher and lower despite LLM's confidence. It was a good fix in isolation, but not enough to fix the whole bug.
Upon describing this behaviour, and asking it if anything would change between guesses, it caught the modulo if-statement that was casting my result to a string. I verified it worked by playtesting, resulting in my first bug fixed.
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?
I would play-test the game to make sure my bugs were fixed. Most of these involved a fixed input, or an input of 1 to 12, where I would check the debug panel to make sure that my answers were going through correctly. I got the idea for 1 to 12 from AI, when I asked it for advice on testing the weird inconsistency in my submissions and the debug log.
---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
