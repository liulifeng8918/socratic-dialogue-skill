# Socratic Dialogue Skill

A Codex / Agent Skills-compatible skill for lightweight Socratic questioning in human-AI conversations.

It helps an AI assistant guide discovery with fewer, sharper questions instead of overwhelming the user with a questionnaire.

中文简介：这是一个用于人和 AI 对话的苏格拉底式提问 skill。它适合在做决策、检查假设、理清想法、学习主题时使用，让 AI 少问、问准、顺着用户的话往前推一步。

## Why This Exists

AI assistants often answer too quickly. That is useful for execution, but weak for reflection: the user's real question, assumptions, criteria, and risks may never get examined.

`socratic-dialogue` gives the assistant a reusable dialogue routine:

- Reframe the user's issue in one plain sentence before asking
- Ask one main question by default, with at most 1-2 helper questions
- Use nested numbering only when helper questions support one main question
- Follow the user's actual wording instead of asking generic "why" questions
- Summarize every few turns to avoid endless questioning
- When the user says "帮我总结" after a reflective dialogue, extract scattered conclusions, assumptions, evidence, open questions, and next steps
- Avoid triggering for coding, factual lookup, urgent answers, or direct execution
- Support both Chinese and English prompts
- No scripts, no network calls, no API keys; this is an instruction-only skill that is safe to inspect before use

## When To Use It

Use this skill when you want to:

- Think through a decision
- Challenge assumptions
- Clarify a vague idea
- Learn through guided questions
- Examine tradeoffs before acting
- Ask the assistant to "反问我", "帮我想清楚", or "challenge my assumptions"

Do not use it when you want a direct implementation, a factual lookup, an urgent answer, or a finished deliverable unless you explicitly want reflective questioning first.

## Example Prompts

```text
用苏格拉底式提问帮我想清楚是否要辞职。
```

```text
反问我，帮我检查这个创业想法的关键假设。
```

```text
Use Socratic questioning to help me evaluate this product strategy.
```

```text
帮我总结一下刚才对话里已经形成的结论。
```

## Install

For Codex user-wide use, copy the skill folder:

```text
skills/socratic-dialogue
```

to:

```text
$HOME/.agents/skills/socratic-dialogue
```

For repo-scoped use, copy it to:

```text
.agents/skills/socratic-dialogue
```

Restart Codex if the skill does not appear immediately.

## Compatibility

This skill uses the common `SKILL.md` directory format and has no runtime dependencies.

See [COMPATIBILITY.md](COMPATIBILITY.md) for usage notes for Codex, Kimi / Kimi Code, OpenClaw, Hermes Agent, WorkBuddy / CodeBuddy, Coze, and Doubao.

For tools that expect the skill root to contain `SKILL.md` directly, use:

```text
dist/socratic-dialogue
```

## Project Structure

```text
socratic-dialogue-skill/
  README.md
  COMPATIBILITY.md
  LICENSE
  skills/
    socratic-dialogue/
      SKILL.md
      agents/
        openai.yaml
  examples/
    decision-career-change.md
    dialogue-summary.md
    lightweight-direction-choice.md
    startup-assumption-check.md
    product-strategy.md
  dist/
    socratic-dialogue/
      SKILL.md
      agents/
        openai.yaml
```

## Feedback Wanted

This skill is intentionally small. The most useful feedback is practical:

- Which prompts triggered the skill correctly?
- Where did it ask too many questions?
- Where did it ask too few questions?
- Which questions felt generic instead of sharp?
- Did the response feel lightweight enough for a confused user?
- Did it avoid triggering when you wanted direct execution?

Please open an issue with your prompt, the assistant response, and what you expected instead.

## License

MIT
