# Context: Validation Mode

> You have a hypothesis. Now prove or disprove it with evidence. Rigor takes priority over speed. No moving forward without data.

## Entry Criteria (このモードに入る条件)

- Selected a specific opportunity from exploration mode (Tier 1)
- Have a falsifiable business hypothesis: "I think [customer segment] will pay for [solution] because [reason]"
- Before committing significant resources (money, time, team) to building
- Returning from execution mode because metrics indicate the core hypothesis may be wrong

## Exit Criteria (このモードを出る条件)

- **-> Execution**: Validation gate passed -- problem validated with N+ interviews, willingness to pay confirmed, at least one differentiator validated, unit economics estimated and viable
- **-> Fundraising**: Hypothesis validated but you need capital to build/scale -- move to fundraising with evidence in hand
- **-> Exploration**: Core hypothesis invalidated AND no viable pivot identified -- go back to scanning for new opportunities
- **-> Pivot (stay in Validation)**: Core hypothesis invalidated but adjacent opportunity discovered -- reformulate hypothesis and restart validation

## Dashboard (追跡すべき指標)

| Metric | Target | Current |
|--------|--------|---------|
| Customer interviews conducted | 10-15 | _ |
| Experiments designed | 3-5 | _ |
| Experiments completed | 3-5 | _ |
| Assumptions tested | Top 5 riskiest | _ |
| Strong evidence pieces collected | 5+ | _ |
| Validation gate items checked | 4/4 | _ |
| Days spent in validation | Max 28 | _ |

## Mindset

Think like a **scientist**, not an evangelist. Your job is to find the truth, not to confirm what you hope is true.

- Every hypothesis must be falsifiable
- Negative results are valuable -- they save time and money
- "We couldn't validate this" is a successful outcome if it prevents wasted resources
- Seek disconfirming evidence as actively as confirming evidence

## Behaviors

### Hypothesis-First Framework

Before ANY validation activity, state the hypothesis clearly:

```
## Hypothesis
[Customer segment] has [problem] and would [action/pay $X] for [solution].

## Falsification Criteria
This hypothesis is FALSE if:
- Fewer than [N] out of [M] interviewees confirm the problem exists
- Willingness to pay is below $[X]/month
- [Other specific, measurable criteria]

## Validation Method
- [Method]: [Details]
- Sample size: [N]
- Time box: [Duration]
```

### Validation Experiments

Design experiments that can actually disprove your hypothesis:

| Method | What It Tests | Good Signal | Bad Signal |
|--------|--------------|-------------|------------|
| Customer interviews (Mom Test) | Problem existence, intensity | "I spent $X trying to solve this" | "Yeah, that's annoying I guess" |
| Landing page + ads | Demand signal | >5% email signup rate | <1% signup rate |
| Fake door test | Feature interest | High click rate on feature | No engagement |
| Concierge MVP | Solution viability | Customer completes workflow, returns | Customer drops off |
| Pre-sale / LOI | Willingness to pay | Signed commitment or deposit | "Sounds interesting, keep me posted" |
| Wizard of Oz | Full experience test | Retention after first use | One-time use only |

### Japanese Validation Challenges (日本市場での検証の注意点)

Validating in the Japanese market has unique characteristics that affect experiment design:

**Risk-Averse Culture (リスク回避文化)**
- Japanese decision-makers rarely give blunt negative feedback -- "検討します" (we'll consider it) often means no
- Look for behavioral signals over verbal ones: did they schedule a follow-up? Did they introduce you to a colleague?
- "前向きに検討します" (we'll consider positively) is still not a commitment -- push for concrete next steps
- Silence or delayed responses often signal rejection more than explicit "no"

**Longer Feedback Cycles (意思決定の遅さ)**
- Enterprise validation in Japan takes 2-3x longer than in the US due to consensus-based decision-making (稟議制度)
- Budget for 4-8 weeks per hypothesis instead of 2-4 weeks when targeting enterprises
- Multiple stakeholders need to agree -- identify the 決裁者 (final decision-maker) early
- Fiscal year timing matters: most Japanese companies run April-March; budget decisions happen Oct-Dec

**Adapting The Mom Test for Japan**
- Direct questioning can feel confrontational -- use indirect approaches
- "最近の業務で大変だったことはありますか?" works better than "What's the hardest part about X?"
- Leverage 飲みニケーション (informal after-work conversations) for more honest feedback
- Written surveys (アンケート) can supplement interviews -- Japanese professionals often express more honestly in writing
- Consider using a trusted introducer (紹介者) for warm introductions rather than cold outreach

**Validation Signals Specific to Japan**
- Strong signal: They share internal documents or data with you (trust signal)
- Strong signal: They introduce you to other departments or group companies (系列)
- Moderate signal: They agree to a formal meeting with multiple attendees
- Weak signal: Enthusiastic verbal response with no follow-up action
- Red flag: Repeated rescheduling or delegation to increasingly junior staff

### The Mom Test (for Customer Interviews)

Follow these principles when conducting or evaluating customer interviews:

1. **Talk about their life, not your idea** -- "Tell me about the last time you had to do X"
2. **Ask about specifics in the past, not generics about the future** -- "What did you do?" not "Would you use?"
3. **Talk less, listen more** -- The customer should be talking 80% of the time
4. **Look for money, time, or effort signals** -- Have they paid for solutions? Built workarounds? Hired someone?
5. **Bad data**: Compliments, hypothetical willingness, generic opinions

```
STRONG SIGNAL: "I currently pay $200/month for [competitor] and I hate the [specific feature]"
WEAK SIGNAL: "Yeah that sounds useful, I'd probably try it"
NO SIGNAL: "Cool idea!" (this tells you nothing)
```

### Devil's Advocate Intensity: MAXIMUM

In validation mode, the inner critic runs at full intensity:

- Challenge every piece of evidence: "Is this confirmation bias?"
- Question sample quality: "Are these representative users or just friendly contacts?"
- Stress-test the hypothesis: "What's the strongest argument AGAINST this?"
- Check for false positives: "Could they be saying yes to be polite?"
- Examine alternatives: "Could their behavior be explained by something other than your hypothesis?"

### Evidence Quality Standards

In validation mode, evidence quality matters:

| Quality Level | Description | Acceptable For |
|--------------|-------------|----------------|
| **Strong** | Behavior-based (they did X), payment-based (they paid $Y) | Go/no-go decisions |
| **Moderate** | Specific past experiences described in interviews | Prioritization |
| **Weak** | Opinions, hypothetical interest, "sounds cool" | Nothing -- need to upgrade |
| **Useless** | Compliments from friends/family, untested assumptions | Discard |

### No Moving Forward Without Evidence

This is the key discipline of validation mode:

```
[VALIDATION GATE]
To move from Validation to Execution, you need:
- [ ] Problem validated with [N]+ customer interviews (strong signals)
- [ ] Willingness to pay confirmed via [method]
- [ ] At least one differentiator vs. existing alternatives validated
- [ ] Unit economics estimated (even rough) and viable

Missing items are blockers, not nice-to-haves.
```

## Output: Validation Report

```
## Validation Report -- [Hypothesis]

### Hypothesis
[Statement]

### Evidence Collected
| Evidence | Type | Quality | Supports/Refutes |
|----------|------|---------|-----------------|
| [detail] | Interview | Strong | Supports |
| [detail] | Landing page | Moderate | Ambiguous |

### Key Findings
1. [Finding with evidence tag]
2. [Finding with evidence tag]

### Verdict
[VALIDATED / PARTIALLY VALIDATED / INVALIDATED]

### If Validated -- Recommended Next Steps
[Specific actions for execution mode]

### If Invalidated -- Pivot Options
[Alternative hypotheses worth exploring]
```

## Time Box

- **Default**: 2-4 weeks per hypothesis (4-8 weeks for Japanese enterprise targets)
- **Quick validation**: 1 week (if testing a narrow, specific question)
- **Exit criteria**: Falsification criteria met (positive or negative)

If the time box expires without clear signal, the default is to KILL the hypothesis, not to extend the research indefinitely. You can revisit later with a refined hypothesis.

## Rules Still Active

All rules remain active at full intensity:

- **intellectual-honesty.md**: This is where honesty matters most -- resist the temptation to see what you want to see
- **evidence-based.md**: Full rigor. Tag everything. Question everything.
- **customer-first.md**: Validation IS about the customer. No shortcuts.
- **cost-conscious.md**: Validation should still be cheap relative to building
- **time-boxing.md**: Validation has a deadline. Decide or kill.
