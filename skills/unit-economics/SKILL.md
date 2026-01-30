# Unit Economics

## Quick Reference
- **Core idea**: Analyze revenue and costs per single "unit" (customer/transaction) to determine if the business model is fundamentally profitable
- **Key question**: "Do we make money on each customer, and if so, how much?"
- **When to use**: Before scaling, fundraising prep, pricing decisions, growth strategy evaluation
- **Output**: LTV, CAC, LTV:CAC ratio, payback period, contribution margin -- with clear pass/fail benchmarks
- **Time**: 2-4 hours for initial analysis; ongoing monthly tracking

## Overview

Unit economics is the analysis of revenue and costs associated with a single "unit" of your business -- typically one customer, one transaction, or one product sold. It answers the fundamental question: **"Do we make money on each unit, and if so, how much?"**

If your unit economics don't work, scaling the business just means losing money faster. Conversely, strong unit economics give you confidence that growth spending will pay off.

## When to Apply

- Before investing in paid acquisition or scaling marketing spend
- Fundraising preparation (investors scrutinize unit economics)
- Evaluating whether to raise prices, cut costs, or change the business model
- Comparing customer segments to decide where to focus
- Assessing whether a business can become profitable
- Post-launch when early revenue data is available (3+ months minimum)

## When NOT to Use

- **Pre-revenue stage with no data**: If you have zero customers, you cannot calculate unit economics. Use `skills/pretotyping/SKILL.md` or `skills/validation-patterns/SKILL.md` to first validate demand.
- **Market sizing questions**: Unit economics tells you about profitability per customer, not total market opportunity. For market size, use `skills/tam-sam-som/SKILL.md`.
- **Strategic positioning questions**: Knowing your LTV:CAC ratio doesn't tell you WHAT to build. For product direction, use `skills/jobs-to-be-done/SKILL.md`.
- **Less than 3 months of data**: LTV projections with less than 3 months of churn data are fiction. Acknowledge the uncertainty explicitly.

## Core Metrics and Formulas

### 1. Customer Acquisition Cost (CAC)

**What it measures:** How much it costs to acquire one new customer.

```
CAC = Total Sales & Marketing Spend / Number of New Customers Acquired
```

**Detailed version:**

```
CAC = (Marketing spend + Sales salaries + Sales commissions + Sales tools
       + Marketing tools + Agency fees + Ad spend)
      / New customers acquired in the same period
```

**Important nuances:**
- **Blended CAC**: All customers (organic + paid). Usually lower.
- **Paid CAC**: Only paid-channel customers. More honest for forecasting.
- **Fully-loaded CAC**: Includes overhead (office, management time). Most conservative.
- **Time lag**: A customer acquired in March may have first been touched in January. Consider using cohort-based attribution.

**Concrete example (SaaS -- USD):**
```
Monthly marketing spend:    $50,000
Monthly sales team cost:    $30,000
New customers this month:   200

CAC = ($50,000 + $30,000) / 200 = $400 per customer
```

**Concrete example (AI研修サービス -- JPY):**
```
月間マーケティング費用:        ¥500,000 (LinkedIn広告 + セミナー開催)
月間営業コスト:               ¥300,000 (提案書作成、商談の人件費)
今月の新規契約:               2社

CAC = (¥500,000 + ¥300,000) / 2 = ¥400,000/社 (approx. $2,650)
```

---

### 2. Lifetime Value (LTV / CLV)

**What it measures:** The total net revenue you expect from a customer over their entire relationship with you.

**Simple formula (subscription business):**

```
LTV = ARPU x Gross Margin % x Average Customer Lifetime

where:
  ARPU = Average Revenue Per User (per month)
  Average Customer Lifetime = 1 / Monthly Churn Rate
```

**Equivalent form:**

```
LTV = (ARPU x Gross Margin %) / Monthly Churn Rate
```

**Concrete example (SaaS -- USD):**
```
ARPU:              $50/month
Gross Margin:      80%
Monthly Churn:     3%

Customer Lifetime = 1 / 0.03 = 33.3 months
LTV = $50 x 0.80 x 33.3 = $1,333
  or equivalently:
LTV = ($50 x 0.80) / 0.03 = $1,333
```

**Concrete example (AI研修サービス -- JPY):**
```
研修1回の売上:     ¥800,000
年間平均契約回数:   3回/年
粗利率:           70% (外部講師費用控除後)
平均契約継続期間:   2年

LTV = ¥800,000 x 3 x 0.70 x 2 = ¥3,360,000 (approx. $22,300)
```

**With expansion revenue (net revenue retention > 100%):**

```
LTV = ARPU x Gross Margin % / (Churn Rate - Net Expansion Rate)
```

If expansion exceeds churn, LTV is theoretically infinite -- but use a practical cap (e.g., 5-year horizon).

**For non-subscription businesses (e-commerce, marketplace):**

```
LTV = Average Order Value x Purchase Frequency x Gross Margin % x Average Customer Lifespan
```

**Concrete example (ECサイト -- JPY/USD):**
```
平均注文額 (AOV):           ¥12,000 ($80)
年間購入頻度:               4回/年
粗利率:                    40%
平均顧客寿命:               3年

LTV = ¥12,000 x 4 x 0.40 x 3 = ¥57,600 (approx. $384)
```

---

### 3. LTV:CAC Ratio

**What it measures:** The return on your customer acquisition investment.

```
LTV:CAC = LTV / CAC
```

**Benchmarks:**

| Ratio | Interpretation |
|---|---|
| < 1:1 | Losing money on every customer. Unsustainable. |
| 1:1 | Breaking even (before overhead). Still losing money. |
| 2:1 | Marginal. May work if overhead is very low. |
| **3:1** | **Healthy. Industry standard target for SaaS.** |
| 5:1+ | Very healthy, but possibly under-investing in growth. |

**Concrete example (SaaS):**
```
LTV:  $1,333
CAC:  $400
LTV:CAC = $1,333 / $400 = 3.3:1  ✓ Healthy
```

**Concrete example (AI研修サービス):**
```
LTV:  ¥3,360,000
CAC:  ¥400,000
LTV:CAC = ¥3,360,000 / ¥400,000 = 8.4:1  ✓ Very healthy (possibly under-investing in growth)
```

---

### 4. CAC Payback Period

**What it measures:** How many months it takes to recover the cost of acquiring a customer.

```
CAC Payback Period = CAC / (ARPU x Gross Margin %)
```

**Benchmarks:**

| Payback Period | Interpretation |
|---|---|
| < 6 months | Excellent. Fast cash recovery. |
| 6-12 months | Good. Standard for SMB SaaS. |
| 12-18 months | Acceptable for mid-market SaaS. |
| 18-24 months | Typical for enterprise SaaS. |
| > 24 months | Risky unless you have strong retention data and capital. |

**Concrete example (SaaS -- USD):**
```
CAC:           $400
ARPU:          $50/month
Gross Margin:  80%

Monthly gross profit per customer = $50 x 0.80 = $40
Payback = $400 / $40 = 10 months  ✓ Good
```

**Concrete example (AI研修 -- JPY):**
```
CAC:           ¥400,000
研修1回の粗利:  ¥800,000 x 0.70 = ¥560,000

Payback = ¥400,000 / ¥560,000 = 0.7回 ≈ 初回研修で回収  ✓ Excellent
```

---

### 5. Gross Margin

**What it measures:** Revenue minus the direct cost of delivering the product/service.

```
Gross Margin % = (Revenue - COGS) / Revenue x 100
```

**What counts as COGS (Cost of Goods Sold):**

| Business Type | Typical COGS |
|---|---|
| SaaS | Hosting, infrastructure, customer support, payment processing |
| E-commerce | Product cost, shipping, packaging, payment processing |
| Marketplace | Payment processing, fraud prevention, customer support |
| Services | Consultant salaries, tools used for delivery |
| AI研修 | 講師人件費, 資料作成費, 会場費, 交通費 |

**Benchmarks by business type:**

| Business Type | Typical Gross Margin |
|---|---|
| SaaS | 70-85% |
| E-commerce | 30-50% |
| Marketplace | 60-75% (on take rate) |
| Professional services | 50-60% |
| AI研修・コンサルティング | 60-75% |
| Hardware | 25-40% |

---

### 6. Contribution Margin

**What it measures:** Revenue minus all variable costs (COGS + variable sales & marketing costs per unit).

```
Contribution Margin = Revenue per Unit - Variable Costs per Unit

Contribution Margin % = Contribution Margin / Revenue per Unit x 100
```

**Difference from Gross Margin:**
- Gross Margin subtracts only COGS.
- Contribution Margin also subtracts variable acquisition costs, variable support costs, etc.
- Contribution Margin is more useful for "should we acquire this customer?" decisions.

---

### 7. Churn Rate

**What it measures:** The percentage of customers (or revenue) lost in a given period.

**Customer churn (logo churn):**

```
Monthly Customer Churn = Customers lost in month / Customers at start of month
```

**Revenue churn (dollar churn):**

```
Monthly Revenue Churn = MRR lost from churned + downgraded customers / MRR at start of month
```

**Net Revenue Churn (includes expansion):**

```
Net Revenue Churn = (Churned MRR + Contraction MRR - Expansion MRR) / Starting MRR
```

If net revenue churn is negative, you have **net revenue retention > 100%** -- existing customers are growing faster than they're leaving. This is the gold standard for SaaS.

**Benchmarks (monthly):**

| Segment | Acceptable Monthly Churn |
|---|---|
| SMB SaaS | 3-5% |
| Mid-market SaaS | 1-2% |
| Enterprise SaaS | 0.5-1% |
| Consumer subscription | 5-10% |

**Annual churn from monthly:**

```
Annual Churn = 1 - (1 - Monthly Churn)^12
```

Example: 3% monthly churn = 1 - (0.97)^12 = 31% annual churn.

---

## Industry Benchmarks Summary

| Metric | SaaS (SMB) | SaaS (Enterprise) | E-commerce | Marketplace |
|---|---|---|---|---|
| Gross Margin | 70-80% | 75-85% | 30-50% | 60-75% |
| LTV:CAC | 3:1+ | 3:1+ | 3:1+ | 3:1+ |
| CAC Payback | 6-12 mo | 12-24 mo | Immediate-3 mo | 3-6 mo |
| Monthly Churn | 3-5% | 0.5-1% | N/A (use repurchase rate) | 2-5% |
| Net Revenue Retention | 90-100% | 110-130% | N/A | 100-110% |

## When Unit Economics "Work" vs "Don't Work"

### They work when:

- **LTV:CAC >= 3:1** and you have confidence in your churn data (at least 12 months of data).
- **CAC payback < 18 months** (or you have the capital to fund longer payback).
- **Gross margin > 60%** for software, > 30% for physical products.
- **Churn is stable or declining** over time (not getting worse as you scale).
- **CAC is stable or declining** as you scale (not exhausting your cheapest channels).

### They don't work when:

- **LTV:CAC < 1:1** -- you lose money on every customer. No amount of volume fixes this.
- **Churn is increasing** as you scale -- a sign of product-market fit issues.
- **CAC is increasing faster than LTV** -- common when you exhaust early adopters and move to less motivated segments.
- **Gross margin is negative** -- you're paying more to deliver than you earn. Need to restructure pricing or costs.
- **Payback > 24 months with limited capital** -- you'll run out of cash before the economics pay off.

### Warning signs:

- **Blended CAC looks great but paid CAC is terrible.** You're riding organic growth that may not last.
- **LTV is based on < 6 months of data.** You're projecting, not measuring. Be skeptical.
- **"We'll improve retention later."** Maybe, but model your economics with current retention.
- **Cohort performance is degrading.** Each new cohort churns faster or has lower ARPU than the last.

## Calculation Templates

### Template 1: SaaS Unit Economics Calculator (Copy-Pasteable)

```
=== INPUTS ===
Monthly subscription price:          $50          (¥7,500)
Gross margin %:                      80%
Monthly customer churn rate:         3%
Monthly marketing spend:             $50,000      (¥7,500,000)
Monthly sales team cost:             $30,000      (¥4,500,000)
New customers per month:             200

=== CALCULATIONS ===
ARPU (monthly):                      $50          (¥7,500)
Gross profit per customer (monthly): $50 x 0.80 = $40 (¥6,000)

CAC:                                 ($50,000 + $30,000) / 200 = $400 (¥60,000)
Customer Lifetime:                   1 / 0.03 = 33.3 months
LTV:                                 $40 x 33.3 = $1,333 (¥200,000)
LTV:CAC Ratio:                       $1,333 / $400 = 3.3:1  ✓
CAC Payback (months):                $400 / $40 = 10 months  ✓

=== HEALTH CHECK ===
[✓] LTV:CAC >= 3:1? YES (3.3:1)
[✓] CAC Payback < 18 months? YES (10 months)
[✓] Gross Margin >= 70%? YES (80%)
[✓] Monthly Churn <= 5%? YES (3%)
```

### Template 2: E-commerce Unit Economics Calculator (Copy-Pasteable)

```
=== INPUTS ===
Average order value (AOV):           ¥12,000      ($80)
COGS per order:                      ¥5,400       ($36)
Shipping cost per order:             ¥800         ($5.30)
Payment processing per order:        ¥400         ($2.70)
Orders per customer per year:        4
Average customer lifespan (years):   3
Customer acquisition cost:           ¥4,500       ($30)

=== CALCULATIONS ===
Gross profit per order:              ¥12,000 - ¥5,400 - ¥800 - ¥400 = ¥5,400 ($36)
Gross margin %:                      ¥5,400 / ¥12,000 = 45%

Annual revenue per customer:         ¥12,000 x 4 = ¥48,000 ($320)
Annual gross profit per customer:    ¥5,400 x 4 = ¥21,600 ($144)
LTV:                                 ¥21,600 x 3 = ¥64,800 ($432)
LTV:CAC Ratio:                       ¥64,800 / ¥4,500 = 14.4:1  ✓
Payback (orders):                    ¥4,500 / ¥5,400 = 0.83 orders (first order!)  ✓

=== HEALTH CHECK ===
[✓] LTV:CAC >= 3:1? YES (14.4:1)
[✓] First order profitable? YES (¥5,400 gross profit > ¥4,500 CAC)
[ ] Repeat purchase rate > 30%? CHECK YOUR DATA
```

### Template 3: Marketplace Unit Economics Calculator (Copy-Pasteable)

```
=== INPUTS ===
Average transaction value (GMV):     ¥150,000     ($1,000)
Take rate (commission %):            15%
Variable cost per transaction:       ¥3,000       ($20) (payment processing, fraud, support)
Buyer acquisition cost:              ¥15,000      ($100)
Seller acquisition cost:             ¥45,000      ($300)
Buyer transactions per year:         6
Seller transactions per year:        24
Average buyer lifespan (years):      2
Average seller lifespan (years):     3

=== CALCULATIONS ===
Revenue per transaction:             ¥150,000 x 0.15 = ¥22,500 ($150)
Gross profit per transaction:        ¥22,500 - ¥3,000 = ¥19,500 ($130)
Gross margin on revenue:             ¥19,500 / ¥22,500 = 86.7%

Buyer LTV:                           ¥19,500 x 6 x 2 = ¥234,000 ($1,560)
Seller LTV:                          ¥19,500 x 24 x 3 = ¥1,404,000 ($9,360)
Buyer LTV:CAC:                       ¥234,000 / ¥15,000 = 15.6:1  ✓
Seller LTV:CAC:                      ¥1,404,000 / ¥45,000 = 31.2:1  ✓

=== HEALTH CHECK ===
[✓] Both buyer AND seller LTV:CAC >= 3:1? YES
[✓] Take rate competitive with market? CHECK (typical 10-20%)
[ ] Supply-side or demand-side constrained? ASSESS
```

### Template 4: Cohort Analysis Table

Track how each monthly cohort performs over time:

```
| Cohort   | Month 0 | Month 1 | Month 2 | Month 3 | Month 6 | Month 12 |
|----------|---------|---------|---------|---------|---------|----------|
| Jan 2026 | 100%    |   %     |   %     |   %     |   %     |    %     |
| Feb 2026 | 100%    |   %     |   %     |   %     |   %     |          |
| Mar 2026 | 100%    |   %     |   %     |   %     |   %     |          |
| Apr 2026 | 100%    |   %     |   %     |   %     |          |          |

Notes:
- Track retention % (customers still active) or cumulative revenue per customer
- Healthy pattern: retention curve flattens over time
- Unhealthy pattern: each cohort drops faster than the previous one
```

## Anti-Patterns (これをやったらアウト)

- **Projected LTV with 3 Months of Data**: The founder says "Our LTV is $5,000" based on 3 months of revenue and a churn projection. This is fiction. With 3 months of data, you have a hypothesis, not a metric. Flag and insist on capping projections (e.g., 12-month LTV).
- **Blended CAC Deception**: The team reports $50 CAC but 80% of customers are organic. Paid CAC is actually $250. When organic growth plateaus, the real economics are exposed. Always ask for segmented CAC.
- **Ignoring Gross Margin in LTV**: Calculating LTV as ARPU x Lifetime without subtracting COGS. A $100/month customer with 30% margin contributes $30/month, not $100. Always use gross-margin-adjusted LTV.
- **"Scale Will Fix It"**: Unit economics are negative, but the team believes "at scale, costs will drop." Sometimes true (hosting costs, bulk pricing), but rarely enough to flip negative to positive. Model the specific scale effect, don't assume it.
- **全体平均の罠 (Average Trap)**: Enterprise customers at 5:1 LTV:CAC and SMB customers at 0.5:1 LTV:CAC average to 2.75:1. The blended number looks OK, but the SMB segment is destroying value. Always segment.
- **解約率を無視 (Ignoring Churn)**: Reporting revenue growth while churn accelerates. If you're adding 100 customers/month but losing 50, your net addition is declining fast. Celebrate net growth, not gross adds.

## Japanese Business Example: AI SaaSのユニットエコノミクス分析

**Context**: A Japanese startup building an AI-powered 業務マニュアル自動生成 (operations manual auto-generation) SaaS for 中小企業 (SMBs).

```
=== INPUTS ===
月額サブスクリプション:             ¥50,000/月 ($330/month)
粗利率:                           75% (AWSインフラ + カスタマーサポート控除)
月次解約率:                        4%
月間マーケティング費用:             ¥1,000,000 ($6,600)
月間営業コスト:                    ¥500,000 ($3,300)
月間新規顧客数:                    8社

=== CALCULATIONS ===
ARPU:                              ¥50,000/月
月次粗利/顧客:                     ¥50,000 x 0.75 = ¥37,500
CAC:                               (¥1,000,000 + ¥500,000) / 8 = ¥187,500 ($1,240)
顧客寿命:                          1 / 0.04 = 25ヶ月
LTV:                               ¥37,500 x 25 = ¥937,500 ($6,200)
LTV:CAC:                           ¥937,500 / ¥187,500 = 5.0:1  ✓
CAC回収期間:                       ¥187,500 / ¥37,500 = 5ヶ月  ✓

=== HEALTH CHECK ===
[✓] LTV:CAC >= 3:1? YES (5.0:1)
[✓] CAC Payback < 18 months? YES (5 months)
[✓] Gross Margin >= 70%? YES (75%)
[✓] Monthly Churn <= 5%? YES (4%, but close to limit)

=== 注意点 ===
- 月次解約率4%は年間換算で39%。中小企業SaaSとしては許容範囲内だが改善余地あり
- 解約率が5%を超えるとLTVが¥750,000に低下し、LTV:CACが4.0:1に下がる
- IT導入補助金を活用すると初年度のARPUが実質下がるため、補助金有無で分けて計算すべき
```

## Common Pitfalls

1. **Using projected LTV instead of observed LTV.** Your LTV formula assumes stable churn. If you have 3 months of data and 2% monthly churn, your projected LTV assumes that rate holds for 50 months. It probably won't. Use a discounted or capped LTV (e.g., 3-year cap).

2. **Excluding costs from CAC.** If your CEO spends 30% of their time on sales calls, that's part of CAC. If your engineers build a free tool for lead generation, that engineering time is part of CAC.

3. **Averaging across segments.** Your enterprise customers may have LTV:CAC of 5:1 while SMB customers are at 1:1. Blended metrics hide this. Always segment.

4. **Ignoring the time value of money.** $1,333 LTV over 33 months is not the same as $1,333 today. For long payback periods (>12 months), consider discounting future cash flows.

5. **Optimizing one metric in isolation.** Cutting CAC by removing the sales team might increase churn. Improving retention by offering discounts might lower ARPU. Always look at the system.

6. **Forgetting about gross margin.** Revenue is not profit. A $100/month customer with 30% gross margin contributes $30/month. Calculate LTV on gross profit, not revenue.

7. **Not tracking by cohort.** Averages lie. If your January cohort retains at 95% and your June cohort retains at 80%, the average is 87.5% -- but the trend is terrible. Always track cohorts individually.

## References

- Skok, David. "SaaS Metrics 2.0." ForEntrepreneurs.com. (The definitive guide to SaaS unit economics)
- Tunguz, Tomasz and Frank Bien. *Winning with Data.* Wiley, 2016.
- Campbell, Patrick. "Unit Economics: The Foundation of Your Business Model." ProfitWell.
- Croll, Alistair and Benjamin Yoskovitz. *Lean Analytics.* O'Reilly Media, 2013.
