# The Mom Test

## Quick Reference
- **Core idea**: Talk about their life, not your idea; ask about the past, not the future; listen more than you talk
- **Key question**: "Is this problem real, frequent, and painful enough that someone will pay to solve it?"
- **When to use**: Any customer conversation -- before building, during discovery, after launch with low adoption
- **Output**: Validated/invalidated problem assumptions, commitment signals, conversation notes
- **Time**: 20-30 minutes per conversation; 5-15 conversations per round

## Overview

The Mom Test, developed by Rob Fitzpatrick, is a set of rules for conducting customer conversations that produce reliable, actionable data rather than false validation. The name comes from a simple observation: if you ask your mom "Do you think my business idea is good?", she will say yes -- because she loves you, not because the idea is good. Most customer interviews suffer from the same problem with strangers, just less obviously.

**The fundamental rule:** Talk about their life, not your idea. Ask about the past, not the future. Ask about specifics, not generalities.

Most startups fail not because they can't build the product, but because they build something nobody wants. And most founders believe they validated demand because they asked people and got positive responses. But those responses were worthless because the questions were biased. The Mom Test provides a framework for asking questions that even your mom can't lie to you about.

**The three rules of The Mom Test:**

1. Talk about their life instead of your idea
2. Ask about specifics in the past instead of generics or opinions about the future
3. Talk less and listen more

## When to Apply

- Before writing a single line of code for a new product
- When validating a pivot or major new direction
- During customer discovery interviews
- When you're getting enthusiastic responses but no actual commitments (a red flag)
- When deciding between multiple product directions
- Anytime you need to understand if a problem is real, frequent, and painful enough to pay for
- When you suspect your current customer feedback is biased or unreliable
- After a product launch when adoption is lower than expected

**Always apply.** There is no situation in customer research where the principles of The Mom Test don't apply. Even experienced researchers slip into biased questions under pressure.

## When NOT to Use

- **You already have strong quantitative data**: If 10,000 users are already using your product and you have detailed analytics, A/B testing will tell you more than 10 interviews. The Mom Test is strongest when you lack data.
- **You need to test demand at scale**: Qualitative interviews reveal depth but not scale. For scale validation, use `skills/pretotyping/SKILL.md` (Fake Door, Landing Page) or `skills/validation-patterns/SKILL.md`.
- **The question is about solution design, not problem discovery**: If you already know the problem and need to test a specific UI or flow, use `skills/design-sprint/SKILL.md` for structured prototype testing.
- **Regulatory or compliance research**: When you need factual answers about regulations, not customer pain points. Just ask directly.

## Step-by-Step Process

### Step 1: Prepare Your Questions

Before any conversation, identify the three most important things you need to learn. These are your assumptions -- the things that, if wrong, would invalidate your business.

**Transform your questions using Mom Test rules:**

| Bad Question (Biased) | Why It's Bad | Good Question (Mom Test) |
|----------------------|-------------|------------------------|
| "Would you use a product that does X?" | Hypothetical. Everyone says yes to hypotheticals. | "How do you currently handle X?" |
| "Do you think this is a good idea?" | Opinion about your idea. Invites compliments. | "Tell me about the last time you dealt with [problem]." |
| "Would you pay $10/month for this?" | Future prediction. People are terrible at predicting their own behavior. | "How much are you currently spending to solve this?" |
| "What would your ideal solution look like?" | Invites feature requests and fantasy. | "What have you tried so far? What happened?" |
| "How often do you have this problem?" | Generic. People overestimate frequency. | "When was the last time this happened? Walk me through it." |
| "Is this problem important to you?" | Leading. The answer is always yes. | "What are the top 3 things you're trying to fix right now?" (See if the problem comes up organically.) |
| "Would you recommend this to friends?" | Hypothetical future behavior. | "Have you told anyone about this problem? What did you tell them?" |

### Step 2: Conduct the Conversation

**Structure:**

1. **Set the context** (2 min)
   Be casual. Don't pitch. "I'm trying to understand how [role/type of person] handles [broad area]. Can you tell me about your experience?"

2. **Anchor in reality** (5 min)
   "Tell me about the last time [problem/situation] happened."
   "Walk me through what you did."
   "How did it end up?"

3. **Dig into the pain** (10 min)
   "What was the hardest part about that?"
   "Why was that hard?"
   "What did you do to solve it?"
   "What didn't you like about that solution?"

4. **Understand the stakes** (5 min)
   "What happens if you don't solve this?"
   "How much time/money does this cost you?"
   "How often does this come up?"

5. **Explore existing behavior** (5 min)
   "Have you looked for a better solution?"
   "What have you tried?"
   "Why did you stop using [previous solution]?"

6. **Close with commitment** (3 min)
   "Who else should I talk to about this?"
   "Can I follow up when I have something to show you?"
   "Would you be willing to try an early version?"

### Step 3: Interpret the Signals

Not all feedback is equal. Here's how to read the signals:

**Strong Signals (Reliable):**
- They describe specific past behavior: "Last Tuesday I spent 3 hours doing X"
- They've already tried to solve the problem: "I built a spreadsheet / hired someone / tried 3 tools"
- They've spent money on the problem: "I'm paying $200/month for a workaround"
- They give you their time, introduce you to colleagues, or offer to be a beta tester
- They describe the problem without you bringing it up

**Weak Signals (Unreliable):**
- "That's a great idea!" (Compliment, not data)
- "I would definitely use that." (Hypothetical promise)
- "Yeah, that's annoying." (Mild agreement, not real pain)
- "You should add [feature]." (Feature request, not validated need)
- "Let me know when it's ready." (Polite brush-off disguised as interest)

**Commitment Signals (Most Reliable):**
Commitment means they give up something of value:
- **Time:** They agree to a follow-up meeting, a longer call, or a trial period
- **Reputation:** They introduce you to their boss, colleagues, or network
- **Money:** They pre-order, put down a deposit, or sign a letter of intent
- **Effort:** They agree to switch workflows, import data, or learn a new tool

If you're getting compliments but no commitments, your idea isn't solving a real problem.

### Step 4: Avoid the Bad Data Traps

**Trap 1: Compliments**
People are nice. They will say encouraging things to avoid hurting your feelings. Compliments are the fool's gold of customer research.

**Defense:** Don't pitch your idea. If you do mention it and they say "That's cool!", deflect and re-anchor: "Thanks -- but help me understand your current process. When you last had this problem, what happened?"

**Trap 2: Fluff (Hypotheticals, Generics, Future Promises)**
Fluff is anything that isn't a specific, concrete fact about the past.

- Hypothetical: "I would probably use it every day" (they won't)
- Generic: "I usually have that problem" (how often exactly?)
- Future promise: "I'll definitely buy it when it's ready" (they won't)

**Defense:** Deflect fluff by anchoring to specifics. "You said you usually have that problem -- when was the last time? What happened?"

**Trap 3: Ideas (Feature Requests)**
When customers say "You should add X," they're designing for you. Don't let them.

**Defense:** Dig into the motivation behind the request. "Interesting -- what would that let you do?" "Why do you want that?" "How are you handling that today?" The underlying need is valuable; the specific feature suggestion is not.

### Step 5: Process and Act on What You Learned

After each conversation, immediately write down:

```
CONVERSATION NOTES
==================
Date: ___________
Person: ___________
Context: ___________

KEY FACTS (specific, past, concrete):
1. ___________
2. ___________
3. ___________

COMMITMENTS MADE:
- ___________

EMOTIONAL SIGNALS:
- ___________

WHAT DID I LEARN?
- ___________

WHAT DO I NEED TO LEARN NEXT?
- ___________

DID I BREAK ANY MOM TEST RULES?
- ___________
```

After 5-10 conversations, look for patterns:
- Are the same problems mentioned repeatedly?
- Are people already spending money/time on this problem?
- Is there a segment that has the problem more acutely?
- What surprised you? (Surprises are the most valuable data.)

## Key Templates and Frameworks

### Pre-Conversation Planning

```
MOM TEST PREP SHEET
====================
What is our riskiest assumption?
___________

What do we need to learn from this conversation?
1. ___________
2. ___________
3. ___________

What questions will we ask? (All must pass the Mom Test)
1. ___________
2. ___________
3. ___________
4. ___________
5. ___________

What would change our mind?
If we learn ___________, we should stop.
If we learn ___________, we should pivot to ___________.
If we learn ___________, we should proceed.
```

### Question Bank (Mom-Test Compliant)

**Understanding the Problem:**
- "What's the hardest part about [doing this thing]?"
- "Tell me about the last time that happened."
- "Why was that hard?"
- "What, if anything, have you done to solve this problem?"
- "What don't you love about the solution you already have?"

**Understanding Existing Behavior:**
- "How are you dealing with this right now?"
- "How much time do you spend on this per week?"
- "How much are you paying for your current solution?"
- "What tools/processes are you using today?"
- "Walk me through your workflow for [task]."

**Understanding Priority and Urgency:**
- "Where does this rank on your list of priorities?"
- "What would happen if you never solved this?"
- "How often does this come up?"
- "When was the last time you actively looked for a solution?"
- "Why haven't you solved this already?"

**Getting Commitments:**
- "Who else should I talk to about this?"
- "Can I follow up in two weeks to show you what we've built?"
- "Would you be willing to pay [amount] for [solution]?"
- "Can I add you to our beta list?"
- "Would you make an introduction to [person who could help]?"

### Signal Strength Assessment

```
SIGNAL ASSESSMENT
==================
After each conversation, score the signals:

Problem Validation:
[ ] They described a specific instance of the problem (Strong)
[ ] They've tried to solve it before (Strong)
[ ] They're currently spending money/time on it (Strong)
[ ] They mentioned the problem without prompting (Strong)
[ ] They said "yeah, that's annoying" but couldn't recall a specific instance (Weak)
[ ] They agreed it was a problem only after I described it (Weak)

Solution Interest:
[ ] They offered to pay / pre-order (Commitment - Strong)
[ ] They asked when they could start using it (Strong)
[ ] They offered to introduce me to their team/boss (Commitment - Strong)
[ ] They agreed to a follow-up meeting (Commitment - Medium)
[ ] They said "let me know when it's ready" (Weak)
[ ] They said "that's a cool idea" (Weak - Compliment)

Overall: Strong evidence / Mixed signals / Weak evidence
```

## Anti-Patterns (これをやったらアウト)

- **The Pitch Disguised as an Interview**: The founder describes their product for 10 minutes, then asks "What do you think?" This is a pitch, not research. If the user mentions their idea before minute 15, flag immediately.
- **Compliment Counting**: The founder returns from 10 interviews and says "Everyone loved it!" Ask: "How many gave a concrete commitment (time, money, reputation)?" If zero, those interviews produced zero data.
- **The Leading Question Chain**: "Don't you think it's frustrating when X happens? And wouldn't it be great if there was a solution? Would you use something like that?" Every question after the first is contaminated. Flag leading questions immediately.
- **Survey Substitution**: Sending a Google Form with "Would you use X?" to 100 people and counting "Yes" responses as validation. Surveys measure stated preference, not behavior. This is not the Mom Test.
- **仮説の確認バイアス (Confirmation Seeking)**: The founder only interviews people they think will say yes, asks questions designed to produce positive answers, and stops interviewing after 3 positive conversations. Flag if <10 interviews or if every interview is "positive."
- **メモを取らない (No Notes)**: If the founder is not writing down exact quotes immediately after conversations, the data is already corrupted by memory bias. Insist on written notes.

## Japanese Business Example: AI議事録ツールのMom Test

**Context**: A developer wants to build an AI-powered 議事録作成ツール (meeting minutes generation tool) for Japanese 中小企業 (SMBs) struggling with 人手不足 (labor shortage).

**Bad Interview (violates Mom Test):**
> 開発者: 「AIで議事録を自動作成するツールを作ろうと思っているんですが、どう思いますか？」
> 部長: 「いいですね！うちも議事録に時間かかってるので、あったら使いたいです。」
> 開発者: 「月額3,000円なら使いますか？」
> 部長: 「そうですね、その金額なら検討しますね。」

What was learned? Nothing. 「いいですね」 is a compliment. 「検討します」 is a polite brush-off.

**Good Interview (follows Mom Test):**
> 開発者: 「御社の会議運営について教えてください。最近の会議で、一番手間がかかったのは何ですか？」
> 部長: 「先週の部門会議は、若手が議事録を書いたんですけど、2時間かかったらしいです。」
> 開発者: 「2時間ですか。その後どうなりましたか？」
> 部長: 「結局、内容が薄くて私が書き直しました。そっちのほうが早かった。」
> 開発者: 「それは大変ですね。議事録の問題を解決するために、何か試したことはありますか？」
> 部長: 「Teamsの文字起こし機能を試しましたが、日本語の精度がひどくて使い物にならなかった。」
> 開発者: 「使い物にならなかった、というのは具体的にどういうことですか？」
> 部長: 「固有名詞が全部間違ってるし、敬語の構造がおかしくなるんです。結局手で直す時間のほうが長い。」

What was learned? The problem is real (2+ hours wasted), they've tried solving it (Teams transcription), the existing solution failed for specific reasons (Japanese accuracy, honorifics), and a specific person (若手社員) bears the burden. This is actionable data.

## Examples

### Example 1: Bad Conversation vs. Good Conversation

**Bad (violates every rule):**
> Founder: "I'm building an app that helps freelancers track their time and send invoices automatically. What do you think?"
>
> Freelancer: "Oh, that sounds really useful! I hate tracking time."
>
> Founder: "Would you pay $15/month for it?"
>
> Freelancer: "Yeah, probably!"
>
> Founder: "Great! I'll let you know when it launches."

What did the founder learn? Nothing. The freelancer was polite. No specific past behavior was discussed. No real commitment was made.

**Good (follows Mom Test):**
> Founder: "I'm curious about how freelancers manage the business side of things. Can you tell me about your process for getting paid?"
>
> Freelancer: "Sure. I usually send invoices in Google Docs."
>
> Founder: "Walk me through what happened with your most recent invoice."
>
> Freelancer: "I finished a project two weeks ago. I still haven't sent the invoice because I keep forgetting."
>
> Founder: "How often does that happen?"
>
> Freelancer: "Honestly? Almost every time. I probably have $3,000 in unsent invoices right now."
>
> Founder: "Have you tried anything to fix that?"
>
> Freelancer: "I tried FreshBooks for a month but it was too complicated for my simple needs. I also set calendar reminders but I just dismiss them."
>
> Founder: "What happened with the $3,000?"
>
> Freelancer: "I'll get around to it eventually. But last year I completely forgot about one invoice for $800 and felt too embarrassed to send it 3 months late. So I just... didn't."
>
> Founder: "That's $800 you never collected?"
>
> Freelancer: "Yeah. It felt awkward."

What did the founder learn? The problem is real ($800 lost), specific (forgetting to send invoices), emotional (embarrassment), and recurring (almost every time). The freelancer tried existing solutions and they failed. This is strong signal.

### Example 2: Detecting Fluff and Redirecting

> Customer: "I think I would definitely use something like that every day."
>
> Founder (redirecting): "Interesting. Tell me about the last time you actually looked for a tool like this."
>
> Customer: "Well... I haven't really looked specifically."
>
> Founder: "When was the last time [the problem] actually happened to you?"
>
> Customer: "Hmm, maybe a few months ago?"
>
> Founder: "What happened?"
>
> Customer: "I don't really remember the details."

The "fluff" signal ("I would definitely use it every day") is contradicted by the reality signal (they can't remember the last time they had the problem and never looked for a solution). This problem isn't urgent enough to build for.

### Example 3: Getting Past a Compliment to a Commitment

> Customer: "This is a really cool idea. I love it."
>
> Founder: "Thanks! Who else on your team deals with this problem? Could you introduce me?"
>
> Customer: "Uh... I'd have to think about that."
>
> Founder: "Sure. We're building an early version right now. Could I show it to you in two weeks and get your feedback?"
>
> Customer: "Yeah, maybe. Send me an email."

The compliment was strong, but the commitment was weak. They wouldn't make an introduction or commit to a specific follow-up. In the founder's notes, this should be flagged as a weak signal, regardless of how enthusiastic the words sounded.

## Common Pitfalls

1. **Talking about your idea too early.** The moment you describe your solution, the conversation shifts from learning to pitching. The other person switches from "sharing my experience" to "evaluating your idea" -- and they will be nice about it. Keep your idea to yourself as long as possible.

2. **Accepting compliments as validation.** "That's a great idea!" means nothing. It's the social equivalent of "Nice weather." The only reliable signals are specific past behaviors and concrete commitments (time, money, reputation, effort).

3. **Asking hypothetical questions.** "Would you use...?" and "Would you pay...?" are science fiction. People cannot predict their own future behavior. Ask about what they HAVE done, not what they WOULD do.

4. **Not digging deep enough.** When someone says "Yeah, that's a problem," most founders mentally check the box and move on. Instead, dig: "Tell me about the last time. What happened? What did you do? How much did it cost you? What would happen if you never solved it?"

5. **Seeking confirmation, not information.** If you go into a conversation hoping to hear "yes," you will hear "yes" -- because you will unconsciously frame questions to produce that answer. Go in seeking to LEARN, not to CONFIRM. The best outcome of a conversation might be discovering your idea is wrong.

6. **Not keeping notes.** Memory is unreliable and self-serving. You will remember the encouraging parts and forget the concerning parts. Write down exact quotes immediately after the conversation.

7. **Talking to the wrong people.** "Potential customers" is too broad. Talk to people who have the problem RIGHT NOW, who are ACTIVELY looking for solutions, and who have BUDGET to spend. Early adopters, not the general population.

8. **Avoiding the money question.** Founders are terrified of asking "Would you pay for this?" But you MUST understand willingness to pay. Instead of the direct question (which is hypothetical and unreliable), ask: "How much are you currently spending to solve this?" and "What would it be worth to you to have this problem go away?"

9. **Running too many conversations without acting.** Customer interviews are not an end in themselves. After 5-10 conversations, you should have enough signal to make a decision. If the signal is unclear, your questions need improvement, not more volume.

10. **Treating conversations as formal interviews.** The best Mom Test conversations don't feel like interviews. They feel like genuine curiosity about someone's life and work. Be a curious human, not a researcher with a clipboard.

## References

- Fitzpatrick, Rob. *The Mom Test: How to Talk to Customers & Learn If Your Business Is Good When Everyone Is Lying to You.* Robfitz Ltd, 2013.
- Fitzpatrick, Rob. *The Workshop Survival Guide: How to Design and Teach Educational Workshops That Work Every Time.* Robfitz Ltd, 2019.
- Blank, Steve. *The Four Steps to the Epiphany.* K&S Ranch, 2005. (Customer Development methodology)
- Alvarez, Cindy. *Lean Customer Development: Building Products Your Customers Will Buy.* O'Reilly Media, 2014.
- Torres, Teresa. *Continuous Discovery Habits: Discover Products That Create Customer Value and Business Value.* Product Talk LLC, 2021.
