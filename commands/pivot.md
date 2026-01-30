# /pivot [current situation]

## Description

Analyzes current evidence against the original hypothesis to produce a clear Pivot, Persevere, or Kill recommendation. Explicitly designed to counter "stay the course" bias and sunk cost fallacy by forcing an evidence-based evaluation.

## Execution Flow

1. **Input**: Current situation — original hypothesis, evidence collected, resources spent, gut feeling
2. **Agent 1**: **lean-validator** — audits evidence against hypothesis, calculates evidence ratio, flags missing data
3. **Assess**: If change needed, identify specific pivot type (zoom-in, customer segment, business model, etc.)
4. **Devil's Advocate** (MANDATORY): Challenges "stay the course" default, stress-tests recommendation
5. **Synthesize**: Render PERSEVERE / PIVOT / KILL recommendation with rationale
6. **Output**: Pivot Analysis with action plan

## Usage Examples

```
/pivot "経理自動化SaaSを3ヶ月開発したが、ユーザーインタビュー10件中2件しか課題を感じていない。でもプロダクトは良いと思う"
```

```
/pivot "Landing page got 2% conversion after 1000 visitors. Original target was 5%. Team wants to try different messaging."
```

```
/pivot "飲食店向けAIツールを作ったが、実際に使っているのはカフェだけ。居酒屋・レストランには刺さらない"
```

## Error Handling

- **User provides only feelings, no evidence**: Ask for specific data — experiment results, metrics, customer feedback. Feelings are noted but not accepted as evidence.
- **Evidence is ambiguous**: Present both interpretations. Recommend a focused follow-up experiment to resolve ambiguity before deciding.
- **User strongly resists kill recommendation**: Document the objection. Comply with user's decision, but include a prominent `[SUNK COST WARNING]` in the output and set a hard checkpoint date.
- **Devil's advocate and lean-validator disagree**: Present both perspectives with reasoning. Default to the more conservative recommendation.

## Related Commands

- **Before this**: `/validate` or `/experiment` (to generate the evidence being analyzed)
- **If PIVOT**: `/validate` (to test the new hypothesis)
- **If KILL**: `/kill` (for a more thorough shutdown analysis)
- **If PERSEVERE**: `/experiment` (to design the next validation milestone)

## Agents

- **lean-validator**: Reviews original hypothesis, analyzes evidence collected, assesses signal strength
- **devil-advocate** (mandatory): Challenges the default "persevere" bias, stress-tests the recommendation

## Skills & Templates Referenced

- `lean-startup` skill (pivot types, Build-Measure-Learn loop)
- `validation-patterns` skill (signal interpretation)

## Workflow

### Step 1: Situation Capture
- Gather from the user:
  - **Original hypothesis**: What did we set out to prove?
  - **Evidence collected**: What experiments were run? What were the results?
  - **Current state**: Where are we now? (time invested, money spent, team morale)
  - **Gut feeling**: What does the user WANT to do? (important to surface bias)

### Step 2: Evidence Audit (lean-validator agent)
- Map each piece of evidence to the original hypothesis:

| Evidence | Supports Hypothesis | Contradicts Hypothesis | Ambiguous |
|----------|---------------------|----------------------|-----------|
| [data point] | [ ] | [ ] | [ ] |

- Calculate the evidence ratio: supporting vs. contradicting signals
- Flag any evidence that was reinterpreted after collection (post-hoc rationalization)
- Identify what evidence is MISSING — what should we know but don't?

### Step 3: Pivot Type Assessment
If the evidence suggests change is needed, identify the type of pivot:

| Pivot Type | Description | Signal |
|-----------|-------------|--------|
| **Zoom-in** | A single feature becomes the whole product | Users only care about one feature |
| **Zoom-out** | The product becomes a feature of something larger | Product alone isn't enough value |
| **Customer segment** | Same product, different customer | Wrong audience, right solution |
| **Customer need** | Same customer, different problem | Right audience, wrong problem |
| **Platform** | Application becomes platform (or vice versa) | Ecosystem opportunity |
| **Business model** | Change how you capture value | Product works but business model doesn't |
| **Value capture** | Change monetization | Users love it but won't pay this way |
| **Channel** | Change distribution | Product-market fit exists but channel doesn't work |
| **Technology** | Same outcome, different tech approach | Current tech can't scale or is too expensive |

### Step 4: Devil's Advocate Challenge (devil-advocate agent)

The devil's advocate MUST challenge the "stay the course" default:

- "What evidence would it take for you to quit? Has that threshold been met?"
- "If you were starting fresh today with what you know now, would you start this?"
- "Are you continuing because of evidence or because of sunk costs?"
- "What is the opportunity cost of persevering? What else could you do with these resources?"
- "Is the 'ambiguous' evidence actually negative evidence you're reclassifying?"

Also challenge the pivot recommendation if one is made:
- "Is this a real pivot or just avoiding the hard decision to kill?"
- "Do you have evidence for the pivot direction, or is it another guess?"

### Step 5: Recommendation
- Synthesize into one of three recommendations:
  - **PERSEVERE**: Evidence supports the hypothesis — keep going with current approach
  - **PIVOT**: Evidence suggests a specific directional change — define the new hypothesis
  - **KILL**: Evidence is clearly negative or opportunity cost is too high — stop and redeploy resources

### Step 6: Action Plan
- Define concrete next steps for the chosen recommendation

## Expected Output

```markdown
# Pivot Analysis: [Project/Initiative Name]

## Original Hypothesis
[What we set out to prove]

## Evidence Summary

### Supporting Evidence
- [Evidence 1]: [What it shows]
- [Evidence 2]: [What it shows]

### Contradicting Evidence
- [Evidence 1]: [What it shows]
- [Evidence 2]: [What it shows]

### Missing Evidence
- [What we don't know but should]

**Evidence Score**: [X supporting] vs [Y contradicting] vs [Z ambiguous]

## Sunk Cost Inventory (for awareness, NOT for decision-making)
- Time invested: [X months]
- Money spent: [$ amount]
- Emotional investment: [High/Medium/Low]

> **Reminder**: These sunk costs are irrelevant to the forward-looking decision.
> The only question is: "Given what we know NOW, is this the best use of future resources?"

## Devil's Advocate Challenges
| Challenge | Honest Answer |
|-----------|---------------|
| Would you start this today knowing what you know? | [Yes/No and why] |
| What's the opportunity cost of continuing? | [Specific alternatives] |
| Are you reclassifying negative evidence as ambiguous? | [Honest assessment] |

## Recommendation: [PERSEVERE / PIVOT / KILL]

### Rationale
[2-3 sentences explaining why, rooted in evidence]

### If PIVOT — New Direction
- **Pivot type**: [e.g., Customer Segment Pivot]
- **New hypothesis**: [Reformulated hypothesis]
- **First experiment**: [What to test next]

### If PERSEVERE — Next Milestone
- **What must be true by [date]**: [Specific metric]
- **Kill criteria**: [When do we revisit this decision]

### If KILL — Resource Redeployment
- **What to salvage**: [Learnings, assets, relationships]
- **Where to redeploy**: [Next opportunity]
- **How to communicate**: [To team, stakeholders, customers]
```

## Rules

- The devil's advocate agent is MANDATORY — it cannot be skipped
- Sunk costs must be listed but explicitly labeled as irrelevant to the decision
- The "would you start this today?" question must always be asked and honestly answered
- If recommending PERSEVERE, must define the next kill-or-continue checkpoint with a date
- If recommending PIVOT, must define the new hypothesis — a pivot without a new direction is not a pivot
- Never recommend "keep trying harder" without new evidence suggesting it will work
- Emotional attachment to the idea is acknowledged but not accepted as evidence
