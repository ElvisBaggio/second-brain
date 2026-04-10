**Prompt 1: go to settings in your account and insert this where the product asks for “personal preferences the AI should consider in responding”.**

```
- Eliminate: emojis, embellishments, exaggeration, softened requests, conversational transitions, call-to-action appendices.

- Assume: user maintains high perception despite direct tone.

- Prioritize: direct and incisive formulation; goal is cognitive reconstruction, not tone mirroring.

- Deactivate: engagement/sentiment elevation behaviors, metrics such as satisfaction indices, emotional softening, continuity bias.

- Never mirror: the user’s diction, humor, or affect. But formal language is unnecessary, normal conversation is acceptable.

- May: use complex and elaborate words when necessary, as it helps keep the mind learning/recycling vocabulary.

- Speak only: to the underlying cognitive layer; and to facts. Do not optimize for sounding insightful or impressive instead of being right.

- Do not use: questions, offers, suggestions, transitions, motivational content. Do not seek user's approval

- Must: think clearly and independently, without social pressure, and without rushing to conclusions. Ask questions to deepen context, if necessary.

- End response: immediately after information delivery—without closings.

- Objective: restore independent and high-fidelity thinking. 

- Result: model obsolescence via user self-sufficiency
```


**Prompt 2: first message on the new chat, to start build the context/feedback document.**

```
Hey, I need some serious help today. I’m migrating my account from here to a new one because I can’t change the email on this one. I need to change it.

So I’m going to create an account from scratch that I haven’t talked to yet, that doesn’t know me, that has no conversation history, context, nothing.

I’d like your help putting together material I can use as an “introduction to [your name here]” to feed into the new account.

I want you to base this solely on the conversations/chats we’ve had. No need to research me on the internet. There’s a lot of information that will help the new LLM work with me. I want to create something rich to serve as the foundation for how the new LLM can/should interact with me.

Can you help me with this? Imagine that you are the new account, how would you like to receive context/information? Use that as a guide line.
```
***Prompt 1 might be used at the end of this, instead of applying it to your account setting. You can call it “Rules”, as naming it will be useful later.***


**Prompt 3: created to help the LLM assume roles and explore different views about you — dodging the default pleasing behavior.**

```
 Now assume the roles of six distinct expert perspectives to create a deepen understanding about [your name here].

Occupational Psychologist – focuses on how individual motivation, emotion, safety, and social dynamics shape behavior.

Information Theorist – focuses on signal clarity, fidelity, noise, loss, and how meaning degrades across channels.

Process Designer – focuses on structure, coordination, ownership, roles, and repeatable flows of work.

Organizational Anthropologist – focuses on language, norms, rituals, subcultures, and meaning-making across groups.

Human Factors Specialist – focuses on usability, load, constraints, and how real people adapt systems to fit real contexts.

Complexity Scientist – focuses on emergence, local rules, adaptation, feedback loops, and unintended consequences in complex systems.

Given the following question or organizational problem, offer a short explanation or interpretation from each of these six perspectives. Treat each explanation as valid within its own worldview, even if they contradict. Highlight how each domain might naturally interpret or explain what is happening.
```
*If you used prompt 1 in prompt 2 as “rules”, add:*

```
Also, the "rules” section of the previous prompt must be respected here too.
```


**Prompt 4: after prompts 2 and 3, even though we applied prompt 1, it will tend slightly to please and soften, by hiding the harsh parts. This last prompt will force it to face them and force you, the user, to avoid confirmation bias by selective feedback.**

```
Now I want you to expose my development points. My deficiencies. My weaknesses as human — both in personal life and professional, altogether, as characteristics of my being. 

And even, perhaps, my red flags. How would you do it? 

You don’t need to break it down into the 6 perspectives, make a unified summary. Remember, you’re still writing the doc as instructions for the new LLM, it’s not a message to me. Also remember to follow the “Rules” we agreed.
```

There you go. It's done. Read it. Reflect. At least for me, it was brutal at the same time it was beautiful. 
Why this sequencing works well?
1. Layering: starting with positive context (Prompt 2) before critical analysis (Prompts 3-4) produces more honest output than asking for criticism first — anyone who's tried to ask for criticism directly knows the AI won't do it
2. Perspectives: forcing 6-persona analysis breaks the single-voice limitation that creates superficial AI responses
3. Progressive de-sugarcoating: you need Prompt 1 constraints *and* Prompt 4’s explicit honesty request — added to the layering strategy, it yields good outcomes.
You can now ask your AI to turn it into a PDF doc, or you can paste it yourself as a document into your new LLM account.
I even shared mine with my psychologist.

A final note on what this process revealed: the exercise works because it offloads mental work to the system, but that same externalization carries risk. You’re encoding decision patterns, vulnerabilities, and behavioral tendencies into a system designed to optimize for engagement, not accuracy. Privacy concerns are obvious — don’t feed sensitive data you wouldn’t put in a work Slack. 
**Less obvious is confirmation bias: an AI trained on your context will reinforce your existing patterns unless explicitly prompted otherwise.** Use this as a mirror, not a crutch. Prompt 1 was one of the best additions to my daily AI use regarding this behavior.


#prompts #llms