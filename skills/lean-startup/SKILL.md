# Lean Startup

## Quick Reference
- **Core idea**: Test business assumptions through rapid Build-Measure-Learn cycles before committing resources
- **Key question**: "Is this idea worth pursuing, and what's the fastest way to find out?"
- **When to use**: New product/service launch, market entry, or any high-uncertainty initiative
- **Output**: Validated/invalidated hypotheses, experiment cards, pivot-or-persevere decisions
- **Time**: 1-4 weeks per Build-Measure-Learn cycle

## Overview

The Lean Startup methodology, developed by Eric Ries, is a systematic approach to creating and managing startups and new products under conditions of extreme uncertainty. The core insight is that startups are not smaller versions of large companies -- they are organizations searching for a scalable, repeatable business model. Instead of executing a fixed plan, startups should run experiments to validate (or invalidate) their assumptions as quickly and cheaply as possible.

The methodology is built on three pillars:

1. **Build-Measure-Learn** -- the fundamental feedback loop
2. **Validated Learning** -- the unit of progress for a startup
3. **Innovation Accounting** -- how to measure progress when traditional metrics don't apply

## When to Apply

- Launching a new product or service where customer demand is uncertain
- Entering a new market with an existing product
- Adding a major new feature where user behavior is unpredictable
- Any situation where you have a hypothesis but lack evidence
- Internal innovation projects within established companies ("intrapreneurship")
- When the cost of being wrong is high but the cost of testing is low
- Early-stage ventures with limited runway

## When NOT to Use

- **Requirements are well-known and stable**: When building to a clear specification (e.g., regulatory compliance features), just execute.
- **Regulatory environments requiring full solutions before launch**: Medical devices, financial products with strict compliance -- you cannot ship an MVP to patients or investors without meeting legal requirements.
- **Infrastructure projects with clear specifications**: Building a database migration or internal tool with known requirements does not benefit from hypothesis testing.
- **You haven't identified your riskiest assumption yet**: If you don't know what you're testing, use `skills/jobs-to-be-done/SKILL.md` or `skills/mom-test/SKILL.md` first to discover the real problem.
- **You need to validate demand before even building an MVP**: Use `skills/pretotyping/SKILL.md` -- it's cheaper and faster than an MVP.

## Step-by-Step Process

### Step 1: Identify Your Leap-of-Faith Assumptions

Every business plan rests on assumptions. The two most critical are:

- **Value Hypothesis**: Does the product deliver value to customers once they use it? Will customers care?
- **Growth Hypothesis**: How will new customers discover the product? What is the engine of growth?

**Action:** List every assumption your business model depends on. Rank them by risk (how likely they are to be wrong) and impact (how much damage being wrong would cause). Start with the riskiest, highest-impact assumption.

```
Assumption Mapping Template:
| # | Assumption | Risk (H/M/L) | Impact (H/M/L) | Priority | How to Test |
|---|-----------|---------------|-----------------|----------|-------------|
| 1 |           |               |                 |          |             |
| 2 |           |               |                 |          |             |
```

### Step 2: Build the MVP (Minimum Viable Product)

The MVP is the smallest thing you can build to test your riskiest assumption. It is NOT a stripped-down version of your final product. It is an experiment designed to generate validated learning.

**Types of MVPs:**
- **Concierge MVP**: Manually deliver the service to a handful of customers (no tech)
- **Wizard of Oz MVP**: Looks automated to the user but is manual behind the scenes
- **Landing Page MVP**: A page describing the product with a sign-up button (measures demand)
- **Video MVP**: A demo video showing what the product would do (Dropbox used this)
- **Single-Feature MVP**: One core feature, nothing else

> **See also**: For detailed descriptions of each experiment type with success criteria templates, refer to `skills/validation-patterns/SKILL.md`. For pre-MVP demand testing techniques, refer to `skills/pretotyping/SKILL.md`.

**Key principle:** The MVP should test the assumption, not showcase your vision. Remove everything that doesn't directly contribute to learning.

### Step 3: Measure

Define your metrics BEFORE you build. You need to know what "success" and "failure" look like in advance, or you will rationalize any result.

**Use actionable metrics, not vanity metrics:**
- Vanity: total users, page views, downloads
- Actionable: activation rate, retention at day 7, revenue per user, referral rate

**Cohort Analysis:** Group users by when they signed up and track their behavior over time. This reveals whether your changes are actually improving things.

**Split Testing (A/B):** When possible, test variations simultaneously to isolate the effect of changes.

### Step 4: Learn

Compare your results to your hypothesis. There are three outcomes:

1. **Hypothesis validated** -- the data supports your assumption. Proceed with more confidence.
2. **Hypothesis invalidated** -- the data contradicts your assumption. You learned something valuable.
3. **Inconclusive** -- your experiment wasn't designed well enough. Redesign and try again.

Document what you learned. This is the actual output of the process -- not the product, but the knowledge.

### Step 5: Pivot or Persevere

Based on your learning, make a deliberate decision:

- **Persevere**: The data supports your direction. Continue iterating and optimizing.
- **Pivot**: A fundamental hypothesis was wrong. Change strategy while preserving what you've learned.

**Types of Pivots:**
| Pivot Type | Description | Example |
|-----------|-------------|---------|
| Zoom-in | A single feature becomes the whole product | Flickr started as a game; photo sharing became the product |
| Zoom-out | The whole product becomes a single feature of something larger | |
| Customer Segment | Same product, different customer | |
| Customer Need | Same customer, different problem | |
| Platform | Change from application to platform (or vice versa) | |
| Business Architecture | B2B to B2C (or vice versa) | |
| Value Capture | Change how you monetize | |
| Engine of Growth | Switch between viral, sticky, or paid growth | |
| Channel | Change distribution channel | |
| Technology | Same solution, different technology | |

## Key Templates and Frameworks

### Build-Measure-Learn Card

```
EXPERIMENT CARD
===============
Date: ___________
Iteration: #___

HYPOTHESIS:
We believe that [specific, falsifiable statement].

TEST:
To verify this, we will [describe the MVP/experiment].

METRIC:
We will measure [specific metric].

SUCCESS CRITERIA:
We will know the hypothesis is validated if [metric] reaches [target].
We will know the hypothesis is invalidated if [metric] is below [threshold].

RESULTS:
Actual outcome: ___________
Validated / Invalidated / Inconclusive

LEARNING:
What we learned: ___________

NEXT ACTION:
Persevere / Pivot / Redesign experiment
Next experiment: ___________
```

### Innovation Accounting Dashboard

Innovation Accounting provides a way to measure progress when revenue and profit are not yet meaningful.

```
Phase 1: Establish the Baseline
- What does each metric look like today (or at launch)?

Phase 2: Tune the Engine
- Are experiments moving metrics in the right direction?

Phase 3: Pivot or Persevere
- Are we making sufficient progress to justify continuing?

Key Metrics to Track:
1. Acquisition: How do users find you?
   Baseline: ___ | Current: ___ | Target: ___
2. Activation: Do users have a good first experience?
   Baseline: ___ | Current: ___ | Target: ___
3. Retention: Do users come back?
   Baseline: ___ | Current: ___ | Target: ___
4. Revenue: Can you monetize?
   Baseline: ___ | Current: ___ | Target: ___
5. Referral: Do users tell others?
   Baseline: ___ | Current: ___ | Target: ___
```

### Engines of Growth

| Engine | How It Works | Key Metric |
|--------|-------------|------------|
| Sticky | High retention; users keep coming back | Churn rate (must be < new customer acquisition rate) |
| Viral | Users bring new users as a side effect of usage | Viral coefficient (must be > 1.0 for exponential growth) |
| Paid | Spend money to acquire customers profitably | LTV > CAC (customer lifetime value exceeds cost of acquisition) |

> **See also**: For detailed LTV, CAC, and churn calculations, refer to `skills/unit-economics/SKILL.md`.

## Anti-Patterns (これをやったらアウト)

- **MVP as v1.0 Product**: The founder spends 3+ months building a polished product and calls it an "MVP." If it took more than 2-4 weeks, it is not minimum. Flag immediately and push for a smaller experiment.
- **Vanity Metrics Dashboard**: The team tracks total signups, page views, or app downloads as their primary success metrics. These feel good but inform zero decisions. Insist on actionable metrics (activation rate, retention, revenue per user).
- **Post-Hoc Success Criteria**: The team defines "success" AFTER seeing the experiment results. This guarantees self-deception. Always define the threshold before running the test.
- **Pivot Without Data**: The founder pivots based on gut feeling, a single conversation, or one bad week. A pivot must be based on accumulated evidence across multiple experiments. Flag premature pivots.
- **永遠の検証ループ (Endless Validation Loop)**: The team runs experiment after experiment but never commits to building. After 3 cycles on the same assumption, either commit or abandon.
- **"リーンだから品質は不要" (Lean = No Quality)**: Treating Lean Startup as permission to ship sloppy, broken experiments. The experiment must be good enough to generate reliable data. A broken landing page doesn't test demand -- it tests patience.

## Japanese Business Example: AI研修サービスの検証

**Context**: An AI consultant (AIコンサルタント) wants to launch a standardized AI training service (AI研修サービス) for 中小企業 (SMBs) facing 人手不足 (labor shortage) and pressure for DX推進 (digital transformation).

**Assumption Mapping:**
| # | Assumption | Risk | Impact | How to Test |
|---|-----------|------|--------|-------------|
| 1 | 中小企業の経営者はAI導入に予算をつける意思がある | H | H | Problem interviews with 15 SMB executives |
| 2 | 1日研修で実務に使えるレベルになる | H | H | Concierge MVP: deliver one workshop, measure post-training adoption |
| 3 | 口コミで新規顧客を獲得できる | M | H | Track referral rate from first 10 customers |

**MVP:** Concierge MVP -- personally deliver a 1-day AI workshop to 3 companies at a discounted price of 15万円/回 (approx. $1,000 USD). Normally, a full curriculum would take months to develop. Instead, customize each session manually to learn what content resonates.

**Metrics:**
- Post-training satisfaction score (target: >4.5/5)
- % of attendees who use AI tools 2 weeks later (target: >60%)
- % of companies willing to book a follow-up session (target: >50%)

**Result:** 2 of 3 companies booked follow-up sessions. Attendees reported that hands-on exercises with their own業務データ (business data) were 10x more valuable than slides. This learning shaped the product: shift from lecture-based to workshop-based format.

## Examples

### Example 1: Dropbox

**Assumption:** People want a file sync tool that "just works" across devices.

**Problem:** Building the actual product would take months of engineering. How do you validate demand first?

**MVP:** Drew Houston created a 3-minute video demonstrating how Dropbox would work. The video was posted to Hacker News.

**Result:** The waiting list went from 5,000 to 75,000 overnight. The value hypothesis was validated without writing a single line of sync code.

**Learning:** Demand for seamless file sync was real and massive. Proceed to build.

### Example 2: Zappos

**Assumption:** People will buy shoes online (this was controversial in 1999).

**MVP (Concierge):** Nick Swinmurn went to local shoe stores, photographed their inventory, posted the photos online. When someone ordered, he went back to the store, bought the shoes at full price, and shipped them.

**Result:** People did buy shoes online. The value hypothesis was validated.

**Learning:** The inconvenience of not trying on shoes was outweighed by selection and convenience. This justified building the real infrastructure.

### Example 3: Food on the Table

**Assumption:** Busy families want a meal planning service that integrates grocery deals.

**MVP (Concierge):** The founder personally visited one customer each week, asked about their family's food preferences, checked local store deals, and created a custom meal plan and grocery list by hand.

**Result:** The customer loved it and was willing to pay. Then they added a second customer, then a third. Only when the manual process became unsustainable did they start automating.

**Learning:** By doing it manually first, they deeply understood the customer's needs before writing any code.

## Common Pitfalls

1. **Building too much into the MVP.** The MVP is not v1.0 of your product. It is the minimum experiment to test a hypothesis. If you spent 3 months building it, it probably wasn't minimum.

2. **Vanity metrics addiction.** Total sign-ups, page views, and app downloads feel good but tell you nothing about whether you have a sustainable business. Always ask: "So what? What action does this metric inform?"

3. **Failing to define success criteria in advance.** If you decide what counts as "good enough" after seeing the data, you will unconsciously move the goalposts. Write down your threshold before running the experiment.

4. **Pivot phobia.** Founders get emotionally attached to their original idea. A pivot is not a failure -- it's a strategic course correction based on evidence. The sunk cost of previous work is irrelevant.

5. **Pivoting too quickly.** The opposite problem. Some teams pivot at the first sign of difficulty without giving the current strategy a fair test. Make sure you have real data, not just anxiety.

6. **Confusing "no one wants this" with "we haven't found the right customer yet."** A negative result from one customer segment doesn't mean the idea is dead. It might mean you need a Customer Segment Pivot.

7. **Skipping the learning step.** Teams rush from Build to the next Build without stopping to analyze what they learned. The loop is Build-Measure-LEARN, not Build-Measure-Build.

8. **Treating Lean Startup as "just launch fast and break things."** Speed is a means, not an end. The goal is validated learning, not shipping quickly for its own sake.

## References

- Ries, Eric. *The Lean Startup: How Today's Entrepreneurs Use Continuous Innovation to Create Radically Successful Businesses.* Crown Business, 2011.
- Ries, Eric. *The Startup Way: How Modern Companies Use Entrepreneurial Management to Transform Culture and Drive Long-Term Growth.* Currency, 2017.
- Blank, Steve. *The Four Steps to the Epiphany.* K&S Ranch, 2005. (Precursor to Lean Startup; Customer Development methodology)
- Maurya, Ash. *Running Lean: Iterate from Plan A to a Plan That Works.* O'Reilly Media, 2012. (Practical application of Lean Startup)
- Croll, Alistair and Benjamin Yoskovitz. *Lean Analytics: Use Data to Build a Better Startup Faster.* O'Reilly Media, 2013. (Deep dive on metrics)
