# /pitch [audience: investor|partner|internal]

## Description

Creates a complete pitch deck content outline tailored to the specified audience. Produces slide-by-slide content following the pitch-deck-outline template, then runs a devil's advocate review to strengthen weak points before finalizing.

## Execution Flow

1. **Input**: Audience type (investor/partner/internal) + business context + the ask
2. **Clarify**: Gather product, traction, team, timing, and presentation duration
3. **Agent 1**: **pitch-writer** — selects audience-specific frame, creates slide-by-slide content with narrative arc
4. **Devil's Advocate** (MANDATORY): Attacks pitch from audience's perspective, identifies weak arguments
5. **Refine**: Strengthen slides based on devil's advocate findings, prepare Q&A responses
6. **Output**: Complete pitch deck content with speaker notes and Q&A preparation

## Usage Examples

```
/pitch investor — AI経理自動化SaaS、シードラウンド5000万円調達。MRR 50万円、月次30%成長
```

```
/pitch partner — propose integration partnership with Salesforce Japan for CRM + AI automation bundle
```

```
/pitch internal — 社内AI活用プロジェクトの予算申請。年間1200万円、3名体制。経営会議で20分プレゼン
```

## Error Handling

- **Audience type not specified**: Ask immediately — generic pitches are weak pitches. Must be one of: investor, partner, internal.
- **No traction data available**: Be honest. Frame what HAS been validated (interviews, landing page tests, LOIs). Never fabricate traction.
- **Devil's advocate finds CRITICAL weakness**: Do not hide it. Either strengthen the slide that addresses it, add a preemptive counter-argument, or flag it as a known risk with a mitigation plan.
- **Ask is vague** (e.g., "we're raising a round"): Require specifics — how much, for how long, what milestones it funds.

## Related Commands

- **Before this**: `/research` (market data for the market size slide)
- **Before this**: `/pricing` (unit economics for the business model slide)
- **Before this**: `/validate` (traction evidence for the traction slide)
- **Alternative**: `/experiment` (if you need more traction data before pitching)

## Agents

- **pitch-writer**: Crafts the narrative arc, writes slide content, tailors messaging to the audience
- **devil-advocate** (mandatory final pass): Attacks the pitch from the audience's perspective, identifies weak arguments and missing evidence

## Skills & Templates Referenced

- `pitch-deck-outline` template (slide structure per audience type)
- `storytelling` skill (narrative arc, hook, tension, resolution)
- `lean-startup` skill (traction metrics, validation evidence)
- `unit-economics` skill (for investor audience — financial projections)

## Workflow

### Step 1: Context Gathering
- Clarify with the user:
  - **Audience**: Investor, partner, or internal stakeholder?
  - **Goal**: What is the ask? (Funding amount, partnership terms, budget approval, headcount)
  - **Business**: What is the product/service? Who is the customer?
  - **Traction**: What evidence/metrics exist? (users, revenue, growth rate, LOIs, pilot results)
  - **Team**: Who is on the team? What is their relevant background?
  - **Time**: How long is the presentation? (5 min, 10 min, 20 min)

### Step 2: Audience-Specific Frame Selection

**Investor audience** — They care about:
- Return potential (market size, growth rate)
- Defensibility (moat, unfair advantages)
- Team capability (can they execute?)
- Capital efficiency (how far will my money go?)
- Exit potential

**Partner audience** — They care about:
- Mutual value creation (what's in it for both sides?)
- Strategic alignment (does this fit their roadmap?)
- Risk to their brand/business
- Implementation complexity
- Revenue/value sharing

**Internal audience** — They care about:
- Strategic alignment (does this support company goals?)
- Resource requirements (people, money, time)
- Risk assessment (what could go wrong?)
- Opportunity cost (why this over other initiatives?)
- Timeline and milestones

### Step 3: Slide-by-Slide Content Creation (pitch-writer agent)

#### Investor Deck (10-12 slides)
1. **Title**: Company name, one-line description, your name
2. **Problem**: The pain point — make it visceral and relatable
3. **Solution**: Your product/service — clear, concise, visual
4. **Demo / How It Works**: Show, don't tell
5. **Market**: TAM/SAM/SOM with methodology
6. **Business Model**: How you make money, unit economics
7. **Traction**: Metrics, growth curve, key milestones
8. **Competition**: Positioning matrix (not "we have no competitors")
9. **Team**: Why THIS team wins
10. **Financials**: Projections, key assumptions, use of funds
11. **The Ask**: Specific amount, what it buys, expected milestones
12. **Close**: Contact info, memorable final statement

#### Partner Deck (8-10 slides)
1. **Title**: Partnership proposal framing
2. **Context**: Market opportunity both parties can capture
3. **The Opportunity**: What's possible together that isn't possible alone
4. **Your Capabilities**: What you bring to the table
5. **Partner Value**: What's in it for them — be specific
6. **Proposed Structure**: How the partnership works
7. **Proof Points**: Evidence this approach works (pilots, case studies)
8. **Terms Overview**: High-level deal structure
9. **Next Steps**: Clear, time-bound action items
10. **Close**: Relationship-focused ending

#### Internal Deck (8-10 slides)
1. **Title**: Initiative name and sponsor
2. **Strategic Context**: How this fits company strategy
3. **Problem / Opportunity**: What we're missing or what's possible
4. **Proposed Solution**: What we want to do
5. **Expected Impact**: Quantified outcomes (revenue, efficiency, risk reduction)
6. **Resource Requirements**: People, budget, timeline
7. **Risk Assessment**: What could go wrong and mitigations
8. **Alternatives Considered**: Why this approach over others
9. **Timeline & Milestones**: Phased rollout with decision gates
10. **The Ask**: Specific approval needed

### Step 4: Narrative Arc Review (pitch-writer agent)
- Check the story flow: Does each slide naturally lead to the next?
- Verify the emotional arc: Hook --> Tension --> Resolution --> Call to Action
- Ensure the "why now?" is answered early
- Confirm the ask is specific and justified by the preceding content

### Step 5: Devil's Advocate Review (devil-advocate agent)

Attack the pitch from the audience's perspective:

**For investors:**
- "Why won't a big company just copy this?"
- "Your market size feels inflated — defend it"
- "Your projections assume X — what if that's wrong?"
- "Why is this team uniquely positioned to win?"

**For partners:**
- "This sounds like it benefits you more than us"
- "What's the risk to our brand?"
- "Why can't we just build this ourselves?"

**For internal:**
- "Why should we prioritize this over [other initiative]?"
- "What happens if this fails? What's the blast radius?"
- "Your timeline seems optimistic — justify it"

For each challenge, either:
- Strengthen the slide that addresses it
- Add a preemptive counter-argument
- Flag it as a known risk with a mitigation plan

### Step 6: Final Assembly
- Compile the refined slide content
- Add speaker notes for each slide
- Include an appendix slide list for anticipated questions

## Expected Output

```markdown
# Pitch Deck: [Company/Initiative Name]
**Audience**: [Investor / Partner / Internal]
**Duration**: [X minutes]
**The Ask**: [Specific request]

---

## Slide 1: [Title]
**Visual**: [Description of what should appear]
**Key Message**: [One sentence]
**Content**:
[Bullet points or narrative text]

**Speaker Notes**: [What to say, not what's on the slide]

---

## Slide 2: [Problem]
**Visual**: [Description]
**Key Message**: [One sentence]
**Content**:
[Content]

**Speaker Notes**: [Notes]

---

[...repeat for all slides...]

---

## Devil's Advocate Findings

### Challenges Addressed (strengthened in deck)
| Challenge | Where Addressed | How |
|-----------|----------------|-----|
| [objection] | Slide N | [change made] |

### Known Risks to Prepare For (not in deck, but ready for Q&A)
| Likely Question | Recommended Response |
|----------------|---------------------|
| [question] | [response] |

## Appendix Slides (for Q&A)
- **Detailed financials**: [summary]
- **Technical architecture**: [summary]
- **Customer testimonials**: [summary]
```

## Rules

- The audience type MUST be specified — generic pitches are weak pitches
- Every slide must have exactly ONE key message — if you can't state it in one sentence, the slide is unfocused
- The devil's advocate review is NOT optional — it always runs before finalizing
- Never claim "no competitors" — there are always alternatives (including doing nothing)
- Traction slides must use real data — if there is no traction yet, be honest and frame what's been validated
- Financial projections must state their key assumptions explicitly
- The Ask must be specific: "$500K for 18 months of runway" not "we're raising a round"
- Speaker notes are mandatory — the deck is a visual aid, not a document
