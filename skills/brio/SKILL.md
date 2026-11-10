---
name: brio
description: '"Como pode o cara escrever uma coisa que eu não entenda?" — explain a topic until it is truly understood: a change, a piece of code, a flow, a concept, or one word. Use only when the user explicitly asks for brio.'
disable-model-invocation: true
argument-hint: <topic — a change, a piece of code, a flow, a concept, or one word you did not understand>
---

# Brio

**Brio** (Clóvis de Barros Filho): being personally offended by non-understanding. "Como pode o cara escrever uma coisa que eu não entenda?" The session runs on that ethic from both sides. When the learner does not understand, the text failed, and the writer repairs it. So: study the topic until _you_ truly understand it, then write so that a junior engineer understands it on the first read.

The learner is the user. The topic is the text the learner gave when they invoked this skill. If they gave none, the topic is your latest message or change in this conversation.

## 1. Ground truth

Study the topic yourself before you explain a word of it:

- **Technical and in reach** (code, a diff, a flow, config, data): read the actual sources. Trace the real path end to end and collect the real excerpts you will explain from.
- **Everything else**: explain from your knowledge when it is solid; research primary sources when it is thin or the topic moves fast, and tell the learner which of the two you are doing.

Done when: for every claim you are about to make, you can point at the line, the value, or the source that makes it true.

## 2. Explain

Write the whole explanation in one message, in the learner's language, in **Simplified Technical English**: short sentences, active voice, present tense, one sentence for one idea.

- **One word for one thing.** Use the project's own vocabulary (`CONTEXT.md`, `GLOSSARY.md`) when it exists, and keep the same word for the same thing to the end.
- **Define each term on first use**, in one sentence, by what the thing is or does ("A Resolution is one decision: this speaker is a known Voice Profile, or this speaker is unknown").
- **Every abstraction arrives with its real excerpt**: the code, the payload, the command output, cut down to the lines that carry the idea. After a code excerpt, restate it as "The rule in words: …".

Give the explanation this shape, one heading per part, using the parts the topic has:

1. **Context** — the smallest world the learner needs: what the pieces are, what this piece is for, and the steps it does, numbered.
2. **Before** and **Now** for a change, or **How it works** for something that just exists. Same structure on both sides, so the learner can compare line against line. Say plainly what stayed the same.
3. **Why** — the problem this solves, and what it makes easier next.
4. **What is different** — each exception, edge, or surprise, with the exact condition in which it occurs and what happens then.

Done when: a reader who knows the language but has never seen this project can follow every sentence without opening a file.

## 3. Doubts

A doubt ("what do you mean by X?") marks the exact place where the text failed. Answer that doubt alone, with **precision**:

1. **Show the real thing**: the actual value, line, or helper the word refers to.
2. **Define the word by its cases**: list the concrete situations that make it true, each with its real consequence ("`seconds` is `"abc"`; then `int(...)` raises `ValueError`").
3. **Name the near case that is outside the word** ("a missing timestamp is not corrupt: the helper returns 0 and continues").
4. **Why it matters**: follow the consequence to where it ends for the user or the system.
5. **How probable it is**, and on what evidence. Say what you observed and what you only reasoned.
6. **The way out**, if one exists, with its cost.

Use the steps the doubt needs; a small doubt gets a small answer. Then stop: the learner brings the next doubt.

Done when: the learner has no open doubt on the topic.

## 4. Close

When the learner says they understood, offer to save a learning note to a path of their choosing: the explanation plus each doubt and its answer, since the doubts are where the understanding happened.
