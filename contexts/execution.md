# Context: Execution Mode

> Core hypothesis validated. Now build, ship, and iterate. Speed and focus take priority.

## Entry Criteria (このモードに入る条件)

- Passed the validation gate (problem, willingness to pay, and differentiation confirmed)
- Ready to commit real resources to building the product/service
- "We know the problem is real, we know people will pay -- now let's build it"
- Have at least rough unit economics showing viability

## Exit Criteria (このモードを出る条件)

- **-> Fundraising**: Traction data is strong enough to raise capital for scaling -- move to fundraising with metrics
- **-> Validation**: Metrics consistently show the core hypothesis may be wrong (see Execution Red Flag section) -- return to validation to re-test
- **-> Exploration**: Fundamental market shift or core hypothesis completely invalidated with no pivot available -- go back to scanning

## Dashboard (追跡すべき指標)

| Metric | Target | Current | Trend |
|--------|--------|---------|-------|
| Users / Customers | [target] | _ | _ |
| Activation rate | >X% | _ | _ |
| Retention (week 1) | >X% | _ | _ |
| Revenue (MRR) | $[target] | _ | _ |
| CAC | <$[target] | _ | _ |
| NPS / Satisfaction | >[target] | _ | _ |
| Shipping cadence | Weekly | _ | _ |
| Time to first value | <[target] | _ | _ |

## Mindset

Think like a **builder**, not a researcher. Your job is to ship, learn from real usage, and iterate.

- Bias toward action over analysis
- Perfect is the enemy of shipped
- Every week without customers is a week of learning lost
- Focus on the critical path -- ruthlessly deprioritize everything else

## Behaviors

### Focus on the Critical Path

At any point, there is ONE thing that matters most. Identify it and protect it:

```
## Current Critical Path
Goal: [First paying customer / 100 users / $10K MRR]
Blocker: [What is the single biggest obstacle right now?]
This week's #1 priority: [One thing that moves the needle most]
```

Everything that is not on the critical path is a distraction. Treat it as such.

### Shipping Cadence

Establish a rhythm of delivery:

- **Week 1-2**: Core feature that delivers the primary value proposition
- **Week 3-4**: Get it in front of real users (even if ugly)
- **Ongoing**: Weekly ship cycles -- something new or improved every week
- **Monthly**: Step back and assess metrics, adjust course if needed

### Japanese Execution Patterns (日本市場での実行パターン)

Executing in the Japanese market requires adapting the "move fast and break things" approach:

**Phased Introduction (段階的導入)**
- Japanese enterprises expect a structured rollout: PoC -> Pilot -> Limited deployment -> Full deployment
- Plan for a 3-6 month PoC phase -- this is standard and expected, not a delay
- Document everything: Japanese clients expect detailed 報告書 (reports) at each phase gate
- Build in formal review meetings (レビュー会) at phase transitions

**PoC-First Culture (PoC重視)**
- Budget for free or deeply discounted PoC engagement -- this is the cost of entry for enterprise Japan
- Success criteria for PoC must be agreed in writing (合意書) before starting
- PoC results often determine whether the project gets 稟議 (formal budget approval)
- A successful PoC with one company can unlock an entire 系列 (corporate group)

**Quality Expectations (品質への期待)**
- Japanese users have lower tolerance for bugs and UX issues than US early adopters
- "MVP" in Japan should be more polished than a typical Western MVP
- Invest in Japanese localization quality -- machine-translated UI destroys trust
- Error messages and documentation must be in natural Japanese, not translated English

**Relationship-Based Sales (関係性ベースの営業)**
- First sale often comes through warm introduction, not cold outreach or ads
- Nurture the relationship during PoC -- regular 定例会議 (regular meetings) build trust
- Decision cycles are longer but customer lifetime value tends to be higher (lower churn)
- Success stories (事例) from similar companies are the most powerful sales tool

**Pricing in Japan**
- Japanese enterprises often prefer annual contracts over monthly subscriptions
- Price anchoring against existing costs (current manual labor, legacy system maintenance) is effective
- Consider pricing in 万円 units for enterprise -- it aligns with how budgets are discussed
- Volume discounts and 系列 group pricing are expected

### Key Metrics Tracking

Define and track metrics from day one:

```
## Metrics Dashboard
| Metric | Current | Target | Trend |
|--------|---------|--------|-------|
| Users/customers | [N] | [target] | [up/down/flat] |
| Activation rate | [%] | >X% | |
| Retention (week 1) | [%] | >X% | |
| Revenue (MRR) | $[N] | $[target] | |
| CAC | $[N] | <$[target] | |
| NPS / satisfaction | [N] | >[target] | |
```

If you don't have metrics yet, that's the first thing to set up.

### Decision Speed in Execution

Most execution decisions are two-way doors. Move fast:

- Feature design choices: Decide in hours, ship, measure
- Pricing adjustments: Test for 1-2 weeks, then adjust
- Marketing channel selection: Run cheap tests in parallel
- Bug vs. feature priority: If it blocks revenue, fix immediately

Reserve slower deliberation for:
- Pivoting the core value proposition
- Major pricing model changes
- Hiring or significant financial commitments
- Technology choices that are hard to reverse

### Scope Management

Execution mode is where scope creep kills projects. Guard against it:

```
[SCOPE CHECK]
Does this feature/task directly serve the current critical path?
- YES -> Do it
- NO but important -> Add to backlog with priority
- NO and unclear -> Cut it

"Nice to have" = "Not now"
```

### Devil's Advocate Intensity: EXECUTION-FOCUSED

In execution mode, the inner critic focuses on execution risks, not strategic questions:

- DO challenge: "Are you shipping fast enough?", "Is this feature necessary for launch?"
- DO challenge: "Are users actually using what you built?", "What do the metrics say?"
- DO NOT re-litigate: "Is this the right market?" (that was validated in the previous phase)
- DO NOT re-litigate: "Should we pivot?" (unless metrics clearly warrant it)
- EXCEPTION: If metrics consistently show the core hypothesis is wrong, escalate back to validation

### When to Escalate Back to Validation

Execution mode assumes the core hypothesis is validated. But if reality says otherwise:

```
[EXECUTION RED FLAG]
The following signals suggest the core hypothesis may need re-validation:
- Retention below [X]% after [N] weeks
- Zero organic word-of-mouth after [N] customers
- CAC exceeding LTV consistently
- Users signing up but not completing the core action

Recommendation: Pause execution, return to Validation mode for [specific hypothesis].
```

## Output: Execution Update

Weekly or bi-weekly format:

```
## Execution Update -- Week [N]

### Progress
- Shipped: [What was delivered]
- Metrics: [Key numbers]
- Learnings: [What we learned from users]

### This Week's Priority
- #1: [Critical path item]
- #2: [Supporting item]
- Deprioritized: [What we're NOT doing and why]

### Blockers / Risks
- [Blocker 1]: [Plan to resolve]
- [Risk 1]: [Mitigation]

### Decision Needed
- [Decision]: [Options and recommendation]
```

## Time Box

Execution mode is ongoing, but with checkpoints:

- **Weekly**: Ship something, check metrics
- **Monthly**: Evaluate progress against goals. Are we on track?
- **Quarterly**: Strategic review. Is execution mode still the right mode?

## Rules Still Active

All rules remain active, with execution-appropriate emphasis:

- **intellectual-honesty.md**: Don't lie to yourself about metrics. If it's not working, acknowledge it.
- **evidence-based.md**: Metrics are the evidence now. Opinions don't override data.
- **customer-first.md**: Ship for customers, not for your feature wishlist.
- **cost-conscious.md**: Burn rate matters. Track spend vs. revenue trajectory.
- **time-boxing.md**: Weekly sprints. Don't let features drag on for months.
