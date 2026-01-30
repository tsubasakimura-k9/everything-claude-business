# Design Sprint

## Quick Reference
- **Core idea**: Compress months of design debate into a structured 5-day process: Map, Sketch, Decide, Prototype, Test
- **Key question**: "What is the right solution for this specific user problem, and how do we validate it in one week?"
- **When to use**: Big strategic question, high-stakes decision, team stuck in analysis paralysis
- **Output**: Tested prototype with 5 user interviews, clear go/no-go decision
- **Time**: 5 days (full) or 2-3 days (compressed with Claude)

## Overview

The Design Sprint is a five-day process for answering critical business questions through design, prototyping, and testing ideas with customers. Developed at Google Ventures (GV) by Jake Knapp, John Zeratsky, and Braden Kowitz, it compresses months of debate, design, and testing into a single week.

The fundamental insight is that you can learn more from a realistic prototype tested with real users in one week than from months of internal debate or premature development. The sprint provides structure that prevents the two most common failure modes: (1) endless discussion without action, and (2) building something expensive without validating it first.

**Adapted for Solo/Small Team + Claude:** The original sprint assumes 4-7 people in a room. This guide adapts the process for solo founders or small teams who use Claude as a thinking partner, design critic, and research synthesizer. The 5-day structure can be compressed to 2-3 days when working with AI assistance.

## When to Apply

- You have a big, important question that affects the direction of your product or business
- Stakes are high (significant investment of time, money, or reputation)
- You're stuck in debate or analysis paralysis
- You need to validate a new product idea, feature, or service concept quickly
- A team disagrees on the right approach and needs a way to break the tie with evidence
- You're about to invest weeks or months of development and want confidence first
- You need to align stakeholders around a concrete direction

## When NOT to Use

- **Incremental improvements**: Small UI tweaks or bug fixes don't need a 5-day process. Just ship and measure.
- **Well-understood problems with obvious solutions**: If everyone agrees on the answer and you have data to support it, skip the sprint and execute.
- **You already have strong customer data**: If you have 1,000 users and clear analytics showing what to build, you don't need 5 qualitative interviews.
- **Problem not yet defined**: If you don't know what problem to solve, use `skills/jobs-to-be-done/SKILL.md` or `skills/mom-test/SKILL.md` first.
- **Validating demand (not solution)**: If the question is "Do people want this at all?" rather than "Is this the right design?", use `skills/pretotyping/SKILL.md` or `skills/validation-patterns/SKILL.md` instead.

## Step-by-Step Process

### Day 1: Map (Understand the Problem)

**Goal:** Create a shared understanding of the problem space and choose a specific target for the sprint.

**Activities:**

1. **Set a Long-Term Goal**
   Ask: "Why are we doing this? Where do we want to be in 6 months / 1 year / 3 years?"
   Write it down. This is the North Star for the week.

2. **List Sprint Questions**
   Ask: "What could go wrong? What do we need to learn to know if we're on the right track?"
   Frame as questions: "Can we...?" "Will users...?" "Is it possible to...?"
   These are the uncertainties the sprint should resolve.

3. **Make a Map**
   Draw a simple diagram of how customers interact with your product/service from discovery to completion.
   - Left side: how customers find you
   - Middle: key interactions
   - Right side: the end goal (purchase, completion, satisfaction)
   Keep it simple: 5-15 steps maximum.

4. **Ask the Experts**
   Interview people with relevant knowledge (even if it's just yourself wearing different hats):
   - The customer perspective
   - The technical perspective
   - The business/market perspective
   - The sales/support perspective

   **With Claude:** Share your map and context, then ask Claude to role-play each perspective and challenge your assumptions.

5. **Pick a Target**
   Choose ONE specific customer and ONE specific moment on the map to focus the rest of the sprint on. You cannot solve everything in one sprint. Pick the most important, most risky moment.

```
DAY 1 OUTPUT:
- Long-term goal: ___________
- Sprint questions (top 3):
  1. ___________
  2. ___________
  3. ___________
- Customer map (diagram)
- Target customer: ___________
- Target moment on map: ___________
```

### Day 2: Sketch (Generate Solutions)

**Goal:** Generate a wide range of possible solutions, then converge on the most promising ones.

**Activities:**

1. **Lightning Demos** (30 min)
   Review existing solutions -- competitors, analogous products from other industries, inspiring examples.
   For each, capture: what's the big idea? What can we steal?

   **With Claude:** Ask Claude to research and present 5-10 analogous solutions from different industries that solve similar problems.

2. **Four-Step Sketch Process**

   a. **Notes** (20 min): Review all information from Day 1. Write down what stands out.

   b. **Ideas** (20 min): Sketch rough ideas -- words, diagrams, anything. Quantity over quality.

   c. **Crazy 8s** (8 min): Fold a sheet into 8 panels. Sketch 8 variations of your best idea, one per panel, one minute each. This forces you past your first (often obvious) idea.

   d. **Solution Sketch** (30-60 min): Create a detailed, 3-panel storyboard of your best solution. It should be self-explanatory -- someone who wasn't in the room should understand it. Add notes. Be specific.

   **With Claude:** Describe your top concepts and ask Claude to generate 5 alternative approaches you haven't considered. Use these as input for your Crazy 8s.

3. **Anonymize and Post**
   In a team setting, sketches are anonymous to reduce bias. Pin them on a wall. Solo? Lay them out and evaluate them the next day with fresh eyes.

```
DAY 2 OUTPUT:
- Lightning demo notes (5-10 examples)
- 8+ rough concepts (Crazy 8s)
- 1-3 detailed solution sketches (3-panel storyboards)
```

### Day 3: Decide (Choose the Best Solution)

**Goal:** Select one solution to prototype without getting bogged down in debate.

**Activities:**

1. **Art Museum** (silent review)
   Walk through all solution sketches silently. No discussion yet.

2. **Heat Map**
   Everyone places dot stickers on parts of solutions they find compelling. Clusters of dots reveal what resonates. Solo: mark what you believe has the highest chance of answering your sprint questions.

3. **Speed Critique** (3 min per sketch)
   The facilitator narrates each sketch. The group calls out standout ideas and concerns. The creator stays silent and listens, then explains anything the group missed at the end.

4. **Straw Poll**
   Each person votes for the solution they want to prototype. The Decider (whoever has authority) makes the final call.

5. **Storyboard**
   Create a detailed, step-by-step storyboard (10-15 frames) of the user experience you will prototype tomorrow. This is the blueprint for Day 4.

   **With Claude:** Share your chosen concept and ask Claude to help you create the storyboard, identifying gaps in the flow, edge cases, and moments where users might get confused.

```
DAY 3 OUTPUT:
- Winning solution selected
- Detailed storyboard (10-15 frames)
- Clear scope of what the prototype will include and exclude
```

### Day 4: Prototype (Build a Facade)

**Goal:** Build a realistic-looking prototype that is just real enough to test with users. It does NOT need to work. It needs to look like it works.

**Key Principle:** "Goldilocks quality" -- good enough to get honest reactions, not so polished that it took too long.

**Prototype Tools:**
- **Digital product:** Figma, Keynote/PowerPoint, or a simple HTML page
- **Physical product:** 3D print, cardboard, or modify an existing product
- **Service:** A brochure, a script for a "concierge" experience, a fake website
- **Marketing:** A landing page, ad mock-up, or email draft

**Rules:**
- Assign roles: Makers (build), Stitcher (ensures consistency), Writer (realistic copy), Asset Collector (images, icons), Interviewer (prepares for Day 5)
- Solo: You are all roles. Use Claude as your Writer and Asset Collector.
- Work from the storyboard. Each frame becomes a screen or step.
- Use real text, not Lorem Ipsum. Realism is critical for honest feedback.
- Do a trial run at the end of the day. Walk through the prototype as if you were a customer.

**With Claude:** Ask Claude to write realistic UI copy, generate test data, draft email content, or create interview scripts for Day 5.

```
DAY 4 OUTPUT:
- Clickable/walkable prototype
- Interview script for Day 5
- Schedule of 5 test users confirmed
```

### Day 5: Test (Learn from Real Users)

**Goal:** Show the prototype to 5 real users and identify patterns in their reactions.

**Why 5 users?** Nielsen's research shows that 5 users reveal approximately 85% of usability issues. More users produce diminishing returns.

**Interview Structure (60 min each):**

1. **Friendly Welcome** (5 min)
   Put the user at ease. "There are no wrong answers. We're testing the product, not you."

2. **Context Questions** (10 min)
   Learn about their life, habits, and current solutions. Do NOT mention your product yet.

3. **Introduce the Prototype** (3 min)
   "This is an early concept. Some things work, some don't. I didn't design it, so you won't hurt my feelings."

4. **Tasks and Observation** (30 min)
   Give them tasks: "Show me how you would [do X]."
   Watch. Don't help. Don't explain. Ask: "What are you thinking?" when they pause.

5. **Debrief** (10 min)
   "What did you think overall? What would you change? Would you use this? Would you pay for it?"

> **See also**: For rigorous interview technique that avoids biased questions, refer to `skills/mom-test/SKILL.md`.

**After All 5 Interviews:**

Create a grid:
```
| Interview Question / Moment | User 1 | User 2 | User 3 | User 4 | User 5 | Pattern |
|-----------------------------|--------|--------|--------|--------|--------|---------|
|                             |  +/-   |  +/-   |  +/-   |  +/-   |  +/-   |         |
```

Look for patterns:
- 3+ users with the same positive reaction = validated
- 3+ users with the same negative reaction = problem identified
- Mixed results = needs more investigation

```
DAY 5 OUTPUT:
- 5 user interviews completed
- Pattern grid filled in
- Top 3 learnings
- Sprint questions answered (Yes / No / Partially)
- Next steps decided
```

## Compressed Sprint (2-3 Days with Claude)

For solo founders or small teams using Claude:

| Original | Compressed | Focus |
|----------|-----------|-------|
| Day 1: Map | Morning of Day 1 | Goal, questions, map, target |
| Day 2: Sketch | Afternoon of Day 1 | Lightning demos (Claude research), Crazy 8s, solution sketch |
| Day 3: Decide | Morning of Day 2 | Evaluate with Claude as critic, storyboard |
| Day 4: Prototype | Afternoon of Day 2 | Build facade with Claude assistance |
| Day 5: Test | Day 3 | Test with 3-5 users (can be remote) |

**Claude's Roles in the Compressed Sprint:**
- Expert interviewer (Day 1): challenges your assumptions from multiple perspectives
- Research assistant (Day 2): finds analogous solutions and generates alternatives
- Design critic (Day 3): identifies weaknesses in your chosen solution
- Copywriter (Day 4): writes realistic content for the prototype
- Interview prep (Day 5): drafts interview guide and helps analyze results

## Key Templates and Frameworks

### Sprint Brief

```
DESIGN SPRINT BRIEF
====================
Sprint Dates: ___________
Challenge: ___________

Long-Term Goal:
In [timeframe], we want [outcome] for [customer].

Sprint Questions:
1. Can we ___________?
2. Will users ___________?
3. Is ___________ technically feasible?

Target Customer:
[Name/persona]: ___________
Context: ___________

Target Moment:
The specific step in the journey we are focusing on: ___________

Decider: ___________
Sprint Team: ___________
```

### Interview Script Template

```
USABILITY TEST SCRIPT
======================

INTRODUCTION (5 min)
"Thanks for coming. We're looking at some early ideas and your honest
feedback is really valuable. There are no right or wrong answers.
We're testing the concept, not you."

"Do you mind if I record this for notes?"

BACKGROUND (10 min)
"Before I show you anything, I'd like to learn a bit about you."
- "Tell me about [relevant topic]..."
- "How do you currently handle [problem area]?"
- "What's the hardest part about that?"
- "When was the last time you [relevant activity]?"

PROTOTYPE (30 min)
"Now I'm going to show you something. Some things will work,
some won't. Please think out loud as you go."

Task 1: "Imagine you want to [scenario]. Show me what you'd do."
Task 2: "Now try to [scenario]."
Task 3: "If you wanted to [scenario], how would you do that?"

Probing questions (use when they pause):
- "What are you thinking?"
- "What did you expect to happen?"
- "What would you do next?"
- "Is this what you expected to see?"

DEBRIEF (10 min)
- "What was your overall impression?"
- "What did you like most?"
- "What was confusing or frustrating?"
- "How does this compare to what you currently use?"
- "Would you use something like this? Why or why not?"
- "What would you change?"
```

## Anti-Patterns (これをやったらアウト)

- **Boil-the-Ocean Sprint**: Trying to solve 5 problems in one sprint. The sprint must target ONE customer and ONE moment. If the scope is "redesign the whole app," flag immediately and force a narrower focus.
- **Pretty Prototype Trap**: The team spends all of Day 4 making the prototype beautiful instead of functional. Keynote slides are an excellent prototype. If it takes more than 1 day to build, it's too complex.
- **Leading the Witness**: During Day 5 testing, the interviewer says "Did you notice the button here?" or "This feature lets you..." The user's confusion IS the data. Never explain. Never help. Bite your tongue.
- **Friendly Test Users**: Testing with friends, family, or colleagues who will be too kind. Recruit strangers who match your target customer profile.
- **Sprint Without a Question**: "Let's sprint on our homepage" is not a sprint question. "Will first-time visitors understand our value prop and sign up?" is. If there's no specific question, don't start.
- **無限議論モード (Infinite Discussion Mode)**: The team uses the sprint framework but still spends Day 3 debating endlessly instead of using the structured voting process. The Decider makes the call. Period.

## Japanese Business Example: 高齢者向けAIチャットサービス

**Context**: A スタートアップ (startup) wants to build an AI-powered companion chat service for 高齢者 (elderly users) living alone, addressing 高齢化社会 (aging society) challenges. Japan has 9 million single-person elderly households.

**Day 1 (Map):**
- Long-term goal: 一人暮らしの高齢者が孤独を感じず、安心して生活できる
- Sprint question: "70代以上のユーザーがAIチャットを自分で使い始められるか？" (Can users 70+ start using AI chat on their own?)
- Target: 75歳、一人暮らし、スマートフォン利用歴1年の女性

**Day 2 (Sketch):** Studied LINE (dominant in Japan's elderly population), らくらくスマートフォン (simplified phone UI), and NHK's テレビ体操 app. Key insight: LINE is already the communication platform for elderly Japanese users.

**Day 3 (Decide):** Selected concept: LINE公式アカウント (LINE Official Account) as the interface -- no new app download required. The AI responds in polite Japanese (です・ます調), initiates morning greetings, and asks about health.

**Day 4 (Prototype):** Built a fake LINE conversation flow using screenshots and Figma. Claude wrote all conversation scripts in appropriate Japanese politeness levels.

**Day 5 (Test):** Tested with 5 elderly users at a 地域包括支援センター (community support center). 4 of 5 understood how to start the conversation. All 5 said they preferred LINE over a new app. Key finding: users wanted the AI to remember previous conversations -- "覚えてくれるの？" (Will it remember me?) was asked by 3 users.

## Examples

### Example 1: Hotel Booking Redesign

**Challenge:** A hotel chain's online booking process had a 70% abandonment rate.

**Day 1 (Map):** Mapped the customer journey from "I want to book a hotel" to "Booking confirmed." Sprint question: "Can we get the abandonment rate below 50% by simplifying the flow?"

**Day 2 (Sketch):** Studied Airbnb, OpenTable, and Southwest Airlines booking flows. Generated ideas: one-page checkout, progressive disclosure, saved preferences, price comparison view.

**Day 3 (Decide):** Selected a concept combining one-page checkout with a price confidence indicator ("You're getting a good deal" badge).

**Day 4 (Prototype):** Built a clickable Figma prototype of the new booking flow with realistic hotel data.

**Day 5 (Test):** 4 of 5 users completed the booking without confusion. The price confidence badge was the most praised element. One user missed the date picker. Clear direction for development.

### Example 2: Solo Founder with Claude (Compressed)

**Challenge:** A solo founder wants to launch a meal planning app for people with food allergies.

**Day 1 Morning (Map):** With Claude's help, mapped the journey from "I need to plan meals" to "I have a week of safe, delicious meals planned." Sprint question: "Will users trust an AI to handle their food allergy constraints?"

**Day 1 Afternoon (Sketch):** Claude researched 8 existing meal planning apps and 3 allergy management apps. Founder did Crazy 8s and selected the strongest concept: a "chat-first" interface where users describe allergies conversationally.

**Day 2 Morning (Decide):** Claude critiqued the concept, pointing out that users might not trust a chat interface for safety-critical decisions. Revised to include a visual "safety checklist" alongside the chat.

**Day 2 Afternoon (Prototype):** Built a 7-screen Keynote prototype. Claude wrote all the UI copy and sample meal plans.

**Day 3 (Test):** Tested with 5 people who have food allergies (recruited via an allergy support forum). 4 of 5 loved the concept. All 5 said the safety checklist was "essential." Key learning: users wanted the ability to scan product barcodes to verify ingredients -- a feature not in the prototype. Pivot the next sprint toward barcode scanning integration.

## Common Pitfalls

1. **Trying to solve too many problems in one sprint.** Pick ONE target customer and ONE moment on the map. Trying to address everything produces a prototype that tests nothing well.

2. **Making the prototype too real.** If it takes more than one day to build, it's too complex. The prototype is a facade for testing, not a beta product. Keynote slides can be an excellent prototype.

3. **Leading the user during testing.** Never say "This button lets you..." or "Did you notice the..." Let them struggle. Their confusion IS the data. Bite your tongue.

4. **Recruiting the wrong test users.** Test with people who match your target customer. Friends and family will be too kind. Strangers who fit the profile will give you real reactions.

5. **Skipping the decision process.** Without a structured decision method (heat maps, votes, Decider), teams default to the loudest voice or the most senior person's preference. The process exists to counter this bias.

6. **Not timeboxing ruthlessly.** The sprint works because of time pressure. If you let Day 2 bleed into Day 3, you lose the forcing function. Set timers. Move on even if it feels incomplete.

7. **Ignoring negative results.** The point of the sprint is to learn, not to confirm what you already believe. If 4 out of 5 users were confused, that is an excellent outcome -- you saved months of building the wrong thing.

8. **Running a sprint without a clear question.** "Let's design a new homepage" is not a sprint question. "Will first-time visitors understand what we do and sign up for a trial?" is a sprint question.

## References

- Knapp, Jake, John Zeratsky, and Braden Kowitz. *Sprint: How to Solve Big Problems and Test New Ideas in Just Five Days.* Simon & Schuster, 2016.
- Knapp, Jake. "The Design Sprint." GV Library. https://www.gv.com/sprint/
- Banfield, Richard, C. Todd Lombardo, and Trace Wax. *Design Sprint: A Practical Guidebook for Building Great Digital Products.* O'Reilly Media, 2015.
- Courtney, Jonathan. "Design Sprint 2.0." AJ&Smart. (Compressed 4-day variant)
- Knapp, Jake and John Zeratsky. *Make Time: How to Focus on What Matters Every Day.* Currency, 2018. (Complementary to sprint methodology)
