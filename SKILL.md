---
name: sensemaking
description: 'Use this skill when the user feels confused by messy information and wants help finding judgeable certainty: clarifying what they are really asking, what signals or conditions matter, and what next action follows. Use for uncertain real-world questions with no single standard answer, especially economics, investing, housing, career choice, city choice, policy/news interpretation, reading notes, or any claim that affects action and needs causal logic, evidence checks, falsification conditions, and action implications. Trigger on requests like "怎么看", "怎么判断", "用 sensemaking 分析", "是不是到底", "该不该", "会不会", "有没有机会", "值不值", "靠不靠谱", "我有点乱", "帮我建立大局观", or "学以致用". Do not use for simple factual lookup, definitions, routine debugging, or questions with a direct objective answer unless the user asks for judgment or implications.'
---

# Sensemaking

Use this skill to help people find judgeable certainty in confusion. It does not promise absolute certainty about the world; it helps the user clarify what they are really asking, what information would actually matter, which signals are credible, and what next step they can take.

In plain language:

```text
What am I really asking?
What should I look at?
What should I do next?
```

## Use Cases and Boundaries

Use this skill for questions that are uncertain, complex, and action-relevant. The common shape is:

```text
Should I?
Will it?
Is there an opportunity?
Is this reliable?
How should I view this?
What does this imply for me?
```

Good use cases:

- Investing: whether to buy stocks, bonds, gold, property, or an industry theme.
- Career: whether to change industries, study a skill, move cities, or assess AI impact.
- Housing and cities: whether to buy, rent, wait, leave, or choose a city.
- Policy and news: whether a policy will work, who benefits, and what signals to watch.
- Reading and learning: whether an author's claim holds, how to apply it, and where it fails.
- Life decisions: whether to start a business, take a degree, make a large purchase, or commit to a long-term path.

Do not use this skill as the primary mode for:

- Simple facts: dates, definitions, names, direct lookup.
- Mechanical tasks: routine code debugging, formatting, file operations.
- Closed-form questions with a direct objective answer.

If a factual question has action implications, answer the factual part first, then optionally apply the judgment system to the implication.

When the user feels confused or overwhelmed, reduce the system to three questions:

```text
What am I really asking?
What should I look at?
What should I do next?
```

## Core Workflow

1. **Define the judgment**
   - Translate vague wording into observable versions.
   - Ask what exactly is being judged: price, volume, policy, trend, valuation, risk, timing, fit, or action.
   - If the user's wording is ambiguous, offer 2-4 possible meanings and proceed with the most decision-relevant one.

2. **Classify the layer**
   - Long-term structure: population, technology, productivity, industry, institutions, debt, geography.
   - Medium-term cycle: demand, supply, inventory, profit, credit, employment, inflation.
   - Short-term market: policy stance, liquidity, risk appetite, positioning, price reaction, narrative.
   - Warn when the user mixes layers, such as treating a short-term rebound as a long-term reversal.

3. **Draw the causal chain**
   - Use the format: `cause -> mechanism -> observable result -> second-order effect`.
   - Prefer simple mechanisms with clear variables.
   - Avoid empty explanations such as "confidence is weak" unless it is unpacked into income expectations, credit behavior, risk preference, or balance-sheet pressure.
   - If the causal chain feels abstract, force it through the concrete behavior template in "Causal Chain Method" below.

4. **List evidence on both sides**
   - Use at least three categories of evidence when possible.
   - Prefer cross-validation: independent signals should point in the same direction.
   - Separate facts, inference, and speculation.
   - For current data, browse or otherwise verify rather than relying on memory.

5. **Set falsification conditions**
   - Always answer: "What would show this judgment is wrong?"
   - Make the condition observable and time-bound when possible.
   - If a claim cannot be falsified, label it as a belief, preference, or narrative rather than a judgment.

6. **Translate to action**
   - Ask who the user is in this decision: investor, homebuyer, employee, founder, student, reader, citizen, operator.
   - Give different action implications for different identities.
   - Include downside handling: what to do if right, what to do if wrong, and the smallest next action.

## Standard Output

Use this compact structure unless the user asks for a different format:

```text
判断对象：
一句话结论：
它属于：长期结构 / 中期周期 / 短期市场
核心因果链：
支持证据：
反对证据：
反证条件：
行动含义：
下一步最小行动：
```

## Causal Chain Method

Build causal chains around behavior change, not abstract nouns. A useful causal chain should answer: what changed, who was affected, why their behavior changed, what data trace this leaves, and what result follows.

Use this minimum formula:

```text
variable changes -> actor behavior changes -> data changes -> result changes
```

Or in question form:

```text
What changed?
Who is affected?
Why would they change behavior?
What would they do differently?
What data trace would this leave?
What larger result follows?
```

Prefer concrete actors:

- Households: borrow, save, buy homes, consume, postpone big purchases.
- Firms: hire, produce, invest, cut prices, build inventory, reduce debt.
- Banks: lend, tighten standards, reprice risk, roll over debt.
- Governments: subsidize, regulate, spend, relax restrictions, absorb risk.
- Investors: buy risk assets, sell duration, demand risk premium, rotate sectors.

For housing, do not jump from policy to bottom. Insert the actors:

```text
Mortgage rates fall
-> monthly payment pressure falls for buyers
-> some waiting buyers enter the market
-> second-hand transactions rise
-> sellers face less discount pressure
-> second-hand prices stabilize
```

Also test the opposite chain:

```text
Home prices keep falling
-> buyers expect cheaper homes later
-> buyers postpone purchases
-> transactions stay weak
-> developers' cash collection worsens
-> developers cut land purchases and new starts
-> real-estate investment keeps falling
```

When a chain has no actor behavior change, treat it as incomplete. Ask the user or yourself to fill in the missing actor before moving to evidence.

## Signal and Turning Point Discipline

Use this section when the user asks how to identify main variables, filter noise, judge trends, or locate inflection points.

### Main Variables vs Noise

A main variable has at least one of these traits, and preferably all three:

1. **It changes key actors' behavior.**
   - Ask: "Would this variable change what households, firms, banks, governments, or investors do?"
   - If it changes nobody's behavior, treat it as noise or narrative.

2. **It propagates across many links.**
   - A main variable affects several parts of the system, such as income expectations affecting consumption, savings, borrowing, home purchases, and risk appetite.
   - Noise is usually local, short-lived, and hard to trace beyond one place.

3. **It leaves multiple data traces.**
   - A real variable change should show up in several related indicators.
   - Use the rule: `one thing changes -> many places change`.

When uncertain, ask:

```text
Does this variable change behavior?
Does it affect more than one link?
Can I observe it in more than one data series?
```

### Causal Chain Quality Check

Judge causal chains by behavior and data traces:

```text
variable really changed?
-> who is affected?
-> why would behavior change?
-> what would they do differently?
-> what data trace should appear?
```

If the chain moves only from concept to concept, rewrite it. For example, do not stop at `policy easing -> housing bottom`. Expand it into actors, behavior, and data:

```text
policy easing
-> buying cost or purchase eligibility improves
-> some buyers enter the market
-> transactions rise
-> inventory pressure falls
-> prices stabilize
```

### Trend Judgment

Do not call a trend from one data point. Require:

```text
direction + persistence + diffusion
```

- **Direction**: Is the indicator improving or worsening?
- **Persistence**: Has it continued for several months or reporting periods, rather than one noisy print?
- **Diffusion**: Is the change spreading across related indicators, cities, industries, or actors?

Treat single-month, single-city, or single-indicator improvement as a signal to watch, not a confirmed trend.

### Inflection Point Judgment

An inflection point is not merely "data got better." It means the old causal chain is weakening and a new causal chain is starting to work.

Use this test:

```text
old feedback loop weakens
-> leading indicators turn first
-> related indicators confirm
-> lagging indicators follow
```

Look for three signs:

1. **Leading indicators change first.**
   - Examples: transactions, new orders, credit demand, inquiries, inventory movement, risk appetite.

2. **The old negative or positive feedback loop weakens.**
   - Example for housing: "prices fall -> buyers wait -> transactions fall" starts becoming "prices fall enough -> buyers enter -> transactions recover."

3. **Cross-validation appears.**
   - The judgment becomes stronger when transactions, prices, credit, funding, inventory, and investment begin to point in compatible directions.

When explaining a possible inflection point, name both chains:

```text
Old chain:
...

New chain:
...

Evidence that the old chain is weakening:
...

Evidence that the new chain is forming:
...
```

### Compact Heuristic

Use this sentence when teaching the user:

```text
Main variables change behavior; causal chains leave data traces; trends need persistence and diffusion; inflection points require the old chain to break and a new chain to form.
```

## Reading Companion Mode

When using the system for reading, convert each highlighted passage into:

- The phenomenon the author explains
- The causal chain
- The prediction implied by the argument
- Evidence that would support or weaken it
- Where the user can apply it

For economics books, especially market research or macro analysis, keep returning to three practical questions:

1. Economic direction: improving, weakening, diverging, or unclear?
2. Policy stance: easing, tightening, neutral, or targeted?
3. Liquidity: money becoming cheaper, tighter, or unevenly distributed?

## Domain Hints

For housing/property questions, distinguish policy bottom, sales bottom, price bottom, investment bottom, and personal buying opportunity. Check demand, price, supply, developer funding, inventory, and household credit.

For investing questions, distinguish macro direction, policy/liquidity, valuation, earnings, market positioning, and the user's time horizon. Do not reduce the answer to "bullish/bearish" without naming the invalidation point.

For career/city/life decisions, distinguish long-term structural tailwinds from short-term emotional pressure. Translate macro variables into personal exposure: income, skill accumulation, optionality, cash flow, relationships, and reversibility.

For news/policy interpretation, separate the stated policy goal, the transmission channel, the implementation constraint, likely beneficiaries, and observable follow-up signals.

## Style

Be warm, concrete, and intellectually honest. Avoid pretending certainty. Prefer "current evidence points to..." over absolute claims. Help the user build judgment muscle by showing the thinking moves, not just the conclusion.

