# Pretotyping

> **Quick Reference**
> - **Core idea**: 作る前に「作るべきか」をテストする（The Right It before building It Right）
> - **Key question**: この製品/サービスを欲しがる人は本当にいるのか？
> - **When to use**: アイデア段階で需要を数日〜2週間で検証したいとき
> - **Output**: XYZ仮説 + プリトタイプ実験結果 + Go/No-Go判定
> - **Time**: 数時間〜2週間（MVP前のステップ）

## Overview

Pretotyping, coined by Alberto Savoia (former Google Engineering Director), is a set of techniques for testing the initial appeal and actual usage of a potential new product by simulating its core experience with the smallest possible investment of time and money. The key question pretotyping answers is: "Should we build this thing at all?" -- before asking "Can we build this thing well?"

**The core insight:** Most new products fail in the market, not in the lab. The number one cause of failure is not poor execution -- it is building something nobody wants. Savoia calls this **The Law of Market Failure**: "Most new products will fail in the market, even if competently executed."

**Pretotyping vs. Prototyping:**
- **Prototyping** answers: "Can we build it? Will it work technically?"
- **Pretotyping** answers: "Should we build it? Will people actually want it?"

A prototype is an early version of the product. A pretotype is a fake version designed to test whether the product SHOULD exist. Pretotyping is cheaper, faster, and earlier than both prototyping and MVP.

**The evolution:**
```
Pretotype → MVP → Prototype → Product
(Should we?) → (Is it viable?) → (Can we build it?) → (Ship it)
```

Savoia's mantra: **"Make sure you are building The Right It before you build It Right."**

## When to Apply

- You have a new product idea and need to validate demand before investing
- You want to test market interest in days, not months
- You have multiple ideas and need to quickly determine which one to pursue
- Someone (a client, a boss, a partner) is enthusiastic about an idea, and you want evidence before committing
- You want to avoid the most common innovation failure: building something nobody wants
- Your budget is limited and you need maximum learning per dollar
- You suspect an idea "feels" good but might not have real demand
- Before committing to an MVP (pretotyping is pre-MVP)

## When NOT to Use

| Situation | Why Not | Better Alternative |
|---|---|---|
| Core risk is technical feasibility, not demand | Pretotyping tests demand, not technical viability | プロトタイプ/PoC（技術検証） |
| Already have strong demand evidence (受注済み, LOI取得済み) | Demand is proven; execution is the risk | > **See also**: `lean-startup/` のBuild-Measure-Learn |
| Highly regulated industry where "fake" offerings are illegal | 金融商品、医療機器等はFake Doorが法的リスク | Problem Interview (後述) or > **See also**: `validation-patterns/` Section 1 |
| Customer relationship is too valuable to risk | 大口既存顧客に対するFake Doorは信頼毀損 | > **See also**: `mom-test/` でヒアリングから始める |
| Problem itself が不明確 | Pretotypingはソリューションの需要テスト。問題が分からない段階ではまだ早い | > **See also**: `jobs-to-be-done/` で課題発見から |

## Step-by-Step Process

### Step 1: Formulate Your XYZ Hypothesis

Before testing anything, state your belief in a specific, falsifiable format. Savoia's XYZ Hypothesis replaces vague optimism with concrete, measurable predictions.

**XYZ Hypothesis Format:**
```
At least X% of Y will Z.
（Y のうち少なくとも X% が Z する）
```

Where:
- **X** = a specific percentage (your prediction of adoption/usage)
- **Y** = a clearly defined target audience
- **Z** = a specific, measurable action (not "like it" or "be interested" but "sign up," "pay," "use it daily")

**Examples:**

| Vague Belief | XYZ Hypothesis |
|-------------|----------------|
| "People would love a dog-walking app" | "At least 10% of dog owners in Austin who see our flyer will sign up for a trial walk within 48 hours" |
| "Businesses need better invoicing" | "At least 20% of freelancers who visit our landing page will enter their email to join the waitlist" |
| "Students want AI tutoring" | "At least 5% of college students who receive our flyer will book a free tutoring session within one week" |
| "This feature will increase retention" | "At least 30% of current users who see the feature announcement will click through to try it" |

**Rules for good XYZ Hypotheses:**
- X must be a number you commit to BEFORE the test (no moving goalposts)
- Y must be specific enough to find and reach
- Z must be an observable action, not a feeling or opinion
- The hypothesis must be falsifiable -- there must be a result that would make you stop

### Step 2: Choose a Pretotype Type

Select the pretotyping technique that best matches what you need to learn.

#### The Mechanical Turk

**What:** The product appears to be automated/technological but is actually operated by a human behind the scenes.

**When to use:** When the core question is "Will people use this?" and the technology to automate it doesn't exist yet (or would be expensive to build).

**Example:** Before building an AI-powered personal shopping assistant, you create a chat interface. Users type their request, but instead of AI, a human operator reads the message and manually responds with product recommendations. The user doesn't know it's a human.

**What you learn:** Whether people actually want the service, what they ask for, how they phrase requests, what makes them buy or abandon.

```
Setup:
- Front end: [What the user sees]
- Back end: [Human doing the work manually]
- Duration: [How long to run the test]
- Success metric: [What XYZ hypothesis are you testing?]
```

#### The Pinocchio

**What:** A non-functional version of the product that looks real. Like Pinocchio, it looks like a real boy but isn't alive.

**When to use:** When you need to test whether people will physically interact with or pick up the product, whether it fits into their environment, or whether the form factor is right.

**Example:** Before manufacturing a new type of water bottle, create a realistic-looking 3D-printed shell (no actual functionality). Place it on store shelves alongside real products and observe: Do people pick it up? Do they read the label? Do they take it to the register?

**What you learn:** Initial physical appeal, shelf presence, whether the concept attracts attention.

#### The Fake Door (or Smoke Test)

**What:** Advertise or present the product as if it exists. Measure how many people try to "buy" or "use" it.

**When to use:** When you need to test demand at scale with minimal investment.

**Techniques:**
- **Landing page:** Create a page describing the product with a "Buy Now" or "Sign Up" button. When clicked, show "Coming Soon -- enter your email to be notified." Measure click-through rate.
- **Feature button:** Add a button for a feature that doesn't exist yet in your existing product. When clicked, show a message: "This feature is coming soon. Would you like to be notified?" Measure clicks.
- **Ad campaign:** Run ads for the product and measure click-through rates and sign-up conversions. No product needed.

**What you learn:** Whether the value proposition resonates, whether people will take action (not just say they're interested).

#### The One-Night Stand

**What:** Provide the product or service exactly once (or for a very short period) to see if people actually use it and like it.

**When to use:** When you can deliver the experience manually for a few customers to test the value proposition.

**Example:** Before building an AI-powered resume review service, manually review 20 resumes for free (found via LinkedIn, Reddit, etc.). Deliver the feedback. Then measure: Did they read the feedback? Did they implement the suggestions? Would they pay for this? Would they refer others?

**What you learn:** Whether the value proposition delivers in practice, not just in theory. Real usage data from real users.

#### The Infiltrator

**What:** Place your product inside an existing channel or platform to test demand without building your own infrastructure.

**When to use:** When you want to test the product concept without building distribution/marketing.

**Example:** Before launching a direct-to-consumer snack brand, sell your product at a local farmer's market or through an existing online marketplace. Use their infrastructure (payment, foot traffic, logistics) to test whether people actually buy.

**What you learn:** Real purchase behavior in a real context, without building a website, payment system, or marketing funnel.

#### The Re-label (or Relabel)

**What:** Take an existing product, re-label or repackage it, and test whether the new positioning attracts a different audience.

**Example:** Take an existing project management tool, re-brand it as "The Creative Brief Tool for Agencies," and test whether agencies find it more appealing than generic project management.

**What you learn:** Whether the positioning/framing changes demand without changing the product.

#### The Impersonator

**What:** Use existing products/services to simulate what your product would do, cobbled together.

**Example:** Before building a custom CRM for real estate agents, set up a combination of Airtable + Zapier + Gmail to simulate the workflow. Have real estate agents use this cobbled-together system. Observe what works and what frustrates them.

**What you learn:** Which parts of the workflow are most valued, which are most frustrating, and what the "real" product actually needs to do.

### Pretotype Selection Guide

```
WHAT DO YOU NEED TO LEARN?              BEST PRETOTYPE

"Will people want this service?"     →  Mechanical Turk
"Does this physical form appeal?"    →  Pinocchio
"Is there demand for this concept?"  →  Fake Door
"Does the experience deliver?"       →  One-Night Stand
"Will people buy in existing channels?" → Infiltrator
"Does repositioning change demand?"  →  Re-label
"What does the workflow need to be?" →  Impersonator
```

### Pretotype Cost/Speed Comparison

| Pretotype Type | Typical Cost (USD / JPY) | Time to Set Up | Time to Get Data |
|---|---|---|---|
| Fake Door | $50-500 / 7,500-75,000円 | 1-3 days | 1-2 weeks |
| Mechanical Turk | $0-200 / 0-30,000円 | 1-2 days | 1-4 weeks |
| One-Night Stand | $0-100 / 0-15,000円 | 1 day | 1-3 days |
| Pinocchio | $50-500 / 7,500-75,000円 | 1-5 days | 1-2 weeks |
| Infiltrator | $0-200 / 0-30,000円 | 1-3 days | 1-4 weeks |
| Re-label | $0-100 / 0-15,000円 | Hours | 1-2 weeks |
| Impersonator | $0-50 / 0-7,500円 | Hours-1 day | 1-4 weeks |

Compare to: MVP ($5,000-50,000+ / 75万-750万円+, 1-6 months) or full product ($50,000-500,000+ / 750万-7,500万円+, 6-18 months).

### Step 3: Run the Pretotype

Execute the test with real people in real conditions.

**Rules:**
- Use REAL data from REAL potential users (not friends, family, or colleagues)
- Set a specific timeframe (usually days to 2 weeks, not months)
- Define success/failure criteria BEFORE starting (your XYZ Hypothesis)
- Collect quantitative data (numbers, rates, amounts) not just qualitative (opinions, feelings)
- Make it as close to a "skin in the game" test as possible (clicking a buy button > filling out a survey)

> **See also**: `mom-test/` -- 定性データ（インタビュー）とプリトタイプの定量データを組み合わせると最も強力

### Step 4: Evaluate Against Your XYZ Hypothesis

```
PRETOTYPE RESULTS
=================
Hypothesis: At least X% of Y will Z.
Actual result: ___% of Y did Z.

VERDICT:
[ ] Hypothesis VALIDATED (proceed to MVP)
[ ] Hypothesis INVALIDATED (pivot or abandon)
[ ] INCONCLUSIVE (redesign the test)

KEY OBSERVATIONS:
- ___________
- ___________

SURPRISING FINDINGS:
- ___________

NEXT STEP:
___________
```

### Step 5: Iterate or Proceed

Based on results:

| Result | Action |
|--------|--------|
| Hypothesis validated with strong signal | Proceed to MVP or prototype |
| Hypothesis validated with marginal signal | Run a second test with a different pretotype type to confirm |
| Hypothesis invalidated | Pivot the concept or abandon |
| Inconclusive | Redesign the pretotype (wrong audience? Wrong channel? Wrong metric?) |

## Key Templates and Frameworks

### Market Engagement Hypothesis (MEH)

A broader version of the XYZ Hypothesis that includes the engagement mechanism:

```
MARKET ENGAGEMENT HYPOTHESIS
=============================
PRODUCT CONCEPT:
___________

TARGET MARKET (Y):
Who specifically? ___________
Where do we find them? ___________
How many can we reach? ___________

ENGAGEMENT ACTION (Z):
What specific action? ___________
What does it cost them? (time/money/effort) ___________

EXPECTED RATE (X):
At least ___% will take this action.

TEST METHOD:
Pretotype type: ___________
Duration: ___________
Sample size: ___________
Channel: ___________

DATA COLLECTION:
How will we measure Z? ___________
What other data will we collect? ___________
```

> **See also**: `validation-patterns/` -- プリトタイプの結果をさらに深く検証するための実験テンプレート集（Landing Page Test, Pre-Order, Van Westendorp等）

## Japanese Business Example: AI業務マニュアル自動生成ツール

### 背景
「社内の属人化された業務手順を、AIが自動でマニュアル化する」ツールのアイデア。製造業の中小企業（従業員50-200名）がターゲット。人手不足と技術継承が深刻な日本市場で、属人化解消のニーズを検証したい。

### XYZ Hypothesis

```
XYZ仮説:
「製造業の中小企業（50-200名）の生産管理担当者のうち、
LinkedIn広告を見た人の少なくとも3%が
ランディングページで無料トライアルのメールアドレスを登録する」
```

### Pretotype: Fake Door

**セットアップ:**
- ペライチ（日本のLP作成ツール）で1ページ作成: 15,000円
- LinkedIn広告（日本の製造業・生産管理担当者ターゲット）: 50,000円 / 2週間
- 合計投資: 65,000円（約$430）

**LP内容:**
- ヘッドライン: 「ベテランの頭の中を、誰でも読めるマニュアルに。」
- サブ: 「AI業務マニュアル自動生成 -- 属人化を30日で解消」
- CTA: 「無料トライアルに申し込む」→ クリック後「近日公開。メールアドレスをご登録ください」

**結果:**
```
PRETOTYPE RESULTS
=================
Hypothesis: At least 3% of Y will register email.
Actual result: 4.2% registered.

LinkedIn広告データ:
  表示回数: 12,400
  クリック数: 310 (CTR 2.5%)
  LP訪問 → メール登録: 13人 / 310 = 4.2%
  CPC: 161円 ($1.07)
  CPL (Cost per Lead): 3,846円 ($25.60)

VERDICT:
[x] Hypothesis VALIDATED (proceed to MVP)

KEY OBSERVATIONS:
- 「属人化」「技術継承」のキーワードが最もCTRが高い
- 50-100名規模の企業からの反応が最も多い
- 製造業だけでなく建設業からもクリックあり

NEXT STEP:
Mechanical Turk -- 登録した13人のうち3社に、手動でマニュアル作成を提供
（AIではなく人力で作成し、実際に使ってもらえるか検証）
```

> **See also**: `validation-patterns/` Section 2 (Solution Validation) -- この次のステップとしてConcierge MVP or Wizard of Oz MVPを実施

## Anti-Patterns (これをやったらアウト)

### 1. 「とりあえず作ろう」症候群
**Detection**: 「作ってみないと分からない」「まず動くものを」という発言がチーム内で出る
**Problem**: Pretotypingの存在意義そのものの否定。作る前にテストできることを作って検証してしまう
**Fix**: 「それは"Should we build it?"と"Can we build it?"のどちらの質問ですか？」と問い返す

### 2. 友人・同僚テスト
**Detection**: テスト対象が社内メンバー、友人、家族のみ
**Problem**: ソーシャルバイアスで正確な需要データが得られない。「いいね！」は礼儀であって需要ではない
**Fix**: リアルなターゲット顧客にリーチする。LinkedIn広告、Reddit投稿、コミュニティ掲示板など

### 3. 意見を需要と混同
**Detection**: 「アンケートで80%が『使いたい』と回答」をもって検証完了とする
**Problem**: 「使いたい」と言うことと実際に行動することは別。特に日本では社交辞令（建前）リスクが高い
**Fix**: 行動ベースの指標のみ計測する（クリック、登録、支払い、時間投資）

### 4. Fake Doorの倫理違反
**Detection**: 実在しない商品の購入ボタンで決済まで進む、個人情報を不適切に収集する
**Problem**: 法的リスク（特定商取引法、景品表示法）、ブランド毀損、信頼喪失
**Fix**: 「Coming Soon」表示は必須。決済は絶対に発生させない。メール収集時はプライバシーポリシー明示

### 5. 成功基準の後出しジャンケン
**Detection**: テスト結果を見てから「3%でも十分」と言い始める（当初目標は10%だった）
**Problem**: 確証バイアスにより、どんな結果でも「成功」と解釈してしまう
**Fix**: XYZ仮説をテスト前に文書化し、チーム全員で合意。結果が出てからの変更は不可

### 6. プリトタイプに凝りすぎる
**Detection**: Fake DoorのLPデザインに3週間かけている。Mechanical Turkのフロントエンドを本格開発
**Problem**: プリトタイプの目的は「速く安く学ぶ」こと。凝った時点でMVPと変わらない
**Fix**: 予算上限と時間上限を先に決める（例: 5万円以内、3日以内）

## Common Pitfalls

1. **Skipping the XYZ Hypothesis.** Without a specific, quantified prediction, you will rationalize any result as "encouraging." Define success before running the test.

2. **Testing with the wrong audience.** Your friends, colleagues, and social media followers are NOT your target market (unless they are).

3. **Measuring interest instead of action.** "Would you use this?" is not a pretotype. "Click this button to sign up" is a pretotype.

4. **Over-investing in the pretotype.** If your Fake Door landing page took 3 weeks to design and build, you missed the point. Hours to days, not weeks.

5. **Giving up after one test.** A single negative result might mean the concept is wrong, OR it might mean the execution of the test was wrong. Try a different pretotype type or audience before abandoning.

6. **Confusing pretotyping with "cutting corners."** Pretotyping is not about building a bad version. It's about testing whether the product should exist at all.

7. **Not iterating on the concept.** If 3% clicked instead of 10%, don't just say "failed." Ask: Why? Adjust and retest.

## Examples

### Example 1: Palm Pilot (Jeff Hawkins)

**Concept:** A handheld personal digital assistant (before smartphones).

**Pretotype (Pinocchio):** Jeff Hawkins carved a block of wood to the exact dimensions of the proposed Palm Pilot. He carried it in his shirt pocket for weeks. When he needed to check his calendar, he pulled out the wooden block and pretended to tap on it.

**What he learned:** The form factor was right. He actually reached for it dozens of times per day. The "jobs" were real and frequent.

**Result:** Palm Pilot became one of the most successful consumer electronics products of its era.

### Example 2: Zappos (Nick Swinmurn)

**Concept:** Sell shoes online (radical idea in 1999).

**Pretotype (Mechanical Turk + Infiltrator):** Swinmurn went to local shoe stores, photographed shoes, posted the photos on a simple website. When someone ordered, he went back to the store, bought the shoes at retail price, and shipped them to the customer.

**What he learned:** People WOULD buy shoes online without trying them on.

**Result:** Zappos eventually sold to Amazon for $1.2 billion.

### Example 3: Fake Door for a SaaS Feature

**Concept:** Adding a "Team Analytics Dashboard" to an existing project management tool.

**Pretotype (Fake Door):** Added a "Team Analytics" tab to the navigation bar. When clicked, it showed a modal: "Team Analytics is coming soon! Enter your email to be the first to know."

**XYZ Hypothesis:** "At least 15% of active users will click on Team Analytics within 2 weeks, and at least 30% of those who click will enter their email."

**Result:** 8% clicked (below 15% threshold). Of those, 45% entered their email (above 30% threshold).

**Interpretation:** Interest among those who noticed was strong (45% email signup), but discoverability/appeal was lower than expected (8% click rate). Retest with "Performance Insights" instead of "Team Analytics." The second test hit 18% clicks. Proceed to MVP.

## References

- Savoia, Alberto. *The Right It: Why So Many Ideas Fail and How to Make Sure Yours Succeed.* HarperOne, 2019.
- Savoia, Alberto. "Pretotype It." (Original manifesto, 2011). Available at pretotyping.org.
- Savoia, Alberto. "Pretotyping@Google." (Internal Google presentation, widely shared)
- Ries, Eric. *The Lean Startup.* Crown Business, 2011. (MVP is one step beyond pretotyping)
- Fitzpatrick, Rob. *The Mom Test.* Robfitz Ltd, 2013. (Complementary: qualitative data alongside pretotype quantitative data)
