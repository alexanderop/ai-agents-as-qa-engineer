# Agent verification on the Otto clone

## Current synthesis

With a generated verification skill (feature map + helper script), one agent builds a ticket feature and checks the Gherkin scenarios itself in the browser, and a second QA agent finds bugs during exploratory testing that no scenario covers. All three runs together cost under $6.

## Claims and evidence

- The skill generator mapped the shop in 56 turns for $3.37 and found a real search field bug along the way. [raw](../raw/2026-11-07-otto-shop-agent-runs.md)
- The implementation agent used the skill to check its own work: 16 turns, $0.90, all scenarios green. [raw](../raw/2026-11-07-otto-shop-agent-runs.md)
- The QA agent found the planted quantity bug without prior knowledge and derived four findings from it, among them a negative total. 20 turns, $1.00. [raw](../raw/2026-11-07-otto-shop-agent-runs.md)

## Tensions and open questions

- The bug was planted on purpose. The first QA run spotted it through the commit message and was discarded. This has to be transparent on stage.
- The QA prompt named “quantity changes” and “removing items” as examples for exploratory tests (test charter). The agent did not know the planted bug, but the search direction was given. The negative total and the cookie manipulation were not in the prompt. [raw](../raw/2026-11-07-otto-shop-agent-runs.md)
- The QA agent reads the diff and the code (white box). A pure black-box run without code access has not been tested.
- One run is one sample. Non-determinism was not measured.

## Sources

- [Agent runs in otto-nuxt-shop](../raw/2026-11-07-otto-shop-agent-runs.md)
