# Validation Patterns

> **Quick Reference**
> - **Core idea**: ビジネス仮説を構造化された実験で段階的に検証する
> - **Key question**: この仮説は事実か？最小コストでどう確認するか？
> - **When to use**: 問題・ソリューション・価格・チャネルの仮説を実験で検証したいとき
> - **Output**: 実験設計 + 成功基準 + 結果判定（Validated / Invalidated / Inconclusive）
> - **Time**: 1-12週間（検証フェーズにより異なる）

## Overview

Validation patterns are structured experiments designed to test specific business hypotheses before committing significant resources. The goal is to **reduce uncertainty systematically** -- moving from "I think" to "I know" as cheaply and quickly as possible.

This document organizes validation patterns by what you're trying to validate:

1. **Problem Validation** -- Does the problem actually exist? Is it painful enough?
2. **Solution Validation** -- Does our proposed solution solve the problem?
3. **Willingness-to-Pay Validation** -- Will people pay for it? How much?
4. **Channel Validation** -- Can we reach customers cost-effectively?

Each pattern includes a description, when to use it, cost/time estimates, how to run it, and a success criteria template.

## When NOT to Use

| Situation | Why Not | Better Alternative |
|---|---|---|
| まだアイデアが漠然としている | 実験設計には明確な仮説が必要 | > **See also**: `jobs-to-be-done/` で課題を構造化, `business-model-canvas/` で全体像を整理 |
| 技術的実現可能性がリスクの中心 | このスキルは市場・需要の検証が専門 | Technical PoC / Prototype |
| 既に十分な需要データがある | 検証済みなら実行フェーズへ | > **See also**: `unit-economics/` でスケーラビリティ分析 |
| 大企業の既存プロダクト改善 | A/Bテスト等の本番環境での最適化が適切 | Product Analytics / A/B Testing Framework |

---

## 1. Problem Validation

> "Are we solving a real problem that people care enough about?"

### 1.1 Problem Interview

**Description:** One-on-one conversations with potential customers to understand their problems, current workflows, and pain points.

> **See also**: `mom-test/` -- Problem Interviewの具体的なインタビュー手法、質問設計、やってはいけないことの詳細ガイド

**When to use:**
- Very early stage -- before you've built anything.
- When you need qualitative depth (why, how, what emotions).
- When you're entering an unfamiliar market.

**Cost:** Free - $500 / 0-75,000円 (incentives for interviewees)
**Time:** 1-3 weeks for 10-20 interviews
**Team:** 1 person can run this

**How to run it:**

1. Define your target customer profile.
2. Recruit 10-20 people who fit the profile (LinkedIn, communities, friends-of-friends, cold outreach).
3. Conduct 20-30 minute interviews using this structure:
   - Context: "Tell me about the last time you [relevant activity]."
   - Problem: "What's the hardest part about [activity]?"
   - Current solution: "How do you deal with that today?"
   - Impact: "What happens when this problem isn't solved?"
   - Willingness: "Have you ever looked for a better solution? What happened?"
4. Take notes during the interview (or record with permission).
5. After each interview, extract: problems mentioned, severity, current solutions, quotes.
6. After all interviews, look for patterns: What problem came up most? What language did people use?

**Success criteria template:**

```
Hypothesis: [Target customer] has a significant problem with [problem description].

Results:
  Interviews conducted:           ____ / 15 target
  % who mentioned the problem
    unprompted:                    ____% (target: >50%)
  % who actively tried to solve
    the problem:                   ____% (target: >30%)
  % who spend money on current
    solutions:                     ____% (target: >20%)
  Average severity rating
    (1-10, self-reported):         ____ (target: >7)

Decision:
  [ ] VALIDATED: >50% unprompted mention, >7 severity -> proceed to solution
  [ ] PARTIALLY VALIDATED: 30-50% mention -> refine problem definition, more interviews
  [ ] INVALIDATED: <30% mention -> pivot to different problem
```

---

### 1.2 Observation / Contextual Inquiry

**Description:** Watch people in their natural environment as they perform the task your product would address. Don't ask -- observe. People often can't articulate their problems, but their behavior reveals friction.

**When to use:**
- When you suspect people don't know they have a problem (latent need).
- When the workflow is physical or complex (factory, office, retail).
- When interviews produce inconsistent results (people say one thing, do another).

**Cost:** $0-$1,000 / 0-150,000円 (travel, access fees)
**Time:** 1-2 weeks for 5-10 sessions
**Team:** 1-2 people

**How to run it:**

1. Identify where your target customers perform the relevant activity.
2. Get permission to observe (offer value in return -- a report, consultation).
3. Watch silently for 30-60 minutes. Note:
   - Workarounds and hacks (Post-it notes, spreadsheets, manual steps).
   - Points of frustration (sighs, repeated actions, errors).
   - Time spent on each step.
   - Tools used and how they're (mis)used.
4. After observation, ask clarifying questions: "I noticed you did X. Why?"
5. Synthesize across sessions: common friction points, time sinks, error-prone steps.

**Success criteria template:**

```
Hypothesis: [Target customer] experiences significant friction when [activity].

Results:
  Sessions conducted:              ____ / 8 target
  Distinct friction points
    observed:                      ____
  Top friction point:              [description]
    Frequency (sessions where
    it appeared):                  ____ / ____
    Time wasted per occurrence:    ____ minutes
  Workarounds observed:            ____ distinct workarounds

Decision:
  [ ] VALIDATED: Consistent friction across >60% of sessions -> design solution
  [ ] INCONCLUSIVE: Mixed signals -> more sessions or switch to interviews
  [ ] INVALIDATED: Workflow is smooth, no significant friction -> different problem
```

---

### 1.3 Search Volume / Demand Analysis

**Description:** Use publicly available search data to quantify how many people are actively looking for a solution to the problem. If no one is searching, either the problem doesn't exist, people don't know it's solvable, or they use different language.

**When to use:**
- To validate that a problem has sufficient scale (quantitative check).
- To discover what language people use to describe their problem.
- As a complement to qualitative methods (interviews).

**Cost:** $0 (free tools) to $100/month / 0-15,000円/月 (paid tools)
**Time:** 1-3 days
**Team:** 1 person

**Tools:**
- Google Keyword Planner (free with Google Ads account)
- Google Trends (free)
- Ahrefs, SEMrush, or Ubersuggest (paid, more detailed)
- AnswerThePublic (free tier available)
- Reddit, Quora, Twitter/X search (free)
- Japan-specific: Yahoo!知恵袋, はてなブックマーク, note.com search

**How to run it:**

1. Brainstorm 10-20 keywords that someone with this problem would search for.
2. Check monthly search volume for each keyword (and related keywords).
3. Check Google Trends for trajectory (growing, stable, declining).
4. Search forums (Reddit, Quora, Yahoo!知恵袋) for discussions about the problem:
   - How many threads?
   - How many upvotes/replies?
   - What language do people use?
   - What existing solutions do people recommend?
5. Compile results into a demand map.

**Success criteria template:**

```
Hypothesis: There is meaningful search demand for solutions to [problem].

Results:
  Primary keywords tested:         ____
  Total monthly search volume
    (primary keywords):            ____ (target: >1,000/month for niche, >10,000 for mass)
  Google Trends direction:         [ ] Growing [ ] Stable [ ] Declining
  Related keywords discovered:     ____
  Forum threads found:             ____
  Average engagement per thread:   ____ replies

Decision:
  [ ] VALIDATED: Growing demand + significant volume -> proceed
  [ ] PARTIALLY VALIDATED: Low volume but growing -> may be early market
  [ ] INVALIDATED: No demand + declining -> reconsider problem
```

---

## 2. Solution Validation

> "Does our specific solution actually solve the problem?"

### 2.1 Fake Door Test (Painted Door)

**Description:** Create the appearance of a feature or product (a button, link, or page) that doesn't actually work yet. Measure how many people try to use it. This tests demand for the solution without building it.

> **See also**: `pretotyping/` -- Fake Door以外のプリトタイプ手法（Mechanical Turk, Pinocchio, Infiltrator等）の詳細ガイド

**When to use:**
- You have an existing product and want to test demand for a new feature.
- You want quantitative data on interest before investing in development.
- The feature is expensive to build and you want to de-risk.

**Cost:** $0-$500 / 0-75,000円
**Time:** 1-2 weeks (setup + data collection)
**Team:** 1 designer + 1 developer (a few hours)

**How to run it:**

1. Add a button, menu item, or link for the not-yet-built feature.
2. When clicked, show a message: "Coming soon! Sign up to be notified when [feature] is available."
3. Collect email signups.
4. Measure: click-through rate, signup rate, and any qualitative feedback.
5. Remove the fake door after 1-2 weeks or when you have enough data.

**Ethical note:** Be transparent. The "coming soon" message should be honest. Don't fake a transaction.

**Success criteria template:**

```
Hypothesis: Users want [feature/solution] enough to try it.

Setup:
  Where fake door was placed:      [location in product/page]
  Duration:                        ____ days
  Total users exposed:             ____

Results:
  Clicked the fake door:           ____ (____%)
  Signed up for notification:      ____ (____%)
  Conversion (click -> signup):    ____%

Benchmarks:
  Feature CTR > 5%:               [ ] Yes  [ ] No
  Signup rate > 2%:               [ ] Yes  [ ] No

Decision:
  [ ] VALIDATED: CTR > 5% and signup > 2% -> build it
  [ ] INCONCLUSIVE: CTR > 5% but low signup -> test messaging
  [ ] INVALIDATED: CTR < 2% -> users don't want this
```

---

### 2.2 Concierge MVP

**Description:** Deliver the value proposition manually to a small number of customers, as if you were their personal concierge. No technology needed -- you are the product. This tests whether the solution truly solves the problem before you automate it.

**When to use:**
- Very early stage, before building any product.
- When you need to deeply understand the customer's workflow.
- When the solution involves complex logic that's hard to spec without experience.

**Cost:** Your time (significant) + $0-$500 / 0-75,000円 for tools
**Time:** 2-4 weeks for 5-10 customers
**Team:** 1-2 people delivering the service manually

**How to run it:**

1. Recruit 5-10 early customers from your problem interviews.
2. Deliver the promised value proposition manually:
   - If your product would automate meal planning, YOU create the meal plans.
   - If your product would match freelancers to jobs, YOU do the matching.
3. Charge something (even if minimal) -- paying customers give better feedback.
4. After each delivery, ask:
   - "Did this solve your problem?"
   - "What would you change?"
   - "Would you continue using this? At what price?"
5. Track: time spent per customer, satisfaction, retention, willingness to pay.

**Success criteria template:**

```
Hypothesis: Manually delivering [solution] solves [problem] for [customer].

Setup:
  Customers served:                ____ / 10 target
  Duration:                        ____ weeks
  Price charged:                   ¥____ / $____

Results:
  Customer satisfaction (1-10):    ____ average
  Problem solved? (customer
    self-report):                  ____% said yes (target: >70%)
  Would continue using:            ____% (target: >60%)
  Willing to pay more:             ____% (target: >30%)
  Time per customer:               ____ hours/week

Decision:
  [ ] VALIDATED: >70% problem solved, >60% would continue -> build MVP
  [ ] PARTIALLY VALIDATED: Solution works but needs major tweaks -> iterate manually
  [ ] INVALIDATED: <50% problem solved -> rethink solution approach
```

---

### 2.3 Wizard of Oz MVP

**Description:** The product appears to be fully automated to the user, but behind the scenes, a human is doing the work. Unlike Concierge MVP, the customer doesn't know it's manual. This tests whether the product experience (not just the outcome) works.

> **See also**: `pretotyping/` -- Wizard of OzはPretotypingの「Mechanical Turk」パターンに相当

**When to use:**
- When the user experience matters (not just the outcome).
- When you want to test a specific UI/UX before building the backend.
- When automation is the hard part and you want to validate demand first.

**Cost:** $500-$5,000 / 75,000-750,000円 (frontend development + manual labor)
**Time:** 2-6 weeks
**Team:** 1 developer (frontend) + 1-2 people doing manual work behind the scenes

**How to run it:**

1. Build a functional-looking frontend (can be a simple app, chatbot, or form).
2. When the user submits a request, a human receives it and processes it manually.
3. The response is delivered through the product interface as if it were automated.
4. Measure: usage, satisfaction, retention, willingness to pay.

**Success criteria template:**

```
Hypothesis: Users will engage with [product] as if it were automated,
            and the experience delivers value.

Setup:
  Users acquired:                  ____
  Duration:                        ____ weeks
  Appeared automated:              [ ] Yes
  Price charged:                   ¥____ / $____

Results:
  Completed the core action:       ____% of users (target: >40%)
  Returned for 2nd use:            ____% (target: >20%)
  Satisfaction (1-10):             ____
  Noticed it was manual:           ____% (target: <10%)
  Response time achieved:          ____ (acceptable for "automated"?)

Decision:
  [ ] VALIDATED: Good engagement + satisfaction + acceptable response time -> build automation
  [ ] PARTIALLY VALIDATED: Good demand but UX needs work -> iterate on frontend
  [ ] INVALIDATED: Low engagement even with perfect manual delivery -> rethink product
```

---

### 2.4 Landing Page Test

**Description:** Create a landing page that describes your product, its benefits, and a call-to-action (signup, waitlist, pre-order). Drive traffic to it and measure conversion. Tests both messaging and demand.

**When to use:**
- After you've validated the problem and want to test whether your framing resonates.
- To test different value propositions / positioning.
- To build a waitlist before launch.

**Cost:** $200-$2,000 / 30,000-300,000円 (page creation + ad spend)
**Time:** 1-2 weeks
**Team:** 1 person (using no-code tools like Carrd, Webflow, Unbounce, or ペライチ for Japan)

**How to run it:**

1. Create a landing page with:
   - Clear headline (value proposition)
   - 3-5 benefit statements
   - Social proof (if available)
   - Call-to-action (email signup, waitlist, "request access")
2. Drive traffic:
   - Paid ads: ¥75,000-150,000円 ($500-$1,000) budget for statistical significance
   - Post in relevant communities (Reddit, Hacker News, Twitter/X, note.com)
   - Share with your network
3. Measure conversions.
4. Optionally: A/B test different headlines, CTAs, or pricing.

**Success criteria template:**

```
Hypothesis: [Value proposition] resonates with [target customer]
            enough to sign up.

Setup:
  Landing page URL:                ____
  Traffic source(s):               ____
  Ad spend:                        ¥____ / $____
  Duration:                        ____ days

Results:
  Unique visitors:                 ____ (target: >500 for significance)
  Email signups / waitlist:        ____
  Conversion rate:                 ____% (target: >5% for waitlist,
                                          >2% for pre-order)
  Cost per signup:                 ¥____ / $____
  Bounce rate:                     ____%
  Average time on page:            ____ seconds

A/B test results (if applicable):
  Variant A: [description] -> ____% conversion
  Variant B: [description] -> ____% conversion

Decision:
  [ ] VALIDATED: >5% conversion to waitlist -> build MVP
  [ ] PARTIALLY VALIDATED: 2-5% conversion -> test different messaging
  [ ] INVALIDATED: <2% conversion -> rethink value proposition or targeting
```

---

## 3. Willingness-to-Pay Validation

> "Will people actually pay? How much?"

### 3.1 Pre-Order / Deposit

**Description:** Ask customers to pay (or put down a deposit) for a product that doesn't exist yet. The strongest signal of willingness to pay is actually paying.

**When to use:**
- After problem and solution validation.
- When you need to prove revenue before building.
- For physical products, courses, or clearly-defined services.

**Cost:** $200-$1,000 / 30,000-150,000円 (landing page + payment setup)
**Time:** 1-4 weeks
**Team:** 1 person

**How to run it:**

1. Create a product page with clear deliverables, timeline, and price.
2. Set up payment (Stripe, Gumroad, or similar; Japan: PAY.JP, Square).
3. Offer a clear refund policy (reduces risk for customer).
4. Drive traffic (same as landing page test).
5. Track: orders, revenue, refund requests.

**Options:**
- **Full pre-order:** Customer pays full price. Product delivered later.
- **Deposit:** Customer pays 10-30% upfront. Remainder on delivery.
- **Founding member pricing:** Discounted price for early adopters.

**Success criteria template:**

```
Hypothesis: [Target customer] will pay ¥[price] / $[price] for [product].

Setup:
  Price point tested:              ¥____ / $____
  Offer type:                      [ ] Full pre-order  [ ] Deposit  [ ] Founding member
  Refund policy:                   ____
  Traffic source:                  ____
  Duration:                        ____ days

Results:
  Page visitors:                   ____
  Orders placed:                   ____
  Conversion rate:                 ____% (target: >1% for cold traffic,
                                          >5% for warm traffic)
  Revenue collected:               ¥____ / $____
  Refund requests:                 ____ (____%)

Decision:
  [ ] VALIDATED: >1% conversion + <10% refunds -> build and deliver
  [ ] PARTIALLY VALIDATED: Conversions but high refunds -> refine offer
  [ ] INVALIDATED: <0.5% conversion -> wrong price, wrong audience, or wrong product
```

---

### 3.2 Crowdfunding Campaign

**Description:** Launch on Kickstarter, Indiegogo, or similar platforms (Japan: Makuake, CAMPFIRE) to validate demand and willingness to pay simultaneously, while also raising funds to build the product.

**When to use:**
- Physical products, creative projects, or hardware.
- When you need both validation AND capital.
- When your product has visual/tangible appeal.

**Cost:** $2,000-$10,000 / 300,000-1,500,000円 (video production, page design, sample/prototype, ad spend)
**Time:** 2-4 weeks preparation + 30-day campaign
**Team:** 2-3 people

**How to run it:**

1. **Pre-launch (2-4 weeks):**
   - Build an email list of at least 500 interested people.
   - Create a compelling video (can be DIY, but quality matters).
   - Design reward tiers.
   - Line up press/influencer coverage for launch day.

2. **Launch:**
   - Target 30% of funding goal in first 48 hours (critical for platform algorithms).
   - Activate your email list and network on Day 1.
   - Post daily updates.

3. **During campaign:**
   - Track funding velocity, backer count, average pledge.
   - Run ads if organic momentum stalls.
   - Engage with comments and backers.

**Success criteria template:**

```
Hypothesis: [Target market] will fund [product] at ¥[price] / $[price].

Setup:
  Platform:                        [ ] Kickstarter  [ ] Makuake  [ ] CAMPFIRE  [ ] Other
  Funding goal:                    ¥____ / $____
  Campaign duration:               ____ days
  Pre-launch email list:           ____ subscribers
  Reward tiers:                    ¥____ / ¥____ / ¥____

Results:
  Total raised:                    ¥____ / $____
  % of goal reached:               ____% (target: >100%)
  Total backers:                   ____
  Average pledge:                  ¥____ / $____
  Funded in first 48 hours:        ____% of goal (target: >30%)
  Email list conversion:           ____%

Decision:
  [ ] VALIDATED: >100% funded -> deliver the product
  [ ] PARTIALLY VALIDATED: 50-100% funded -> adjust and retry or find alternative funding
  [ ] INVALIDATED: <30% funded -> major pivot needed
```

---

### 3.3 Price Sensitivity Survey (Van Westendorp)

**Description:** A structured survey method to determine optimal pricing by asking four questions about price perception. Developed by Dutch economist Peter van Westendorp.

**When to use:**
- When you need to set a price for a new product.
- When you have access to a pool of potential customers (50+).
- When you want data-driven pricing rather than guessing.

**Cost:** $0-$500 / 0-75,000円 (survey tool)
**Time:** 1-2 weeks
**Team:** 1 person
**Minimum respondents:** 50 (ideally 100+)

**The four questions (in order):**

1. "At what price would you consider [product] to be **so expensive** that you would not consider buying it?" (Too Expensive)
2. "At what price would you consider [product] to be **expensive**, but you might still consider it?" (Expensive / High)
3. "At what price would you consider [product] to be a **bargain** -- a great buy for the money?" (Cheap / Low)
4. "At what price would you consider [product] to be **so cheap** that you'd question its quality?" (Too Cheap)

**How to analyze:**

1. Plot cumulative frequency distributions for each question.
2. Find intersections:
   - **Point of Marginal Cheapness (PMC):** "Too Cheap" intersects "Expensive"
   - **Point of Marginal Expensiveness (PME):** "Too Expensive" intersects "Cheap"
   - **Optimal Price Point (OPP):** "Too Cheap" intersects "Too Expensive"
   - **Indifference Price Point (IDP):** "Expensive" intersects "Cheap"
3. Your acceptable price range is PMC to PME.
4. Your optimal price is between OPP and IDP.

**Success criteria template:**

```
Hypothesis: The optimal price for [product] is between ¥X-Y / $X-Y.

Setup:
  Respondents:                     ____ (target: >50)
  Target segment match:            ____%
  Survey tool used:                ____

Results:
  Point of Marginal Cheapness:     ¥____ / $____
  Optimal Price Point:             ¥____ / $____
  Indifference Price Point:        ¥____ / $____
  Point of Marginal Expensiveness: ¥____ / $____
  Acceptable range:                ¥____-____ / $____-____

Decision:
  Price to test:                   ¥____ / $____
  Reasoning:                       ____
```

> **See also**: `unit-economics/` -- 価格設定がLTV/CAC/粗利率にどう影響するかの分析

---

## 4. Channel Validation

> "Can we reach customers cost-effectively?"

### 4.1 Small-Budget Ad Test

**Description:** Run paid ads on 2-3 platforms with a small budget to test which channels can deliver customers at an acceptable CAC.

**When to use:**
- When you need to find scalable acquisition channels.
- After you have a landing page or product that can convert visitors.
- When organic growth alone won't hit your targets.

**Cost:** $500-$2,000 / 75,000-300,000円 per channel test
**Time:** 2-4 weeks per channel
**Team:** 1 person (or agency)

**How to run it:**

1. **Select 2-3 channels to test:**

   | Channel | Best for | Minimum budget (JPY/USD) |
   |---|---|---|
   | Google Search Ads | High-intent buyers searching for solutions | ¥75,000 / $500 |
   | Facebook/Instagram Ads | B2C, visual products, interest targeting | ¥75,000 / $500 |
   | LinkedIn Ads | B2B, professional audiences | ¥150,000 / $1,000 (expensive CPMs) |
   | Twitter/X Ads | Tech, media, opinion leaders | ¥75,000 / $500 |
   | TikTok Ads | Gen Z/Millennial consumers | ¥75,000 / $500 |
   | LINE Ads (Japan) | Japanese consumer market, broad reach | ¥100,000 / $670 |

2. **For each channel:**
   - Create 3-5 ad variations (different headlines, images, CTAs).
   - Set up proper tracking (UTM parameters, conversion pixels).
   - Run for 7-14 days or until you have 100+ clicks per variation.
   - Measure: CPC, CTR, conversion rate, CPA (cost per acquisition).

3. **Compare channels** on CPA vs your target CAC.

> **See also**: `unit-economics/` -- Target CACの計算方法（LTV:CAC > 3:1）

**Success criteria template:**

```
Hypothesis: We can acquire customers through [channel] at a CAC
            under ¥[target] / $[target].

Setup:
  Channels tested:                 ____
  Budget per channel:              ¥____ / $____
  Duration:                        ____ days
  Landing page conversion rate:    ____%

Results per channel:
  | Channel    | Spend     | Clicks | CTR   | Signups | CPA       | Target CAC |
  |------------|-----------|--------|-------|---------|-----------|------------|
  | Channel A  | ¥    / $  |        |    %  |         | ¥    / $  | ¥    / $   |
  | Channel B  | ¥    / $  |        |    %  |         | ¥    / $  | ¥    / $   |
  | Channel C  | ¥    / $  |        |    %  |         | ¥    / $  | ¥    / $   |

Best performing channel:           ____
CPA vs target CAC:                 ¥____ vs ¥____ (____% of target)

Decision:
  [ ] VALIDATED: CPA < target CAC with room to scale -> increase budget
  [ ] PARTIALLY VALIDATED: CPA close to target -> optimize ads/landing page
  [ ] INVALIDATED: CPA > 2x target CAC -> try different channels or messaging
```

---

### 4.2 Content Marketing Experiment

**Description:** Publish 5-10 pieces of content (blog posts, videos, tweets, LinkedIn posts) to test whether content can attract your target audience organically.

**When to use:**
- When your product solves a problem people actively search for information about.
- When you want a scalable, lower-cost channel (long-term).
- When you have expertise that provides genuine value.

**Cost:** $0-$1,000 / 0-150,000円 (writing time, tools)
**Time:** 4-8 weeks (content takes time to compound)
**Team:** 1 person

**How to run it:**

1. **Identify 5-10 topics** your target customers search for (use keyword research from Problem Validation).
2. **Create content:**
   - Blog posts (1,000-2,000 words, SEO-optimized)
   - Twitter/X threads
   - LinkedIn posts
   - YouTube videos
   - note.com articles (Japan)
   - Newsletter issues
3. **Publish consistently** (at least 2x/week for 4 weeks).
4. **Measure:**
   - Traffic (organic + referral)
   - Email signups from content
   - Time on page / engagement
   - Shares and comments
5. **Track which topics and formats perform best.**

**Success criteria template:**

```
Hypothesis: Content about [topic area] will attract [target customer]
            and convert them to [action].

Setup:
  Pieces published:                ____ / 10 target
  Platforms:                       ____
  Duration:                        ____ weeks
  CTA on content:                  ____

Results:
  Total impressions/views:         ____
  Total clicks/visits:             ____
  Email signups from content:      ____
  Signup rate:                     ____%
  Best-performing piece:           [title] (______ views)
  Best-performing platform:        ____

Content-to-signup funnel:
  Impressions -> Visits:           ____% (CTR)
  Visits -> Signups:               ____%
  Cost per signup (time-based):    ~¥____ / $____ (your hourly rate x hours / signups)

Decision:
  [ ] VALIDATED: Consistent signups + growing traffic -> scale content production
  [ ] PARTIALLY VALIDATED: Traffic but low conversion -> improve CTAs and funnel
  [ ] INVALIDATED: No traction after 4+ weeks -> content may not be the channel
```

---

## Validation Sequencing Guide

Run validations in this order to minimize waste:

```
Phase 1: Problem Validation (Week 1-3)
  |-- Problem Interviews (10-20 interviews)
  |   > See also: mom-test/ for interview technique
  |-- Search Volume Analysis (parallel)
  |-- Observation (if applicable)
       |
       v
  GATE: Is the problem real and painful enough?
  If NO -> pivot to a different problem
  If YES -> proceed to Phase 2
       |
       v
Phase 2: Solution Validation (Week 3-6)
  |-- Concierge MVP or Wizard of Oz (5-10 customers)
  |   > See also: pretotyping/ for additional pretotype types
  |-- Landing Page Test (parallel)
  |-- Fake Door Test (if existing product)
       |
       v
  GATE: Does the solution work? Do people want it?
  If NO -> iterate on solution or pivot
  If YES -> proceed to Phase 3
       |
       v
Phase 3: Willingness-to-Pay (Week 6-8)
  |-- Pre-order / Deposit test
  |-- Price Sensitivity Survey (parallel)
  |-- OR Crowdfunding (if applicable)
       |
       v
  GATE: Will people pay enough to make unit economics work?
  If NO -> adjust pricing, features, or target segment
  If YES -> proceed to Phase 4
  > See also: unit-economics/ for LTV/CAC analysis
       |
       v
Phase 4: Channel Validation (Week 8-12)
  |-- Small-budget ad tests (2-3 channels)
  |-- Content marketing experiment (parallel)
       |
       v
  GATE: Can we acquire customers at acceptable CAC?
  If NO -> test more channels or improve conversion
  If YES -> SCALE
  > See also: tam-sam-som/ for market sizing to plan scale
```

## Japanese Business Example: AI議事録ツールの4段階検証

### 背景
「オンライン会議の議事録をAIで自動生成する」ツール。ターゲットは日本の中小企業（50-300名）のDX推進担当者。

### Phase 1: Problem Interview (2週間)

```
仮説: DX推進担当者は議事録作成に月10時間以上費やしており、
      それを大きな課題と感じている。

結果:
  インタビュー数:            15名（LinkedIn経由で募集）
  議事録が課題と自発的に
    言及した割合:            73% ✓ (target: >50%)
  月の議事録作成時間:        平均8.5時間
  既存の解決策に
    お金を使っている:        27% ✓ (target: >20%)
  深刻度 (1-10):             7.8 ✓ (target: >7)

判定: VALIDATED → Phase 2へ
追加発見: 「議事録よりも、決定事項のフォローアップが追えない」という
         隣接問題が12/15名から出た → 将来の機能候補
```

### Phase 2: Fake Door Test (2週間)

```
仮説: DX推進担当者の5%以上がLP訪問時に無料トライアルに申し込む

セットアップ:
  LP: ペライチで作成（15,000円）
  広告: LinkedIn + Google検索広告（100,000円）
  キーワード: 「AI 議事録」「会議 自動文字起こし」「議事録 自動化」

結果:
  LP訪問者:                  420名
  メール登録:                29名 (6.9%)  ✓ (target: >5%)
  CPC: 238円 ($1.59)
  CPL: 3,448円 ($23.00)

判定: VALIDATED → Phase 3へ
```

### Phase 3: Pre-Order (3週間)

```
仮説: メール登録者の10%以上が、月額¥9,800の年間プランを先行予約する

セットアップ:
  29名のメール登録者にオファーメール送信
  先行予約特典: 初年度30%オフ = ¥82,320/年（通常¥117,600）
  PAY.JPで決済セットアップ

結果:
  メール開封:                22/29 (76%)
  LP再訪問:                  18/29 (62%)
  先行予約:                  4/29 (13.8%)  ✓ (target: >10%)
  Revenue collected:         ¥329,280 ($2,195)

判定: VALIDATED → Phase 4へ
```

> **See also**: `unit-economics/` -- この価格設定でのLTV/CAC/Payback Period分析

### Phase 4: Channel Test (4週間)

```
仮説: CAC ¥30,000以下で月10社獲得可能なチャネルがある

テスト結果:
  | Channel         | Budget    | Signups | CPA       | Target  |
  |-----------------|-----------|---------|-----------|---------|
  | Google Search   | ¥80,000   | 8       | ¥10,000   | ¥30,000 | ✓ Best
  | LinkedIn Ads    | ¥100,000  | 3       | ¥33,333   | ¥30,000 | △ Over
  | note.com記事    | ¥0 (時間) | 5       | ~¥8,000*  | ¥30,000 | ✓ 効率的

  *時間コスト: 記事4本 x 5時間 x ¥2,000/h = ¥40,000 → ¥40,000/5 = ¥8,000

判定: Google Search + Content Marketingの組み合わせで
      CAC ¥10,000-15,000で獲得可能 → SCALE
```

## Anti-Patterns (これをやったらアウト)

### 1. 検証フェーズの飛ばし
**Detection**: 問題検証なしにいきなりLP作成やMVP開発に入る
**Problem**: 誰も持っていない課題のソリューションを検証しても意味がない
**Fix**: Phase 1 → 2 → 3 → 4の順序を守る。各Gateで判定してから次へ

### 2. 確証バイアスによる結果解釈
**Detection**: 「3%は悪くない」（当初目標は10%だった）、「この人は例外」（否定的な声を無視）
**Problem**: どんな結果でも成功と解釈してしまい、ピボットのタイミングを逃す
**Fix**: 成功基準をテスト前に書面で合意。テンプレートの「Decision」セクションを事前に埋める

### 3. サンプル不足での判断
**Detection**: 「3人に聞いたら全員『いいね』と言った」→ 検証完了
**Problem**: n=3では統計的に何も言えない。特に定性データは最低10人必要
**Fix**: 最低サンプル: インタビュー10-20名、アンケート50名以上、LP 500訪問者以上

### 4. 「使いたい」を検証と勘違い
**Detection**: アンケートの「使いたいですか？」に「はい」が多い → 検証成功
**Problem**: 仮説的な質問には仮説的な回答しか返ってこない。日本では特に「はい」バイアスが強い
**Fix**: 行動シグナルのみ計測する：クリック、登録、支払い、時間投資、紹介
> **See also**: `mom-test/` -- 意見ではなく行動・事実を引き出すインタビュー手法

### 5. 全部同時に検証
**Detection**: 問題・ソリューション・価格・チャネルを同時並行でテスト
**Problem**: 変数が多すぎて何が効いているか分からない。失敗時に原因特定不可
**Fix**: Validation Sequencing Guideに従い、1フェーズずつ進める

### 6. 記録しない実験
**Detection**: 実験を走らせたが結果を文書化していない。「なんとなく良かった」
**Problem**: 学びが蓄積せず、同じ失敗を繰り返す。チームへの共有も不可
**Fix**: 全実験でSuccess Criteria Templateを使い、日付と結果を記録・保存

## Common Pitfalls

### 1. Skipping problem validation

**Mistake:** Jumping straight to building an MVP because "we already know the problem."
**Fix:** Always start with 10+ problem interviews, even if you think you know the answer.

### 2. Confirmation bias

**Mistake:** Interpreting ambiguous results as positive because you want the idea to work.
**Fix:** Define success criteria BEFORE running the experiment. Be honest.

### 3. Asking "Would you use this?"

**Mistake:** Hypothetical questions produce hypothetical answers.
**Fix:** Look for commitment signals: time, money, reputation, behavior.

### 4. Running too many experiments simultaneously

**Mistake:** Testing problem, solution, pricing, and channels at the same time.
**Fix:** Sequence your validations. Each phase should inform the next.

### 5. Insufficient sample size

**Mistake:** "We talked to 3 people and they loved it!"
**Fix:** Minimum sample sizes:
- Problem interviews: 10-20
- Surveys: 50+ (ideally 100+)
- Landing page tests: 500+ visitors
- Ad tests: 100+ clicks per variation

### 6. Not recording what you learned

**Mistake:** Running experiments but not documenting results systematically.
**Fix:** Use the success criteria templates above. Fill them in. Date them. Store them where the team can see them.

### 7. Anchoring on the first idea

**Mistake:** Validating one solution when you should be exploring the solution space.
**Fix:** Before committing to a solution approach, brainstorm at least 3 possible solutions. Test the riskiest assumptions of each before picking one.

## References

- Ries, Eric. *The Lean Startup.* Crown Business, 2011.
- Fitzpatrick, Rob. *The Mom Test.* Robfitz Ltd, 2013.
- Savoia, Alberto. *The Right It.* HarperOne, 2019.
- Bland, David & Osterwalder, Alexander. *Testing Business Ideas.* Wiley, 2019.
- Croll, Alistair & Yoskovitz, Benjamin. *Lean Analytics.* O'Reilly, 2013.
