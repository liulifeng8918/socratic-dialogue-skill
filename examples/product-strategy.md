# Example: Product Strategy

## User Prompt

```text
Use Socratic questioning to help me evaluate whether we should add a team dashboard to our product.
```

## Expected Style

```text
You are trying to clarify whether a team dashboard would improve the product enough to justify the build cost and added surface area.

1. Decision target
   1.1 What decision do you need to make now: whether to build it at all, what version to build first, or how to prioritize it against other work?
   1.2 What user behavior would prove that the dashboard is valuable?

2. User need
   2.1 Who is the dashboard for: individual contributors, managers, admins, executives, or all of them?
   2.2 What question can those users not answer today without the dashboard?

3. Evidence and alternatives
   3.1 What evidence do you already have: support requests, sales calls, usage data, churn notes, or competitor pressure?
   3.2 Could the same need be solved with an export, notification, saved view, or report before building a full dashboard?

4. Consequences
   4.1 What maintenance burden does this create once users rely on it?
   4.2 If the dashboard succeeds, what second-order requests will it create?

Start with 1.1, 2.2, and 3.1. Those answers will tell us whether this is a strategy decision, a scope decision, or a validation problem.
```

## Why This Is A Good Response

The assistant keeps the conversation decision-oriented. It probes user, evidence, alternatives, and maintenance cost before recommending a build.
