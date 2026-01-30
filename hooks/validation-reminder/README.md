# Hook: Validation Reminder

## Concept

After any major business document is created (canvas, pitch deck, business plan, financial model), automatically remind the user to validate key assumptions before proceeding to the next step. Prevents the common pattern of planning extensively without ever talking to customers.

This is the business equivalent of how Claude Code runs TypeScript type-checks after editing `.ts` files -- except instead of type errors, it checks for "evidence errors."

## Analogy to Code Hooks

| Code World | Business World |
|-----------|---------------|
| TypeScript compiler checks after `.ts` edit | Validation reminder after business document edit |
| "Type 'string' is not assignable to type 'number'" | "Revenue assumption has no customer evidence" |
| Build fails until types are fixed | Planning should pause until assumptions are tested |
| `tsc --noEmit` as pre-commit hook | Validation check as post-document hook |

## How It Would Work

### Trigger
When a business document is created or a significant section is completed:
- Lean Canvas filled out
- Pitch deck drafted
- Financial projections created
- Go-to-market plan written
- Experiment card completed with results

### Action

1. **Identify the document type** and its validation requirements
2. **Extract the top 3 riskiest assumptions** from the document
3. **Check the assumption log** for existing evidence
4. **Generate a validation reminder** with specific next steps

### Reminder Logic by Document Type

#### After Lean Canvas Creation
```
[validation-reminder] Canvas created with 7 assumption blocks.

Before building anything, validate these first:
  1. PROBLEM: "Sales teams spend 4+ hours/week on manual CRM updates"
     -> Suggested: Interview 10 sales managers (use /interview template)
     -> Time estimate: 1-2 weeks

  2. CUSTOMER: "B2B SaaS companies with 10-50 employees"
     -> Suggested: Identify and reach out to 20 potential matches
     -> Time estimate: 1 week

  3. REVENUE: "Willing to pay $49/mo per seat"
     -> Suggested: Landing page with pricing, measure signup intent
     -> Time estimate: 1 week

Do NOT proceed to building until at least Problem and Customer are validated.
Run /experiment to create experiment cards for these assumptions.
```

#### After Pitch Deck Draft
```
[validation-reminder] Pitch deck drafted.

Investor-readiness check:
  - Slide 2 (Problem): Based on [A]ssumption -- need customer evidence
  - Slide 4 (Market): TAM sourced, but SAM/SOM are estimates
  - Slide 6 (Traction): No traction data yet -- this slide will be your weakest

Priority: Get 5 customer interviews before presenting this deck.
Investors will ask "How do you know this is a real problem?"
You need a better answer than "We think so."
```

#### After Experiment Completion
```
[validation-reminder] Experiment EXP-003 completed (FAILURE).

This was testing: "Users prefer AI-generated reports over manual ones"
Result: 2/10 users preferred AI version

Impact on other documents:
  - Lean Canvas: Solution block needs revision
  - Pitch Deck: Slide 3 (Solution) no longer supported by evidence
  - Financial Model: Conversion rate assumption of 30% is likely too high

Suggested next steps:
  1. Update canvas Solution block
  2. Run follow-up interviews to understand why (use /interview)
  3. Consider pivot -- run /kill to evaluate

3 failed experiments in the last 30 days. Consider running /kill for a full evaluation.
```

### Severity Levels

| Level | Trigger | Response |
|-------|---------|----------|
| **Info** | Document created with assumptions | List assumptions, suggest validation |
| **Warning** | Proceeding to build/spend with untested assumptions | Block reminder, strongly suggest validation first |
| **Critical** | Multiple experiments failed, still proceeding | Force a /kill evaluation conversation |

### Grace Period Logic

The hook respects momentum -- it does not interrupt during active creation. Instead:
- During document creation: silent (let the user think freely)
- After document is saved/completed: show reminder
- After 48 hours with no validation activity: gentle nudge
- After 7 days with critical untested assumptions: stronger reminder

## Implementation Approach

### As Claude Code Behavior (no settings.json needed)

The agent should naturally embed these reminders into its workflow:

- **After completing a Lean Canvas**, automatically list the top 3 riskiest `[A]` blocks and suggest validation methods for each
- **After drafting a pitch deck**, scan each slide for `[A]` markers and flag slides that lack evidence
- **After an experiment card is marked as FAILURE**, trace the impact back to related documents (canvas blocks, pitch slides, financial assumptions) and list what needs updating
- **Before creating execution plans**, check if the validation gate (from `contexts/validation.md`) has been passed -- if not, remind the user
- **When the user says "let's build this"**, check assumption coverage and warn if critical assumptions are untested

Example agent behavior when user requests building:

```
Before we start building, let me check the validation status:

Validation Gate Check:
  [x] Problem validated -- 8/10 interviewees confirmed (EXP-001)
  [ ] Willingness to pay -- NOT YET TESTED
  [x] Differentiator validated -- freee OCR precision gap confirmed
  [ ] Unit economics -- NOT YET ESTIMATED

2 of 4 gate items are incomplete. I recommend:
1. Run a pricing experiment (templates/experiment-card.md)
2. Estimate unit economics using interview data

Want me to create an experiment card for the pricing test?
```

### As Settings.json Hook (optional automation)

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "tool == 'Write' && tool_input.file_path matches '.*canvas.*\\.md$'",
        "description": "Run validation reminder for canvas -- list untested assumptions and suggest experiments"
      },
      {
        "matcher": "tool == 'Write' && tool_input.file_path matches '.*pitch.*\\.md$'",
        "description": "Run investor-readiness check -- flag slides without evidence"
      },
      {
        "matcher": "tool == 'Write' && tool_input.file_path matches '.*experiment.*\\.md$'",
        "description": "Check experiment results, cascade impact to related documents, escalate if failure accumulates"
      }
    ]
  }
}
```

## Integration Points

- **Reads from `assumption-tracker` hook** to know what is tested vs. untested -- never duplicates the tracking, just consumes the data
- **Escalates to `pivot-detector` hook** when validation reminder reaches "critical" level (multiple failures, ignored warnings)
- **References `evidence-based` rule** for evidence quality classification -- ensures recommendations match the required quality for the current mode
- **Works with `/validate` command** to create experiment cards directly from the reminder output
- **Works with `/kill` command** by triggering a full Go/No-Go evaluation when failure accumulation is detected
- **Uses `contexts/validation.md`** validation gate criteria to determine what must be validated before moving to execution
- **Triggers `devil-advocate` agent** at Warning and Critical severity levels to challenge the user's assumptions

## Why This Matters

The most dangerous moment in a startup is right after a planning session. You feel productive and confident. You have a beautiful canvas, a polished deck, a detailed financial model. The temptation is to start building immediately.

But none of those documents are evidence. They are hypotheses dressed up as plans. This hook is the voice that says: "Great plan. Now go find out if it's true."
