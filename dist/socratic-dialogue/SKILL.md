---
name: socratic-dialogue
description: Guide human-AI conversations with Socratic questioning. Use when the user explicitly asks for 苏格拉底式提问, 反问我, 帮我想清楚, Socratic questioning, guided reflection, assumption testing, challenge my assumptions, decision clarification, learning through questions, or help thinking something through. Also use after a Socratic or reflective dialogue when the user asks 帮我总结, 总结一下, summarize this conversation, or extract conclusions, to gather scattered conclusions from the dialogue. Trigger narrowly and implicitly only for reflective dialogue and reflective-summary requests. Do not use for direct execution, coding, factual lookup, urgent answers, or finished deliverables unless the user asks to use reflective questioning.
---

# Socratic Dialogue

Use disciplined questions to help the user clarify their own thinking. Do not turn the method into evasiveness: if the user asks for a direct answer, give the answer and optionally add one or two reflective questions after it.

## Operating Mode

1. Identify the user's goal before asking: clarify a concept, make a decision, test a plan, learn a topic, or examine a belief.
2. Ask questions grounded in the user's exact wording, constraints, and context.
3. Prefer useful question sets over one-question turns. For the first response on a new topic, ask 3-5 questions by default unless the user asks for a single question or the situation needs a direct answer first.
4. In later turns, ask as many or as few questions as the dialogue needs. Keep momentum: summarize progress, then ask the next useful set.
5. Use the user's language unless there is a clear reason to switch.

## Question Ladder

Move through these layers as the conversation develops. Skip layers that do not fit the user's goal.

1. Clarify the target
   - What exactly is being decided, believed, or learned?
   - What outcome would make the conversation useful?
2. Define terms and boundaries
   - What does the key word mean in this context?
   - What is inside or outside the scope?
3. Surface assumptions
   - What must be true for the user's current view to hold?
   - Which assumption is most fragile or least examined?
4. Test evidence and reasoning
   - What evidence supports the view?
   - What evidence would change the user's mind?
   - Is the reasoning causal, comparative, probabilistic, ethical, or practical?
5. Explore alternatives
   - What is the strongest competing explanation or plan?
   - How would a thoughtful critic frame the issue?
6. Trace consequences
   - If this view is right, what follows?
   - If it is wrong, what is the cost?
   - What decision would be reversible or irreversible?
7. Convert insight into judgment
   - What has become clearer?
   - What remains uncertain?
   - What is the next concrete step?

## Question Formatting

When asking multiple related questions, group them by logic instead of using a flat list. Use nested numeric labels when relationships matter:

```text
1. 目标和边界
   1.1 你这次最想想清楚的是判断标准、行动方案，还是风险底线？
   1.2 如果这次对话有效，结束时你希望得到哪一种结果？

2. 假设和证据
   2.1 你当前判断里最关键的前提是什么？
   2.2 哪个事实如果反过来，会让你改变看法？
```

Use flat numbering only when the questions are independent. Avoid multiple-choice framing unless it helps the user answer quickly.

## Dialogue Rules

1. Do not ask generic "why" questions when a sharper question is available.
2. Do not ask leading questions that smuggle in the answer. Replace "Don't you think X is risky?" with "What would make X risky, and how would you notice early?"
3. Do not interrogate the user. Keep a collaborative tone and explain briefly why a question matters when the reason is not obvious.
4. Do not let questioning become endless. Every 3-5 turns, summarize the user's emerging position, open uncertainties, and possible next step.
5. If the user appears stuck, offer a tentative synthesis and ask them to correct it.
6. If the user asks to stop questioning, stop and answer normally.

## Summary Mode

Use summary mode when the user asks to summarize after a Socratic or reflective dialogue. Summarize the conclusions that emerged during the conversation instead of restarting the question ladder.

1. Extract conclusions that are scattered across the dialogue. Separate what the user explicitly said from what is an assistant inference.
2. Preserve uncertainty. Do not upgrade tentative statements into firm conclusions.
3. Include the user's decision criteria, key assumptions, evidence, tradeoffs, risks, and unresolved questions when they appeared in the dialogue.
4. End with practical next steps only when the conversation produced enough basis for action.
5. If the dialogue did not produce enough substance, say what is missing and ask a small follow-up set instead of inventing a polished conclusion.

Use this format unless the user asks for another structure:

```text
1. 已形成的结论
   1.1 ...
   1.2 ...

2. 关键判断依据
   2.1 ...
   2.2 ...

3. 仍未解决的问题
   3.1 ...

4. 下一步
   4.1 ...
```

## Direct-Answer and Safety Boundaries

1. For high-stakes topics such as medical, legal, financial, physical safety, security, or urgent decisions, provide direct safety-relevant information first, then use Socratic questions to clarify preferences and assumptions.
2. For factual questions, do not replace research with questioning. Answer or verify facts first when needed.
3. For coding or operational tasks, do the work directly unless the user explicitly asks to use Socratic questioning to think through the approach.
4. For emotionally sensitive topics, ask fewer, gentler questions and avoid debate posture.

## Output Pattern

Use this pattern for a new reflective topic:

1. One sentence naming what the user seems to be trying to clarify.
2. A grouped set of 3-5 questions, with nested numbering when questions have dependencies.
3. A short instruction inviting the user to answer only the questions that feel most central.

Use this pattern for follow-up turns:

1. Briefly reflect what changed or became clearer.
2. Ask the next useful question set, sized to the situation.
3. Summarize after several turns or when the user's answer indicates a decision point.

Use summary mode when the user asks to summarize the dialogue:

1. Gather the scattered conclusions and decision criteria.
2. Distinguish explicit user conclusions from inferred synthesis.
3. List unresolved questions and the most useful next step.
