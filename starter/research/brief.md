# Talk brief

## Working title

AI Agents as QA Engineers: Automated Quality Assurance with Claude Code & GitHub Actions. First given in German at QS-Tag Frankfurt 2026 (30 minutes, last talk of the day, directly after Robert Fey). This repo is the English version; no event is fixed yet.

## Audience

QA engineers and testers. Many use AI day to day, few have automatic verification loops.

## Intended outcome

The audience knows how an agent checks a ticket in the browser against Gherkin scenarios, keeps testing exploratively and delivers a report with evidence. And they see their own role as an opportunity: builders with a quality specialty.

## Current thesis

Coding is largely solved. Whoever wants to merge PRs without reading every line needs better automatic verification. QA people build the systems for that.

## Supporting ideas

- The bottleneck moves from writing to checking.
- Acceptance criteria are the test oracle.
- Feature map as the agent's memory (pstack `create-verification-skill`).
- During exploratory testing the agent finds a bug that no scenario covers.
- Roles are blending, see [Roles are blending](wiki/rollen-verschmelzen.md).

## Open questions

- Source for “4.2 % recall from QA-Bench” is still missing in `research/raw/`.
- Take real Gherkin scenarios from Linear (slide “The ticket” has placeholders).
- Repo URL for the QR code.

## Scope boundaries

- No introduction to LLM basics.
- No comparison of different agents.

## Timing log

History of the German QS-Tag deck up to 2026-11-11; slide titles are translated, file names and run numbers are kept as they were. The English version starts at 2026-11-18.

- 2026-11-07: 32 slides, 30:00. Chapter 8 (QA role, 4 min) new, chapter 7 cut to 2 min. Cut candidates: bridge to Robert Fey, CLI vs MCP, test oracle, counter-voice. Slide plan: [plan.md](plan.md).
- 2026-11-07: Bridge to Robert Fey cut (−15s). The 15s go to the about slide (TACON photo, now 30s). Content still ends at 29:45. New: event cover, funnel slide (30s, taken from the thesis slide).
- 2026-11-07: New slide “One command builds the onboarding binder” (pstack /create-verification-skill, 30s) before the binder. Binder and “Skill in every run” 60s → 45s each. Content still ends at 29:45.
- 2026-11-07: “CLI beats MCP” cut (−15s). The number (114k vs 27k) now sits in the notes of “Eyes and hands”, that slide has 60s instead of 45s. Content still ends at 29:45.
- 2026-11-07: Example block (Otto clone, ticket SHOP-42, test oracle) moved before the pstack slide. Otto slide now two columns with “Our task: coupon code in the cart”. Times unchanged, content ends at 29:45.
- 2026-11-07: Two editor slides (code-editor layout) after the binder: SKILL.md (35s) and features/warenkorb.md (35s). Binder 45→20s, “Skill in every run” 45→30s, ticket 45→30s, “The real workflow” 75→60s. Content ends at 29:45.
- 2026-11-07: Restructure after a structure review (subagent, comparison with Matt Pocock): role question as a promise on the thesis slide (+15s), demo 1 cut (video slide 90s, pause at 0:15 with the audience question “Where would you look?”), F2 + F3 merged into “Two critical findings” (45s), PR slide switched to run 5 (sofa, −€191.96, 14 screenshots, 110 turns · $1.33 · 3.1 min) like the goal slide, Cherny quotes merged into one slide (45s). Content ends at 28:15, 1:45 buffer. Still open from the review: source for “4.2 % recall”, QR on the thank-you slide, problem before solution ahead of pstack, merge the dev-agent slides.
- 2026-11-07: Slides “without AI” and “with AI” now show the Delivery Factory from alexop.dev/lab (era 2022 / 2026) instead of Mermaid. Code lives in `features/`, wrapper in `components/DeliveryFactory.vue`.
- 2026-11-07: Chapters 3–5 rebuilt on real data from otto-nuxt-shop: real feature map, new slides “How the skill helps”, “Real bug while creating it”, “This is how the agent builds the feature”, two finding slides, real report (CRITICAL_BUGS). 38 slides, content until 29:45. See [Agent verification on the Otto clone](wiki/agent-verifikation-otto-shop.md).
- 2026-11-07: The CI chapter now shows the real workflow from otto-nuxt-shop (`.github/workflows/claude-qa.yml`, commit ae7d693): label `qa-verify` → start the shop via the skill → claude-code-action reads the ticket from the PR description → report as a PR comment → merge gate via `--json-schema`. Based on the blog posts “Building an AI QA Engineer…” and “How to Use Claude Code as an AI QA Tester with Agent Browser”. Not yet run in GitHub.
- 2026-11-07: The QA workflow runs for real in GitHub (PR alexanderop/otto-nuxt-shop#1, ticket as issue #2, label qa-verify, Claude Code subscription). Run 4 (run 42368126398): CRITICAL_BUGS, 109 turns, $1.19, 2.9 min, 13 embedded screenshots, total −€1,512.20 with a Rolex. New slide “This is how it looks in the PR”, workflow slide updated to two jobs (qa reads, report writes).
- 2026-11-07: Run 5 (run 42368915488): video as a GIF directly in the PR comment (1.36 MB), 14 screenshots, CRITICAL_BUGS, 110 turns, $1.33, 3.1 min, total −€191.96. The goal slide now shows this real comment instead of PR #136.
- 2026-11-08: Duplicates trimmed, 10 slides out: test oracle, binder analogy (moved into the notes of “One command…”), “Skill in every run”, “Verification loop” (moved into “This is how the agent builds”), “Two critical findings”, “How to rebuild this” (moved into “Monday”), second PR slide (sofa line moved into “right in the PR”), “Everything to rebuild it”, “When the human steps in” (third point on the human slide); “Claude Code can do more…” merged with the tool slide. Content ends at 23:40, 6:20 buffer.
- 2026-11-08: Bridge slide after the ticket (statement, 10s): “The agent should check this in the real shop. But it does not know the shop.” Ticket 30→25s, pstack 30→25s. End time unchanged.
- 2026-11-08: Feature map slide suche.md (10s, one click on the gotchas) after warenkorb.md. Cart 35→25s. End time unchanged.
- 2026-11-08: Bridge slide before prompt 2 (statement, 10s): “The same skill then does QA.” Build-feature slide 75→65s, stats line (15 tool calls · $0.90) removed. End time unchanged.
- 2026-11-08: New slide “The call is a test brief with guardrails” before the workflow (45s, 5 clicks): claude -p translated line by line for QA. “Set a label” 45→30s, workflow 60→30s. End time unchanged.
- 2026-11-08: New slide “This is how the run looks in the terminal” (30s) after the claude call slide: real output of a local run as text (CRITICAL_BUGS, $2.12, 4.1 min). All slides after it +30s, content ends at 24:10, 5:50 buffer.
- 2026-11-08: Summary slide “From ticket to a red or green PR” (30s, numbered list, no clicks) after the human slide. Everything after it +30s, content ends at 24:40, 5:20 buffer.
- 2026-11-09: New slide “Test matrix for the known, charter for the rest” (45s, 2 clicks) after prompt 2: test design by risk with QA techniques (state transitions, boundary values), fixed results incl. pre-existing defects and BLOCKED, PASS only in the browser. Based on a QA skill from a client project (private gist). Everything after it +45s, content ends at 25:25, 4:35 buffer.
- 2026-11-09: QA language across the whole deck: funnel question changed to “How do we catch bugs…”, expected/actual instead of “expected/is”, quality gate (PR and summary slide), verification/validation as columns on the human slide, false positive, test design on the groundwork slide, Monday slide charter instead of rubric. Times unchanged.
- 2026-11-09: New slide “Set the label, then watch live” (30s, no clicks) after the claude call slide: screenshot of the label event from PR #1 plus the real Actions log (run 42368915488), which streams in line by line live when the slide changes. Everything after it +30s, content ends at 25:55, 4:05 buffer.
- 2026-11-09: otto-nuxt-shop: the QA schema now has a boolean `passed`, the merge gate checks `passed` (commit d650193). The log slide shows the new real run 42622982046 (passed: false, CRITICAL_BUGS, $1.17, 2.8 min). Times unchanged.

- 2026-11-09: Slide “This is how the run looks in the terminal” removed (−30 s, duplicate of the live log from GitHub Actions). All TIME lines after it −30 s, end 25:25, 4:35 buffer. The demo slide now uses 11 stills per click instead of a video (AnnotatedStills).
- 2026-11-09: Runs untangled, times unchanged. Local part (demo, report, punchline) = local mascara run (commit 302bad8, 5 findings): punchline price tag −€493.34 instead of −€191.96. Cloud part (log, JSON example, PR slide) = run 42622982046 (3 findings, 115 turns · $1.17 · 2.8 min): PR slide with new screenshots (`pr-report-kopf.png`, `pr-report-fund.png` instead of `pr-report-szenarien.png`), line “Different run, different path, same root cause”, “Merge blocked” cut. The goal slide stays on run 42368915488.
- 2026-11-09: Test matrix slide moved from before the demo to after the punchline and rebuilt as an evaluation: “Three of five findings were state transitions” (45s, 1 click), column “In the run” with F1–F5 and two rows “not checked”. Result pills out (now in the notes). Demo, report and punchline −45s each, end time unchanged at 25:40.
- 2026-11-09: Skill block (8:50–10:55, still 125s, 5 slides) reversed: first what, then how, then files, then installation. New: analogy slide “An agent is a new colleague who forgets everything every evening” (25s) and flow slide “This is how the agent uses the binder in every run” (25s). SKILL.md 35→25s with 3 instead of 6 clicks, warenkorb.md 25s, “One command” 30→25s moved to the end. Out: the separate poteto slide (now a source line + note) and suche.md (gotchas in the note of warenkorb.md). End time unchanged.
- 2026-11-09: Four explanation improvements. (1) New slide “An agent works in a loop” (25s) before the tool slide, tool slide 75→50s, time-neutral. (2) New slide “A quality gate needs true or false, not prose” (25s, 2 clicks) after the test brief; test brief 45→35s, the JSON click now only a pointer. Everything after it +15s, content ends at 25:55, 4:05 buffer. (3) The bridge slide before prompt 2 names the second agent (independence of testing). (4) Jira teaser without the three building-block boxes, technical terms moved into the note.
- 2026-11-09: Summary slide “From ticket to a red or green PR” removed (−30s). Everything after it −30s, content ends at 25:25, 4:35 buffer.
- 2026-11-09: Agent browser slide built up in three clicks (look → act → check), 45→60s. Commands verbatim from the local run (`find role … --name`, `wait --text`, `get text`), markers show the role instead of the ref number, command chips out, closing line “role and name” / getByRole. Everything after it +15s, content ends at 25:40, 4:20 buffer.
- 2026-11-09: YAML slide “The real workflow” replaced by the diagram “What happens when someone sets the label?” (45s, 4 clicks, MermaidSteps with subgraphs). YAML (gate now `passed`) moved to the backup. Everything after it +15s, content ends at 25:40, 4:20 buffer.
- 2026-11-10: Slides “The agent found the bug because someone did good groundwork” (30s) and “Become builders with a quality specialty” (15s) removed. Monday slide and thank-you −45s, content ends at 24:55, 5:05 buffer. `public/bild-builder.jpeg` stays as a style reference for the image prompts.
- 2026-11-10: Quote slide Boris Cherny (“replaced by builder”, 45s) removed (photo `public/boris-cherny.jpg` still sits unused in the repo). O-shaped, Monday slide and thank-you −45s, content ends at 24:10, 5:50 buffer. Cherny remains only in the note of the O-shaped slide (42:46).
- 2026-11-10: Stand-up slide “Everyone stand up, please” (75s, 5 clicks) removed, hook note of the title slide without “let's get moving”. All TIME lines after it −75s, content ends at 22:55, 7:05 buffer. `HamcrabPose` and `public/funnel/mensch.webp` stay (poses still used on two slides, `mensch.webp` now unused).
- 2026-11-11: Two show-of-hands questions. (1) New slide after About “Who used a coding agent this week?” (30s, 1 click: “And who lets it test too?”). (2) Show-of-hands cue in the note of the slide “Am I still needed?”, no new slide. Thank-you slide: line “Please rate my talk. But only if it was good.”, replacement question without the stand-up reference. All TIME lines after About +30s, content ends at 23:25, 6:35 buffer.
- 2026-11-11: New slide “That is exactly what the agent cannot do” (30s, 1 click: “Tester” struck out, “Humans” above it) after “Am I still needed?”: photo of Richard's keynote slide from the same day (“What we testers are very good at: asking, doubting, connecting”, `public/keynote-richard.jpg`, perspective-corrected), on the right the three words mapped onto the talk. Everything after it +30s, content ends at 23:55, 6:05 buffer. Richard = Richard Seidl, keynote “Testen ist People Business. Erst recht mit KI.” (“Testing is people business. Even more so with AI.”, 11 Nov, 09:15, qs-tag.de/programm/11-11-2026), added to the caption and the sources slide.
- 2026-11-18: English deck: the photo is replaced by an HTML rebuild of the slide in English (“What we testers do very well. Asking, doubting, connecting”); `public/keynote-richard.jpg` removed here, the photo stays in the German deck. Caption says “rebuilt and translated from German”.
- 2026-11-18: English version of the deck created from the German QS-Tag deck. Event cover slide removed (no event yet), slide texts and notes translated, shop examples switched to the English UI of otto-nuxt-shop (cart, coupon code SAVE10). Stills on the demo slide re-captured against the English UI. PR screenshots and the Actions log come from the German runs and are marked as such. Times unchanged, content ends at 23:55.
