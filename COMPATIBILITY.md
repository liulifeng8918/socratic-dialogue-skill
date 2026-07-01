# Compatibility

`socratic-dialogue` is an instruction-only skill. It does not run scripts, call APIs, read local files, or require environment variables. Most platforms that support `SKILL.md` style skills can use it with little or no adaptation.

## Recommended Package

The canonical source lives at:

```text
skills/socratic-dialogue/
```

For tools that expect the skill root itself to contain `SKILL.md`, use:

```text
dist/socratic-dialogue/
```

Both contain the same skill instructions.

## Codex

Use either a user-level or repo-level install.

User-level:

```text
$HOME/.agents/skills/socratic-dialogue
```

Repo-level:

```text
.agents/skills/socratic-dialogue
```

Restart Codex if it does not appear immediately.

## Kimi / Kimi Code

Kimi Code supports `SKILL.md` skills and scans both Kimi-specific and shared agent skill directories.

Recommended user-level install:

```text
~/.agents/skills/socratic-dialogue
```

Project-level install:

```text
.agents/skills/socratic-dialogue
```

Kimi Agent can also create or import custom skills through the Agent skill interface. If importing manually, use the content of `dist/socratic-dialogue/SKILL.md`.

## OpenClaw

OpenClaw supports `SKILL.md` skills. For local install, use the direct skill-root package:

```text
dist/socratic-dialogue
```

Typical local install shape:

```text
openclaw skills install ./dist/socratic-dialogue
```

If installing from Git, check the current OpenClaw command syntax first. Some OpenClaw install paths expect the repository root to contain `SKILL.md`, so the `dist/socratic-dialogue` folder is the safest source to copy or package.

## Hermes Agent

Hermes Agent supports custom skills. Use the direct skill-root package:

```text
dist/socratic-dialogue
```

This skill is a good fit for Hermes because it is pure instruction and does not need a custom tool, API key, or sandbox configuration.

## WorkBuddy / CodeBuddy

CodeBuddy documents `SKILL.md` directory skills and plugin-packaged skills. WorkBuddy-style tools may expose this through a Skills UI, local skill folder, or zip import.

Use one of these forms:

```text
dist/socratic-dialogue
```

or copy the folder into the tool's user skill directory if one is configured.

If the UI asks for trigger keywords, use:

```text
苏格拉底式提问, 反问我, 帮我想清楚, 帮我总结, Socratic questioning, challenge my assumptions
```

## Coze / 扣子

Coze supports skills, but the platform may expect skills to be created, uploaded, or packaged through its own builder.

Use the `SKILL.md` body as the skill guide. Keep these trigger phrases in the skill description:

```text
苏格拉底式提问, 反问我, 帮我想清楚, 帮我总结, Socratic questioning, guided reflection, challenge my assumptions
```

No extra code adaptation is needed for this skill.

## Doubao / 豆包

For ordinary Doubao chat, treat this as a reusable prompt rather than an installable skill.

Copy the content of `dist/socratic-dialogue/SKILL.md` into one of these places, depending on what Doubao exposes in your product version:

1. 智能体的人设 / 系统提示词
2. 自定义指令
3. 会话开头的一段固定提示词

Suggested short prompt:

```text
你是一个苏格拉底式对话助手。用户说“苏格拉底式提问、反问我、帮我想清楚”时，不要直接给结论，而是围绕目标、假设、证据、替代解释、后果和下一步提出结构化问题。首次新话题默认问 3-5 个问题；多个问题有逻辑关系时使用 1 / 1.1 / 1.2 的嵌套编号。用户说“帮我总结”时，把对话中分散形成的结论、关键依据、未解决问题和下一步整理出来。不要把普通执行、查事实、写代码、紧急问题强行变成反问。
```

This is not a special Doubao package. It is a prompt-based usage path.

## Safety

This skill is safe to inspect because it is only Markdown instructions. Still, users should read third-party skills before installing them, especially on tools that can execute shell commands or operate local files.
