# /validate [hypothesis]

## Description

Designs a validation experiment for a business hypothesis. Transforms vague assumptions into falsifiable hypotheses with measurable success criteria, a clear method, time box, and budget. The cardinal rule: success criteria MUST be defined BEFORE execution begins.

## Execution Flow

1. **Input**: Business hypothesis or assumption to test
2. **Clarify**: Extract structured hypothesis — if vague, ask "Who? What behavior? What proves you wrong?"
3. **Map**: Break hypothesis into ranked assumptions (risk x uncertainty)
4. **Agent**: **lean-validator** — selects lightest-weight method, defines quantitative success/failure/kill criteria
5. **Assemble**: Compile experiment card with time box, budget, sample size
6. **Output**: Execution-ready Experiment Card

## Usage Examples

```
/validate "中小企業の経理担当者は月次決算に10時間以上かけており、自動化ツールに月額3万円払う意思がある"
```

```
/validate "Japanese enterprise HR teams (1000+ employees) will adopt AI screening if it integrates with existing ATS"
```

```
/validate "飲食店オーナーはInstagram運用に困っており、AI投稿生成ツールに月額1万円払う"
```

## Error Handling

- **Input too vague** (e.g., "people want this"): Ask three clarifying questions — Who is the customer? What behavior are you predicting? What would prove you wrong?
- **User cannot define failure**: The hypothesis is not ready to test. Help the user sharpen it before proceeding.
- **Multiple assumptions bundled together**: Split into separate experiments. Test the riskiest assumption first.
- **Hypothesis is actually an opinion**: Reframe as falsifiable statement with WHO/WHAT/HOW MUCH/BY WHEN.

## Related Commands

- **Before this**: `/research` (to understand the market and identify hypotheses worth testing)
- **After this**: `/experiment` (for deeper experimental design on the riskiest assumption)
- **If validation fails**: `/pivot` (to analyze evidence and find a new direction)
- **If validation succeeds**: `/pricing` (to design the revenue model)

## Agents

- **lean-validator**: Designs the experiment, selects the appropriate validation method, defines success/failure criteria

## Skills & Templates Referenced

- `validation-patterns` skill (experiment types, signal detection)
- `lean-startup` skill (Build-Measure-Learn loop, MVP definition)
- `pretotyping` skill (fake-it-before-you-make-it techniques)
- `mom-test` skill (customer interview best practices — no leading questions)
- `experiment-card` template (structured output format)

## Workflow

### Step 1: Hypothesis Extraction
- Parse the user's input into a structured hypothesis
- If the input is vague, ask clarifying questions:
  - "Who is the customer?"
  - "What behavior are you predicting?"
  - "What would prove you wrong?"
- Format as: **"We believe [customer segment] will [behavior] because [reason]"**

### Step 2: Assumption Mapping
- Break the hypothesis into its underlying assumptions
- Rank assumptions by:
  - **Risk**: How damaging if wrong? (High/Medium/Low)
  - **Uncertainty**: How confident are we? (High/Medium/Low)
- Identify the **riskiest assumption** — this is what we test first

### Step 3: Method Selection (lean-validator agent)
Choose the lightest-weight validation method that can test the riskiest assumption:

| Method | When to Use | Time | Cost |
|--------|-------------|------|------|
| Mom Test interviews | Understanding problem/need | Days | Free |
| Landing page test | Demand validation | Days | $50-500 |
| Concierge MVP | Service/process validation | 1-2 weeks | Low |
| Wizard of Oz | Product experience validation | 1-2 weeks | Low |
| Pretotype | Concept validation | Hours-days | Minimal |
| Smoke test (ads) | Demand + willingness to pay | Days | $100-1000 |
| Pre-sale / LOI | Revenue validation | Weeks | Low |

- Always prefer cheaper and faster methods
- Never build a full product to validate a hypothesis that can be tested with a conversation

### Step 4: Success Criteria Definition

**THIS IS THE MOST CRITICAL STEP. Do not proceed without it.**

- Define **quantitative** success criteria:
  - Specific number or percentage threshold
  - Example: "5 out of 10 interviewees mention [problem] unprompted"
  - Example: "Landing page converts at >5% click-to-signup"
  - Example: "3 LOIs signed within 2 weeks"
- Define **kill criteria** — what result means we stop:
  - Example: "0 out of 10 interviewees have this problem"
  - Example: "Landing page converts at <1%"
- Define the **ambiguous zone** — what results need further investigation

### Step 5: Experiment Card Assembly
- Compile all elements into the experiment card format
- Review for completeness and internal consistency
- Ensure the time box is realistic for the method chosen

## Expected Output

```markdown
# Experiment Card

## Hypothesis
We believe [customer segment] will [behavior] because [reason].

## Riskiest Assumption
[The single most critical assumption to test]

## Method
**Type**: [e.g., Mom Test Interviews]
**Description**: [What we will do, step by step]

## Success Criteria (defined BEFORE execution)
| Outcome | Threshold | Action |
|---------|-----------|--------|
| Success | [specific metric] >= [threshold] | Proceed to next assumption |
| Ambiguous | [metric] between [X] and [Y] | Run follow-up experiment |
| Failure | [specific metric] < [threshold] | Pivot or kill |

## Execution Plan
- **Time box**: [X days/weeks — hard deadline]
- **Budget**: [$ amount or "zero cost"]
- **Who**: [Who runs this experiment]
- **Sample size**: [How many data points needed]

## What We Will Learn
- If SUCCESS: [what it proves, what to do next]
- If FAILURE: [what it proves, what to do instead]

## Anti-Patterns to Avoid
- [ ] Don't extend the time box if results are bad
- [ ] Don't change success criteria mid-experiment
- [ ] Don't cherry-pick positive signals from a failed experiment
```

## Rules

- **MUST define measurable success criteria BEFORE execution** — this is non-negotiable
- Success criteria must be quantitative, not qualitative ("feels right" is not a criterion)
- Always select the cheapest, fastest validation method that can produce a clear signal
- Time boxes are hard deadlines — no extensions allowed
- If the user cannot articulate what "failure" looks like, the hypothesis is not ready to test
- Never skip the assumption mapping step — testing the wrong assumption wastes everything
- Reference the Mom Test skill when the method involves customer interviews: never ask "Would you use this?"
