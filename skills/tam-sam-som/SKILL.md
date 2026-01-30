# TAM / SAM / SOM -- Market Sizing

> **Quick Reference**
> - **Core idea**: 市場規模を3層（全体→到達可能→獲得可能）で構造化する
> - **Key question**: この事業の市場はどれくらい大きく、現実的にどこまで取れるか？
> - **When to use**: 投資判断、Go/No-Go、ピッチデック、事業計画時
> - **Output**: TAM/SAM/SOM数値（Top-Down & Bottom-Up）+ サニティチェック
> - **Time**: 2-5日（調査含む）

## Overview

Market sizing estimates how large the opportunity is for your business. The TAM-SAM-SOM framework breaks this into three concentric layers:

- **TAM (Total Addressable Market):** The total market demand for your product or service if you had 100% market share and no constraints. The theoretical maximum.
- **SAM (Serviceable Addressable Market):** The portion of TAM that your business model can actually serve, given your geography, pricing, distribution, and product capabilities.
- **SOM (Serviceable Obtainable Market):** The portion of SAM you can realistically capture in the near term (typically 1-3 years), given your current resources, competition, and go-to-market.

Think of it as a funnel:

```
  +---------------------------+
  |           TAM             |  "If we sold to everyone in the world"
  |   +-------------------+   |
  |   |       SAM         |   |  "If we sold to everyone we CAN reach"
  |   |   +-----------+   |   |
  |   |   |    SOM    |   |   |  "What we'll actually capture"
  |   |   +-----------+   |   |
  |   +-------------------+   |
  +---------------------------+
```

## When to Apply

| Situation | Purpose |
|---|---|
| Fundraising / pitch deck | Investors want to see market size (especially TAM and SOM) |
| Go/no-go decision on a new product | Is the market big enough to justify the investment? |
| Strategic planning | Which market segments to prioritize? |
| Competitive analysis | Understanding your share relative to the total |
| Pricing strategy | What's the revenue potential at different price points? |
| Expansion planning | Sizing adjacent markets before entering them |

## When NOT to Use

| Situation | Why Not | Better Alternative |
|---|---|---|
| まだ顧客の課題が不明確 | 市場規模より先に課題の実在性を確認すべき | > **See also**: `mom-test/` or `jobs-to-be-done/` |
| 既存市場が存在しないカテゴリー創造型 | TAM=0になってしまう。問題の規模を算出すべき | Value-Theory Method（後述）で問題コストから推計 |
| 短期の実行計画に落とし込みたい | TAM/SAMは戦略レベル。実行にはSOMの分解が必要 | > **See also**: `unit-economics/` のCapacity-Based SOM計算 |
| 単一顧客への提案書 | 市場全体の話は1社への提案には不要 | 顧客固有のROI分析 |

## Two Approaches: Top-Down vs Bottom-Up

### Top-Down Approach

Start with a large, known market number and narrow it down.

```
TAM = Industry report total market size
SAM = TAM x % relevant to your geography/segment/use case
SOM = SAM x % you can realistically capture
```

**Pros:** Fast, uses authoritative data sources (Gartner, IDC, Statista, 矢野経済研究所, 富士キメラ総研).
**Cons:** Often inflated, relies on someone else's definition of the market, harder to defend the filtering logic.

**Example: Project Management SaaS in Japan**

```
TAM: Global project management software market = $7.0B (Statista 2025)
     = 約1兆500億円
SAM: Japan = ~8% of global SaaS spend = $7.0B x 8% = $560M (約840億円)
     Filter: SMB segment only (~40%) = $560M x 40% = $224M (約336億円)
SOM: Year 1 capture estimate = $224M x 1% = $2.2M (約330万ドル / 約3.3億円)
```

### Bottom-Up Approach

Start with your specific unit economics and scale up.

```
SOM = Number of customers you can acquire x Revenue per customer
SAM = Total potential customers in your reachable market x Revenue per customer
TAM = Total potential customers globally x Revenue per customer
```

**Pros:** More credible, grounded in your actual business, easier to defend.
**Cons:** Slower, requires you to know your unit economics, may underestimate the opportunity.

**Example: Project Management SaaS in Japan**

```
Target: SMBs in Japan with 10-50 employees using project management tools
Total SMBs in Japan (10-50 employees):     ~250,000 companies
% that use project management tools:        ~30% = 75,000 companies
Average seats per company:                  15 users
Price per user per month:                   ¥1,800 ($12)
Annual revenue per customer:                15 x ¥1,800 x 12 = ¥324,000 ($2,160)

TAM = 75,000 x ¥324,000 = ¥243億 ($162M)
SAM = Companies reachable via our channels (online, Japanese-language):
      ~50,000 x ¥324,000 = ¥162億 ($108M)
SOM = Year 1 target: 200 customers x ¥324,000 = ¥6,480万 ($432K)
```

### Which Approach to Use?

| Context | Recommendation |
|---|---|
| Investor pitch (early stage) | Bottom-up as primary, top-down as sanity check |
| Investor pitch (growth stage) | Both, showing convergence |
| Internal planning | Bottom-up (more actionable) |
| Quick estimation | Top-down (faster) |
| New/undefined market | Bottom-up is the only option (no industry reports exist) |

**Best practice: Do both and compare.** If they differ by more than 5x, investigate why.

## Step-by-Step Process

### Step 1: Define Your Unit

What is the "unit" you're sizing?

- Revenue per customer per year?
- Revenue per transaction?
- Revenue per seat/user?

Be explicit. The unit determines everything downstream.

### Step 2: Estimate TAM

**Top-down method:**

1. Find a credible industry report (Gartner, IDC, Statista, 矢野経済研究所, 富士キメラ総研, 総務省統計).
2. Note the year, geography, and definition used.
3. Use the broadest reasonable definition of your market.

**Bottom-up method:**

1. Count the total number of potential customers globally.
   - Sources: Census data, LinkedIn Sales Navigator, industry directories, government statistics (経済産業省, 中小企業庁).
2. Multiply by your revenue per customer.

**Value-theory method (useful for new categories):**

1. Identify the problem you solve.
2. Estimate the cost of that problem per customer per year.
3. Multiply by the number of people/companies with that problem.
4. Your TAM = total cost of the problem (you can capture some fraction of the value you create).

### Step 3: Estimate SAM

Filter TAM by your real constraints:

| Filter | Question |
|---|---|
| Geography | Which countries/regions can you serve? |
| Language | Can your product serve non-English speakers? (日本語対応は必須か？) |
| Company size | Do you serve SMB, mid-market, or enterprise? |
| Industry | Are there industries you can't serve (regulated, etc.)? |
| Technology | Do customers need specific infrastructure? |
| Price point | Does your pricing exclude certain segments? |
| Channel | Can you reach these customers through your distribution? |

```
SAM = TAM x (% after geography filter)
          x (% after segment filter)
          x (% after other filters)
```

### Step 4: Estimate SOM

SOM is the most practical number. It should be bottoms-up and tied to your plan.

**Method 1: Capacity-based**

```
SOM = (Sales capacity x Close rate x Avg deal size)
    + (Marketing leads x Conversion rate x Avg deal size)

Example (JPY):
  営業2名 x 月20商談 x 成約率25% x 平均単価324,000円 = 年間3,888万円
  マーケ月100リード x 転換率5% x 平均単価324,000円 = 年間1,944万円
  SOM = 5,832万円（約$389K）
```

**Method 2: Growth-rate based**

```
SOM = Current ARR x (1 + Expected growth rate)

Example:
  Current ARR = ¥2,000万 ($133K)
  Expected growth = 150%
  SOM = ¥2,000万 x 2.5 = ¥5,000万 ($333K)
```

**Method 3: Market-share based**

```
SOM = SAM x Realistic market share %

Example:
  SAM = ¥162億 ($108M)
  Target share = 0.4% (Year 1)
  SOM = ¥6,480万 ($432K)
```

For a startup entering an established market, 1-5% of SAM in year 1-3 is aggressive but possible. For a new category, market share is less meaningful.

> **See also**: `unit-economics/` -- SOMのCapacity-based計算に必要なCAC、LTV、Close Rateの詳細

### Step 5: Sanity Check

Apply these reality checks:

1. **Comparable companies check:** What revenue did similar companies achieve at a similar stage? If no comparable has exceeded $50M (75億円) in your market, claiming a $500M SOM needs strong justification.

2. **Growth rate check:** To reach your SOM from current revenue, what CAGR is required? Is that realistic?
   ```
   Required CAGR = (SOM / Current Revenue)^(1/Years) - 1
   ```

3. **Customer count check:** How many customers does your SOM imply? Do that many customers actually exist in your reachable market?

4. **Bottom-up vs top-down convergence:** If your bottom-up TAM is $100M and your top-down TAM is $5B, something is wrong with one of them.

5. **The "10% test":** If you captured 10% of your SAM, would that be a venture-scale business? If not, either the market is too small or your SAM is too narrow.

## Templates

### Market Sizing Worksheet

```
=== DEFINITION ===
Product/Service:        ____________________
Unit of measurement:    [ ] Revenue per customer/year
                        [ ] Revenue per transaction
                        [ ] Revenue per user/seat
Unit value:             ¥____ / $____ per ____

=== TAM (Total Addressable Market) ===

Top-down:
  Source:               ____________________ (report name, year)
  Global market size:   ¥____ / $____
  Relevant subsegment:  ¥____ / $____ (explain filter: ___________)

Bottom-up:
  Total potential customers worldwide:   ____
  Revenue per customer:                  ¥____ / $____
  TAM = ____ x ¥____ = ¥____ ($____)

Value-theory:
  Cost of the problem per customer:      ¥____ / $____ /year
  Number of affected customers:          ____
  Total problem value:                   ¥____ / $____

TAM Estimate:           ¥____ / $____ (which method, why)

=== SAM (Serviceable Addressable Market) ===

Filters applied:
  [ ] Geography:        ____ (% of TAM remaining: ___%)
  [ ] Company size:     ____ (% remaining: ___%)
  [ ] Industry:         ____ (% remaining: ___%)
  [ ] Technology req:   ____ (% remaining: ___%)
  [ ] Language:         ____ (% remaining: ___%)
  [ ] Price point:      ____ (% remaining: ___%)
  [ ] Other:            ____ (% remaining: ___%)

SAM = TAM x combined filter = ¥____ / $____

=== SOM (Serviceable Obtainable Market) ===

Time horizon:           ____ years
Method used:            [ ] Capacity  [ ] Growth rate  [ ] Market share

Capacity-based:
  Sales reps x quota:              ¥____ / $____
  Marketing-sourced pipeline:      ¥____ / $____
  SOM = ¥____ / $____

Growth-rate-based:
  Current ARR:                     ¥____ / $____
  Expected CAGR:                   ____%
  SOM = ¥____ / $____

Market-share-based:
  Target market share of SAM:      ____%
  SOM = SAM x ____% = ¥____ / $____

SOM Estimate:           ¥____ / $____

=== SANITY CHECKS ===
[ ] Comparable companies: Largest similar company does ¥____ / $____ in revenue
[ ] Customer count: SOM implies ____ customers. Realistic?
[ ] Growth rate: Achieving SOM requires ____% CAGR. Realistic?
[ ] Bottom-up vs top-down within 5x?
[ ] 10% of SAM = ¥____ / $____. Is that venture-scale?
```

### Pitch Deck Market Slide Template

```
[Title]: ¥X億 / $XB Market Opportunity

TAM: ¥____億 / $____B
  [One sentence: what this includes]

SAM: ¥____億 / $____M
  [One sentence: how you filtered]

SOM: ¥____億 / $____M (Year 3 target)
  [One sentence: how you get there]

Sources: [List reports/data]
Methodology: [Top-down / Bottom-up / Both]
```

### Market Sizing Comparison Table

Use this to compare multiple market entry strategies:

```
| Dimension        | Option A          | Option B          | Option C          |
|------------------|-------------------|-------------------|-------------------|
| Target segment   |                   |                   |                   |
| TAM              | ¥      / $        | ¥      / $        | ¥      / $        |
| SAM              | ¥      / $        | ¥      / $        | ¥      / $        |
| SOM (Year 1)     | ¥      / $        | ¥      / $        | ¥      / $        |
| SOM (Year 3)     | ¥      / $        | ¥      / $        | ¥      / $        |
| Competition      | Low / Med / High  | Low / Med / High  | Low / Med / High  |
| GTM complexity   | Low / Med / High  | Low / Med / High  | Low / Med / High  |
| Unit economics   | LTV:CAC = X:1     | LTV:CAC = X:1     | LTV:CAC = X:1     |
| Recommendation   |                   |                   |                   |
```

## Japanese Business Example: AI研修市場のTAM/SAM/SOM

### Bottom-Up Approach (JPY Primary)

```
Step 1: Define the unit
  - Revenue per company per engagement
  - Pricing: 1日30-50万円 x 8日 = 240-400万円/案件（平均320万円）

Step 2: Count potential customers
  - 日本の従業員100名以上の企業: ~52,000社（中小企業庁統計）
  - DX推進に関心がある割合: ~60% = 31,200社
  - 外部AI研修に予算を割ける割合: ~30% = 9,360社

Step 3: Calculate TAM
  - TAM = 9,360社 x ¥320万 = ¥299.5億（約$200M）

Step 4: Calculate SAM
  - Filter: 日本語対応: 100%
  - Filter: 8日間の集中研修が可能な規模（100-1,000名）: ~70% = 6,552社
  - Filter: パートナー経由で到達可能: ~50% = 3,276社
  - SAM = 3,276社 x ¥320万 = ¥104.8億（約$70M）

Step 5: Calculate SOM
  - Year 1: 講師2名体制、月2案件ペース = 年24案件
  - SOM (Year 1) = 24 x ¥320万 = ¥7,680万（約$512K）
  - Year 3: 講師5名体制、月5案件ペース = 年60案件
  - SOM (Year 3) = 60 x ¥320万 = ¥1.92億（約$1.28M）

Step 6: Sanity checks
  ✓ Comparable: 大手研修会社のAI部門 ~¥5-10億/年 → ¥1.92億は控えめで現実的
  ✓ Growth: ¥7,680万 → ¥1.92億 = 2年で2.5x = ~58% CAGR。積極的だが可能
  ✓ Customer count: 60社/年。SAM 3,276社の1.8%。到達可能
  ✓ 10% of SAM = ¥10.5億。コンサル規模なら十分な事業規模
```

### Top-Down Cross-Check

```
日本のIT人材育成・研修市場（矢野経済研究所 2025）: ~¥5,000億
AI関連研修の割合（推定）: ~8% = ¥400億
企業向け外部委託割合: ~40% = ¥160億
SMB-Midmarket (100-1,000名) 向け: ~30% = ¥48億

→ Top-Down SAM: ¥48億
→ Bottom-Up SAM: ¥104.8億

差異: Bottom-upの方が2.2x大きい。
理由: Bottom-upは「関心がある企業」を含むが、
      Top-downは「実際に支出した企業」のみ。
→ 保守的にTop-Down寄りの¥50-60億を採用
```

> **See also**: `unit-economics/` -- SOM達成に必要なCAC、LTV、Payback Periodの算出

## Anti-Patterns (これをやったらアウト)

### 1. 「中国の1%」論法（The 1% Fallacy）
**Detection**: 「日本の中小企業360万社の1%でも3.6万社。十分大きい」
**Problem**: 「たった1%」はマジックワード。3.6万社に実際に到達し、契約を取る難しさを完全に隠蔽する
**Fix**: SOMは必ずBottom-upで計算する。営業人員 x 月間商談数 x 成約率 = 到達可能な顧客数

### 2. TAMの水増し（Inflated TAM）
**Detection**: 自社のニッチツールなのにTAMが「グローバルSaaS市場 $200B」
**Problem**: 投資家は即座に見抜く。信頼性ゼロ。「Addressable」の定義を無視
**Fix**: TAMは「自社プロダクトの購入を検討し得る全顧客」のみ。フィルター条件を明示

### 3. データソースなき市場規模
**Detection**: 「このマーケットは推定500億円です」（出典なし）
**Problem**: 数字に信頼性がない。投資家やステークホルダーは出典を確認する
**Fix**: 全ての数字にソースと年を明記。古いデータにはCAGR推計を付ける

### 4. SOM = SAM x 感覚的%
**Detection**: 「SAMの5%を取るのは現実的」（根拠なし）
**Problem**: 5%の根拠が不明。営業計画、マーケティング予算、リソースとの整合性がない
**Fix**: SOMはCapacity-based（営業力ベース）で算出し、Market-shareベースはクロスチェックのみ

### 5. 隣接市場の過剰取り込み
**Detection**: TAMに「将来展開予定の」市場をすべて含める
**Problem**: 現時点で提供できない市場をTAMに含めるのは不誠実
**Fix**: Core TAM（現プロダクトで対応可能）と Expansion TAM（将来の拡張）を分けて表示

### 6. 静的な市場観
**Detection**: 市場規模を一度算出して更新しない。市場の成長・縮小トレンドを無視
**Problem**: AI市場のように急成長している領域では、2年前のデータは無意味
**Fix**: CAGRを明示し、Time horizonに応じた将来推計を使う

## Common Pitfalls

### 1. The Inflated TAM Problem

**Mistake:** "The global HR software market is $30B. We're building HR software, so our TAM is $30B."

**Reality:** Your product is a niche scheduling tool for hourly workers at restaurants. Your TAM is a tiny slice of that $30B.

**Fix:** Be specific about what "addressable" means. TAM should reflect only the part of the market that would genuinely consider buying your product if they knew it existed.

### 2. The "1% of China" Fallacy

**Mistake:** "If we capture just 1% of the Chinese market, that's $2B in revenue!"

**Why it's wrong:**
- Capturing even 0.1% of a large market is extraordinarily hard.
- The "just" in "just 1%" hides enormous execution challenges.
- It's lazy math that doesn't demonstrate market understanding.

**Fix:** Always build SOM bottom-up from your actual go-to-market plan.

### 3. Confusing TAM with Revenue Forecast

TAM is not a forecast. It's the theoretical ceiling. Your actual revenue trajectory should be based on your SOM and growth plan.

### 4. Using Stale Data

**Mistake:** Using a 2019 market report for a 2026 pitch. Markets grow (and shrink).

**Fix:** Use the most recent data available. If the report is old, apply a CAGR to project forward, and cite your assumption.

### 5. Ignoring Market Dynamics

Static market sizing misses:
- **Market creation:** If you're creating a new category, there's no existing TAM. Size the problem instead.
- **Market disruption:** If you're 10x cheaper, you might expand the market (people who couldn't afford the old solution).
- **Platform shifts:** New technology (AI, mobile) can dramatically expand or shrink markets.

### 6. Double-Counting in Multi-Sided Markets

**Mistake:** For a marketplace, counting both buyer spend AND seller revenue as TAM.

**Fix:** Pick one side. Usually: TAM = total transaction volume (GMV), and your revenue = GMV x take rate.

### 7. Forgetting Adjacent Markets

The opposite of inflated TAM: being too narrow. If you're building a tool for graphic designers but it naturally extends to video editors and 3D artists, your TAM should include those adjacent segments (as a separate, clearly-labeled expansion opportunity).

## Worked Example: AI Writing Assistant for Japanese SMBs

### Bottom-Up Approach

```
Step 1: Define the unit
  - Revenue per company per year
  - Pricing: ¥4,500/user/month ($30/user/month)

Step 2: Count potential customers
  - SMBs in Japan (5-100 employees): ~1.5M companies (source: 経済産業省)
  - % that create regular written content (marketing, docs, email): ~40% = 600K
  - % willing to adopt AI tools: ~25% = 150K

Step 3: Calculate TAM
  - Average users per company: 5
  - Revenue per company: 5 x ¥4,500 x 12 = ¥270,000/year ($1,800)
  - TAM = 150,000 x ¥270,000 = ¥405億 ($270M)

Step 4: Calculate SAM
  - Filter: Japanese-language capable (our product): 100% (OK)
  - Filter: Tech-savvy enough to adopt SaaS: ~60% = 90K companies
  - Filter: Budget for writing tools: ~50% = 45K companies
  - SAM = 45,000 x ¥270,000 = ¥121.5億 ($81M)

Step 5: Calculate SOM
  - Year 1 plan: 2 sales reps, content marketing, product-led growth
  - Realistic Year 1 customers: 300
  - SOM (Year 1) = 300 x ¥270,000 = ¥8,100万 ($540K)
  - Year 3 target: 2,500 customers
  - SOM (Year 3) = 2,500 x ¥270,000 = ¥6.75億 ($4.5M)

Step 6: Sanity checks
  ✓ Comparable: AI writing tools in US (Jasper ~$80M ARR at peak)
    → Japan is ~8% of US market → ~¥14.4億 ($9.6M) ceiling seems plausible
  ✓ Growth: ¥8,100万 → ¥6.75億 in 2 years = ~190% CAGR. Aggressive but possible for SaaS
  ✓ Customer count: 2,500 SMBs in 3 years. Requires ~70 new customers/month by Year 3
  ✓ 10% of SAM = ¥12.15億 ($8.1M). Not venture-scale alone, but viable as capital-efficient business
```

### Top-Down Cross-Check

```
Global AI writing tools market (2025): ~$1.5B (¥2,250億)
Japan as % of global: ~5% = ¥112.5億 ($75M)
SMB segment: ~50% = ¥56.25億 ($37.5M)

→ Top-Down SAM: ¥56.25億 ($37.5M)
→ Bottom-Up SAM: ¥121.5億 ($81M)

Difference: Bottom-up is 2.2x higher than top-down.
Likely because: bottom-up assumes higher willingness to adopt.
Adjusted estimate: SAM = ¥56-120億 ($37-81M) range.
Use ¥75億 ($50M) as working estimate.
```

## References

- Osterwalder, Alexander & Pigneur, Yves. *Business Model Generation.* John Wiley & Sons, 2010.
- Blank, Steve & Dorf, Bob. *The Startup Owner's Manual.* K&S Ranch, 2012.
- 矢野経済研究所. Various industry reports. https://www.yano.co.jp/
- 富士キメラ総研. IT/digital market reports. https://www.fcr.co.jp/
- 中小企業庁. 中小企業白書. https://www.chusho.meti.go.jp/
