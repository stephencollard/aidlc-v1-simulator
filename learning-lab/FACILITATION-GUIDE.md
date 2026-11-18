# AI-DLC v1 Learning Lab: facilitation guide

A guide for running the Learning Lab (`learning-lab/index.html`) in a live training call. It covers preparation, a timed run of show, a short script for each part, the points to land, an answer key for the planted mistakes, and questions people often ask.

The scenario, people and figures in the lab are made up for training.

---

## At a glance

| | |
|---|---|
| **Audience** | Product owners, project managers, designers, architects and engineers. No coding needed. |
| **Length** | 75 minutes is comfortable. A 45-minute version is at the end of the run of show. |
| **Group size** | Works best with 4 to 20 people. |
| **Format** | You share your screen and drive the lab. The group makes the decisions. |
| **Outcome** | People can explain how AI-DLC v1 works in stages, why people approve each stage, and where their own role fits. |

### The three ideas to leave people with

1. **The AI drafts, people decide.** AI-DLC v1 makes the assistant work in stages and stop for approval. An approval is only worth something if someone checked the work.
2. **Questions come first.** The AI writes its questions into a file before it builds anything. Gaps found on day one are cheap; gaps found in testing are not.
3. **The process fits the change.** v1 runs only the stages a piece of work needs, and the team can add a stage back.

---

## Before the call

### Preparation checklist

- [ ] Open the lab in the browser you will share, and play it through once on your own. It takes about 30 minutes.
- [ ] Press **Restart** afterwards, so the session starts clean. Progress is saved in the browser, so a half-finished run will reopen where you left it.
- [ ] Set the size with the **−** and **+** buttons in the top bar so people can read it on a shared screen. 120% to 130% usually works. Click the percentage to reset.
- [ ] Widen the middle panel by dragging the handles between panels if you want the files and app larger. Double-click a handle to reset.
- [ ] Decide how the group will vote: chat, reactions, or a poll tool. You will need it for about ten decisions.
- [ ] Have the AI-DLC repository open in a tab for questions: <https://github.com/awslabs/aidlc-workflows> (the `v1` branch holds v1).
- [ ] Read the [answer key](#answer-key-spoilers) below. The planted mistakes are the best moments of the session, so don't give them away early.

### How to run the room

- **Drive, don't lecture.** Read the guide panel aloud in your own words, then ask the group what to do.
- **Vote on every decision.** Let the group's choices go into the lab, even the risky ones. The production results at the end follow from what they chose, and that's where the learning lands.
- **At each approval gate, ask "Do we approve?" before clicking.** Some drafts have a mistake in them on purpose. Give people a moment to look.
- **Use the role notes.** Each step shows who is involved and whose decision it is. Ask the people in that role to speak first.
- **If you fall behind,** use jump-ahead (click a later stage in the top bar). Note that it fills in typical answers and approves without checking, so it misses any planted mistakes in the skipped steps.

### Controls you will use

| Control | What it does |
|---|---|
| **Continue**, or <kbd>→</kbd> | Moves on when the step is done, or sends the suggested message |
| <kbd>←</kbd> | Goes back a step to re-read it. Nothing is undone. |
| <kbd>Enter</kbd> or <kbd>Space</kbd> | Presses the highlighted button, which is always the next action |
| <kbd>?</kbd> or **Help** | Opens the start guide again |
| Stage name in the top bar | Shows every stage, and why any stage was skipped |
| **Before / Your build** | In the app preview, switches between the product today and after the change |

---

## Run of show (75 minutes)

| Time | Section | Lab steps |
|---|---|---|
| 0:00 | Welcome and framing | Start screen |
| 0:05 | What AI-DLC v1 is; meet the product | Getting set up |
| 0:10 | The intent; the AI looks around | Intent, Workspace Detection |
| 0:15 | The first approval gate | Reverse Engineering |
| 0:22 | Answering the AI's questions | Requirements Analysis |
| 0:35 | Stories with testable criteria | User Stories |
| 0:42 | Choosing the stages | Workflow Planning (and Application Design, if added) |
| 0:48 | Splitting the work | Units Generation |
| 0:52 | Building unit by unit | NFR Requirements, Code Generation |
| 1:02 | Proving it works | Build and Test |
| 1:08 | Release and one month later | Operations |
| 1:12 | Wrap-up and discussion | Summary |

### Shorter 45-minute version

- Skip the start guide pages (press **Skip the intro and start**) and move quickly through Getting set up.
- Spend full time on Reverse Engineering, Requirements Analysis, Workflow Planning and Code Generation unit 1. These hold the key decisions and three of the four planted mistakes.
- Jump ahead past Units Generation and unit 2 of Code Generation.
- Finish on "One month later" and the summary.

---

## Script and key points

Each section has a short script (**Say**), what to do on screen (**Do**), what to ask (**Ask**) and the points to land (**Key points**). Put the script in your own words.

### 1. Welcome and framing (0:00 to 0:05)

**Say:** "Today we're going to take one real-sized change from a customer complaint to working software, using AI-DLC v1. You make the decisions. I'll drive. Along the way the AI will get some things wrong, and it's our job to catch them."

**Do:** Show the start screen. Introduce the team: Priya (Product Owner), Mei (UX Designer), Tomas (Architect), Sam (Software Engineer) and Jordan (Project Manager). Show page 2, "How the lab works", for the three panels and the red outline.

**Key points:**
- The lab looks like an AI coding tool: a guide, the project files and app, and an AI assistant chat.
- The red outline and the **Your move** label always show where to act next.

### 2. Getting set up (0:05 to 0:10)

**Say:** "AI-DLC v1 isn't an app you install. It's a set of plain-text rule files the AI assistant reads and follows."

**Do:** Open `core-workflow.md`. Point at the three phases and which stages always run. Then open **App preview**, select **Alex Morgan** and press **Run risk assessment**.

**Ask:** "Alex scores 22, low risk. What's wrong with that?" (Alex's details have been used on four applications this week, and the product can't see across applications.)

**Key points:**
- v1 has three phases: Inception (what and why), Construction (how), and Operations (a placeholder in v1).
- The rules make the AI work in stages, ask before it assumes, and wait for approval.
- Notice there is no "Identity history" panel in the console. It appears only after the change.

**Discussion:** "How does a change like this reach the team today, and how long before anyone writes code?"

### 3. Intent and Workspace Detection (0:10 to 0:15)

**Do:** Read the three intent options and take a vote. Then send the first message, which starts with "Using AI-DLC".

**Say:** "A good intent states the outcome, who has the problem, and what success looks like. It leaves the how open."

**Do:** Open `aidlc-state.md` and `audit.md` as the AI creates them.

**Key points:**
- In v1, "Using AI-DLC, …" is the phrase that starts the workflow.
- The intent isn't a stage of its own. The request is logged, then analysed in Requirements Analysis.
- Workspace Detection decides whether this is new code (greenfield) or existing code (brownfield). It's the one stage that doesn't stop for approval.
- From now on every decision is recorded in the audit log as it happens.

**Discussion:** "Where do our decisions live today? How easy is it to find out who agreed what?"

### 4. Reverse Engineering: the first approval gate (0:15 to 0:22)

**Say:** "Before changing anything, the AI reads the existing code and writes down how the product works."

**Do:** Open `architecture.md` and read "Things to know before changing it" together. Answer the quiz as a group.

**Ask at the gate:** "Do we approve this summary? Is everything in it right?" Encourage someone to open `score.py` and `applications.py` to compare. (There is a planted mistake here. See the [answer key](#answer-key-spoilers).)

**Key points:**
- This is the first approval gate. Nothing moves on without a yes.
- The data retention rule (7 days) is a constraint found on day one, not when it blocks a release.
- An approval is only worth something if someone checked.

**Discussion:** "How do new team members learn how our systems work today? What would a summary like this have saved?"

### 5. Requirements Analysis (0:22 to 0:35)

This is the heart of the session. Allow the time.

**Say:** "The AI won't guess. It has written eight questions into a file, and each one belongs to a role."

**Do:** Open `requirement-verification-questions.md`. Take each question in turn. Ask the role named on it to speak first, then vote and click the answer.

**Ask:** After the answers are in and the AI comes back with a follow-up: "What did it find, and why didn't we spot it?"

**Key points:**
- Questions use lettered options with an `[Answer]:` tag, plus "X) Other" for anything else.
- The AI checks answers against each other and against what it learned about the existing product. The follow-up depends on the group's answers: a conflict with the 7-day retention rule, a gap that would miss the lenders' reported case, or a scope question.
- Every line in `requirements.md` traces back to an answer. Nothing was invented.
- The group's choices change what gets built. They will see the effect at the end.

**Discussion:** "Think of a recent project. Which question was discovered late that could have been asked on day one?"

### 6. User Stories (0:35 to 0:42)

**Say:** "Several stages work in two parts: a plan you approve, then the output you approve."

**Do:** Answer the story plan question, approve the plan, then open `stories.md`.

**Ask at the gate:** "Could a tester answer yes or no to every 'Accept when' line?" (Story 2 says "the reason is clear". That can't be tested.)

**Key points:**
- Acceptance criteria become automated tests. A vague criterion becomes a vague test, then a vague product.
- You become the editor, not the author. Changing a draft takes seconds.

**Discussion:** "Who writes acceptance criteria today, and how often are they vague?"

### 7. Workflow Planning (0:42 to 0:48)

**Say:** "v1 is adaptive. The AI proposes which remaining stages this change needs, and explains what it skips."

**Do:** Open `execution-plan.md`. Point out RUN and SKIP. Read out the disagreement in chat: Tomas thinks Application Design can be skipped, Sam wants a short design first.

**Ask:** "Approve the plan, or ask for Application Design back? Who decides?" (The Project Manager approves, with the Architect's advice.)

**Key points:**
- The plan is a proposal, not a decision. The team can add a stage back.
- If the group adds Application Design back, it runs as its own stage with its own approval.
- Worth knowing: v1's own rules say Application Design should run when new components are needed, and this change adds one. Sam has the rules on their side.

**Discussion:** "Where does our current process feel too heavy for small changes, or too light for risky ones?"

### 8. Units Generation (0:48 to 0:52)

**Do:** Open the unit plan, approve it, then open `unit-of-work.md`, `unit-of-work-dependency.md` and `unit-of-work-story-map.md`.

**Key points:**
- A unit of work is a group of stories designed, built and tested together. Here: `repeat-check` (the API check) and `console-warning` (what analysts see).
- The dependency file sets the build order: the console needs the check first.
- v1 lists the units and their order. It doesn't plan how long each takes.
- Pause on the recap: Inception is finished and not one line of code has been written.

**Discussion:** "If the thinking is done before any code, what has to change in how we plan?"

### 9. Construction: NFR Requirements and Code Generation (0:52 to 1:02)

**Say:** "Construction is a loop. Each unit goes through its design stages and code before the next starts."

**Do:**
1. **NFR plan question (missing date of birth).** Read out the disagreement: Sam wants to treat it as a pass, Mei wants analysts told the check couldn't run. Ask the Product Owner in the room to decide. There's no wrong answer; the trade-off shows up in the production results.
2. **Code generation plan.** Ask the group to check each step against `requirements.md` and `nfr-requirements.md` before approving. (There's a planted mistake here.)
3. **Code approval.** Compare `test_repeat_applications.py` with `stories.md`. "Does every acceptance criterion for stories 1 and 3 have a test?" (There's a planted mistake here too.)
4. **Unit 2.** Move briskly. Point out the AI re-judged the stages for this unit and skipped NFR Requirements, with a reason.

**Key points:**
- Code Generation has two parts: a plan, then code. Once the plan is approved, the AI follows it exactly, so a mistake in the plan becomes a mistake in the code.
- The engineer's job moves from writing most of the code to steering and checking it.
- The AI never approves its own work.

**Discussion:** "What would stop us rubber-stamping AI-written code when we are busy?"

### 10. Build and Test (1:02 to 1:08)

**Do:** Send the build message and watch the test run. Open `build-and-test-summary.md`. Then use the app preview: run **Alex Morgan** in **Your build**, then the other three applicants.

**Ask:** "Does the warning say why it fired?" (Only if story 2 was made testable.) "Does Maria get wrongly flagged?" (Only if the group matched on name and date of birth alone.)

**Key points:**
- Traceability: a line from the intent, to a requirement, to a story, to a passing test.
- If the group missed a planted mistake earlier, it surfaces here or a teammate finds it late. Point out what it would have cost in real life.
- Show **Before** and **Your build** side by side. The new Identity history panel is the visible result of the team's decisions.

**Discussion:** "How do we prove today that what we shipped is what was asked for?"

### 11. Operations and one month later (1:08 to 1:12)

**Say:** "In v1, Operations is a placeholder. The team releases the way it does today."

**Do:** Send the release message, then read **One month later** together.

**Key points:**
- The production figures follow from the group's own choices: time period, threshold, matching rule, real time or overnight, what happens with a missing date of birth, and story 2.
- The figures are made up for training, but the trade-offs are real.

**Discussion:** "What would we want AI-DLC to do for us in Operations?"

### 12. Wrap-up (1:12 to 1:15)

**Do:** Open the **Summary** tab. Walk through:
- **What would have changed:** the same month if one decision had gone the other way.
- **Mistakes in the AI's drafts:** how many the group caught at the gate.
- **The 13 stages, and what happened to each:** which ran, which were skipped and why, who approved.

**Close with the three ideas** from the top of this guide, then ask: "Where would this fit first in our own work?"

---

## Answer key (spoilers)

Keep this to yourself until the group has had a go.

### Quiz answers

| Step | Answer |
|---|---|
| Choose a good intent | The third option: it names the problem, who has it and what success looks like, and leaves the how open. |
| Spot the constraint | "Application data is deleted after 7 days." It limits how far back the check can look. |

### Planted mistakes

Each gate also offers a plausible objection that is wrong. If the group picks it, the AI checks its source and politely keeps the draft as it is. That's a useful moment too: the AI can be right.

| Gate | The mistake | Request to make | Wrong objection | If missed |
|---|---|---|---|---|
| Reverse Engineering | `architecture.md` says a failed check adds 30 points. `score.py` says 50. | "A failed check adds 50 points, not 30" | "Data is kept for 30 days, not 7" (it is 7) | Sam finds it later, after nearly designing around the wrong number. |
| User Stories | Story 2's criterion is "the reason is clear", which can't be tested. | "Make story 2 testable" | none | The warning goes live without saying why it fired. |
| Code generation plan (unit 1) | Step 3 flags when the count is *more than* the threshold. Requirement R2 says the threshold *or more*. | "Step 3 does not match requirement R2" | "Store names and addresses as they are" (the approved NFRs say fingerprints only) | A test fails in Build and Test, after the code was written. |
| Code approval (unit 1) | Story 1 has two acceptance criteria, but only one has a test. | "One of story 1's criteria has no test" | "WINDOW does not match the requirements" (it does) | Sam spots the gap in Build and Test, after the code was approved. |

### Badges

Nine badges reward good habits: running the product and seeing the problem, choosing a clear intent and spotting the constraint first time, catching each of the four planted mistakes, trying all four applicants in the build, and seeing the release through. The count is in the top bar.

---

## Where the lab simplifies AI-DLC v1

The lab follows v1's stages, approval gates and documents, but simplifies some details to keep a training session moving. If someone asks, these are the honest answers.

- **Roles at each gate.** v1 has a single "user" who answers and approves. Assigning each gate to a role (Architect, Product Owner and so on) is the lab's teaching layer, to show where each role adds value.
- **"Mob Elaboration".** The Requirements Analysis step mentions it. It's a term from the wider AI-DLC methodology, not from the v1 rule files.
- **The audit log.** Real v1 logs each user input word for word with ISO timestamps, in a set format. The lab shows short one-line entries.
- **Build and Test.** In v1 this stage mainly writes build and test instruction files (build, unit, integration and performance tests) plus a summary. The lab shows a test run and the summary only.
- **Operations.** v1 says the workflow ends after Build and Test. In the lab the AI runs the release through the team's existing pipeline, to show the end of the story.
- **Extensions.** v1 asks during Requirements Analysis whether to turn on optional extensions, such as a security baseline. The lab leaves these out.
- **Fewer documents.** Some stages write more files in v1 than the lab shows, for example the full set of reverse-engineering documents.
- **Folder layout.** The rule files sit in a simplified folder. In real use their location depends on the AI tool.

---

## Frequently asked questions

### About AI-DLC

**What is AI-DLC?**
The AI-Driven Development Life Cycle, published by AWS Labs as open source at [awslabs/aidlc-workflows](https://github.com/awslabs/aidlc-workflows). v1 is a set of rule files that make an AI coding assistant work in stages, ask before it assumes, and stop for human approval.

**Is it a product we have to buy or install?**
No. It's plain-text rule files saved in the project. The AI assistant you already use reads and follows them.

**Which AI tools does it work with?**
v1 includes setup for several assistants, including Amazon Q Developer, Kiro, Cursor, Cline, Claude Code, GitHub Copilot and OpenAI Codex. Check the repository for the current list.

**How do you start it?**
Begin a request with "Using AI-DLC, …" and describe the outcome you want.

**Which stages always run?**
Workspace Detection, Requirements Analysis, Workflow Planning, Code Generation and Build and Test. The others run only when the work needs them. Reverse Engineering runs only for existing code.

**Can we skip stages, or add one back?**
Yes. At Workflow Planning the AI proposes which stages to run and explains what it skips. The team can ask for a stage to be added or removed.

**Does it work for brand-new products?**
Yes. For new code (greenfield), Reverse Engineering is skipped and the AI starts from Requirements Analysis.

**Where does everything get written?**
Documents go in an `aidlc-docs/` folder in the project. Application code goes in the normal project folders, never in `aidlc-docs/`. Two files track the whole run: `aidlc-state.md` for progress and `audit.md` for every input and approval.

**How does the AI ask questions?**
It writes them into a question file with lettered options, "Other" as the last option, and an `[Answer]:` tag for each. After you answer, it checks for contradictions and ambiguities and asks follow-ups if needed.

**Who approves each stage?**
In v1, the user does. v1 doesn't assign roles. In practice, teams decide who should approve what; the lab shows one sensible way to split it.

**Does this replace agile, sprints or our ceremonies?**
v1 doesn't define sprints or ceremonies. It defines how the AI works with people on a piece of work. Teams decide how it fits with how they already plan and release.

**What are Bolts and Mob Elaboration?**
Terms from the wider AI-DLC methodology and from AI-DLC v2. They aren't part of the v1 rule files.

**What does v2 change?**
The lab's summary has a short overview: an earlier Ideation phase, named AI roles, choosing the scope up front, more gates, delivery planning and a real Operations phase. v2 is still changing, so check the current guide before relying on details.

**Can we trust the AI to catch problems like the follow-up question?**
The rules require it to check answers for gaps and contradictions, but how well it does depends on the model and the context it has. That's exactly why every stage ends with a person's approval.

**Is it secure to use with our code?**
AI-DLC itself is rule files; security depends on the AI tool and how your organisation has set it up. v1 also offers an optional security baseline extension that adds security rules to each stage.

### About the lab

**Is my progress saved?**
Yes, in the browser you're using. It isn't shared between devices or browsers.

**How do I start again?**
Press **Restart** in the top bar. Choosing different answers gives a different product and different production results.

**Can I go back and change an answer?**
You can go back to re-read any step with **←** or **Earlier step**, but decisions already made stay. Restart to try other choices.

**What does jump-ahead do?**
Clicking a later stage in the top bar offers to jump there. It completes the steps in between with typical answers and approves without checking, so it misses any planted mistakes on the way.

**Is there a right answer to the requirement questions?**
No. The choices are trade-offs. The production results at the end show what each one led to.

**Are the scores and production figures real?**
No. The company, people, applicants, scores and figures are made up for training.

**The text is too small or too large.**
Use the **−** and **+** buttons in the top bar. The lab also scales itself to larger screens.

**Can I use it on a phone?**
Yes, but a laptop or desktop is better. On a phone the three panels become tabs at the bottom.

**I'm stuck. What do I do?**
Look for the red outline and the **Your move** label. Or press **?** to open the guide again.
