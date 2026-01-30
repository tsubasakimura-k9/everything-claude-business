# Jobs to Be Done (JTBD)

## Quick Reference
- **Core idea**: People don't buy products -- they "hire" them to make progress in a specific life circumstance
- **Key question**: "What job is the customer hiring this product to do?"
- **When to use**: Feature prioritization, competitive analysis, customer segmentation by need, reframing a stalled product
- **Output**: Job statements, job map, opportunity scores, needs-based segments
- **Time**: 2-4 weeks for full research cycle (interviews + analysis)

## Overview

Jobs to Be Done is a theory of innovation and customer behavior that reframes how we understand why people buy and use products. Instead of asking "What do our customers look like?" (demographics) or "What do they say they want?" (stated preferences), JTBD asks: "What job is the customer hiring this product to do?"

The core insight: people don't buy products -- they "hire" them to make progress in a specific circumstance. When the product does the job well, they "hire" it again. When it fails, they "fire" it and look for something else.

This theory was developed primarily by Clayton Christensen (Harvard Business School) and expanded into a practical innovation framework by Tony Ulwick (Strategyn) through his Outcome-Driven Innovation (ODI) methodology.

**The milkshake example (Christensen):** A fast-food chain wanted to sell more milkshakes. Demographics and surveys didn't help. By observing customers, researchers found that 40% of milkshakes were bought before 8:30 AM by commuters. The "job" wasn't "enjoy a dessert" -- it was "give me something interesting to do during my boring commute that keeps me full until lunch." Competitors weren't other milkshakes -- they were bananas, bagels, and boredom. This reframing led to actionable improvements (thicker consistency, flavor variety, faster purchase process).

## When to Apply

- Defining what to build next (feature prioritization, product roadmap)
- Understanding why customers switch to or from your product
- Entering a new market and identifying unmet needs
- Segmenting customers by need rather than demographics
- Competitive analysis (your real competitors may not be who you think)
- Reframing a product that isn't gaining traction
- Identifying innovation opportunities in mature markets
- Writing better marketing copy that resonates with actual motivations

## When NOT to Use

- **Pure efficiency improvements to existing workflows**: When the job is already well-understood and the customer just wants "faster/cheaper," you don't need JTBD research -- optimize the existing solution.
- **Commodity markets driven purely by price**: If the purchase decision is 100% price-driven (e.g., bulk raw materials), JTBD adds no insight.
- **Behavior dictated by regulation**: When customer actions are mandated by law rather than choice, JTBD is less relevant.
- **You need to validate demand, not understand motivation**: If the question is "Will anyone buy this?", use `skills/pretotyping/SKILL.md` or `skills/validation-patterns/SKILL.md` first. JTBD assumes you know the market exists; it helps you understand WHY people buy.
- **You already know the job and need to test solutions**: Use `skills/design-sprint/SKILL.md` to prototype and test specific solutions.

## Step-by-Step Process

### Step 1: Identify the Job

A "job" has a specific structure. It is NOT a task, activity, or solution. It is the progress the customer is trying to make.

**Job Statement Format (Ulwick's ODI):**
```
[Verb] + [object of the verb] + [contextual clarifier]
```

Examples:
- "Manage personal finances over time" (NOT "use a budgeting app")
- "Stay informed about industry trends during my commute" (NOT "listen to podcasts")
- "Ensure my family eats healthy meals on busy weeknights" (NOT "order a meal kit")

**Three Dimensions of Every Job:**

| Dimension | Question | Example (morning commute) |
|-----------|----------|--------------------------|
| **Functional** | What practical outcome am I trying to achieve? | Get to work on time without being hungry |
| **Emotional (personal)** | How do I want to feel? | Feel in control of my morning, not rushed |
| **Social** | How do I want to be perceived? | Be seen as someone who has their life together |

All three dimensions matter. Products that only address functional jobs often lose to inferior products that nail the emotional and social dimensions.

### Step 2: Map the Job

Every job follows a universal process (Ulwick's Job Map):

```
1. DEFINE    - What needs to be accomplished? What's the scope?
2. LOCATE    - What inputs (information, materials) are needed?
3. PREPARE   - How do I set up to do the job?
4. CONFIRM   - Is everything ready? Am I on track?
5. EXECUTE   - Perform the core activity
6. MONITOR   - Is it going as expected?
7. MODIFY    - Adjust if needed
8. CONCLUDE  - Finish the job and clean up
```

Map your customer's job across these stages. At each stage, identify:
- What is the customer trying to do?
- What outcomes do they want (speed, accuracy, reliability, etc.)?
- What is frustrating or difficult?

### Step 3: Identify Desired Outcomes

Outcomes are the metrics customers use to judge how well a job is being done. They follow a specific format:

**Outcome Statement Format (Ulwick):**
```
[Direction of improvement] + [metric] + [object of control] + [contextual clarifier]
```

Examples:
- "Minimize the time it takes to identify the right meal for tonight"
- "Minimize the likelihood of choosing an ingredient my child won't eat"
- "Increase the accuracy with which I estimate total preparation time"

**Rules for good outcomes:**
- They are solution-agnostic (no product references)
- They are measurable (even if subjectively)
- They have a clear direction (minimize, increase, reduce)
- They represent what the customer wants, not what they do

### Step 4: Quantify Opportunity

Survey customers on each outcome using two questions:

1. **Importance:** "How important is this outcome to you?" (1-5 scale)
2. **Satisfaction:** "How satisfied are you with how well current solutions deliver this outcome?" (1-5 scale)

**Opportunity Score (Ulwick):**
```
Opportunity = Importance + max(Importance - Satisfaction, 0)
```

- Score > 10: **Underserved** -- high importance, low satisfaction. These are innovation opportunities.
- Score 8-10: **Appropriately served** -- current solutions are adequate.
- Score < 8: **Overserved** -- potential for disruption by simpler, cheaper solutions.

```
OPPORTUNITY LANDSCAPE
| Outcome Statement | Importance (1-5) | Satisfaction (1-5) | Opportunity Score | Segment |
|-------------------|-------------------|--------------------|-------------------|---------|
|                   |                   |                    |                   |         |
```

### Step 5: Discover Segments Based on Unmet Needs

Traditional segmentation uses demographics. JTBD segments by unmet needs. Customers with similar unmet outcomes cluster into opportunity segments, regardless of age, income, or geography.

This often reveals surprising segments:
- A "power user" segment that is underserved on advanced outcomes
- A "simplicity seeker" segment that is overserved (they'd prefer a simpler, cheaper solution)
- A "niche" segment with unique outcomes that no one is addressing

### Step 6: Build Solutions That Address Underserved Outcomes

Now -- and only now -- do you design solutions. For each underserved outcome:
- Brainstorm features or approaches that would improve that outcome
- Evaluate: does this feature address a high-opportunity outcome?
- Prioritize features by the number of underserved outcomes they address

## Key Templates and Frameworks

### Job Story Format (Alan Klement)

An alternative to user stories that centers the job:

```
When [situation/context],
I want to [motivation/forces],
so I can [expected outcome].
```

Example:
```
When I'm planning meals for the week and my partner has dietary restrictions,
I want to quickly find recipes that work for both of us,
so I can avoid the stress of last-minute meal decisions on weeknights.
```

Compare to a user story: "As a home cook, I want to filter recipes by dietary restriction so that I can find suitable meals." The job story captures the WHY (the circumstance, the emotional weight, the desired progress).

### Forces of Progress Diagram

Four forces determine whether a customer will switch from their current solution to a new one:

```
           FORCES PUSHING FOR CHANGE
           +------------------------+
           |  Push of the current   | <- Frustration with status quo
           |      situation         |
           |                        |
           |  Pull of the new       | <- Attraction of the new solution
           |      solution          |
           +------------------------+
                     vs.
          FORCES RESISTING CHANGE
           +------------------------+
           |  Anxiety of the new    | <- "What if it doesn't work?"
           |      solution          |
           |                        |
           |  Habit of the current  | <- "I'm used to how I do it now"
           |      situation         |
           +------------------------+

Switch happens when PUSH + PULL > ANXIETY + HABIT
```

**Template for Analysis:**
```
FORCES OF PROGRESS ANALYSIS
============================
Product/Solution: ___________
Target Job: ___________

PUSH (frustration with current situation):
- ___________
- ___________

PULL (attraction of new solution):
- ___________
- ___________

ANXIETY (fears about switching):
- ___________
- ___________

HABIT (comfort with current behavior):
- ___________
- ___________

Net Assessment:
Push + Pull [vs.] Anxiety + Habit = Switch likely? Y/N
What can we do to reduce anxiety? ___________
What can we do to break habit? ___________
```

### Competitive Landscape (Job-Based)

```
JOB-BASED COMPETITIVE ANALYSIS
================================
Job: ___________

| Solution (Hired) | Type | Functional Score | Emotional Score | Social Score | Weaknesses |
|-------------------|------|-----------------|-----------------|--------------|------------|
| [Your product]    |      |                 |                 |              |            |
| [Direct competitor]|     |                 |                 |              |            |
| [Indirect: different category]| |          |                 |              |            |
| [Non-consumption: doing nothing]| |        |                 |              |            |
```

Note: "Non-consumption" (doing nothing, or cobbling together a workaround) is often your biggest competitor.

## JTBD Interview Techniques

### Interview Goal

Uncover the REAL job by exploring a specific instance when the customer "hired" or "fired" a solution. Do NOT ask hypothetical questions. Ask about real past events.

> **See also**: For comprehensive interview technique that prevents biased questioning, refer to `skills/mom-test/SKILL.md`. The Mom Test principles apply directly to JTBD interviews.

### Timeline Interview (Switch Interview)

Focus on the moment they switched from one solution to another:

```
1. FIRST THOUGHT
   "When did you first start thinking you needed something different?"
   "What was going on in your life at that time?"

2. PASSIVE LOOKING
   "Did you start looking at alternatives? How?"
   "What did you look at? What was appealing?"

3. ACTIVE LOOKING (Event 1: Something triggers active search)
   "What happened that made you start actively looking?"
   "What did you search for? Who did you talk to?"

4. DECIDING (Event 2: The purchase/switch moment)
   "When did you actually decide? What tipped you over?"
   "What almost stopped you from switching?"
   "Did anyone influence your decision?"

5. CONSUMING / FIRST USE
   "What was the first experience like?"
   "Was it what you expected?"

6. ONGOING USE
   "How has it been since then?"
   "Is it doing the job you hired it for?"
   "What's still frustrating?"
```

### Interview Do's and Don'ts

| Do | Don't |
|----|-------|
| Ask about specific past events | Ask hypothetical "would you..." questions |
| Ask "Tell me about the last time..." | Ask "What do you usually do?" |
| Listen for emotions and context | Focus only on features mentioned |
| Ask "Why?" multiple times to dig deeper | Accept the first answer at face value |
| Note what they DID, not just what they SAY | Assume stated preferences equal actual behavior |
| Explore the full timeline (months before the switch) | Only ask about the moment of purchase |

## Anti-Patterns (これをやったらアウト)

- **Solution Masquerading as a Job**: "I need a CRM" is a solution. "Manage customer relationships to close more deals" is a job. If the user defines their job as a product category, dig deeper immediately.
- **Jobs Too Broad or Too Narrow**: "Live a better life" gives no product direction. "Click the submit button" is a UI step, not a job. The right level: "Manage personal finances over time." Flag both extremes.
- **Demographics-First Segmentation After JTBD Research**: If JTBD reveals needs-based segments, DO NOT collapse them back into age/income/geography segments. A 22-year-old and a 55-year-old can share the same job.
- **Ignoring Emotional and Social Jobs**: Engineers and technical founders gravitate toward functional jobs. People buy Harley-Davidsons for identity (social), not transportation (functional). If the analysis only covers functional jobs, flag the gap.
- **Asking "What Features Do You Want?"**: This produces feature requests, not job insights. The customer designs for you -- badly. Dig into motivation: "What would that let you do? Why?"
- **競合を同業他社だけで見る (Competitors = Same Industry Only)**: The milkshake's competitors were bananas and boredom, not other milkshakes. If the competitive analysis only lists direct competitors, it's incomplete.

## Japanese Business Example: DX推進コンサルティングのJTBD分析

**Context**: A consulting firm offering DX推進 (digital transformation) services to 中小企業 (SMBs) in Japan. Many companies are adopting DX because of government pressure (デジタル庁の方針) and 人手不足 (labor shortage), but adoption is slow.

**Research:** Interviewed 15 中小企業の経営者 using the timeline interview about the last time they considered or adopted a digital tool.

**Discovery -- Three Distinct Jobs:**

| Job | Functional | Emotional | Social |
|-----|-----------|-----------|--------|
| **Job 1: 属人化を解消する** (Eliminate key-person dependency) | Ensure operations continue when the 担当者 (person in charge) is absent | Feel secure that the business won't collapse if someone quits | Be seen as a well-managed company by partners and banks |
| **Job 2: 補助金を活用する** (Utilize government subsidies) | Get IT導入補助金 to reduce costs | Feel smart about using public resources | Be perceived as forward-thinking by industry peers |
| **Job 3: 若い人材を採用する** (Attract young talent) | Offer modern work environment to compete for talent | Feel proud of the company's future | Be seen as innovative by job candidates |

**Key Insight:** Most DX vendors sell "efficiency" (functional). But the strongest underserved job was Job 1 (属人化の解消) with a dominant emotional dimension: fear of business collapse. Marketing should lead with "あの人がいなくても回る仕組み" (a system that works even without that one person), not "業務効率化" (operational efficiency).

**Opportunity Scores:**
| Outcome | Importance | Satisfaction | Score |
|---------|-----------|-------------|-------|
| Minimize risk of knowledge loss when key employee leaves | 5 | 1 | 10 (Underserved) |
| Minimize time to onboard new employees | 4 | 2 | 8 (Appropriately served) |
| Minimize total cost of digital tools | 3 | 3 | 6 (Overserved) |

## Examples

### Example 1: Milkshake (Christensen)

**Situation:** Fast-food chain wants to sell more milkshakes. Traditional approach: survey customers, improve the recipe.

**JTBD Discovery:** Researchers observed two distinct jobs:
- **Morning commuters (Job 1):** "Give me something interesting during my boring drive that keeps me full until lunch." Competitors: bananas (too quick, hungry again), bagels (dry, crumbs), snickers (guilt). Milkshake wins: thick (lasts 20 min), satisfying, fun through straw.
- **Parents with kids after school (Job 2):** "Be a good parent by saying yes to a treat." Competitors: toys, candy. Milkshake loses: too thick, takes too long, kids get impatient.

**Insight:** Same product, two different jobs, requiring two different solutions. Morning milkshake should be thicker with chunks (more interesting, longer lasting). After-school milkshake should be thinner and smaller (faster to finish).

### Example 2: Intercom (B2B SaaS)

**Situation:** Intercom used JTBD to understand their customer messaging platform.

**JTBD Discovery:** Customers didn't hire Intercom for "customer support chat." They hired it for different jobs:
- "Onboard new users so they reach their aha moment faster"
- "Re-engage users who are about to churn"
- "Qualify leads without hiring more salespeople"

**Insight:** Each job required different features, messaging, and positioning. Intercom built separate product lines (Acquire, Engage, Support) around these distinct jobs rather than one monolithic "chat widget."

### Example 3: JTBD for a New Product

**Situation:** A founder wants to build a tool for freelancers.

**Research:** Interviewed 12 freelancers using the timeline interview technique about the last time they changed how they manage their business.

**Discovery:**
- Functional job: "Get paid reliably and on time without chasing clients"
- Emotional job: "Feel like a legitimate business, not a side hustler"
- Social job: "Be perceived as professional by clients"

**Underserved outcomes:**
- "Minimize the time it takes to follow up on overdue invoices" (Importance: 5, Satisfaction: 1)
- "Minimize the embarrassment of asking for money" (Importance: 4, Satisfaction: 1)
- "Increase the confidence that I'll be paid before starting work" (Importance: 5, Satisfaction: 2)

**Insight:** The emotional job (feeling legitimate) and the functional job (getting paid) converge. A tool that automates payment collection AND makes the freelancer look professional (branded invoices, automated reminders that look like they come from a "system" rather than a person) addresses the top underserved outcomes.

## Common Pitfalls

1. **Confusing jobs with solutions.** "I need a faster horse" is a solution request. The job is "get from A to B quickly and comfortably." Always abstract up from the stated desire to the underlying progress the customer wants to make.

2. **Ignoring emotional and social jobs.** Engineers and technical founders gravitate toward functional jobs and miss the emotional dimensions. People buy Harley-Davidsons for the identity (social), not the transportation (functional). Consumer products almost always have a dominant emotional or social job.

3. **Defining jobs too broadly or too narrowly.** "Live a better life" is too broad -- it doesn't guide product decisions. "Click the blue button" is too narrow -- it's a step, not a job. The right level is: "Manage personal finances over time" or "Stay informed about industry trends."

4. **Asking customers what they want instead of observing what they do.** Customers are notoriously bad at predicting their own behavior. JTBD is grounded in actual behavior -- what they hired, what they fired, and why. The timeline interview reveals reality; surveys reveal aspiration.

5. **Treating JTBD as another way to write user stories.** Job stories and user stories serve different purposes. User stories describe features. Job stories describe the progress customers want to make. Don't just swap the format and keep the feature-centric thinking.

6. **Forgetting "non-consumption."** Sometimes the biggest competitor is NOT another product. It's the customer doing nothing, using a spreadsheet, or cobbling together a manual workaround. These are the most underserved situations -- and often the biggest opportunities.

7. **Segmenting by demographics after doing JTBD research.** If your JTBD research reveals needs-based segments, don't collapse them back into demographic segments for convenience. A 22-year-old college student and a 55-year-old executive can have the same job.

## References

- Christensen, Clayton M., Taddy Hall, Karen Dillon, and David S. Duncan. *Competing Against Luck: The Story of Innovation and Customer Choice.* Harper Business, 2016.
- Christensen, Clayton M. *The Innovator's Dilemma.* Harvard Business Review Press, 1997.
- Ulwick, Anthony W. *Jobs to Be Done: Theory to Practice.* IDEA BITE PRESS, 2016.
- Ulwick, Anthony W. *What Customers Want: Using Outcome-Driven Innovation to Create Breakthrough Products and Services.* McGraw-Hill, 2005.
- Klement, Alan. *When Coffee and Kale Compete.* 2016. (Free online: https://www.whencoffeeandkalecompete.com/)
- Moesta, Bob and Greg Engle. *Demand-Side Sales 101: Stop Selling and Help Your Customers Make Progress.* Lioncrest Publishing, 2020.
- Christensen, Clayton M., Scott Cook, and Taddy Hall. "Marketing Malpractice: The Cause and the Cure." *Harvard Business Review*, December 2005.
