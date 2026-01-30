# /pricing [product/service description]

## Description

Develops a pricing strategy for a product or service. Produces a pricing recommendation backed by unit economics modeling, competitor price comparison, and sensitivity analysis. Ensures pricing is sustainable (covers costs + margin) and competitive (aligned with market expectations).

## Execution Flow

1. **Input**: Product/service description + target customer + cost structure (or best estimates)
2. **Clarify**: Gather product details, customer segment, costs, current pricing (if any)
3. **Agent 1** (parallel): **pricing-strategist** — analyzes cost structure, estimates value ceiling, builds unit economics model
4. **Agent 2** (parallel): **competitor-analyst** — gathers competitor pricing, identifies market price anchors
5. **Synthesize**: Select pricing model, set price point between cost floor and value ceiling, run sensitivity analysis
6. **Output**: Pricing Recommendation with unit economics and implementation notes

## Usage Examples

```
/pricing 中小企業向け経理自動化SaaS — 月次決算の工数を10時間→2時間に削減。インフラ費用は月額5万円、変動費は1社あたり月2000円
```

```
/pricing AI-powered English writing assistant for Japanese business professionals. Target: 従業員100-500名のB2B企業。Competitor range: ¥500-3000/user/month
```

```
/pricing コンサルティングサービス — 生成AI導入支援。1回2時間のワークショップ形式。対象は中堅企業の経営企画部
```

## Error Handling

- **Cost structure unknown**: Ask the user directly — do not guess. Provide a template for them to fill in (fixed costs, variable costs per unit, semi-variable).
- **No competitor data available**: Flag as `[PRICING IN VACUUM WARNING]`. Use value-based pricing as primary approach and recommend competitor research as immediate next step.
- **LTV:CAC ratio below 3:1**: Flag as `[UNIT ECONOMICS WARNING]`. Show what price point or churn rate would fix the ratio. Do not recommend launch without a path to viable economics.
- **User wants to price below cost floor**: Challenge immediately. Require an explicit subsidization strategy (VC funding runway, loss leader strategy with upsell path, etc.).

## Related Commands

- **Before this**: `/research` (to understand market and customer willingness to pay)
- **Before this**: `/validate` (to confirm demand exists before pricing)
- **After this**: `/experiment` (to A/B test price points or validate willingness to pay)
- **After this**: `/pitch` (to present the business case including pricing)

## Agents

- **pricing-strategist**: Analyzes value drivers, selects pricing model, builds the recommendation
- **competitor-analyst**: Gathers and compares competitor pricing data

## Skills & Templates Referenced

- `unit-economics` skill (CAC, LTV, margin calculations, break-even analysis)
- `competitor-analysis` skill (pricing intelligence gathering)
- `pricing-models` reference (freemium, tiered, usage-based, per-seat, etc.)

## Workflow

### Step 1: Product/Service Understanding
- Clarify with the user:
  - What is the product/service?
  - Who is the target customer? (segment, size, budget)
  - What problem does it solve? What is the value to the customer?
  - What are the costs to deliver? (fixed costs, variable costs per unit)
  - Current pricing (if any) and what's working/not working
  - Revenue model preferences or constraints

### Step 2: Cost Structure Analysis (pricing-strategist agent)
- Map the cost structure:

| Cost Type | Item | Amount | Per Unit? |
|-----------|------|--------|-----------|
| Fixed | [e.g., infrastructure] | $/month | No |
| Variable | [e.g., API costs per request] | $/unit | Yes |
| Semi-variable | [e.g., support staff] | $/tier | Stepped |

- Calculate the **cost floor** (minimum price to break even per unit)
- Identify which costs scale with customers vs. usage vs. neither

### Step 3: Value Analysis (pricing-strategist agent)
- Estimate value to the customer:
  - **Cost savings**: What does the customer save by using this? (time, money, headcount)
  - **Revenue generation**: Does this help the customer make more money?
  - **Risk reduction**: Does this reduce a costly risk?
  - **Intangible value**: Status, convenience, peace of mind
- Calculate the **value ceiling** (maximum a rational customer would pay)
- The optimal price lives between the cost floor and value ceiling

### Step 4: Competitor Price Comparison (competitor-analyst agent)
- Build a competitor pricing matrix:

| Competitor | Pricing Model | Entry Price | Mid-Tier | Enterprise | Key Differentiator |
|-----------|---------------|-------------|----------|------------|-------------------|
| [Name] | [model] | $X/mo | $Y/mo | Custom | [what justifies price] |

- Identify the market's **price anchors** (what customers expect to pay)
- Note any competitors using aggressive pricing (loss leaders, freemium)
- Map price-to-value ratio across competitors

### Step 5: Pricing Model Selection (pricing-strategist agent)
- Evaluate candidate pricing models:

| Model | Pros | Cons | Fit Score |
|-------|------|------|-----------|
| Per-seat | Predictable, scales with org | Discourages adoption | ? |
| Usage-based | Aligns with value | Unpredictable revenue | ? |
| Tiered | Clear upgrade path | Feature gating complexity | ? |
| Flat rate | Simple | Leaves money on table | ? |
| Freemium | Low friction acquisition | Conversion risk | ? |
| Value-based | Maximizes capture | Hard to implement | ? |

- Select the recommended model with rationale

### Step 6: Unit Economics Model (pricing-strategist agent)
- Build the unit economics at the recommended price:

| Metric | Value | Notes |
|--------|-------|-------|
| Price per unit | $X | [per month/year/transaction] |
| COGS per unit | $Y | [what it costs to serve one customer] |
| Gross margin | Z% | Price minus COGS |
| CAC (estimated) | $A | Customer acquisition cost |
| LTV (estimated) | $B | Lifetime value |
| LTV:CAC ratio | B:A | Target: >3:1 |
| Payback period | N months | Time to recover CAC |
| Break-even | N units | Units needed to cover fixed costs |

### Step 7: Sensitivity Analysis
- Model how the business changes under different scenarios:

| Scenario | Price | Volume | Revenue | Margin | LTV:CAC |
|----------|-------|--------|---------|--------|---------|
| Aggressive (low price) | $X | High | $R | Low | ? |
| **Recommended** | **$Y** | **Medium** | **$R** | **Good** | **?** |
| Premium (high price) | $Z | Low | $R | High | ? |

- Identify the key variables that most affect profitability
- Stress test: What happens if CAC doubles? If churn increases 50%?

### Step 8: Recommendation Assembly
- Compile the final pricing recommendation

## Expected Output

```markdown
# Pricing Recommendation: [Product/Service]

## Executive Summary
[Recommended pricing model and price point in 2-3 sentences]

## Cost Structure
| Type | Item | Amount |
|------|------|--------|
| Fixed | ... | ... |
| Variable | ... | ... |

**Cost floor (break-even price)**: $X per unit

## Value Analysis
- Customer value estimate: $X per [period]
- Value drivers: [list]

**Value ceiling**: $X per unit

## Competitor Pricing Landscape
| Competitor | Model | Entry | Mid | Enterprise |
|-----------|-------|-------|-----|------------|
| ... | ... | ... | ... | ... |

**Market price anchor**: $X-Y range

## Recommended Pricing

### Model: [e.g., Three-Tier SaaS]

| Tier | Price | Includes | Target Segment |
|------|-------|----------|----------------|
| Starter | $X/mo | [features] | [who] |
| Pro | $Y/mo | [features] | [who] |
| Enterprise | Custom | [features] | [who] |

### Why This Model
[Rationale for the model choice]

### Why This Price Point
[Rationale: positioned between cost floor and value ceiling, competitive context]

## Unit Economics
| Metric | Value |
|--------|-------|
| Gross margin | X% |
| CAC (est.) | $X |
| LTV (est.) | $X |
| LTV:CAC | X:1 |
| Payback period | X months |
| Break-even | X customers |

## Sensitivity Analysis
| Scenario | Price | Volume | Revenue | Margin |
|----------|-------|--------|---------|--------|
| Low price / high volume | ... | ... | ... | ... |
| **Recommended** | ... | ... | ... | ... |
| High price / low volume | ... | ... | ... | ... |

### Key Risk Variables
- [Variable 1]: If X changes by Y%, margin drops to Z%
- [Variable 2]: ...

## Implementation Notes
- Launch strategy: [e.g., start with flat rate, add tiers at N customers]
- Grandfather existing customers? [Yes/No]
- Annual discount: [Recommendation]
- Price increase cadence: [Recommendation]
```

## Rules

- Never recommend a price below the cost floor without an explicit subsidization strategy
- Competitor pricing comparison is mandatory — never price in a vacuum
- Unit economics must show LTV:CAC > 3:1 or explicitly flag the risk
- Sensitivity analysis must include at least 3 scenarios
- If cost data is unknown, ask the user — do not guess at cost structure
- Always consider whether a free tier is appropriate and state the rationale either way
- Price is not just a number — always recommend the pricing MODEL (how to charge) alongside the price POINT (how much)
