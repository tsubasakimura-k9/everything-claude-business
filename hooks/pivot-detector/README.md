# Hook: Pivot Detector

## Concept

Monitors validation results over time and flags when accumulated negative signals suggest a pivot or kill decision is needed. Like a CI build going red -- when enough experiments fail, the system forces a pivot conversation instead of letting you quietly ignore the evidence.

## Analogy to Code Hooks

| Code World | Business World |
|-----------|---------------|
| CI build goes red | Experiment failure rate exceeds threshold |
| Test suite failure report | Validation scorecard turns negative |
| Build blocked until tests pass | Major spending blocked until pivot decision made |
| Flaky test detector | Pattern of inconclusive experiments |
| Code coverage dropping | Assumption validation coverage declining |

## How It Would Work

### Trigger
After any experiment card is completed with results, or on a scheduled basis (e.g., weekly review).

### Monitoring Logic

The pivot detector tracks three signal categories:

#### Signal 1: Experiment Failure Rate

```
Total experiments completed: 12
  Validated:     4 (33%)
  Invalidated:   5 (42%)
  Inconclusive:  3 (25%)

THRESHOLD BREACH: Failure rate (42%) exceeds 40% threshold.
```

| Failure Rate | Status | Action |
|-------------|--------|--------|
| 0-20% | Green | Continue -- normal exploration |
| 21-40% | Yellow | Review -- are failures in the same area? |
| 41-60% | Orange | Warning -- consider pivot. Run /kill checklist. |
| 61%+ | Red | Critical -- strong evidence against current direction |

#### Signal 2: Core Assumption Health

Tracks the status of the three most critical assumptions (typically Problem, Customer, Revenue):

```
Core Assumptions:
  [PROBLEM]   "Users spend 4+ hrs/week on manual updates"  -> INVALIDATED (EXP-002)
  [CUSTOMER]  "B2B SaaS companies 10-50 employees"         -> VALIDATED (EXP-001)
  [REVENUE]   "$49/mo per seat pricing"                     -> UNTESTED

ALERT: Core assumption PROBLEM has been invalidated.
If the problem isn't real, nothing else matters.
Recommendation: IMMEDIATE PIVOT CONVERSATION
```

| Core Assumption Status | Action |
|----------------------|--------|
| All 3 validated | Strong foundation -- proceed with confidence |
| 1 invalidated | Investigate -- may need adjustment, not full pivot |
| 2 invalidated | Likely need significant pivot |
| Problem invalidated | Full stop -- reconsider everything |

#### Signal 3: Momentum Indicators

Tracks behavioral signals that suggest the initiative is stalling:

```
Momentum Check:
  Days since last experiment completed: 21
  Days since last customer conversation: 35
  Experiments planned but not started: 4
  Canvas last updated: 45 days ago

WARNING: Activity has stalled. Common pattern before quiet abandonment.
Either re-engage or make an explicit kill decision.
```

| Indicator | Yellow | Red |
|-----------|--------|-----|
| Days since last experiment | >14 days | >30 days |
| Days since customer conversation | >21 days | >45 days |
| Planned experiments not started | >3 | >5 |
| Canvas not updated | >30 days | >60 days |

### Alert Output

When thresholds are breached, the pivot detector generates an alert:

```
=======================================================
  PIVOT DETECTOR ALERT
  Initiative: [Name]
  Date: YYYY-MM-DD
  Alert Level: ORANGE
=======================================================

SUMMARY:
  - 5 of 12 experiments failed (42%)
  - Core Problem assumption invalidated
  - 21 days since last experiment
  - 3 planned experiments not started

PATTERN DETECTED: "Evidence Avoidance"
  You have invalidated your core problem assumption but
  have not updated your canvas or run follow-up experiments.
  This pattern often indicates emotional attachment to the
  original idea despite contrary evidence.

RECOMMENDED ACTION:
  Run /kill to perform a full Go/No-Go evaluation.
  This is not a suggestion. The evidence warrants a decision.

OPTIONS:
  1. /kill     -- Run full evaluation checklist
  2. /pivot    -- Explicitly document what changes and why
  3. /override -- Acknowledge the alert and continue (requires written justification)

  Choosing /override will be logged. Future alerts will escalate.
=======================================================
```

### Named Patterns

The pivot detector recognizes common anti-patterns:

| Pattern | Description | Signal |
|---------|-------------|--------|
| **Evidence Avoidance** | Core assumption invalidated, no follow-up action | Experiments stopped after failure |
| **Zombie Initiative** | No activity for 30+ days, no kill decision | Stalled momentum indicators |
| **Confirmation Bias Loop** | Only running experiments likely to succeed | All recent experiments validate; none challenge |
| **Pivot Without Learning** | Changing direction without completing experiments | New canvas created before experiments finished |
| **Boiling Frog** | Gradual decline in all metrics, no single trigger | Slow deterioration across all signals |

### Escalation Path

```
Level 1 (Info):    "Experiment failed. Consider implications."
Level 2 (Warning): "Multiple failures detected. Review recommended."
Level 3 (Alert):   "Threshold breached. /kill evaluation recommended."
Level 4 (Critical):"Pattern detected. Pivot conversation required before proceeding."
```

Each escalation level is logged with a timestamp. Acknowledging an alert without action causes faster escalation on the next trigger.

## Implementation Approach

### As Claude Code Behavior (no settings.json needed)

The agent should naturally monitor these signals as part of its workflow:

- **After every experiment card is completed**, calculate the running failure rate and compare against thresholds
- **After an experiment marked FAILURE**, check if the invalidated assumption is a core assumption (Problem, Customer, Revenue) and escalate immediately if so
- **When the user starts a new work session**, check momentum indicators (days since last experiment, canvas freshness) and surface stale items
- **When the user says "let's continue with..."**, check the pivot detector scorecard and warn if signals are Orange or Red
- **When creating a new canvas or hypothesis**, check if prior experiments were completed first (detect "Pivot Without Learning" pattern)

Example agent behavior after experiment failure:

```
Experiment EXP-005 completed: FAILURE
"Users prefer AI-generated summaries" -- only 2/10 preferred AI version

Pivot Detector Update:
  Experiment failure rate: 3/8 = 37.5% (Yellow -- approaching Orange threshold)
  Core assumptions:
    [PROBLEM]  Validated (EXP-001)
    [CUSTOMER] Validated (EXP-003)
    [SOLUTION] Now has 2 failures (EXP-004, EXP-005) -- this is concerning

  Pattern check: No anti-patterns detected yet, but Solution block
  has failed validation twice. Consider:
  1. Is the solution approach fundamentally wrong?
  2. Should we redesign the solution before testing again?
  3. Run /kill if you want a full evaluation.

  The Problem and Customer are solid. This may be a solution pivot,
  not a full pivot. Would you like to brainstorm alternative solutions?
```

### As Settings.json Hook (optional automation)

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "tool == 'Write' && tool_input.file_path matches '.*experiment.*\\.md$'",
        "description": "Update pivot detector scorecard: recalculate failure rate, check core assumptions, detect patterns"
      }
    ],
    "PreToolUse": [
      {
        "matcher": "tool == 'Write' && tool_input.file_path matches '.*canvas.*\\.md$'",
        "description": "Before creating new canvas, check if prior experiments were completed (detect Pivot Without Learning)"
      }
    ]
  }
}
```

### Data Storage

The pivot detector maintains a scorecard file:

```
scorecard/
  initiative-name/
    experiment-results.md    # Running log of experiment outcomes
    signal-history.md        # Timestamped signal readings
    alerts.md                # History of alerts and responses
    overrides.md             # Logged override decisions with justifications
```

## Integration Points

- **Reads from `assumption-tracker` hook** to get the raw data on which assumptions are tested/untested and their current status
- **Receives escalations from `validation-reminder` hook** when reminders are repeatedly ignored (stall detection)
- **Triggers `/kill` command** automatically when signals reach Orange or Red level -- generates a pre-filled Go/No-Go checklist using `templates/go-no-go-checklist.md`
- **Triggers `devil-advocate` agent** at Level 3+ alerts to force a structured challenge of the user's reasoning for continuing
- **References `intellectual-honesty` rule** to prevent rationalization of negative signals -- the rule requires acknowledging uncomfortable truths
- **References `evidence-based` rule** to ensure all signal readings are based on actual experiment data, not feelings
- **Works with `contexts/validation.md`** to determine what constitutes a core assumption and when the validation gate is not met
- **Works with `contexts/execution.md`** Execution Red Flag section -- pivot detector monitors the same signals during execution mode

## Why This Matters

Most startups don't die from a single dramatic failure. They die from a thousand small signals that nobody aggregated. The founder runs an experiment that fails, adjusts slightly, runs another, gets an inconclusive result, gets busy with something else, and slowly the initiative becomes a zombie -- neither alive nor dead.

The pivot detector exists to prevent quiet failure. It aggregates weak signals into a clear picture and forces an explicit decision. You can choose to continue, but you have to look at the evidence and say "I see this, and I'm continuing anyway" -- which is very different from not seeing it at all.

The goal is not to kill ideas prematurely. The goal is to make sure every continuation is a conscious choice backed by evidence, not an unconscious default driven by sunk costs.
