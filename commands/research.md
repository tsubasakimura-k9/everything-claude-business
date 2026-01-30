# /research [topic or business idea]

## Description

Conducts comprehensive market research on a topic or business idea. Produces a structured market brief with quantified opportunity sizing, competitive landscape mapping, and identified gaps — then stress-tests the findings through a devil's advocate review.

## Execution Flow

1. **Input**: Topic or business idea + market boundaries (geography, vertical, customer type)
2. **Scope**: Clarify research topic, define boundaries, identify what decisions this informs
3. **Agent 1** (parallel): **market-researcher** — sizes TAM/SAM/SOM, identifies customer segments, maps pain points and WTP signals
4. **Agent 2** (parallel): **competitor-analyst** — builds competitor matrix, maps positioning, identifies direct/indirect competitors
5. **Synthesize**: Cross-reference customer needs against competitor offerings to identify opportunity gaps
6. **Devil's Advocate** (MANDATORY): Challenges TAM estimates, questions gap analysis, flags risks and confirmation bias
7. **Output**: Structured Market Research Brief (see template below)

## Usage Examples

```
/research AI-powered HR screening tool for Japanese enterprise (従業員1000名以上)
```

```
/research 中小企業向け経理自動化SaaS — 月次決算の工数削減ツール
```

```
/research vertical AI agent for real estate property management in Tokyo metropolitan area
```

## Error Handling

- **Input too vague** (e.g., "AI business"): Ask for specifics — Who is the customer? What geography? What problem?
- **Agents produce conflicting data**: Present both findings with evidence quality tags. Let the devil's advocate adjudicate.
- **Devil's advocate finds CRITICAL issues**: Surface them in Executive Summary as `[FATAL FLAW]` before any other analysis. Do not bury critical findings.
- **Insufficient data available**: Explicitly state `[DATA GAP]` and recommend specific validation steps rather than fabricating estimates.

## Related Commands

- **After this**: `/validate` (test the hypotheses identified in opportunity gaps)
- **After this**: `/pricing` (if the research reveals a viable opportunity, design pricing)
- **Alternative**: `/experiment` (for a lighter-weight test of a specific assumption from the research)
- **If research shows no opportunity**: `/kill` (formalize the decision to stop)

## Agents

- **market-researcher**: Gathers market data, sizes the opportunity (TAM/SAM/SOM), identifies trends and customer segments
- **competitor-analyst**: Maps the competitive landscape, analyzes positioning, identifies strengths/weaknesses of existing players
- **devil-advocate** (final pass): Challenges assumptions, pokes holes in optimistic estimates, flags blind spots

## Skills & Templates Referenced

- `market-research` skill (research frameworks, data source hierarchy)
- `competitor-analysis` skill (Porter's Five Forces, competitive matrix template)
- `lean-startup` skill (for connecting research to actionable hypotheses)

## Workflow

### Step 1: Scope Definition
- Clarify the research topic with the user
- Define the market boundaries (geography, industry vertical, customer type)
- Identify what decisions this research will inform

### Step 2: Market Sizing (market-researcher agent)
- **TAM** (Total Addressable Market): The entire market if you had 100% share
- **SAM** (Serviceable Addressable Market): The segment you can realistically reach
- **SOM** (Serviceable Obtainable Market): What you can capture in 1-3 years
- Cite sources and show calculation methodology (top-down AND bottom-up when possible)
- Identify key market trends and growth drivers

### Step 3: Customer Landscape (market-researcher agent)
- Identify primary customer segments
- Map pain points and unmet needs per segment
- Estimate willingness-to-pay signals where available
- Note any regulatory or structural barriers

### Step 4: Competitive Landscape (competitor-analyst agent)
- Build a competitor matrix with these dimensions:
  - Company name, positioning/value proposition, target segment
  - Pricing model, key strengths, key weaknesses, funding/stage
- Identify direct competitors, indirect competitors, and potential future entrants
- Map competitive positioning (e.g., price vs. feature richness)

### Step 5: Opportunity Gap Analysis
- Cross-reference customer needs (Step 3) against competitor offerings (Step 4)
- Identify underserved segments or unmet needs
- Highlight potential differentiation vectors
- Flag any "why hasn't someone done this?" questions (and attempt to answer them)

### Step 6: Devil's Advocate Review (devil-advocate agent)
- Challenge the TAM/SAM/SOM estimates — are they inflated?
- Question the gap analysis — are the "gaps" real or wishful thinking?
- Identify risks not covered: regulatory, technology, timing, execution
- Ask: "What would make this opportunity NOT worth pursuing?"
- Flag any confirmation bias in the research

### Step 7: Synthesis
- Compile the final market brief

## Expected Output

```markdown
# Market Research Brief: [Topic]

## Executive Summary
[2-3 sentence overview of the opportunity and key finding]

## Market Sizing
| Metric | Estimate | Methodology | Confidence |
|--------|----------|-------------|------------|
| TAM    | $X       | [approach]  | High/Med/Low |
| SAM    | $X       | [approach]  | High/Med/Low |
| SOM    | $X       | [approach]  | High/Med/Low |

### Key Trends
- [Trend 1]
- [Trend 2]

## Customer Segments
| Segment | Size | Pain Points | Willingness to Pay |
|---------|------|-------------|-------------------|
| ...     | ...  | ...         | ...               |

## Competitive Landscape

### Competitor Matrix
| Company | Positioning | Target | Pricing | Strengths | Weaknesses |
|---------|-------------|--------|---------|-----------|------------|
| ...     | ...         | ...    | ...     | ...       | ...        |

### Positioning Map
[Description of competitive positioning]

## Opportunity Gaps
1. [Gap 1]: [Why it exists, why it matters]
2. [Gap 2]: [Why it exists, why it matters]

## Devil's Advocate Challenges
- **Challenge**: [assumption questioned]
  **Response**: [honest assessment]

## Risks & Open Questions
- [Risk/question 1]
- [Risk/question 2]

## Recommended Next Steps
- [Action 1]
- [Action 2]
```

## Rules

- Never present market sizing without showing the methodology
- Always provide confidence levels (High/Medium/Low) for estimates
- The devil's advocate review is NOT optional — it always runs last
- If data is unavailable, say so explicitly rather than fabricating numbers
- Distinguish between facts (cited) and educated estimates (labeled)
