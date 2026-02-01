# /wellbeing [company context or wellbeing challenge]

## Description

Designs a comprehensive employee wellbeing strategy that maximizes happiness (幸福度) and strengthens company loyalty (ロイヤリティ). Produces a structured assessment across five wellbeing dimensions, prioritized interventions with ROI projections, and an implementation roadmap — then stress-tests the strategy through a devil's advocate review.

## Execution Flow

1. **Input**: Company context (size, industry, current challenges) + specific wellbeing goals or pain points
2. **Scope**: Clarify organization profile, existing programs, available data, and what decisions this informs
3. **Agent 1**: **wellbeing-strategist** — assesses five wellbeing dimensions, identifies priority gaps, designs interventions with ROI projections, creates measurement framework
4. **Agent 2** (optional, parallel): **customer-profiler** — profiles employee segments as "internal customers" to deepen persona-specific needs analysis
5. **Synthesize**: Cross-reference wellbeing gaps with employee segment needs to ensure interventions match the people who need them most
6. **Devil's Advocate** (MANDATORY): Challenges intervention assumptions, questions ROI estimates, flags cultural blind spots, identifies implementation risks
7. **Output**: Structured Wellbeing Assessment Report (see template below)

## Usage Examples

```
/wellbeing 300人規模のSaaS企業、エンジニアの離職率が35%で業界平均の2倍以上
```

```
/wellbeing 製造業1000人規模、健康経営優良法人の認定を目指したい。現在ストレスチェック実施済み
```

```
/wellbeing 50-person startup experiencing burnout across engineering and sales teams, no existing wellbeing programs
```

```
/wellbeing リモートワーク中心の100人企業、社員の帰属意識とエンゲージメントが低下している
```

## Error Handling

- **Input too vague** (e.g., "社員の幸福度を上げたい"): Ask for specifics — Company size? Industry? What triggered this concern? Any data available (turnover rate, survey results)?
- **No data provided**: Proceed with industry benchmarks marked as `[A]` (Assumption). Explicitly flag data gaps and recommend data collection as Step 1.
- **Devil's advocate finds CRITICAL issues**: Surface them in Executive Summary as `[FATAL FLAW]` before any other analysis. Common fatal flaws: legal compliance violations (overtime limits), privacy risks, toxic leadership not addressed.
- **Conflicting priorities**: Present trade-offs explicitly. Do not pretend everything can be done at once. Time-box and sequence.
- **Budget is zero**: Design zero-cost interventions first (management practices, process changes, cultural rituals). Many high-impact interventions cost nothing.

## Related Commands

- **Before this**: `/research` (if entering a new market where employer brand and talent acquisition are key)
- **After this**: `/validate` (test specific wellbeing hypotheses with employee experiments)
- **After this**: `/experiment` (design a detailed pilot for a specific wellbeing intervention)
- **If wellbeing program failing**: `/pivot` (reassess approach based on measurement data)
- **If evidence shows no impact**: `/kill` (decide whether to continue or stop a specific program)

## Agents

- **wellbeing-strategist**: Assesses current state, designs interventions, projects ROI, creates measurement framework
- **customer-profiler** (optional): Treats employees as internal customers — builds segment personas for targeted interventions
- **devil-advocate** (final pass): Challenges assumptions, questions optimistic ROI projections, flags implementation risks and cultural blind spots

## Skills & Templates Referenced

- `employee-wellbeing` skill (five-dimension framework, PERMA model, anti-patterns, Japan context)
- `lean-startup` skill (experiment-first mindset for piloting interventions)
- `validation-patterns` skill (for designing wellbeing experiment pilots)
- `unit-economics` skill (for ROI calculation methodology)
- `wellbeing-assessment` template (structured output format)

## Workflow

### Step 1: Context Gathering (コンテキスト収集)
- Clarify company profile: size, industry, stage, structure
- Identify available data: engagement surveys, turnover data, overtime records, health check results
- Understand triggers: Why now? What pain is being felt?
- Define constraints: Budget, timeline, leadership commitment level
- Set goals: What does success look like in 6 months? 12 months?

### Step 2: Five-Dimension Assessment (5次元アセスメント)
Using the `employee-wellbeing` skill framework:
- **Career Wellbeing** (キャリア充実度): Growth opportunities, skill development, career clarity
- **Social Wellbeing** (社会的つながり): Team dynamics, psychological safety, belonging
- **Financial Wellbeing** (経済的安定): Compensation satisfaction, financial security, equity participation
- **Physical Wellbeing** (身体的健康): Work-life balance, overtime, health support
- **Community Wellbeing** (帰属意識): Mission alignment, organizational pride, advocacy

Score each dimension 1-5 with data quality labels:
- `[E]` Evidence: Based on actual company data
- `[A]` Assumption: Based on industry benchmarks or company profile inference
- `[?]` Unknown: No data — flag as gap requiring collection

### Step 3: Employee Segmentation (従業員セグメント分析)
- Segment employees by relevant dimensions (role, tenure, generation, work style)
- Identify which segments have the largest wellbeing gaps
- Map segment-specific needs to intervention types
- Prioritize segments with highest business impact (e.g., highest turnover, hardest to replace)

### Step 4: Intervention Design (施策設計)
For each priority gap:
- Design light → medium → heavy interventions (experiment ladder)
- Estimate cost in yen ranges (not false precision)
- Define success criteria BEFORE implementation (non-negotiable)
- Assign ownership (specific role, not "HR")
- Identify risks and mitigation

### Step 5: ROI + VOI Projection (投資対効果の予測)
- Calculate expected financial returns (turnover cost savings, productivity gains, healthcare cost reduction)
- Label all projections as assumptions with confidence levels
- Include VOI metrics (employer brand, engagement, culture)
- Benchmark against industry data: 95% of companies measuring wellness ROI see positive returns, median $2+ per $1 invested

### Step 6: Implementation Roadmap (実行ロードマップ)
- Phase 1 (Month 1-3): Quick wins + measurement baseline
- Phase 2 (Month 4-6): Strategic intervention pilots
- Phase 3 (Month 7-12): Scale + first ROI reporting
- Phase 4 (Year 2+): Continuous improvement + certification pursuit

### Step 7: Devil's Advocate Review (デビルズアドボケート・レビュー)
Mandatory critical review covering:
- Are ROI projections realistic or optimistic?
- Are cultural factors adequately addressed?
- What implementation risks are being underestimated?
- Is the program addressing root causes or just symptoms?
- Are there privacy/legal compliance gaps?
- What could cause the program to fail silently?

## Expected Output

```markdown
# Employee Wellbeing Strategy: [Company/Topic]
## Date: YYYY-MM-DD

## Executive Summary
[FATAL FLAW] if applicable
[2-3 sentence overview: current state, top priority, expected impact]

## Organization Profile
[Company details, current programs, available data]

## Five-Dimension Wellbeing Scorecard
| Dimension | Score | Data Quality | Key Finding | Priority |
|-----------|-------|-------------|-------------|----------|
| Career | X/5 | [E]/[A]/[?] | ... | P1/P2/P3 |
| Social | X/5 | [E]/[A]/[?] | ... | P1/P2/P3 |
| Financial | X/5 | [E]/[A]/[?] | ... | P1/P2/P3 |
| Physical | X/5 | [E]/[A]/[?] | ... | P1/P2/P3 |
| Community | X/5 | [E]/[A]/[?] | ... | P1/P2/P3 |

## Employee Segments Analysis
[Segment-specific findings and needs]

## Recommended Interventions
### Quick Wins (0-3 months)
1. [Intervention] — Cost: ¥X / Success: [criteria] / Owner: [role]

### Strategic Investments (3-12 months)
1. [Intervention] — Cost: ¥X / Success: [criteria] / Owner: [role]

## ROI Projection
[Financial model with labeled assumptions]
Expected ROI: X:1 ratio over [timeframe]

## Measurement Framework
| Frequency | Metrics | Target |
|-----------|---------|--------|
| Monthly | [Leading indicators] | ... |
| Quarterly | [Lagging indicators] | ... |
| Annually | [Business impact] | ... |

## Implementation Roadmap
[Phase 1-4 with milestones]

## Devil's Advocate Review
### CRITICAL Findings
[Findings that could derail the strategy]

### HIGH Findings
[Significant risks or blind spots]

### Recommendations
[Specific actions to address findings]

## Data Gaps & Next Steps
[What to collect, how, and by when]

---
Data Quality: [E] Evidence / [A] Assumption / [?] Unknown
Overall Confidence: High / Medium / Low
```

## Rules (変更不可のルール)

1. **Five dimensions mandatory**: All five wellbeing dimensions must be assessed, even with limited data. Unknown dimensions marked `[?]` with data collection plan.
2. **Success criteria before interventions**: No intervention recommended without pre-defined success/failure criteria. Same discipline as experiment cards.
3. **ROI honesty**: All financial projections labeled as assumptions with confidence levels. Never present estimates as facts. If ROI cannot be estimated, say so.
4. **Cultural awareness required**: Every strategy must address Japan-specific factors (建前/本音, 稟議, 残業文化, 個人情報保護法). Strategies that ignore cultural context will fail.
5. **Manager role addressed**: Every intervention must specify how managers are involved. Manager bypass = intervention failure.
6. **Privacy first**: No recommendation that requires individual health data exposure. Aggregate only. Voluntary participation for all programs.
7. **Devil's advocate non-negotiable**: Strategy must be stress-tested. Zero critical findings from devil's advocate = not actually reviewing.
8. **Cheap before expensive**: Recommend the lightest intervention that tests the assumption. Do not jump to expensive programs without validating the underlying hypothesis.
