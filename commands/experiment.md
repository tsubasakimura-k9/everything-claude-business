# /experiment [what to test]

## Description

Designs a detailed, execution-ready experiment to test a specific business assumption. Produces a complete experiment card with a falsifiable hypothesis, method, quantitative success criteria, time box, budget, and kill criteria. This is the tactical companion to `/validate` — while `/validate` starts from a broad hypothesis and selects a method, `/experiment` goes deep on the experimental design itself.

## Execution Flow

1. **Input**: Specific assumption or question to test
2. **Clarify**: Determine validation type (problem/solution/demand/channel/feasibility) — ask if ambiguous
3. **Agent**: **lean-validator** — formulates falsifiable hypothesis (WHO/WHAT/HOW MUCH/BY WHEN), designs method, sets thresholds
4. **Pre-mortem**: Identify what could give a WRONG answer, build safeguards
5. **Assemble**: Complete experiment card with anti-pattern checklist
6. **Output**: Execution-ready Experiment Card

## Usage Examples

```
/experiment "日本のB2B SaaS企業のマーケ担当者がAIレポート自動生成に月額5万円払うか検証したい"
```

```
/experiment "Test whether Tokyo cafe owners will sign up for AI Instagram post generator via Google Ads landing page"
```

```
/experiment "従業員50-200名の製造業で、品質管理のAI自動化に対する課題感があるかインタビューで検証"
```

## Error Handling

- **Input too broad** (e.g., "test if people want AI"): Ask to narrow down — What specific customer? What specific behavior? What specific metric?
- **Multiple variables being tested**: Split into separate experiments. One experiment = one variable. Flag multi-variable designs as invalid.
- **Hypothesis not falsifiable** (e.g., "people might like this"): Reframe with specific thresholds — WHO will WHAT at RATE of X%.
- **Sample too small for reliable signal**: Flag the risk explicitly. Provide minimum sample size guidance per method type.
- **User wants to skip pre-mortem**: Do not allow. Surface at least 3 risks that could invalidate the experiment results.

## Related Commands

- **Before this**: `/validate` (to identify the riskiest assumption worth testing)
- **Before this**: `/research` (to understand the market context)
- **After this**: `/pivot` (to analyze results and decide next direction)
- **If results are positive**: `/pricing` (to design the business model)
- **Lighter alternative**: `/validate` (if you need method selection, not deep design)

## Agents

- **lean-validator**: Designs the experiment methodology, defines measurement criteria, sets appropriate thresholds

## Skills & Templates Referenced

- `experiment-card` template (structured output format)
- `validation-patterns` skill (experiment types, sample size guidance)
- `lean-startup` skill (Build-Measure-Learn, minimum viable test)
- `pretotyping` skill (pre-build validation techniques)
- `mom-test` skill (if the method involves customer conversations)

## Workflow

### Step 1: Clarify What to Test
- Parse the user's input: What exactly are we trying to learn?
- Distinguish between:
  - **Problem validation**: "Do people actually have this problem?"
  - **Solution validation**: "Does our solution solve the problem?"
  - **Demand validation**: "Will people pay for this?"
  - **Channel validation**: "Can we reach customers this way?"
  - **Feasibility validation**: "Can we build/deliver this?"
- Ask clarifying questions if the test objective is ambiguous

### Step 2: Formulate Falsifiable Hypothesis
- Structure the hypothesis so it can be PROVEN WRONG:

**Good**: "At least 4 out of 10 target customers will describe [problem] unprompted during a 20-minute interview"
**Bad**: "People might have this problem"

**Good**: "A landing page targeting [segment] will achieve >5% email signup rate from 500 visitors within 7 days"
**Bad**: "People will be interested in our product"

- The hypothesis must include:
  - WHO (specific customer segment)
  - WHAT (specific behavior or metric)
  - HOW MUCH (quantitative threshold)
  - BY WHEN (time bound)

### Step 3: Design the Method
- Select and detail the experimental method:

| Component | Detail |
|-----------|--------|
| **What we do** | Step-by-step execution plan |
| **Who participates** | Target segment, recruitment method |
| **Sample size** | Minimum data points needed for a signal |
| **Data collection** | What we measure, how we measure it |
| **Duration** | Start date to end date |
| **Tools needed** | Software, platforms, materials |

- Sample size guidance:
  - Customer interviews: 5-10 for qualitative signal
  - Landing page tests: 200-500 visitors minimum
  - A/B tests: Statistical significance calculator required
  - Pre-sales: 5-10 conversations for enterprise, 50+ signups for consumer

### Step 4: Define Success, Failure, and Kill Criteria

**Success criteria** (we proceed):
- Specific quantitative threshold that must be met
- Example: "Conversion rate >= 5%"
- Example: "7 out of 10 interviewees describe the problem unprompted"

**Failure criteria** (we pivot or change approach):
- The inverse threshold
- Example: "Conversion rate < 2%"
- Example: "Fewer than 3 out of 10 mention the problem"

**Kill criteria** (we stop the experiment early):
- Conditions under which we abandon the experiment before completion
- Example: "After 200 visitors, conversion is 0%"
- Example: "First 5 interviews show zero interest — stop, don't finish all 10"
- Example: "Budget exhausted before minimum sample reached"

**Ambiguous zone** (we need more data):
- The range between success and failure thresholds
- Define what additional experiment would resolve the ambiguity

### Step 5: Resource Planning
- **Time box**: Hard deadline — no extensions
  - If results are bad, you don't get more time
  - If results are ambiguous, you design a NEW experiment
- **Budget**: Maximum spend, broken down by category
- **People**: Who runs this, time commitment required
- **Dependencies**: What must be true/available before we start

### Step 6: Pre-mortem
- Before executing, ask: "What could make this experiment give us a WRONG answer?"
  - Biased sample (e.g., only asking friends)
  - Leading questions in interviews
  - Too small a sample for statistical significance
  - Testing in a non-representative channel
  - Measuring the wrong metric (vanity vs. actionable)
- Build safeguards against each identified risk

## Expected Output

```markdown
# Experiment Card: [Experiment Name]

## Objective
**Testing**: [Problem / Solution / Demand / Channel / Feasibility]
**Learning goal**: [What we want to find out]

## Hypothesis (Falsifiable)
> [WHO] will [BEHAVIOR] at a rate of [THRESHOLD] when [CONDITION] within [TIMEFRAME].

## Method
**Type**: [e.g., Landing Page Test, Mom Test Interviews, Concierge MVP]

### Execution Steps
1. [Step 1: e.g., Create landing page with value proposition A]
2. [Step 2: e.g., Drive 500 visitors via Google Ads targeting [segment]]
3. [Step 3: e.g., Measure email signup conversion rate]
4. [Step 4: e.g., Follow up with signups for 15-min interview]

### Participants
- **Target segment**: [Who]
- **Recruitment method**: [How we find them]
- **Sample size**: [N] (minimum for reliable signal)

### Data Collection
| Metric | How Measured | Tool |
|--------|-------------|------|
| [Primary metric] | [method] | [tool] |
| [Secondary metric] | [method] | [tool] |

## Decision Criteria (Defined BEFORE Execution)

| Outcome | Threshold | Decision |
|---------|-----------|----------|
| **SUCCESS** | [metric] >= [X] | Proceed: [next step] |
| **AMBIGUOUS** | [metric] between [X] and [Y] | Design follow-up experiment |
| **FAILURE** | [metric] < [Y] | [Pivot direction or kill] |

### Kill Criteria (Stop Early If)
- [ ] [Condition 1: e.g., Zero conversions after 50% of budget spent]
- [ ] [Condition 2: e.g., First 5 interviews show no problem awareness]
- [ ] [Condition 3: e.g., Unable to recruit target participants within 3 days]

## Resources

| Resource | Allocation |
|----------|-----------|
| **Time box** | [X days/weeks] — HARD DEADLINE, no extensions |
| **Budget** | $[amount] total |
| - [Category 1] | $[amount] |
| - [Category 2] | $[amount] |
| **People** | [Who], [hours/week commitment] |
| **Tools** | [List of tools/platforms needed] |

## Pre-Mortem: What Could Go Wrong
| Risk | Likelihood | Safeguard |
|------|-----------|-----------|
| [Biased sample] | [H/M/L] | [Mitigation] |
| [Wrong metric] | [H/M/L] | [Mitigation] |
| [Insufficient sample] | [H/M/L] | [Mitigation] |

## Anti-Pattern Checklist
Before starting, confirm:
- [ ] Success criteria defined BEFORE execution
- [ ] Hypothesis is falsifiable (can be proven wrong)
- [ ] Sample is representative (not just friends/family)
- [ ] Metric is actionable (not vanity)
- [ ] Time box is hard (no "let's extend it" allowed)
- [ ] Kill criteria exist (we know when to stop early)
- [ ] One variable tested (not a multi-variable mess)
```

## Rules

- Every hypothesis MUST be falsifiable — if it can't be proven wrong, it's not a hypothesis
- Success criteria MUST be quantitative — "feels promising" is not a criterion
- Time boxes are HARD deadlines — "extending the experiment" is not allowed; design a new one instead
- Kill criteria are mandatory — every experiment needs a way to stop early if it's clearly failing
- One experiment tests ONE variable — if you're testing multiple things, split into separate experiments
- The pre-mortem step is not optional — surface biases before they corrupt results
- Never use friends and family as the sample unless the target market IS friends and family
- If the experiment requires customer conversations, reference the Mom Test skill: never ask "Would you use this?" or "What would you pay?"
