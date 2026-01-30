# Hook: Assumption Tracker

## Concept

Automatically tracks every assumption made during business analysis. When a document is created or updated (canvas, experiment card, pitch deck, etc.), this hook extracts all assumptions and logs them to a centralized assumption registry. Untested assumptions are flagged for validation.

Think of it like how a linter tracks `console.log` statements in code -- this tracks unvalidated claims in business documents.

## Analogy to Code Hooks

In software development, a pre-commit hook might scan for `console.log` statements and warn you before shipping debug code to production. This hook does the same for business planning: it scans for unvalidated assumptions and warns you before building on top of them.

| Code World | Business World |
|-----------|---------------|
| `console.log` left in code | Unvalidated assumption in a plan |
| Linter warning | Assumption flagged for testing |
| Test coverage report | Assumption validation coverage |
| CI build check | Validation checkpoint before major decisions |

## How It Would Work

### Trigger
When any file in `templates/` output or business documents is created or modified.

### Action
1. Parse the document for assumption indicators:
   - Statements marked `[A]` in Lean Canvas
   - Hypotheses in experiment cards
   - Claims without cited evidence (e.g., "customers want...", "the market is...", "we believe...")
   - Phrases like "we assume", "we think", "probably", "likely", "should be"
2. Extract each assumption as a structured entry
3. Append to `assumptions/log.md` (or create if it doesn't exist)
4. Cross-reference against completed experiments to check if already validated
5. Output a summary: X new assumptions found, Y remain untested

### Assumption Log Entry Format

```markdown
## ASM-001: [Assumption text]
- **Source**: [document where it was found]
- **Date Found**: YYYY-MM-DD
- **Category**: Problem / Customer / Solution / Market / Revenue / Technical
- **Status**: Untested / Testing / Validated / Invalidated
- **Experiment**: [link to experiment card, if any]
- **Evidence**: [summary of evidence, if validated]
```

### Output Example

```
[assumption-tracker] Scanned: lean-canvas.md
  Found 7 assumptions:
    - 5 untested (Problem: 2, Customer: 1, Revenue: 2)
    - 1 currently being tested (EXP-003)
    - 1 validated (EXP-001 confirmed)

  WARNING: 3 critical assumptions have been untested for >14 days:
    - ASM-002: "Target customers spend >$500/mo on current solution"
    - ASM-005: "Users will switch from Excel to our tool"
    - ASM-007: "Word-of-mouth will be primary acquisition channel"

  Run /validate to create experiment cards for untested assumptions.
```

## Implementation Approach

### As Claude Code Behavior (no settings.json needed)

The agent should naturally perform these checks as part of its workflow:

- **After creating any business document**, scan for statements marked `[A]` or containing assumption language ("we believe", "we assume", "customers will", "the market is")
- **When reviewing a Lean Canvas**, count how many blocks are `[A]` vs `[E]` and report the ratio
- **Before proceeding to the next phase** (e.g., exploration -> validation), list all untested assumptions that should be validated first
- **When an experiment card is completed**, check if any assumptions in the log can be updated to Validated or Invalidated

Example agent behavior after writing a Lean Canvas:

```
I've completed the Lean Canvas. Here's the assumption inventory:

Assumptions found: 7
  [A] Problem: "経理担当が月40時間を手入力に費やしている" — UNTESTED
  [A] Customer: "従業員10-50名の中小企業" — UNTESTED
  [E] Problem: "インボイス制度で作業量増加" — VALIDATED (国税庁データ)
  ...

Validation coverage: 1/7 (14%)
Recommended: Start with Problem and Customer assumptions.
Run /validate to create experiment cards.
```

### As Settings.json Hook (optional automation)

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "tool == 'Write' && tool_input.file_path matches '.*canvas.*\\.md$'",
        "description": "Scan canvas for assumptions and update assumption log"
      },
      {
        "matcher": "tool == 'Write' && tool_input.file_path matches '.*experiment.*\\.md$'",
        "description": "Cross-reference experiment results against assumption log and update statuses"
      }
    ]
  }
}
```

## Integration Points

- **Triggers `devil-advocate` agent** when critical assumptions (Problem, Customer, Revenue) remain untested for >14 days -- the devil's advocate challenges whether the team is avoiding uncomfortable truths
- **References `evidence-based` rule** for classifying assumption quality -- `[A]` = untested, `[E]` = evidence-based, `[?]` = unknown
- **Works with `/validate` command** to auto-generate experiment cards for the highest-priority untested assumptions
- **Feeds into `validation-reminder` hook** by providing the raw data on which assumptions are tested vs. untested
- **Feeds into `pivot-detector` hook** by tracking the ratio of validated vs. invalidated assumptions over time
- **Uses templates**: Each assumption flagged for testing links to `templates/experiment-card.md` for structured validation

## Why This Matters

The number one cause of startup failure is building something nobody wants. This almost always traces back to untested assumptions that were treated as facts. By making assumptions visible and trackable, you create accountability for validation -- the same way test coverage creates accountability for code quality.
