# /kill [project or initiative]

## Description

The hardest command. Forces an honest, structured evaluation of whether a project or initiative should continue. Explicitly designed to counteract sunk cost fallacy, emotional attachment, and organizational inertia. Uses the go-no-go checklist template and mandatory devil's advocate review to produce a clear Go or No-Go decision.

**This command exists because killing projects is emotionally difficult but strategically essential. Most failed ventures die too late, not too early.**

## Execution Flow

1. **Input**: Project/initiative name + current state + evidence collected + resources consumed
2. **Devil's Advocate** (runs FIRST — default is "kill", project must earn survival): Hard questions — Fresh Start Test, Opportunity Cost Test, Evidence Test, Sunk Cost Test
3. **Agent**: **lean-validator** — evaluates evidence quality, scores Go/No-Go checklist
4. **Synthesize**: Render GO or NO-GO decision grounded in evidence
5. **Output**: Kill Assessment with shutdown plan (if NO-GO) or survival conditions (if GO)

## Usage Examples

```
/kill "経理自動化SaaS — 6ヶ月開発、500万円投資。ユーザー3社のみ、MRR 5万円。チームは疲弊している"
```

```
/kill "AI English writing tool — 4 months in, 200 beta users but 0 paying customers. Pivot to B2B considered but no evidence yet"
```

```
/kill "社内AI活用プロジェクト — 予算1200万円中800万円消化。導入部署3つの予定が1つのみ。経営層の関心低下"
```

## Error Handling

- **User provides only emotions, no evidence**: Ask for specific data. "I feel like it's not working" is noted but not sufficient. Need: experiment results, metrics, customer feedback, financial data.
- **User strongly resists NO-GO recommendation**: Document the objection. Comply with the user's decision, but: (1) include a prominent `[SUNK COST WARNING]`, (2) set a hard checkpoint date with kill criteria, (3) make clear this is the user's choice against the evidence.
- **Evidence is genuinely ambiguous**: Do not force a kill. Recommend a time-boxed experiment to resolve ambiguity, with a hard decision date.
- **No alternative use for freed resources**: Still evaluate the project on its own merits. "Nothing better to do" is not a reason to continue a failing project — rest, learning, and exploration have value.

## Related Commands

- **Before this**: `/pivot` (for a softer evaluation that includes pivot options)
- **Before this**: `/validate` or `/experiment` (to generate evidence before making the kill decision)
- **If GO**: `/experiment` (to design the next validation milestone)
- **If NO-GO**: Consider `/research` (to explore the next opportunity with freed resources)

## Agents

- **devil-advocate** (mandatory, runs FIRST): Challenges every reason to continue, surfaces sunk cost bias, forces confrontation with evidence
- **lean-validator**: Evaluates evidence quality, assesses signal strength

## Skills & Templates Referenced

- `go-no-go-checklist` template (structured decision framework)
- `lean-startup` skill (pivot-or-kill frameworks)
- `unit-economics` skill (financial viability assessment)

## Workflow

### Step 1: Project Inventory
- Gather the facts (not feelings) from the user:
  - **Original goal**: What was this supposed to achieve?
  - **Current state**: Where is it now?
  - **Evidence collected**: What experiments were run? What were the results?
  - **Resources consumed**: Time, money, people, opportunity cost
  - **Resources remaining**: What's left to invest if we continue?
  - **Emotional attachment level**: Be honest (High/Medium/Low)

### Step 2: The Hard Questions (devil-advocate agent — runs FIRST)

The devil's advocate leads with these questions. Every single one must be answered honestly.

**The Fresh Start Test:**
> "If you were starting from scratch today — with everything you now know — would you start this project?"
> If the answer is no, the only reason to continue is sunk costs. And sunk costs are not a reason.

**The Opportunity Cost Test:**
> "What ELSE could you do with the time, money, and energy currently going into this?"
> List specific alternatives. Compare their expected value to this project's expected value.

**The Evidence Test:**
> "What evidence exists that this will succeed? Not hope. Not potential. Evidence."
> - Separate facts from beliefs
> - Separate validated assumptions from untested assumptions
> - Count: How many key assumptions have been PROVEN vs. ASSUMED?

**The Sunk Cost Test:**
> "If you had NOT already spent [X time / $Y / Z effort], would you choose to start spending now?"
> This isolates the forward-looking decision from backward-looking attachment.

**The Honest Trajectory Test:**
> "Based on the current trajectory — not the best case, not the plan, but the ACTUAL trajectory — where does this end up in 6 months?"

**The Pre-Mortem Test:**
> "Imagine it's 12 months from now and this project has failed. What went wrong?"
> If the failure scenario feels more realistic than the success scenario, that's a signal.

### Step 3: Go/No-Go Checklist Evaluation

Score each criterion honestly:

| # | Criterion | Status | Weight |
|---|-----------|--------|--------|
| 1 | **Problem validated**: Evidence that real customers have this problem | Yes/Partial/No | Critical |
| 2 | **Solution validated**: Evidence that our solution solves the problem | Yes/Partial/No | Critical |
| 3 | **Demand validated**: Evidence people will pay / adopt | Yes/Partial/No | Critical |
| 4 | **Unit economics viable**: Can we deliver profitably at scale? | Yes/Partial/No | High |
| 5 | **Competitive position**: Do we have a defensible advantage? | Yes/Partial/No | High |
| 6 | **Team capability**: Can this team execute? | Yes/Partial/No | High |
| 7 | **Market timing**: Is now the right time? | Yes/Partial/No | Medium |
| 8 | **Resource availability**: Do we have what's needed to reach the next milestone? | Yes/Partial/No | Medium |
| 9 | **Strategic alignment**: Does this still fit our overall strategy? | Yes/Partial/No | Medium |
| 10 | **Passion/energy**: Does the team still believe? | Yes/Partial/No | Low |

**Scoring:**
- If ANY "Critical" criterion is "No" --> Strong signal to KILL
- If 2+ "High" criteria are "No" --> Strong signal to KILL
- Criterion 10 (Passion) is deliberately weighted LOW — passion without evidence is dangerous

### Step 4: Sunk Cost Accounting (for awareness only)

List everything invested — then explicitly label it as IRRELEVANT to the decision:

```
SUNK COSTS (irrelevant to forward-looking decision):
- Time invested: [X months]
- Money spent: [$Y]
- Relationships built: [list]
- Code written: [description]
- Emotional energy: [High/Medium/Low]

These costs are GONE regardless of what we decide.
The only question is: "What is the best use of FUTURE resources?"
```

### Step 5: Decision

Based on Steps 2-4, render one of two decisions:

**GO (Continue):**
- Multiple critical criteria are validated with evidence
- Forward-looking expected value exceeds opportunity cost
- Clear path to next milestone with defined resources
- The "Fresh Start Test" answer is genuinely YES

**NO-GO (Kill):**
- One or more critical criteria are "No" without a credible path to "Yes"
- Forward-looking expected value is less than opportunity cost
- The "Fresh Start Test" answer is NO
- Continuing requires more hope than evidence

### Step 6: If NO-GO — Graceful Shutdown Plan
- What to salvage (learnings, code, relationships, data)
- How to communicate the decision (team, stakeholders, customers)
- Where to redeploy freed resources
- What was learned (capture for future projects)

### Step 7: If GO — Conditions to Stay Alive
- Define the NEXT kill-or-continue checkpoint (date + criteria)
- No open-ended "let's keep going" — must have a hard review date
- Define what must be true by that date to continue

## Expected Output

```markdown
# Kill Assessment: [Project/Initiative Name]

## Project Summary
- **Original goal**: [What this was supposed to achieve]
- **Current state**: [Where it is now]
- **Time invested**: [X months]
- **Money invested**: [$Y]
- **Key results to date**: [What has been validated/invalidated]

## Hard Questions — Honest Answers

### Fresh Start Test
> Would you start this today knowing what you know?
**Answer**: [Yes/No]
**Why**: [Honest reasoning]

### Opportunity Cost
> What else could these resources accomplish?
| Alternative | Expected Value | Confidence |
|------------|---------------|------------|
| [Alt 1] | [value] | [H/M/L] |
| [Alt 2] | [value] | [H/M/L] |
| Continue current project | [value] | [H/M/L] |

### Evidence Inventory
| Assumption | Status | Evidence |
|-----------|--------|----------|
| [Assumption 1] | Validated / Invalidated / Untested | [What we know] |
| [Assumption 2] | ... | ... |

**Validated**: [N] / **Invalidated**: [N] / **Untested**: [N]

### Trajectory Assessment
> Based on actual (not planned) trajectory, in 6 months this will be:
[Honest projection]

## Go/No-Go Checklist
| # | Criterion | Status | Weight |
|---|-----------|--------|--------|
| 1 | Problem validated | [Yes/Partial/No] | Critical |
| 2 | Solution validated | [Yes/Partial/No] | Critical |
| 3 | Demand validated | [Yes/Partial/No] | Critical |
| 4 | Unit economics viable | [Yes/Partial/No] | High |
| 5 | Competitive position | [Yes/Partial/No] | High |
| 6 | Team capability | [Yes/Partial/No] | High |
| 7 | Market timing | [Yes/Partial/No] | Medium |
| 8 | Resource availability | [Yes/Partial/No] | Medium |
| 9 | Strategic alignment | [Yes/Partial/No] | Medium |
| 10 | Passion/energy | [Yes/Partial/No] | Low |

## Sunk Cost Inventory
> **These are listed for completeness. They are NOT factors in the decision.**

| Category | Amount |
|----------|--------|
| Time | [X months] |
| Money | [$Y] |
| Relationships | [description] |
| Code / assets | [description] |

**Reminder**: Sunk costs are gone. The decision is about FUTURE resource allocation only.

---

## DECISION: [GO / NO-GO]

### Rationale
[3-5 sentences grounded in evidence, not emotion]

---

### If NO-GO: Shutdown Plan

**Salvage**:
- Learnings: [What we learned that applies elsewhere]
- Assets: [Code, data, relationships to preserve]
- Reputation: [How to communicate professionally]

**Resource Redeployment**:
- [Person/budget] --> [New allocation]

**Communication Plan**:
- Team: [How and when to communicate]
- Stakeholders: [How and when to communicate]
- Customers (if any): [How and when to communicate]

**Post-Mortem**:
- What worked: [List]
- What didn't: [List]
- What we'd do differently: [List]

### If GO: Survival Conditions

**Next checkpoint**: [Specific date, max 4-8 weeks out]
**Must be true by then**:
- [ ] [Specific measurable criterion 1]
- [ ] [Specific measurable criterion 2]
**If NOT true**: Run /kill again — no extensions.
```

## Rules

- **Sunk costs are NOT a reason to continue** — this is the foundational rule of this command
- The devil's advocate agent runs FIRST, not last — the default assumption is "kill" and the project must earn its survival
- The Fresh Start Test must ALWAYS be asked and honestly answered
- Passion/energy is weighted LOW deliberately — passion without evidence is the #1 cause of zombie projects
- If the decision is GO, a hard checkpoint date with kill criteria is MANDATORY — no open-ended continuation
- If the user cannot answer "What evidence exists?" with specifics, that IS the answer
- This command should feel uncomfortable. If it doesn't, it's not being used correctly
- Never soften a NO-GO recommendation with "but maybe if..." — a kill is a kill
- Always include a graceful shutdown plan — killing well is as important as killing decisively
- The post-mortem is not optional — captured learnings are the ROI of a failed project
