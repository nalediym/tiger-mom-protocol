# How to build your own version

The rules in `skills/tiger-mom/SKILL.md` are mine. They probably will not work for you the same way. The transferable part is not the rules; it is the act of writing your own down.

What follows is the actual interview that produced tiger-mom: the questions an AI asked me, the prompts I used to drive the conversation, and what the AI was given access to. Run yourself through this with whatever AI assistant you use. Replace my project names with yours, my collaborators with yours, my failure modes with yours.

## The opening prompt

Open a session with your AI assistant and ask it to interview you about how you actually work. Specifically ask it to:

- look at your `~/Projects` folder so the questions are about real things
- look at your GitHub via the `gh` CLI so it has data about your commit cadence
- use psychology, not just workflow

The "use psychology" line is the one that mattered for me. Without it the AI asked workflow-only questions; with it, it asked me about my own behaviour.

## The questions to ask yourself

Lightly generalised so you can use them. Take your time on each one.

### How you actually work

1. **The abandonment moment and the merge gap.** When you stop working on something, what happens in that moment? Is it that a new shiny thing pulls you away, that you hit a boring or hard part, that you felt like you "got it" already, or something else? And when something is 80% done, what blocks the last 20% — perfectionism, uncertainty, forgetting, friction in the review or merge process?
2. **The thing that survived.** Pick a project you have actually stayed with. What makes that one different? What keeps you coming back?
3. **The late-night question.** When you work past your usual hours, is that your best work? Or is it "I should be sleeping but I cannot stop"? How do you feel about those sessions the next day?
4. **What does done feel like.** When you do finish something, what made that moment possible? What conditions were present?

### Why you actually work

5. **The collaborator factor.** When you build with someone else, what mix is it: wanting to impress them, wanting to build something together, the project genuinely exciting you on its own? When you work alone, is there a loneliness to it, or is it more fun because there is no pressure?
6. **The perfectionism trap.** When a PR sits unmerged, what is the actual sentence in your head?
7. **The honest tooling answer.** How much of your coding is you typing code versus you prompting an AI to write code? No judgment. The workflow you build needs to match how you actually work, not how you think you should.

### Designing the system

8. **The screenshot insight.** If an automated system captured proof your feature worked (screenshots, tests, a generated report), would that make it easier to hit merge?
9. **The smallest acceptable win.** What is the smallest thing you could do in a session that would let you say "okay, I did something real today"?
10. **The continuity question.** If your assistant wrote a session summary at the end of every working session, would you actually look at it next time, or would you start fresh anyway? This determines whether you build a continuity system or a fresh-start system.

The "tiger mom" metaphor came out as my answer to question 10. I did not plan it. I just typed what I wanted: *"I want this to be like my tiger mom: gently nudging me back to the thing I was supposed to finish."*

## The prompt that mattered most

Halfway through, when my answers were too short, I told the assistant to push harder: ask more psychology questions, help me find the answer that was already inside me. That single nudge unlocked a second round of questions that went much deeper. If your interview is staying surface-level, push back on the assistant the same way.

## The prompt that turned the interview into a system

Near the end, I asked: how will you remember this for next time? Will it go away?

That question turned a one-off conversation into a persistent skill. The assistant wrote the first protocol file to disk so the work would survive across sessions. If you stop at the interview, you have a useful conversation. If you write it down, you have a system you can edit.

## What the AI was given access to

The introspection is only as honest as the data the AI can look at. Specifically:

- **Filesystem inspection of `~/Projects`.** The AI read the names and structure of my actual projects, so the questions were about real things.
- **The `gh` CLI on my GitHub username.** It pulled real commit counts, hour-of-day distribution, day-of-week distribution, and the ratio of mine versus my collaborator's commits. The data was the diagnosis.
- **My own prior notes.** It found a `messages_to_self.md` file and the design notes from a previous abandoned project of mine, and used the language and ideas from those as raw material for the new protocol.

If you want a similar interview, give the AI similar access. The protocol you end up with will be as specific as the inputs you let the AI see.
