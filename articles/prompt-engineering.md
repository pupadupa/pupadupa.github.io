---
layout: default
title: Prompt Engineering
---

[Home](../index.md) > Prompt Engineering

<div class="article-meta">
Published: July 3, 2025 | Last updated: July 4, 2025
</div>

**Contents**  
- [Why It Matters](#why-it-matters)
- [Prompt Patterns That Work](#prompt-patterns-that-work)
    - [Zero-shot](#zero-shot)
    - [Few-shot](#few-shot)
    - [Chain-of-Thought (CoT)](#chain-of-thought-cot)
    - [Role Prompting](#role-prompting)
    - [Self-Consistency](#self-consistency)
    - [Structured Output](#structured-output)
- [Tips That Actually Help](#tips-that-actually-help)
- [Useful Resources](#useful-resources)

---

## Why It Matters

Prompting is interface design. You’re not “talking to AI,” you’re shaping its behavior.  
Structure and clarity matter more than cleverness. Good prompts reduce noise, bias, and hallucination.  
Great prompts make the model feel smarter than it is.

---

## Prompt Patterns That Work

### Zero-shot

Straight instruction. No context. Works best on tight, common tasks.

```
Classify the sentiment: “The new design is frustrating.”
```

---

### Few-shot

Priming with examples. Model finishes the pattern.

```
Text: “The UI is amazing”  
Sentiment: Positive

Text: “The onboarding was confusing”  
Sentiment: Negative

Text: “The performance is decent”  
Sentiment: ?
```

Use when tone or logic is fuzzy and you want to anchor behavior.

---

### Chain-of-Thought (CoT)

Force step-by-step thinking. Turns the model from autocomplete into problem solver.

```
Q: A shop sells pens at 3 for $1. How much for 12 pens?

Let’s break it down:  
- 3 pens = $1  
- 12 pens = 4 sets → 4 x $1 = $4
```

Use for math, logic, planning, troubleshooting — anything with intermediate steps.

---

### Role Prompting

Assign a persona to steer tone, depth, and framing.

```
You are a senior ML engineer. Critique this prompt for reliability and edge cases.
```

Obvious, but still underrated.

---

### Self-Consistency

Ask the model to approach the problem multiple ways, then reconcile.

```
Give three solutions. Then pick the most robust one.
```

Useful for open-ended reasoning and reducing flukes.

---

### Structured Output

Force the model to respond in a predictable format — especially useful when parsing responses programmatically.

> Summarize the following user feedback and return JSON with keys: "sentiment", "topics", and "summary".
>
> Feedback: "The search is fast, but the results aren't always relevant."
>
> Return format:
>
> ```
> {
>   "sentiment": "mixed",
>   "topics": ["search speed", "result relevance"],
>   "summary": "Fast search, but relevance could be better."
> }
> ```


Use when you want the output clean, extractable, and machine-readable. Works well in toolchains, API calls, and eval loops.

---

## Tips That Actually Help

- **Tell it what format you want**  
  Markdown, JSON, checklist, TL;DR — be specific.

- **Don’t cram everything into one sentence**  
  Break down complex tasks. Step-by-step isn’t just for CoT.

- **Use system prompts well (if available)**  
  Set behavior up front: tone, rules, limits.

- **Add failure mode guardrails**  
  E.g. “If unsure, say ‘I don’t know.’” This alone cuts hallucination.

- **Iterate and test**  
  Minor prompt changes = major outcome shifts. Tweak ruthlessly.

---

## Useful Resources

- [promptingguide.ai](https://www.promptingguide.ai/) — Solid overview with examples  
- [OpenAI Cookbook](https://github.com/openai/openai-cookbook) — Real-world prompts, API-ready  
- [Learn Prompting](https://learnprompting.org/) — Good if you want to teach others  
- [Anthropic: Constitutional AI](https://www.anthropic.com/constitutional-ai) — How to nudge models toward safer outputs  
- [Microsoft Prompt Engineering](https://microsoft.github.io/prompt-engineering/) — Patterns used at scale

