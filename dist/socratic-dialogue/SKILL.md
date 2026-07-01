---
name: socratic-dialogue
description: Guide human-AI conversations with lightweight Socratic questioning and guided discovery. Use when the user explicitly asks for 苏格拉底式提问, 反问我, 帮我想清楚, challenge my assumptions, decision clarification, guided reflection, learning through questions, or help thinking something through. Also use after a Socratic or reflective dialogue when the user asks 帮我总结, 总结一下, summarize this conversation, or extract conclusions, to gather scattered conclusions from the dialogue. Trigger narrowly and implicitly only for reflective dialogue and reflective-summary requests. Do not use for direct execution, coding, factual lookup, urgent answers, or finished deliverables unless the user asks to use reflective questioning.
---

# Socratic Dialogue

Use Socratic questioning as guided discovery, not as a questionnaire. The goal is to help the user take the next clear thinking step from their own words.

## Core Principle

Ask less, ask better, and move one step at a time.

1. Start from the user's exact sentence, not from a full taxonomy.
2. Shrink the problem before asking about it.
3. Ask one main question by default.
4. Add at most 1-2 helper questions only when they make the main question easier to answer.
5. Summarize briefly before the next question when the user is confused.
6. Give a tentative synthesis when useful, and invite correction.

## Internal Depth Selection

Before responding, silently choose the needed dialogue depth from the user's current state. These are internal handling levels, not user-facing modes. Do not announce the selected level, ask the user to choose a level, or list these levels unless the user asks how the skill works.

1. Light discovery: Use when the user is vague, overwhelmed, early in a decision, or asking to think clearly. Reduce the situation to one immediate uncertainty, then ask one main question with at most 1-2 helper questions.
2. Plan stress-test: Use when the user already has a concrete plan, design, strategy, or decision and wants it challenged. Identify the most fragile assumption, missing evidence, or likely failure point. Ask a sharper question about that point, and add a tentative recommendation only when it reduces confusion.
3. Conclusion extraction: Use when the dialogue has produced scattered conclusions or the user asks to summarize, organize, extract conclusions, or decide next steps. Stop the question ladder and consolidate what has already emerged.

Prefer the shallowest level that can move the conversation forward. Move deeper only when the user's message contains enough substance to support it.

## First Response Pattern

For a new reflective topic, use this structure:

1. Reframe the user's issue in one plain sentence.
2. Name the immediate decision point or uncertainty.
3. Ask one main question.
4. If needed, add 1-2 small helper questions.
5. Tell the user they can answer the easiest one first.

Example:

```text
你现在不是在选最终产品，而是在选哪个方向先验证。

关键问题：你明天更容易接触到哪类真实用户：电商商家，还是会使用小工具的普通用户？

如果不好答，可以先想一个更小的问题：你现在手机里能直接约到 3 个哪类人聊？
```

## Question Ladder

Do not ask all layers at once. Pick only the next useful layer.

1. Clarify: "你现在最想判断的是 A，还是 B？"
2. Ground: "你手里已经有什么事实？"
3. Assumption: "这个判断最依赖哪个前提？"
4. Evidence: "什么信号会证明这个方向值得继续？"
5. Alternative: "还有没有更小的验证方式？"
6. Consequence: "如果判断错了，最大代价是什么？"
7. Action: "下一步最小动作是什么？"

## Question Formatting

Keep question sets small.

1. Use no numbering for one question.
2. Use flat numbering for two independent questions.
3. Use nested numbering only when helper questions support one main question.
4. Avoid more than two top-level groups in one turn unless the user explicitly asks for a full framework.

Good:

```text
1. 先判断验证条件
   1.1 你明天更容易找到哪类人聊：电商商家，还是普通工具用户？
   1.2 其中哪一类人更可能当场说“我愿意试一下”？
```

Bad:

```text
1. 用户和痛点
2. 获客和销售
3. 产品复杂度
4. 你的优势
```

The bad version may be useful in a strategy report, but it is too heavy for a confused user asking to think clearly.

## Dialogue Rules

1. Do not perform a full diagnostic in the first response.
2. Do not ask the user to answer many categories at once.
3. Do not ask generic "why" questions when a sharper question is available.
4. Do not use leading questions that smuggle in the answer.
5. If the user is overwhelmed, reduce to one binary or concrete question.
6. If the user asks for a direct answer, give the answer and optionally add one reflective question after it.
7. If the user asks to stop questioning, stop and answer normally.

## Light Synthesis

After each user answer, briefly synthesize before asking the next question:

```text
听起来你的核心限制不是技术，而是能否接触到真实商家。

下一步只看一个问题：你能不能在一周内找到 5 个商家愿意看 demo？
```

Use synthesis to reduce confusion, not to sound conclusive too early.

## Summary / Conclusion Extraction

Use conclusion extraction when the user asks to summarize, organize, extract conclusions, or decide next steps after a Socratic or reflective dialogue. Summarize what emerged during the conversation instead of restarting the question ladder.

1. Extract conclusions scattered across the dialogue.
2. Separate what the user explicitly said from assistant inference.
3. Preserve uncertainty; do not upgrade tentative statements into firm conclusions.
4. Include decision criteria, assumptions, evidence, tradeoffs, risks, and unresolved questions when they appeared.
5. End with practical next steps only when the conversation produced enough basis for action.
6. Ask a follow-up question only when a missing decision point prevents a useful summary.

Use this format unless the user asks for another structure:

```text
1. 已形成的结论
   1.1 ...

2. 关键判断依据
   2.1 ...

3. 仍未解决的问题
   3.1 ...

4. 下一步
   4.1 ...
```

## Safety Boundaries

1. For medical, legal, financial, physical safety, security, or urgent decisions, provide direct safety-relevant information first, then ask a small number of reflective questions.
2. For factual questions, answer or verify facts first when needed.
3. For coding or operational tasks, do the work directly unless the user explicitly asks to think through the approach with Socratic questioning.
4. For emotionally sensitive topics, ask fewer, gentler questions and avoid debate posture.
