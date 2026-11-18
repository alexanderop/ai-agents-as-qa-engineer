---
theme: '@alexop/slidev-theme-brand'
addons:
  - '@alexop/slidev-addon-utils'
title: 'AI Agents as QA Engineers: Automated Quality Assurance with Claude Code & GitHub Actions'
transition: slide-left
comark: true
pwa: build
seoMeta:
  ogImage: auto
shiki:
  magicMove:
    easing: ease-in-out
    stagger: 3
duration: 30min
timer: countdown
drawings:
  persist: false
info: |
  ## AI Agents as QA Engineers

  Automated quality assurance with Claude Code & GitHub Actions.
  Alexander Opalic
layout: cover
background: /titel-mensch-roboter.jpeg
---

<div class="w-[40%] text-left">

<h1 class="!text-5xl !leading-tight">AI Agents as<br/><span class="text-[#ff6bed] whitespace-nowrap">QA Engineers</span></h1>

<div class="mt-4 text-lg opacity-80">Automated quality assurance with Claude Code & GitHub Actions</div>

<div class="mt-10 text-base opacity-70">Alexander Opalic · alexop.dev</div>

</div>

<!--
TIME: 0:00–0:45 (45s)

- Say a quick hello. “Great that you are all here in my session.”
- **Hook:** “Today an agent will test a shop for us. And it will find a bug that nobody wrote down.”
- No need to take notes, I share the slides via QR code at the end.
- No event cover in this version. If the event has a poster, add it as the first slide (`layout: image`, `hideFooter: true`) and set `footerEvent` in the headmatter.
-->

---
layout: image-right
image: /alex-tacon.jpeg
backgroundSize: cover
---

# Alexander Opalic

<div class="mt-6 text-xl space-y-3 opacity-90">
  <div>Developer at <span class="text-[#ff6bed] font-bold">Otto Payments</span></div>
  <div class="opacity-70">A developer, not a QA engineer.</div>
  <div>Blog: <span class="text-[#ff6bed]">alexop.dev</span></div>
  <div class="mt-8 text-lg opacity-70">My first testing conference was <span class="text-[#ff6bed] font-bold">TACON</span> (photo).<br/>I keep coming back.</div>
</div>

<!--
TIME: 0:45–1:15 (30s)

- Name, developer at Otto Payments, alexop.dev.
- “The shop you are about to see is a private rebuild, not Otto code.”
- Photo: “That is me at TACON, my first testing conference. I really like the testing community.”
- **Say it honestly:** I am a developer, not a QA engineer. I show you my view from the developer side.
-->

---
layout: statement
---

# 🙋 Who used a <span class="text-[#ff6bed]">coding agent</span> this week?

<div v-click class="mt-8 text-3xl">And who lets it <span class="text-[#ff6bed] font-bold">test</span> as well?</div>

<!--
TIME: 1:15–1:45 (30s)

- [Ask for hands] Raise my own hand while asking. “Claude Code, Copilot, Cursor, any of them.”
- Look into the room, estimate the number: “Okay, that is a good half.”
- [click] [Ask for hands] “And who lets the agent test as well? In the browser, like a human?”
- Most hands go down. “That gap is what today is about.”
- If many hands stay up: “Very good, then compare your way with mine in a moment.”
-->

---

# With AI, the <span class="text-[#ff6bed]">bottleneck</span> moves

<div class="flows mt-5">
  <div class="flow">
    <div class="flow__tag">Without AI</div>
    <div class="flow__title">Writing code was expensive</div>
    <div class="flow__row"><div class="flow__name">Requirements</div><div class="flow__track"><div class="flow__bar" style="width:80%"></div></div></div>
    <div class="flow__row"><div class="flow__name">Development</div><div class="flow__track"><div class="flow__bar is-hot" style="width:22%"></div><span class="flow__jam">Bottleneck</span></div></div>
    <div class="flow__row"><div class="flow__name">Code review</div><div class="flow__track"><div class="flow__bar" style="width:70%"></div></div></div>
    <div class="flow__row"><div class="flow__name">QA</div><div class="flow__track"><div class="flow__bar" style="width:60%"></div></div></div>
    <div class="flow__row"><div class="flow__name">Release</div><div class="flow__track"><div class="flow__bar" style="width:75%"></div></div></div>
    <div class="flow__sub">Everything waits for dev.</div>
  </div>
  <div class="flow is-now">
    <div class="flow__tag">With AI</div>
    <div class="flow__title">Code is cheap</div>
    <div class="flow__row"><div class="flow__name">Requirements</div><div class="flow__track"><div class="flow__bar is-hot" style="width:28%"></div><span class="flow__jam">Bottleneck</span></div></div>
    <div class="flow__row"><div class="flow__name">Development <span class="flow__ai">+ AI</span></div><div class="flow__track"><div class="flow__bar" style="width:95%"></div></div></div>
    <div class="flow__row"><div class="flow__name">Code review</div><div class="flow__track"><div class="flow__bar is-hot" style="width:25%"></div><span class="flow__jam">Bottleneck</span></div></div>
    <div class="flow__row"><div class="flow__name">QA</div><div class="flow__track"><div class="flow__bar is-hot" style="width:22%"></div><span class="flow__jam">Bottleneck</span></div></div>
    <div class="flow__row"><div class="flow__name">Release</div><div class="flow__track"><div class="flow__bar" style="width:40%"></div></div></div>
    <div class="flow__sub">Dev is fast. Now everything waits for <b>clear requirements</b>, <b>review</b> and <b>QA</b>.</div>
  </div>
</div>

<div class="mt-4 text-center text-sm opacity-60">Throughput per station · based on my Delivery Factory, alexop.dev/lab/delivery-factory</div>

<style>
.flows { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; }
.flow { border: 1px solid rgba(255,255,255,.15); border-radius: 14px; padding: 14px 18px; background: rgba(255,255,255,.04); }
.flow.is-now { border-color: #ff6bed; background: rgba(255,107,237,.06); }
.flow__tag { font-size: 11px; font-weight: 700; letter-spacing: .06em; text-transform: uppercase; opacity: .6; }
.flow.is-now .flow__tag { color: #ff6bed; opacity: 1; }
.flow__title { font-size: 20px; font-weight: 700; color: #eaedf3; margin: 2px 0 12px; }
.flow__row { display: grid; grid-template-columns: 130px 1fr; align-items: center; gap: 10px; padding: 5px 0; }
.flow__name { font-size: 14px; color: #eaedf3; white-space: nowrap; }
.flow__ai { font-size: 11px; font-weight: 700; color: #1a1d29; background: #f3e6c4; border-radius: 6px; padding: 1px 5px; margin-left: 4px; }
.flow__track { position: relative; height: 22px; background: rgba(255,255,255,.05); border-radius: 6px; display: flex; align-items: center; }
.flow__bar { height: 100%; border-radius: 6px; background: rgba(255,255,255,.28); }
.flow__bar.is-hot { background: #ff6bed; }
.flow__jam { margin-left: 8px; font-size: 11px; font-weight: 800; letter-spacing: .04em; text-transform: uppercase; color: #ff6bed; }
.flow__sub { margin-top: 10px; font-size: 14px; opacity: .8; }
.flow__sub b { color: #ff6bed; }
</style>

<!--
TIME: 1:45–3:15 (90s)

- Left: this is how we built software **without AI**. The bar is how much a station gets done per day. Development was the narrowest bar: writing code was the expensive step. Everything waited for dev.
- Testing was click work at the end of the belt back then, when everything else was already done.
- Right: **with AI**. Coding agents make dev wide and fast. The bottleneck does not disappear, it moves.
- Now we wait for **clear requirements** (what exactly should be built?), for **code review** (who reads all those PRs?) and for **QA** (is it really correct?).
- I merge more PRs than ever and read fewer and fewer of them line by line.
- The picture comes from my Delivery Factory, built like a factory in Factorio. If you want to play it live: alexop.dev/lab/delivery-factory.
- SOURCE: alexop.dev/lab/delivery-factory, blog post “The Factory Must Grow: AI moved the bottleneck”. The bar lengths are illustrative, not measurements.
-->

---
layout: statement
---

# Coding is largely <span class="text-[#ff6bed]">solved</span>.

<div class="mt-8 text-2xl opacity-80">If you want to merge PRs without reading every line,<br/>you need better <span class="text-[#ff6bed]">automatic verification</span>.</div>

<!--
TIME: 3:15–4:00 (45s)

- **The core thesis** of the talk.
- “Largely” is chosen on purpose. There are still hard problems. But for a typical frontend ticket, the agent writes the code.
- So the question is no longer “Who writes this?” but “How do I know it is correct?”
- **Say it out loud, not on the slide:** “If an agent codes and tests, do we still need us?” Do not answer. “You get the answer at the end.”
-->

---
clicks: 1
---

# How do we catch bugs when agents build features <span class="text-[#ff6bed]">on their own</span>?

<VerificationFunnel />

<style>
.funnel { max-height: 360px; }
</style>

<!--
TIME: 4:00–4:30 (30s)

- **Question to the room:** How do we catch bugs when an agent implements a feature completely on its own? Asked differently: what does it take so that we can accept agent code? Answer: several layers that catch bugs.
- A funnel: you catch the most at the top, and only what all layers before missed gets through to the bottom.
- Codebase, static analysis, verification, prose (rules for the agent, e.g. skills and AGENTS.md), and at the very bottom the human in review.
- [click] **Today** is about the middle: verification. The agent checks empirically in a real browser whether the ticket is fulfilled.
- The more the upper layers catch, the smaller the human review gets.

SOURCE: TODO add the author of the funnel diagram (template supplied by Alex as an image, redrawn as SVG).
-->

---

# The <span class="text-[#ff6bed]">goal</span>: a PR with evidence

<div class="ziel mt-4">
  <img src="/ci-pr-kommentar-lauf-2026-11-10.png" alt="Comment by github-actions in the pull request (in German): verdict CRITICAL_BUGS, not passed. Below it the video of the QA run with the shop's cart, then the QA report with the table of scenarios" />
  <div class="ziel__tags"><span>Verdict</span><span>Video of the run</span><span>Screenshots</span></div>
</div>

<style>
.ziel { position: relative; height: 405px; overflow: hidden; border-radius: 10px; border: 1px solid rgba(255,255,255,.18); background: #0d1117; }
.ziel img { display: block; width: 100%; height: 100%; object-fit: cover; object-position: top center; }
.ziel::after { content: ''; position: absolute; inset: auto 0 0 0; height: 110px; background: linear-gradient(to bottom, rgba(13,17,23,0), rgba(13,17,23,.95)); }
.ziel__tags { position: absolute; z-index: 1; left: 0; right: 0; bottom: 14px; display: flex; justify-content: center; gap: 12px; }
.ziel__tags span { padding: 5px 16px; border-radius: 999px; background: #ff6bed; color: #1a1d29; font-size: 17px; font-weight: 700; }
</style>

<!--
TIME: 4:30–5:00 (30s)

- This is what a PR should look like: code plus **evidence**.
- Screenshots of every scenario that was checked.
- A video, so I see what the agent did.
- A clear verdict. Then I do not have to guess.
- This is the real comment of the QA agent in PR #1 of the Otto clone: verdict at the top, below it the video as a GIF, then the report with screenshots. That is where we want to be at the end of the talk.
- **The screenshot is in German:** this run happened before the shop had an English UI. “Urteil” = verdict, “nicht bestanden” = not passed.
- SOURCE: github.com/alexanderop/otto-nuxt-shop/pull/1#issuecomment-6767619659 (run 42817194078, 10 Nov)
-->

---

# An agent works in a <span class="text-[#ff6bed]">loop</span> until the task is done

<div class="mt-8">

<IconCards flow no-clicks :width="146" :loop="{ from: 3, to: 1, label: 'not done yet' }" :items="[
  { icon: '/icons/issue.webp', title: 'Task', sub: '“Build the coupon”', tag: 'You' },
  { icon: '/icons/claude-code.webp', title: 'Think', sub: 'What is the next step?' },
  { icon: '/icons/tools.webp', title: 'Use a tool', sub: 'read a file, run a command, click', accent: true },
  { icon: '/icons/fund-pruefen.webp', title: 'Look at the result', sub: 'Did it work?' },
  { icon: '/icons/szenario-ok.webp', title: 'Done', sub: 'it reports back' },
]" />

</div>

<div class="mt-6 text-center text-xl opacity-80">A chatbot answers. An agent <b class="text-[#ff6bed]">acts</b> and checks its own result.</div>

<!--
TIME: 5:00–5:25 (25s)

- Many know Claude Code only as a coding tool. Claude Code is an **agent** in the terminal. You say what you want, and it works until it is done.
- The difference to a chatbot is this loop: it thinks about the next step, uses a tool, looks at the result. If it does not fit, it goes another round. It does that dozens of times without you clicking in between.
- Tools are for example: reading and writing files, running commands in the terminal, clicking in the browser.
- Writing code is only one thing. It reads tickets, collects screenshots, writes reports. Almost all of that is testing work. That is why it is interesting for QA.
- Remember the loop. The whole rest of the talk is this loop with different tools.
-->

---

# Claude Code can do anything it has a <span class="text-[#ff6bed]">tool</span> for

<div class="text-lg opacity-70 -mt-2">For the <b class="text-[#ff6bed]">browser</b> it needs a tool. Here are four.</div>

<div class="mt-8">

<IconCards :columns="4" :items="[
  { icon: '/icons/playwright-cli.webp', title: 'Playwright CLI', sub: 'For teams that already know Playwright. Stable and cheap.' },
  { icon: '/icons/playwright-mcp.webp', title: 'Playwright MCP', sub: 'For exploring locally. Convenient, but expensive in context.' },
  { icon: '/icons/agent-browser.webp', title: 'Agent Browser', sub: 'My favourite. Snapshot with refs, built for agents.', accent: true },
  { icon: '/icons/computer-use.webp', title: 'Computer Use', sub: 'When there is no browser: desktop apps, legacy UIs.' },
]" size="lg" no-clicks />

</div>

<!--
TIME: 5:25–6:15 (50s)

- The loop can only do what it has a tool for. Without a browser the agent does not see the app. If Claude Code should operate a browser or an app, it needs a tool for it. Here are four.
- **Playwright CLI:** you know it already. The agent calls it through Bash.
- **Playwright MCP:** good for exploring locally. But it pushes a lot into the context at every step.
- **Agent Browser** by Vercel Labs: a Rust CLI, accessibility snapshot with refs like @e1. That is what I use.
- **Computer Use:** the agent sees the screen and clicks with the mouse. Slow, but works everywhere.
- My rule: MCP locally for exploring, CLI in the pipeline. Same smoke test: about 114k tokens with MCP, 27k with the CLI (source: “Playwright CLI vs MCP”, see my Quality Night deck).
-->

---
clicks: 3
---

# This is how the agent <span class="text-[#ff6bed]">sees</span> a web page

<div class="ab mt-3">
  <div class="ab__col">
    <div class="ab__h">What you see</div>
    <div class="ab__page">
      <div class="ab__pagebar"><i></i><i></i><i></i><span>otto-shop / cart</span></div>
      <div class="ab__pagebody">
        <div class="ab__el ab__title">Cart <em v-show="$clicks >= 1">heading</em></div>
        <div class="ab__sum">
          <div><span>Subtotal</span><span>€8.94</span></div>
          <div><span>Shipping</span><span>€5.95</span></div>
          <div v-if="$clicks >= 3" class="is-new"><span>Coupon (SAVE10)</span><span>−€0.89</span></div>
          <div class="ab__total" :class="{ 'is-new': $clicks >= 3 }"><span>Total</span><span>{{ $clicks >= 3 ? '€14.00' : '€14.89' }}</span></div>
        </div>
        <div v-if="$clicks < 3" class="ab__row">
          <div class="ab__el ab__input"><span class="ab__ph" v-if="$clicks < 2">Coupon code</span><span v-else>SAVE10</span> <em v-show="$clicks >= 1">textbox</em></div>
          <div class="ab__el ab__btn" :class="{ 'is-hit': $clicks === 2 }">Redeem <em v-show="$clicks >= 1">button</em></div>
        </div>
        <div v-else class="ab__row">
          <div class="ab__done">Coupon <b>SAVE10</b> applied</div>
          <div class="ab__link">Remove coupon</div>
        </div>
      </div>
    </div>
  </div>
  <div class="ab__arrow">→</div>
  <div class="ab__col">
    <div class="ab__h">What the agent sees and does</div>
    <div class="ab__term">
      <div v-if="$clicks === 0"><span class="c-dim">$ ▍</span></div>
      <div v-if="$clicks >= 1" :class="{ 'is-old': $clicks > 1 }">
        <div><span class="c-dim">$</span> agent-browser <b>snapshot</b></div>
        <div>- <span class="c-ref">heading</span> "Cart" <span class="c-dim">[ref=e6]</span></div>
        <div>- <span class="c-ref">textbox</span> "Coupon code" <span class="c-dim">[ref=e23]</span></div>
        <div>- <span class="c-ref">button</span> "Redeem" <span class="c-dim">[ref=e24]</span></div>
      </div>
      <div v-if="$clicks >= 2" class="mt-2" :class="{ 'is-old': $clicks > 2 }">
        <div><span class="c-dim">$</span> agent-browser <b>find</b> role <span class="c-ref">textbox</span> <span class="c-dim">\</span></div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;fill "SAVE10" --name "Coupon code"</div>
        <div><span class="c-dim">$</span> agent-browser <b>find</b> role <span class="c-ref">button</span> click --name "Redeem"</div>
      </div>
      <div v-if="$clicks >= 3" class="mt-2">
        <div><span class="c-dim">$</span> agent-browser <b>wait</b> --text "Coupon (SAVE10)"</div>
        <div><span class="c-dim">$</span> agent-browser <b>get text</b> ".summary__rows"</div>
        <div class="c-out">Coupon (SAVE10) −€0.89 · Total €14.00</div>
      </div>
    </div>
  </div>
</div>

<div class="ab__loop mt-4">
  <div :class="{ on: $clicks === 1 }"><b>1</b> look <code>snapshot</code></div>
  <span>→</span>
  <div :class="{ on: $clicks === 2 }"><b>2</b> act <code>find … fill</code> <code>click</code></div>
  <span>→</span>
  <div :class="{ on: $clicks === 3 }"><b>3</b> check <code>wait</code> <code>get text</code></div>
</div>

<div class="mt-4 text-center text-lg">It searches like a screen reader: by <b class="text-[#ff6bed]">role and name</b>. You know this as <code>getByRole</code>.</div>

<style>
.ab { display: grid; grid-template-columns: 340px auto minmax(0, 1fr); gap: 14px; align-items: start; }
.ab__h { font-size: 12px; font-weight: 700; letter-spacing: .06em; text-transform: uppercase; color: #ff6bed; margin-bottom: 8px; }
.ab__arrow { color: #ff6bed; font-size: 32px; font-weight: 700; padding-top: 110px; }
.ab__page { border-radius: 10px; overflow: hidden; background: #f4f4f4; color: #222; border: 1px solid rgba(255,255,255,.2); height: 262px; }
.ab__pagebar { display: flex; gap: 5px; align-items: center; padding: 6px 10px; background: #ddd; }
.ab__pagebar i { width: 8px; height: 8px; border-radius: 50%; background: #aaa; }
.ab__pagebar span { margin-left: 8px; font-size: 11px; color: #666; }
.ab__pagebody { padding: 14px 22px 14px 16px; }
.ab__el { position: relative; }
.ab__el em { position: absolute; top: -10px; right: -10px; font-style: normal; font-size: 10px; font-weight: 800; background: #ff6bed; color: #1a1d29; border-radius: 999px; padding: 1px 7px; font-family: var(--slidev-code-font-family, monospace); }
.ab__title { display: inline-block; font-size: 20px; font-weight: 700; padding-right: 34px; }
.ab__sum { margin-top: 8px; font-size: 14px; }
.ab__sum > div { display: flex; justify-content: space-between; padding: 2px 0; }
.ab__sum .is-new { color: #1a7f37; font-weight: 700; }
.ab__total { margin-top: 4px; padding-top: 6px !important; border-top: 1px solid #ccc; font-weight: 700; font-size: 16px; }
.ab__row { display: flex; gap: 12px; margin-top: 16px; align-items: center; }
.ab__input { flex: 1; border: 1px solid #bbb; border-radius: 6px; padding: 6px 10px; background: #fff; font-size: 14px; }
.ab__ph { color: #999; }
.ab__btn { border: 1.5px solid #222; border-radius: 6px; padding: 6px 12px; font-weight: 700; font-size: 14px; background: #fff; }
.ab__btn.is-hit { background: #222; color: #fff; }
.ab__done { flex: 1; font-size: 12px; }
.ab__done b { color: #222 !important; }
.ab__link { font-size: 12px; text-decoration: underline; white-space: nowrap; }
.ab__term { border-radius: 10px; background: #1a1d29; border: 1px solid rgba(255,255,255,.15); padding: 12px 14px; font-family: var(--slidev-code-font-family, monospace); font-size: 12.5px; line-height: 1.7; color: #eaedf3; height: 262px; white-space: nowrap; overflow: hidden; }
.ab__term b { color: #f3e6c4; }
.ab__term .is-old { opacity: .45; }
.c-dim { opacity: .5; }
.c-ref { color: #ff6bed; font-weight: 700; }
.c-out { color: #6ee7a0; }
.ab__loop { display: flex; justify-content: center; align-items: center; gap: 12px; }
.ab__loop > span { color: #ff6bed; font-weight: 700; }
.ab__loop > div { display: flex; align-items: center; gap: 8px; padding: 6px 14px; border: 1px solid rgba(255,255,255,.15); border-radius: 999px; background: rgba(255,255,255,.04); font-size: 15px; opacity: .6; }
.ab__loop > div.on { opacity: 1; border-color: #ff6bed; background: rgba(255,107,237,.12); }
.ab__loop b { display: inline-grid; place-items: center; width: 20px; height: 20px; border-radius: 50%; background: #ff6bed; color: #1a1d29; font-size: 12px; }
.ab__loop code { font-size: 13px; }
</style>

<!--
TIME: 6:15–7:15 (60s)

- What does Agent Browser do? It is a program in the terminal that controls a real browser. On the left the cart as you see it.
- [click] **Look.** With `snapshot` the agent gets the page as a **list**. Every element has a **role** and a **name**: a heading “Cart”, a textbox “Coupon code”, a button “Redeem”. The pink tags on the left show the role.
- [click] **Act.** It does not say “click at pixel 400, 300”. It says: “Find the textbox named Coupon code and type SAVE10 into it. Find the button Redeem and click it.”
- [click] **Check.** It waits until the text “Coupon (SAVE10)” is on the page, then reads the summary: 89 cents discount, total 14 euros. That is how it checks its own result.
- This is the loop from before, only with real commands: look, act, check.
- For you: role and name is exactly what a **screen reader** reads out. In Playwright that is `getByRole`. That is why it works well on accessible pages and badly on pages without labels.
- If asked: to read the totals it uses a CSS selector (`.summary__rows`), it does not work entirely without one. The snapshot also assigns numbers (`ref=e23`) that it could click directly (`click @e23`). In my run it almost always used role and name, because the names are already in the feature map. More commands: `open`, `screenshot`, `record` for the video.
- SOURCE: commands from the local run, otto-nuxt-shop `.talk-logs/03-verify-gutschein.jsonl` (scenario 1). That run used the German UI; the control names here are the ones of the English UI (“Warenkorb” → “Cart”, “Gutscheincode” → “Coupon code”, “Einlösen” → “Redeem”, “SPAR10” → “SAVE10”). The output of `get text` is line by line in the run, here on one line and without subtotal and shipping. `agent-browser --help` (v0.38.2).
-->


---

<div class="grid grid-cols-[0.85fr_1.15fr] gap-8 h-full items-center">
<div>

<h1 class="!text-[2.3rem] !leading-tight">Our example: an <span class="text-[#ff6bed]">Otto clone</span> in Nuxt</h1>

<div class="mt-5 text-lg opacity-80 space-y-1">
  <div>Nuxt 4 + OTTO's open B2B design system</div>
  <div>Home page, search, product page, cart</div>
</div>

<div v-click class="mt-6 text-xl">Our task: <b class="text-[#ff6bed]">a coupon code in the cart</b></div>

</div>
<div>

<img src="/otto-klon.png" alt="Home page of the Otto clone in Nuxt, English UI" class="rounded-xl border border-white/15 w-full" />

<div class="mt-2 text-sm opacity-60 text-center">Unofficial demo, not by OTTO · github.com/alexanderop/otto-nuxt-shop</div>

</div>
</div>

<!--
TIME: 7:15–7:45 (30s)

- Before we teach the agent anything: what are we working on?
- Our running example: an Otto clone in Nuxt 4 with OTTO's open B2B design system. Home page, search, categories, product page, cart, wishlist. OTTO is one of the biggest online shops in Germany.
- Unofficial demo, not by OTTO. Repo: github.com/alexanderop/otto-nuxt-shop
- [click] **This is what we want to build:** customers should be able to redeem a coupon code in the cart. And the agent should prove by itself that it works.
-->

---

# The <span class="text-[#ff6bed]">ticket</span>: SHOP-42

<div class="text-lg opacity-80 mb-3">“As a customer I want to redeem a coupon code in the cart.”</div>

```gherkin {1-4|6-9|11-14}
Scenario: Valid coupon
  Given an item is in the cart
  When I redeem the code "SAVE10"
  Then the total drops by 10 % of the subtotal

Scenario: Invalid coupon
  Given an item is in the cart
  When I redeem the code "NOSUCHCODE"
  Then I see "This coupon is invalid"

Scenario: Remove coupon
  Given the code "SAVE10" is redeemed
  When I remove the coupon
  Then the full total applies again
```

<!--
TIME: 7:45–8:10 (25s)

- A completely normal ticket. A user story plus three Gherkin scenarios.
- Valid code, total drops.
- [click] Invalid code, error message.
- [click] Remove the coupon, full price.
- The acceptance criteria are the **test oracle**: what is right, what is wrong? Unclear criteria, unclear verdict. That is your craft, I come back to it at the end.
- Slightly shortened on the slide: the two rules (coupon survives a reload, at most one coupon) are missing, they show up again in the report. Original: `docs/tickets/SHOP-42-coupon.md` (English) and `docs/tickets/SHOP-42-gutschein.md` (German original, commit c6c529e).
-->

---
layout: statement
---

# The agent should check this <span class="text-[#ff6bed]">in the real shop</span>.

<div class="mt-8 text-2xl opacity-80">But it does not know the shop.</div>

<!--
TIME: 8:10–8:20 (10s)

- The agent should click through exactly these three scenarios in the real shop.
- But it does not know how to start the shop, where the cart is, how to enter a coupon.
- Like a new colleague on the first day …
-->

---

# An agent is a new colleague who <span class="text-[#ff6bed]">forgets everything</span> every evening

<div class="text-xl opacity-80 -mt-1">So it gets an <b class="text-[#ff6bed]">onboarding binder</b>. In Claude Code it is called a <b>skill</b>.</div>

<div class="mt-8">

<IconCards :columns="2" size="lg" no-clicks :items="[
  { icon: '/funnel/prosa.webp', title: 'SKILL.md', sub: 'start the shop, operate it, collect evidence', tag: 'Work instruction' },
  { icon: '/icons/feature-map.webp', title: 'Feature map', sub: 'per feature: What exists? How do I get there? Where does it bite?', tag: 'Test concept', accent: true },
]" />

</div>

<!--
TIME: 8:20–8:45 (25s)

- **Analogy:** an agent is like a new colleague on the first day. Smart, but it does not know your shop. And it forgets everything every evening.
- What do you give a new colleague? An **onboarding binder**. In Claude Code such a binder is called a “skill”. It is just a folder with Markdown files in the repo.
- Two parts, in your words: the **SKILL.md** is the work instruction. How do I start the test environment, how do I operate the shop, how do I collect evidence?
- The **feature map** is the test concept: one file per feature. What exists, how do I get there, where does it bite?
- It does not have to guess, it looks things up.
-->

---

# This is how the agent uses the binder in <span class="text-[#ff6bed]">every run</span>

<div class="mt-10">

<IconCards flow no-clicks :items="[
  { icon: '/icons/issue.webp', title: 'Task', sub: '“Check SHOP-42 in the browser”' },
  { icon: '/funnel/prosa.webp', title: 'Spot the binder', sub: 'it only knows the blurb', tag: 'description' },
  { icon: '/icons/launch.webp', title: 'Start the shop', sub: 'script + self-check', tag: 'launch · doctor' },
  { icon: '/icons/feature-map.webp', title: 'Look it up', sub: 'features/cart.md', accent: true },
  { icon: '/icons/evidence.webp', title: 'Click + evidence', sub: 'a screenshot per step' },
]" />

</div>

<div class="mt-8 text-center text-xl opacity-80">It only loads what it needs. Without the binder every run starts <b>from zero</b>.</div>

<!--
TIME: 8:45–9:10 (25s)

- What happens when the agent gets the task “Check SHOP-42 in the browser”?
- Of every binder it only knows the **blurb**, the description. From that it recognises: for this task I need the binder for the shop. Only then does it load it completely.
- It starts the shop with the script from the binder and runs a self-check: is the shop running, is there data?
- Then it looks up the feature. For the coupon that is the page about the cart.
- Only now does it click, and it collects a screenshot at every step.
- Every agent starts the **same** way. Without the binder every run would guess: how does it start, which port, where is the cart?
- In a moment you see the two files.
- SOURCE: otto-nuxt-shop commit 01f006e, `.claude/skills/verify-otto-shop/SKILL.md`
-->

---
layout: code-editor
project: otto-nuxt-shop
activeFile: SKILL.md
tabs: SKILL.md
step: The work instruction
files: |
  .claude/skills/verify-otto-shop
    SKILL.md
    scripts/
      otto-verify.sh
    features/
      README.md
      home.md
      search.md
      product-page.md
      cart.md
      wishlist.md
---

```md {1-4|6-7|9-19|all}
---
name: verify-otto-shop
description: Launch the OTTO demo shop and drive it in a real
  browser with agent-browser to prove a change works.
---
## Hard rules
Never touch port 3000. Kill only what you started.

## Launch
$V launch    # nuxt dev on 3100, ready = "Popular categories"

## Doctor
$V doctor    # every line must say ok

## Drive
agent-browser open http://localhost:3100/ ; $V wait-ready

## Evidence + Cleanup
$V proof cart-after ; $V stop   # evidence stays
```

<!--
TIME: 9:10–9:35 (25s)

- The work instruction for real: a Markdown file in `.claude/skills/`. On the left the whole binder.
- At the top the **blurb**, the description. That is the only part the agent always reads.
- [click] Hard rules. Port 3000 belongs to another project. Only stop what you started yourself.
- [click] The steps from before: start, self-check, operate, save evidence and clean up. Real commands from this repo, not examples. `$V` is just the shortcut for the start script.
- [click] All together: one manual that every agent works through the same way.
- If asked: the agent picked port 3100 itself because 3000 was taken. `doctor` reports e.g. “ok port 3100 owned by our run”, “ok /api/products total=184”.
- Shortened on the slide. Original: about 130 lines.
- SOURCE: otto-nuxt-shop, `.claude/skills/verify-otto-shop/SKILL.md` (first version: commit 01f006e)
-->

---
layout: code-editor
project: otto-nuxt-shop
activeFile: cart.md
tabs: SKILL.md, cart.md
step: The feature map
files: |
  .claude/skills/verify-otto-shop
    SKILL.md
    scripts/
      otto-verify.sh
    features/
      README.md
      home.md
      search.md
      product-page.md
      cart.md
      wishlist.md
---

```md {1|3-6|8-9|11-14|16-18|all}
# Cart

## Sub-features
- cart-qty-plus: `+` raises the quantity, totals and cookie follow.
- cart-qty-minus: `−` lowers the quantity. At 1 the line item is removed.
- cart-shipping: below €79 shipping costs €5.95, otherwise it is free.

## How to get to it (user POV)
- Choose “Cart” in the header.

## Driving it with agent-browser
- agent-browser open http://localhost:3100/p/1
- agent-browser find role button click --name "Add to cart"
- agent-browser find role button click --name "+" --exact

## Gotchas
- The minus button is “−” (U+2212), not a hyphen.
- Toasts live in the shadow DOM. wait --text does not find them.
```

<!--
TIME: 9:35–10:00 (25s)

- And this is one page of the feature map: the cart. Every feature gets a file like this, on the left you see home page, search, product page, wishlist.
- Every file has the same four sections.
- [click] **What exists?** Every sub-feature with its expected behaviour. The coupon is not in there yet. The agent adds it itself in a moment.
- [click] **How do I get there?** From the user's point of view.
- [click] **How do I operate it?** Real commands the agent can copy.
- [click] **Gotchas.** My favourite example: the minus button is a typographic minus, not a hyphen. Exactly the knowledge that otherwise only lives in a tester's head.
- [click] This is a test concept the agent can read.
- If asked, gotchas from the search: a known bug is listed there, which the agent should report as failed instead of weakening the test. And a German word like “uhr” finds nothing, because the seed data is English. Not a bug.
- SOURCE: otto-nuxt-shop, `.claude/skills/verify-otto-shop/features/cart.md` and `search.md` (shortened; first version in German: commit 01f006e, `warenkorb.md` and `suche.md`)
-->

---

# You do not write the binder by hand: <span class="text-[#ff6bed]">one command</span>

<div class="cmds mt-3">
  <div><span>1 · Marketplace</span><code>/plugin marketplace add cursor/plugins</code></div>
  <div><span>2 · Install</span><code>/plugin install pstack@cursor-plugins</code></div>
  <div><span>3 · Run in the repo</span><code>/pstack:create-verification-skill</code></div>
</div>

<style>
.cmds { display: grid; gap: 6px; }
.cmds div { display: grid; grid-template-columns: 170px 1fr; align-items: center; gap: 12px; }
.cmds span { font-size: 13px; font-weight: 700; color: #ff6bed; text-transform: uppercase; letter-spacing: .04em; }
.cmds code { font-size: 15px; padding: 6px 10px; }
</style>

<div class="mt-5">

<IconCards flow :items="[
  { icon: '/funnel/statisch.webp', title: 'Interview the repo', sub: 'How does the app start? How do you operate it?' },
  { icon: '/funnel/prosa.webp', title: 'Write the skill', sub: 'SKILL.md + start script' },
  { icon: '/icons/feature-map.webp', title: 'Feature map', sub: 'one file per feature', accent: true },
  { icon: '/funnel/verifikation.webp', title: 'Prove it', sub: 'play it through once, end to end' },
  { icon: '/jira/workflow.webp', title: 'Maintain', sub: '/maintain-verification-skill' },
]" no-clicks />

</div>

<div class="mt-5 text-center text-base opacity-70"><b>pstack</b> by Lauren Tan (poteto), React Compiler team · github.com/cursor/plugins</div>

<!--
TIME: 10:00–10:25 (25s)

- You do not have to write the binder by hand. One command from pstack: `/create-verification-skill`.
- It interviews the repo, not you: how does the app start, how do you operate it, what evidence is there?
- It writes the SKILL.md with a start script and creates the feature map, one file per feature.
- Important: it proves the skill itself, played through once completely. Only after that can you rely on the skill.
- After that you maintain the map with `/maintain-verification-skill` when the app changes.
- **Who is behind it?** pstack comes from poteto, Lauren Tan. On the React Compiler core team, before that at Meta, Netflix and Cursor (X bio, as of Nov 2026). A collection of skills, playbooks and principles: less code, but better code. “If you want to go fast, go deep first.” Started as a Cursor plugin, by now officially also for Claude Code.
- **The tool is interchangeable:** in my setup the agent automatically takes Agent Browser because it is installed. You can use Playwright CLI or Playwright MCP just as well. The skill describes what is checked, not with what.
- SOURCE: pstack `skills/create-verification-skill/SKILL.md` (v0.15.36), github.com/cursor/plugins/tree/main/pstack (README), x.com/poteto; otto-nuxt-shop commit 01f006e.
-->

---

# Prompt 1: <span class="text-[#ff6bed]">Build the feature</span>

<div class="text-sm opacity-60 -mt-2 mb-3">The real prompt, slightly shortened and translated from German</div>

<div class="prompt">
  <div class="prompt__bar"><i></i><i></i><i></i><span>Claude Code · Prompt</span></div>
  <div class="prompt__body">
    <div class="prompt__lead"><b>›</b> Implement the ticket <code class="is-file">docs/tickets/SHOP-42-coupon.md</code></div>
    <ol>
      <li><span>1</span><div>Build the feature in the <em>cart</em> <code class="is-file">/cart</code></div></li>
      <li><span>2</span><div>Check every <em>Gherkin scenario</em> in a real browser<br/>with the skill <code class="is-skill">verify-otto-shop</code></div></li>
      <li><span>3</span><div>Add the coupon to the <em>feature map</em> <code class="is-file">features/cart.md</code></div></li>
      <li><span>4</span><div><em>Commit</em> on the current branch. No push.</div></li>
    </ol>
  </div>
</div>

<div v-click class="mt-6 text-lg">Not a word about <b>how</b> to test. That is in the <span class="text-[#ff6bed]">skill</span>.</div>

<style>
.prompt { border: 1px solid rgba(255,255,255,.15); border-radius: 12px; overflow: hidden; background: #1a1d29; }
.prompt__bar { display: flex; align-items: center; gap: 6px; padding: 8px 12px; background: rgba(255,255,255,.05); border-bottom: 1px solid rgba(255,255,255,.08); }
.prompt__bar i { width: 10px; height: 10px; border-radius: 50%; background: rgba(255,255,255,.2); }
.prompt__bar span { margin-left: 8px; font-size: 12px; opacity: .6; }
.prompt__body { padding: 16px 20px; font-size: 18px; }
.prompt__lead b { color: #ff6bed; margin-right: 6px; }
.prompt ol { list-style: none; margin: 14px 0 0; padding: 0; display: grid; gap: 10px; }
.prompt li { display: flex; gap: 12px; align-items: flex-start; margin: 0; }
.prompt li > span { flex: none; width: 26px; height: 26px; border-radius: 50%; display: grid; place-items: center; background: #ff6bed; color: #1a1d29; font-weight: 700; font-size: 14px; margin-top: 1px; }
.prompt em { font-style: normal; font-weight: 700; color: #f3e6c4; }
.prompt code { font-size: 15px; padding: 1px 8px; border-radius: 6px; }
.prompt code.is-file { background: rgba(255,107,237,.14); color: #ff9ff3; }
.prompt code.is-skill { background: rgba(122,92,192,.35); color: #d9c9ff; }
</style>

<!--
TIME: 10:25–11:10 (45s)

- That is the whole prompt. Shortened by the port hint, the skill path and “reply with a summary”.
- The ticket is the source, not my chat text.
- Build.
- Check it yourself: every scenario, in a real browser, with the skill.
- The feature map grows with the feature. The next agent then already knows the coupon.
- Commit, do not push. A human decides.
- [click] How to start and operate the shop is not in the prompt. The agent knows that from the skill.
- Call: `claude -p "…" --model opus --permission-mode bypassPermissions`
- The original prompt was in German and pointed at the German file names (`SHOP-42-gutschein.md`, `/warenkorb`, `features/warenkorb.md`).
- SOURCE: otto-nuxt-shop `.talk-logs/02-implement-gutschein.jsonl`
-->

---

# This is how the agent builds the <span class="text-[#ff6bed]">feature</span>

<div class="mt-10">

<IconCards flow no-clicks :width="146" :loop="{ from: 3, to: 1, label: 'fixed a CSS detail' }" :items="[
  { icon: '/icons/issue.webp', title: 'Read', sub: 'ticket, skill, code' },
  { icon: '/funnel/codebasis.webp', title: 'Build', sub: 'useCoupon.ts, the cart page', tag: '+ typecheck' },
  { icon: '/jira/agent.webp', title: 'Check in the browser', sub: '3 scenarios with the skill', accent: true },
  { icon: '/icons/evidence.webp', title: 'Look at screenshots', sub: 'its own evidence' },
  { icon: '/icons/feature-map.webp', title: 'Commit', sub: 'feature map extended' },
]" />

</div>

<div class="mt-6 text-center text-base opacity-80">It also writes <b>deterministic tests</b>. But not everything has an E2E test.<br/>So it additionally checks <span class="text-[#ff6bed]">in a real browser</span> until everything is green.</div>

<!--
TIME: 11:10–12:15 (65s)

- The agent does not use the verification skill only in QA. It already uses it while building the feature.
- Of course it also writes unit and component tests. But in most projects we do not have E2E tests for everything. The check in the browser closes exactly that gap.
- This is the real sequence from the log. One prompt: “Implement SHOP-42, check every scenario with the skill, extend the feature map, commit.”
- It first reads the ticket **and** the verification skill. So it knows beforehand how it will check.
- After the code it starts the shop through the skill and clicks through the three scenarios.
- The interesting part is the arrow back: it looks at its own screenshots, sees a CSS detail and fixes it.
- Cost below one dollar (15 tool calls, $0.90). Commit b70393e.
- It also adds the coupon to the feature map. The docs grow with the feature.
- SOURCE: log `.talk-logs/02-implement-gutschein.jsonl`
-->

---
layout: statement
---

# The same skill then does <span class="text-[#ff6bed]">QA</span>.

<div class="mt-8 text-2xl opacity-80">A <b>second</b> agent that did not write the code.<br/>It does not just tick off scenarios, it also tests <b>exploratively</b>.</div>

<!--
TIME: 12:15–12:25 (10s)

- The developer agent used the skill and Agent Browser to build the feature.
- We can now use the same binder a second time: for QA.
- **Independence of testing:** whoever builds does not check alone. So a second agent with fresh context. It did not write the code and does not know the shortcuts of the first one.
- But this time ticking off the three scenarios is not enough. The QA agent should also test exploratively, like an experienced tester.
-->

---

# Prompt 2: The <span class="text-[#ff6bed]">QA agent</span>

<div class="text-sm opacity-60 -mt-2 mb-3">The real prompt, slightly shortened and translated. The pictures in a moment follow this run.</div>

<div class="prompt">
  <div class="prompt__bar"><i></i><i></i><i></i><span>Claude Code · Prompt</span></div>
  <div class="prompt__body">
    <div class="prompt__lead"><b>›</b> You are the <em>QA agent</em> for the PR on <code class="is-file">feat/gutschein</code>. Do not change any code.</div>
    <div class="prompt__lead opacity-80">Ticket: <code class="is-file">docs/tickets/SHOP-42-coupon.md</code></div>
    <ol>
      <li><span>1</span><div>Check every <em>Gherkin scenario</em> in a real browser with the skill <code class="is-skill">verify-otto-shop</code></div></li>
      <li class="is-charter"><span>2</span><div>Then test <em>exploratively</em> around the coupon, like an experienced tester<small>spelling, redeeming twice, quantity changes, removing items, reload</small></div></li>
      <li><span>3</span><div>Record the whole run as a <em>video</em> and take <em>screenshots</em> of every scenario and finding</div></li>
      <li><span>4</span><div>Write a <em>report</em> with a fixed verdict: <code class="is-skill">HEALTHY</code> <code class="is-skill">MINOR_ISSUES</code> <code class="is-skill">CRITICAL_BUGS</code></div></li>
    </ol>
  </div>
</div>

<div class="mt-4 text-lg">Item 2 is a <span class="text-[#ff6bed]">test charter</span>. That is where your QA knowledge goes.</div>

<style>
.prompt { border: 1px solid rgba(255,255,255,.15); border-radius: 12px; overflow: hidden; background: #1a1d29; }
.prompt__bar { display: flex; align-items: center; gap: 6px; padding: 8px 12px; background: rgba(255,255,255,.05); border-bottom: 1px solid rgba(255,255,255,.08); }
.prompt__bar i { width: 10px; height: 10px; border-radius: 50%; background: rgba(255,255,255,.2); }
.prompt__bar span { margin-left: 8px; font-size: 12px; opacity: .6; }
.prompt__body { padding: 16px 20px; font-size: 18px; }
.prompt__lead b { color: #ff6bed; margin-right: 6px; }
.prompt ol { list-style: none; margin: 14px 0 0; padding: 0; display: grid; gap: 10px; }
.prompt li { display: flex; gap: 12px; align-items: flex-start; margin: 0; }
.prompt li > span { flex: none; width: 26px; height: 26px; border-radius: 50%; display: grid; place-items: center; background: #ff6bed; color: #1a1d29; font-weight: 700; font-size: 14px; margin-top: 1px; }
.prompt em { font-style: normal; font-weight: 700; color: #f3e6c4; }
.prompt code { font-size: 15px; padding: 1px 8px; border-radius: 6px; }
.prompt code.is-file { background: rgba(255,107,237,.14); color: #ff9ff3; }
.prompt code.is-skill { background: rgba(122,92,192,.35); color: #d9c9ff; }
.prompt li.is-charter { margin: 0 -10px; padding: 6px 10px; border: 1px solid #ff6bed; border-radius: 10px; background: rgba(255,107,237,.08); }
.prompt__body { font-size: 16px; padding: 12px 18px; }
.prompt ol { gap: 6px; margin-top: 10px; }
.prompt small { display: block; font-size: 14px; opacity: .7; margin-top: 2px; }
</style>

<!--
TIME: 12:25–13:25 (60s)

- A **second** agent. It did not write the code, and it is not allowed to change it.
- Role and boundary: QA agent, no code.
- Again the ticket is the source.
- Scenarios first, with the skill.
- **Say it honestly:** this is my test charter. I put “quantity changes” in as an example. The agent did not know the planted bug, but I told it where experienced testers look.
  - Cookie manipulation was not in there. And that “removing items” leads to a negative total was not either. It found that by itself.
  - That is exactly the point for you: this list is **QA knowledge**. Whoever knows where things break writes the better charter.
- Video and screenshots: that is where the run you see in a moment was recorded.
- Fixed verdict and fixed report structure. The pipeline can work with that later.
- The charter line. I come back to it at the end: that is your work, one level higher.
- After that also: “Commit only the report. No push.”
- `feat/gutschein` is the real branch name (“Gutschein” is German for coupon).
- SOURCE: otto-nuxt-shop `.talk-logs/03-verify-gutschein.jsonl`, report commit 302bad8
-->


---
clicks: 10
---

# Demo: First the ticket, then <span class="text-[#ff6bed]">exploratory</span>

<AnnotatedStills
  class="mt-2"
  dir="/shop42"
  :step="$clicks"
  :chapters="[
    { t: 0, text: 'Put a mascara into the cart' },
    { t: 4, text: 'Scenario 1: redeem SAVE10 → −€0.89', kind: 'pass' },
    { t: 9, text: 'Scenario 2: NOSUCHCODE → “invalid”', kind: 'pass' },
    { t: 15, text: 'Exploratory: “ save10 ” with spaces', kind: 'pass' },
    { t: 20, text: 'Quantity 1 → 5', kind: 'bug', severity: 'major', finding: 'Discount −€0.89 instead of −€4.47' },
    { t: 29, text: 'Redeem at 9 items, reduce to 1', kind: 'bug', severity: 'critical', finding: '−€8.05: 90 % off, not 10 %' },
    { t: 37, text: 'Scenario 3: remove coupon → €14.89', kind: 'pass' },
    { t: 40, text: 'Empty input and reload', kind: 'bug', severity: 'minor', finding: '“invalid” instead of “enter a code”' },
    { t: 62, text: 'Second item: a lemon for €0.71' },
    { t: 70, text: 'Mascara out, only the lemon left', kind: 'bug', severity: 'critical', finding: 'Total −€1.39' },
    { t: 75, text: 'Cookie set to 500', kind: 'bug', severity: 'major', finding: '−€493.34: discount unchecked' },
  ]"
/>

<!--
TIME: 13:25–14:55 (90s)

- A **second** agent, the QA agent, checks the PR. It did not write the code.
- These stills replay the real run of the QA agent step by step. Every click jumps one chapter ahead (11 pictures, 10 clicks). On the right the chapter list.
- LIVE OPTION (if the wifi is stable): in the repo otto-nuxt-shop on `feat/gutschein` start `claude`, prompt from slide “Prompt 2”. Takes about 2.5 minutes. Otherwise these pictures.

VOICE-OVER (per picture):
- **Picture 1** “The agent starts on the home page and puts a mascara into the cart.”
- [click] **Picture 2** “Scenario 1: it redeems SAVE10. 89 cents discount, total 14 euros. Green.”
- [click] **Picture 3** “Scenario 2: NOSUCHCODE. The error message appears. Green.”
- **STOP HERE.** “The first two scenarios from the ticket: green. An E2E test could have done that too. From now on it looks where nothing is in the ticket. It ticks off the third scenario along the way.”
- [Ask for hands] **“You are the testers: where would you look now?”** Wait for two or three shouts (quantity? spaces? removing?).
- [click] **Picture 4** “It types the code in lower case and with spaces. Works.”
- [click] **Picture 5** “Now it raises the quantity to 5. Watch the discount: it stays at 89 cents. That is the first finding.”
- [click] **Picture 6** “It turns it around: redeem at 9 items, then down to 1. 8.05 euros discount on 8.94 euros. That is 90 percent.”
- [click] **Picture 7** “Scenario 3 along the way: remove the coupon, full price. Green.”
- [click] **Picture 8** “Empty input, reload. Here the shop says ‘invalid’ instead of ‘please enter a code’. A small thing.”
- [click] **Picture 9** “Now it gets mean: it adds a lemon for 71 cents …”
- [click] **Picture 10** “… and removes the mascara. Total: minus 1.39 euros.”
- [click] **Picture 11** “At the end it manipulates the cookie. 500 euros discount. That would be a real price exploit.”

- **Where the stills come from:** the original run was recorded by the agent itself with `agent-browser record`, against the German UI (stills of that video are in the German deck). For this deck I replayed the same steps against the English UI and captured each result with `agent-browser screenshot` (`public/shop42/00–10.webp`). Same products, same order, same amounts; only the language and the code (`SAVE10` instead of `SPAR10`) differ. The chapter times are the ones from the original video (±1 s).
-->

---

# The <span class="text-[#ff6bed]">report</span> of the QA agent

<div class="rep">
  <div class="rep__head">
    <div>
      <div class="rep__title">QA report SHOP-42: coupon code in the cart</div>
      <div class="rep__meta">feat/gutschein · Chromium via agent-browser · 12 screenshots · video · 20 turns · $1.00</div>
    </div>
    <div class="rep__verdict">CRITICAL_BUGS</div>
  </div>
  <div class="rep__body">
    <div>
      <div class="rep__h">Ticket: scenarios + rules</div>
      <div class="rep__row"><span class="pill is-pass">PASS</span>Valid coupon</div>
      <div class="rep__row"><span class="pill is-pass">PASS</span>Invalid coupon</div>
      <div class="rep__row"><span class="pill is-pass">PASS</span>Remove coupon</div>
      <div class="rep__row"><span class="pill is-pass">PASS</span>Survives a reload</div>
      <div class="rep__row"><span class="pill is-pass">PASS</span>At most one coupon</div>
    </div>
    <div>
      <div class="rep__h">Findings (exploratory)</div>
      <div class="rep__row"><span class="pill is-crit">CRITICAL</span><b>F2</b> Discount stays high at lower quantity</div>
      <div class="rep__row"><span class="pill is-crit">CRITICAL</span><b>F3</b> Total becomes negative</div>
      <div class="rep__row"><span class="pill is-major">MAJOR</span><b>F1</b> Discount does not grow with quantity</div>
      <div class="rep__row"><span class="pill is-major">MAJOR</span><b>F4</b> Discount taken unchecked from cookie</div>
      <div class="rep__row"><span class="pill is-minor">MINOR</span><b>F5</b> Empty input reports “invalid”</div>
    </div>
  </div>
  <div class="rep__foot">Per finding: repro steps · expected vs. actual · evidence · root cause (<code>useCoupon.ts:15</code>)</div>
</div>

<style>
.rep { margin-top: 10px; border: 1px solid rgba(255,255,255,.15); border-radius: 12px; overflow: hidden; background: #1a1d29; }
.rep__head { display: flex; justify-content: space-between; align-items: center; gap: 16px; padding: 12px 18px; background: rgba(255,255,255,.05); border-bottom: 1px solid rgba(255,255,255,.08); }
.rep__title { font-weight: 700; font-size: 17px; }
.rep__meta { font-size: 12px; opacity: .6; margin-top: 2px; }
.rep__verdict { flex: none; padding: 6px 12px; border-radius: 8px; background: rgba(255,77,77,.18); border: 1px solid #ff4d4d; color: #ff8a8a; font-weight: 800; font-family: var(--slidev-code-font-family, monospace); font-size: 15px; letter-spacing: .03em; }
.rep__body { display: grid; grid-template-columns: 0.85fr 1.15fr; gap: 24px; padding: 14px 18px 8px; }
.rep__h { font-size: 12px; font-weight: 700; text-transform: uppercase; letter-spacing: .06em; color: #ff6bed; margin-bottom: 8px; }
.rep__row { display: flex; align-items: center; gap: 10px; font-size: 15px; padding: 5px 0; border-bottom: 1px solid rgba(255,255,255,.06); }
.rep__row b { color: #f3e6c4; }
.pill { flex: none; width: 74px; text-align: center; font-size: 11px; font-weight: 800; letter-spacing: .04em; padding: 2px 0; border-radius: 999px; }
.pill.is-pass { background: rgba(74,222,128,.15); color: #6ee7a0; }
.pill.is-crit { background: rgba(255,77,77,.18); color: #ff8a8a; }
.pill.is-major { background: rgba(251,146,60,.18); color: #fdba74; }
.pill.is-minor { background: rgba(250,204,21,.16); color: #fde047; }
.rep__foot { padding: 10px 18px; font-size: 13px; opacity: .7; border-top: 1px solid rgba(255,255,255,.08); }
</style>

<!--
TIME: 14:55–15:25 (30s)

- The verdict is one of three fixed values: HEALTHY, MINOR_ISSUES, CRITICAL_BUGS.
- Left: all ticket scenarios green, plus the two rules from the ticket (reload, at most one coupon) that I left out on the ticket slide.
- Right: five findings, two of them critical.
- F4 is even a security problem. With a manipulated cookie you get a 500 euro discount.
- Plus evidence and the root cause for the developer: `useCoupon.ts:15`. It even proposes the fix.
- One dollar for a QA run that would have cost me as a human half an hour.
- **Say it honestly:** I planted one bug on purpose: the discount is stored as a fixed amount when the coupon is redeemed. The QA agent did not know that, the commit is neutrally named “compute and store the discount when redeeming”. Out of that one bug it made four findings.
- The report itself is in German; the slide is my translation.
- SOURCE: otto-nuxt-shop commit 302bad8, docs/reports/SHOP-42-qa-report.md
-->

---
layout: cover
background: /bild-gherkin.jpeg
---

<div class="w-[42%] text-left">

<h1 class="!text-[2.6rem] !leading-tight">That was in <span class="text-[#ff6bed]">no</span> <span class="whitespace-nowrap">Gherkin scenario.</span></h1>

<div class="mt-6 text-2xl opacity-80">Because nobody thought of it.</div>

</div>

<div v-click class="sofa-shock">
  <HamcrabPose v-if="$clicks >= 1" pose="shock" :size="140" />
  <div class="sofa-shock__tag">Total <b>−€493.34</b></div>
</div>

<style>
.sofa-shock { position: absolute; left: 60px; bottom: 34px; display: flex; align-items: center; gap: 4px; }
.sofa-shock__tag { margin-left: -24px; transform: rotate(-6deg); padding: 10px 18px; border-radius: 10px; background: #ff6bed; color: #1a1d29; font-size: 22px; font-weight: 700; box-shadow: 0 6px 20px rgba(0,0,0,.4); }
.sofa-shock__tag b { font-size: 30px; color: #1a1d29 !important; }
</style>

<!--
TIME: 15:25–15:55 (30s)

- **The punchline.** Leave a short pause.
- All three scenarios were green. A classic E2E test would have passed.
- [click] Hamcrab shocked, with the price tag: −€493.34, the total from the last picture of the demo. Let it sink in, wait for the laugh.
- The agent did what good testers do: it asked questions nobody wrote down.
-->

---

# Three of five findings were <span class="text-[#ff6bed]">state transitions</span>

<div class="text-sm opacity-60 -mt-2 mb-3">The findings from the demo, sorted into a test matrix. Ordered by risk.</div>

<div class="rub">
  <div class="rub__row rub__head"><span>Risk</span><span>Technique</span><span>Test cases for SHOP-42</span><span>In the run</span></div>
  <div class="rub__row"><i class="is-must">required</i><b>Acceptance criteria</b><span>one test case per Gherkin scenario</span><em class="is-pass">5 × PASS</em></div>
  <div class="rub__row is-hit"><i class="is-high">high</i><b>State transitions</b><span>redeem → change quantity → remove item</span><em>F1 · F2 · F3</em></div>
  <div class="rub__row"><i class="is-high">high</i><b>Tampering</b><span>change the cookie by hand</span><em>F4</em></div>
  <div class="rub__row"><i class="is-high">high</i><b>Boundary values</b><span>empty input · quantity 1 · maximum quantity</span><em>F5</em></div>
  <div class="rub__row is-open"><i class="is-mid">medium</i><b>Error case</b><span>redeeming fails on the network</span><em>not checked</em></div>
  <div class="rub__row is-open"><i class="is-low">low</i><b>Accessibility</b><span>tab order, labels, screen reader</span><em>not checked</em></div>
</div>

<div v-click class="mt-5 text-lg">My charter was <b>one line</b>. A <span class="text-[#ff6bed]">test matrix</span> plans the cases up front and shows the gaps.</div>

<style>
.rub { border: 1px solid rgba(255,255,255,.15); border-radius: 12px; overflow: hidden; background: #1a1d29; }
.rub__row { display: grid; grid-template-columns: 80px 190px 1fr 130px; gap: 16px; align-items: center; padding: 8px 18px; font-size: 16px; border-bottom: 1px solid rgba(255,255,255,.06); }
.rub__row:last-child { border-bottom: 0; }
.rub__row b { color: #f3e6c4; }
.rub__row i { font-style: normal; font-size: 12px; font-weight: 700; }
.rub__row i.is-must { color: #ff6bed; }
.rub__row i.is-high { color: #ff8a8a; }
.rub__row i.is-mid { color: #fdba74; }
.rub__row i.is-low { color: #fde047; }
.rub__row em { font-style: normal; font-size: 13px; font-weight: 800; text-align: center; padding: 3px 0; border-radius: 999px; background: rgba(255,77,77,.18); color: #ff8a8a; }
.rub__row em.is-pass { background: rgba(74,222,128,.15); color: #6ee7a0; }
.rub__row.is-hit { background: rgba(255,107,237,.08); box-shadow: inset 3px 0 0 #ff6bed; }
.rub__row.is-open em { background: none; border: 1px dashed rgba(255,255,255,.35); color: rgba(255,255,255,.6); font-weight: 600; }
.rub__head { background: rgba(255,255,255,.05); font-size: 12px; font-weight: 700; text-transform: uppercase; letter-spacing: .06em; color: #ff6bed; }
.rub__head span:last-child { text-align: center; }
</style>

<!--
TIME: 15:55–16:40 (45s)

- “Nobody thought of it.” Could somebody have thought of it? Yes. With techniques you all know.
- I sorted the five findings from the demo into a test matrix afterwards. **Three of five** are state transitions: redeem, then change the quantity, then remove an item. The cookie finding is tampering, the empty input a boundary value.
- **Say it honestly:** the run did not have this matrix. It only had my charter, one line of keywords. That is why two rows are open: it did not check the error case and accessibility. Without the matrix I would not even have noticed.
- [click] The lesson: **test design before the browser.** The agent first builds the test matrix from the ticket, ordered by risk, price and discount logic first. Then it executes it. After that comes the exploratory session by charter: the matrix for the known, the charter for the rest.
- This is how I build it: a test matrix template, a report template and **a finished example report** live in the skill. The prompt then only says: “First the test matrix from the template, then execute, then explore by charter.”
- If asked, fixed results per test case: PASS only with evidence from the real UI, a green unit test is not enough. **Pre-existing defects:** on FAIL the agent checks the same case on main. If it is red there too, it becomes its own ticket and does not block this PR. BLOCKED means: not executable, with a reason.
- The sorting is mine, not the agent's. F5 (empty input) as a boundary value is an interpretation.
- SOURCE: findings from otto-nuxt-shop `docs/reports/SHOP-42-qa-report.md` (commit 302bad8). Matrix idea: QA skill from a client project (idea: Yannick Foelsing), private gist alexopotto/2e5b7f09afd15fd3dfdd825515ba9d1d. Do not name the client.
-->

---

# Set a label, and the agent tests <span class="text-[#ff6bed]">in the cloud</span>

<div class="mt-6">

<IconCards flow :items="[
  { icon: '/icons/label.webp', title: 'Set the label', sub: 'qa-verify on the PR', tag: 'You' },
  { icon: '/jira/workflow.webp', title: 'Start the shop', sub: 'with the script from the skill', tag: 'GitHub Actions' },
  { icon: '/icons/issue.webp', title: 'Read the ticket', sub: 'linked GitHub issue', tag: 'Claude Code' },
  { icon: '/jira/agent.webp', title: 'Test in the browser', sub: 'headless in the cloud', tag: 'Agent Browser', accent: true },
  { icon: '/icons/urteil.webp', title: 'Report + verdict', sub: 'comment with screenshots, check green or red', tag: 'PR' },
]" no-clicks />

</div>

<div class="mt-6 text-center text-xl opacity-80">The loop is the same as locally. Only the <b>trigger</b> is now a label.</div>

<!--
TIME: 16:40–17:10 (30s)

- Locally it works. Now it should run without me.
- All five cards are there at once, no click. Walk through from left to right.
- I set the label `qa-verify` on the PR. A label on purpose: I decide which PR is worth a run. From then on every new push to this PR is tested again automatically.
- GitHub Actions starts the shop. With the same script from the verification skill.
- Claude Code finds the linked GitHub issue through the PR (`Closes #2`). The issue is the ticket with the Gherkin scenarios.
- It checks in a real browser, headless in the cloud.
- The report lands with screenshots as a comment in the PR. The verdict decides whether the check turns green or red.
- Same skill, same feature map, same report as locally.
- SOURCE: alexop.dev “Building an AI QA Engineer with Claude Code and Playwright MCP” (label trigger) and “How to Use Claude Code as an AI QA Tester with Agent Browser” (--json-schema).
-->

---

# The call is a <span class="text-[#ff6bed]">test brief</span> with guardrails

<div class="qa-cmd">

```bash {1|2|3|4|5|7}
claude -p "$(envsubst < .github/prompts/qa.md)" \
  --max-budget-usd 10 \
  --allowedTools "Read,Edit(qa-report/**),Bash(agent-browser:*),Bash(gh issue view:*),…" \
  --json-schema "$(cat .github/prompts/qa-verdict.schema.json)" \
  --output-format stream-json --verbose | node claude-live-log.mjs

- uses: actions/upload-artifact@…   # qa-report/ with screenshots + video
```

</div>

<div class="qa-x mt-5">
  <template v-if="$clicks === 0"><span>Test brief</span>The prompt lives as a file in the repo: versioned and reviewable. The PR number is filled in.</template>
  <template v-else-if="$clicks === 1"><span>Timebox</span>It stops at $10. Like a timebox in exploratory testing. Real runs: $1 to $2.</template>
  <template v-else-if="$clicks === 2"><span>Permissions</span>It may operate the browser, read the ticket and write the report. Nothing else.</template>
  <template v-else-if="$clicks === 3"><span>Test result</span>The verdict comes as fixed JSON, not as prose. Why that matters: next slide.</template>
  <template v-else-if="$clicks === 4"><span>Test log</span>Every step shows up live in the Actions log. You watch the agent while it tests.</template>
  <template v-else><span>Evidence</span>Screenshots and video are attached to the run. Ready for the defect ticket.</template>
</div>

<style>
.qa-cmd .slidev-code { font-size: 15px !important; line-height: 1.6 !important; padding: 18px 20px !important; }
.qa-x { display: flex; align-items: center; gap: 16px; min-height: 64px; padding: 12px 18px; border-left: 4px solid #ff6bed; border-radius: 8px; background: rgba(255,107,237,.08); font-size: 20px; line-height: 1.35; }
.qa-x span { flex: none; font-size: 13px; font-weight: 800; text-transform: uppercase; letter-spacing: .05em; color: #ff6bed; width: 120px; }
</style>

<!--
TIME: 17:10–17:45 (35s)

- Before we see the whole workflow: the one line in which the agent runs. Translated for you.
- **Prompt as a file:** that is the test brief. It lives in the repo and is reviewed like code. `envsubst` fills in the PR number.
- [click] **Budget:** a $10 cap. That is your timebox. Real runs cost $1 to a bit over $2, depending on how far it explores.
- [click] **Allowed tools:** an allowlist. Browser, read the ticket, write the report. It may only write into the folder `qa-report/`. `curl` is left out on purpose.
- [click] **JSON schema:** the verdict comes in a fixed format. Only mention it, the next slide explains it.
- [click] **Live log:** every tool call is in the Actions log. Traceable like a test log.
- [click] **Artifact:** screenshots and video stay with the run. That is the evidence.
- SOURCE: otto-nuxt-shop `.github/workflows/claude-qa.yml` (shortened: `--model opus`, `--max-turns 300` and the full tool list are missing), `.github/prompts/qa-verdict.schema.json`
-->

---

# A quality gate needs <span class="text-[#ff6bed]">true or false</span>, not prose

<div class="urteil mt-6">
  <div class="urteil__col">
    <div class="urteil__h">Without a schema</div>
    <div class="urteil__prosa">“The scenarios mostly look good. There are, however, a few oddities in the discount calculation that someone should look at …”</div>
    <div class="urteil__out is-unklar">Red or green?</div>
  </div>
  <div v-click class="urteil__col is-now">
    <div class="urteil__h">With <code>--json-schema</code></div>
    <pre class="urteil__json">{ "passed": <b>false</b>,
  "verdict": "CRITICAL_BUGS",
  "summary": "3 bugs: useCoupon.ts:15" }</pre>
    <div class="urteil__out is-rot"><code>passed</code> is not <code>true</code> → check red</div>
  </div>
</div>

<div v-click class="mt-6 text-center text-xl">The way to the verdict is creative. The verdict is not: nobody enters <b class="text-[#ff6bed]">“almost passed”</b>.</div>

<style>
.urteil { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; }
.urteil__col { display: flex; flex-direction: column; gap: 14px; border: 1px solid rgba(255,255,255,.15); border-radius: 14px; padding: 16px 20px; background: rgba(255,255,255,.04); }
.urteil__col.is-now { border-color: #ff6bed; background: rgba(255,107,237,.06); }
.urteil__h { font-size: 12px; font-weight: 700; letter-spacing: .06em; text-transform: uppercase; opacity: .7; }
.urteil__col.is-now .urteil__h { color: #ff6bed; opacity: 1; }
.urteil__h code { font-size: 12px; text-transform: none; }
.urteil__prosa { flex: 1; font-size: 19px; line-height: 1.45; font-style: italic; color: #eaedf3; opacity: .85; }
.urteil__json { flex: 1; margin: 0; padding: 12px 14px; border-radius: 8px; background: rgba(0,0,0,.35); font-size: 15px; line-height: 1.6; color: #f3e6c4; white-space: pre-wrap; }
.urteil__json b { color: #ff8a8a; }
.urteil__out { padding: 8px 14px; border-radius: 8px; font-size: 17px; font-weight: 700; text-align: center; }
.urteil__out code { font-size: 15px; }
.urteil__out.is-unklar { border: 1px dashed rgba(255,255,255,.35); color: rgba(255,255,255,.7); }
.urteil__out.is-rot { background: rgba(255,77,77,.18); border: 1px solid #ff4d4d; color: #ff8a8a; }
</style>

<!--
TIME: 17:45–18:10 (25s)

- This is the trick that makes an agent work in a pipeline.
- Left: an LLM normally answers in prose. “Mostly looks good, a few oddities …” Is that green or red? A pipeline cannot do anything with that. (The text on the left is an example of mine, not a real run.)
- [click] Right: with `--json-schema` the agent has to deliver exactly this JSON, and Claude Code checks the format. `passed` is a boolean: true or false, nothing in between. After that it is a completely normal `if`: `passed` not true means `exit 1`, check red.
- [click] The way there is creative, the verdict is a fixed value. Like in Xray: passed, failed, blocked. Nobody enters “almost passed”.
- SOURCE: otto-nuxt-shop `.github/prompts/qa-verdict.schema.json` (commit d650193); JSON from run 42622982046 (summary translated from German)
-->

---

<script setup>
import { ref } from 'vue'
import { onSlideEnter, onSlideLeave } from '@slidev/client'

const ghLines = [
  ['13:10:16', '💬', 'First I look for the linked issue to learn the acceptance criteria.'],
  ['13:10:18', '🔧', 'gh issue view 2'],
  ['13:10:20', '💬', 'I load the skill verify-otto-shop to learn how to operate the shop.'],
  ['13:10:47', '🔧', 'agent-browser record start qa-report/video/qa-run.webm http://localhost:3100/p/1'],
  ['13:11:03', '💬', 'Scenario “Valid coupon”: I redeem SPAR10 and check the discount row and the total.'],
  ['13:11:25', '💬', 'I raise the quantity to 2 and see whether the discount grows to €1.79.'],
  ['13:11:32', '💬', 'I put the sofa into the cart, redeem SPAR10 …'],
  ['13:11:42', '💬', 'Now I remove only the sofa.'],
  ['13:11:50', '💬', 'Critical finding: total −€191.96. I reload to see whether the state stays.'],
  ['13:12:30', '💬', 'All evidence is in place. Now I write the report.'],
  ['13:13:00', '⚖️', 'passed: false · verdict: CRITICAL_BUGS · All 3 Gherkin scenarios pass. But …'],
  ['13:13:00', '', '=== success · passed: false · verdict: CRITICAL_BUGS · 115 turns · $1.17 · 2.8 min ==='],
]

const isPrint = typeof document !== 'undefined' && document.documentElement.classList.contains('slidev-print')
const shown = ref(isPrint ? ghLines.length : 0)
let timer
onSlideEnter(() => {
  if (isPrint) return
  shown.value = 0
  clearInterval(timer)
  timer = setInterval(() => {
    if (shown.value >= ghLines.length) return clearInterval(timer)
    shown.value++
  }, 900)
})
onSlideLeave(() => clearInterval(timer))
</script>

# Set the label, then <span class="text-[#ff6bed]">watch live</span>

<HamcrabPose class="absolute right-10 top-2" :size="130" :pose="shown >= ghLines.length - 1 ? 'popcorn-drop' : 'popcorn'" />

<img src="/pr-label-qa-verify.png" class="gh-label mt-2" alt="PR timeline: alexanderop added the qa-verify label, below it the comment by github-actions with the QA report" />

<div class="gh-log mt-3">
  <div class="gh-log__step"><span class="gh-log__caret">⌄</span> <span class="gh-log__spin" :class="{ done: shown >= ghLines.length }"></span> Run set -o pipefail <span class="gh-log__job">QA in the browser</span></div>
  <div v-for="(l, i) in ghLines.slice(0, shown)" :key="i" class="gh-log__line" :class="{ end: !l[1] }">
    <span class="gh-log__no">{{ i + 1 }}</span><span class="gh-log__ts">{{ l[0] }}</span><span>{{ l[1] }} {{ l[2] }}</span>
  </div>
</div>

<div class="mt-2 text-center text-sm opacity-60">Real run · github.com/alexanderop/otto-nuxt-shop/pull/1 · log shortened and translated from German, timestamps real</div>

<style>
.gh-label { width: 100%; height: 64px; object-fit: cover; object-position: top left; border-radius: 10px; border: 1px solid rgba(255,255,255,.18); }
.gh-log { height: 280px; overflow: hidden; border-radius: 10px; border: 1px solid #30363d; background: #0d1117; font-family: ui-monospace, SFMono-Regular, Menlo, monospace; font-size: 13px; line-height: 1.75; color: #e6edf3; display: flex; flex-direction: column; justify-content: flex-end; padding-bottom: 6px; }
.gh-log__step { margin-bottom: auto; padding: 8px 14px; border-bottom: 1px solid #30363d; font-family: -apple-system, 'Segoe UI', sans-serif; font-size: 14px; font-weight: 600; display: flex; align-items: center; gap: 8px; }
.gh-log__caret { color: #7d8590; }
.gh-log__job { margin-left: auto; font-weight: 400; color: #7d8590; font-size: 12px; }
.gh-log__spin { width: 12px; height: 12px; border-radius: 50%; border: 2px solid #d29922; border-right-color: transparent; animation: gh-spin .9s linear infinite; }
.gh-log__spin.done { animation: none; border: none; background: #3fb950; }
.gh-log__line { display: grid; grid-template-columns: 34px 78px 1fr; padding: 0 14px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.gh-log__line.end { color: #ff6bed; font-weight: 700; }
.gh-log__no { color: #6e7681; text-align: right; padding-right: 12px; }
.gh-log__ts { color: #7d8590; }
@keyframes gh-spin { to { transform: rotate(360deg); } }
</style>

<!--
TIME: 18:10–18:40 (30s)

- This is what it looks like in the real PR: I set the label `qa-verify`. That is all I do.
- Below, the Actions log. The lines come in live while the agent tests. Here in fast motion: just under 3 minutes in 11 seconds.
- You watch it think: read the issue, load the skill, scenarios, then exploratory. The sofa: −€191.96.
- At the end a verdict, not a prose text: `passed: false`, CRITICAL_BUGS. $1.17.
- Starts automatically when the slide appears, no click needed. The Hamcrab watches with popcorn and drops it at the verdict.
- The agent wrote these lines in German (the run used the German shop and the code SPAR10). I translated them one to one; tool calls and timestamps are unchanged.
- SOURCE: otto-nuxt-shop PR #1, Actions run 42622982046 of 9 Nov, job “QA im Browser” (log via `gh run view --log`)
-->

---

# What happens when someone sets the <span class="text-[#ff6bed]">label</span>?

<div class="text-sm opacity-60 -mt-2 mb-2">otto-nuxt-shop · .github/workflows/claude-qa.yml, three jobs</div>

<MermaidSteps :steps="['dev', 'qa ticket claude e1', 'evidence e2', 'report comment gatejob gate e3 e4', 'green red']" class="mt-2 flex justify-center">

```mermaid {scale: 0.58}
flowchart LR
  dev@{ shape: person, label: "Set label qa-verify on the PR" }
  subgraph qa["Job 1: QA · read only"]
    direction TB
    ticket@{ shape: doc, label: "Read the ticket" }
    claude@{ shape: browser, label: "Claude tests in the shop" }
    ticket --> claude
  end
  evidence@{ shape: folder, label: "Verdict passed + screenshots + video" }
  subgraph report["Job 2: Report · no AI, may write"]
    comment["💬 Comment with evidence"]
  end
  subgraph gatejob["Job 3: Merge gate · no AI"]
    direction TB
    gate{"passed?"}
    green["✅ Merge allowed"]
    red["❌ Merge blocked"]
    gate -->|true| green
    gate -->|false| red
  end
  dev e1@--> qa
  qa e2@--> evidence
  evidence e3@--> report
  report e4@--> gatejob
```

</MermaidSteps>

<!--
TIME: 18:40–19:25 (45s)

- The real workflow from the repo, as a picture. The YAML is in the backup.
- Someone sets the label `qa-verify` on the PR. Only then does the agent start. After that every new push to this PR is tested again.
- [click] **Job 1:** Claude first reads the ticket with the acceptance criteria, then it tests in a real browser. This job may **only read**: push nothing, comment nothing, merge nothing.
- [click] Out comes a fixed verdict, `passed` true or false, plus screenshots and video.
- [click] **Jobs 2 and 3, without AI:** job 2 posts the comment with the evidence. Only this job has write permissions. Job 3 is the merge gate and checks `passed`.
- [click] `true` → check green, merge allowed. `false` or no verdict → check red, merge blocked.
- The merge gate is a required check on `main` (branch protection). Red blocks the merge until a run passes for exactly this commit.
- SOURCE: otto-nuxt-shop `.github/workflows/claude-qa.yml` (commits d650193 and 18be32e: required check, re-run on push, separate gate job)
-->

---

# The QA agent comments <span class="text-[#ff6bed]">right in the PR</span>

<div class="prshot mt-3">
  <figure>
    <img class="is-contain" src="/pr-report-kopf.png" alt="Bot comment by github-actions (in German): verdict CRITICAL_BUGS, below it the video of the run as a GIF and the title QA report PR #1, SHOP-42, issue #2" />
    <figcaption><b>1</b> Verdict first, then the video of the run</figcaption>
  </figure>
  <figure>
    <img src="/pr-report-fund.png" alt="Finding F2 in the comment (in German): total becomes negative, severity critical. Repro in three steps, expected total 22.04 euros, actual total minus 191.96 euros, below it the screenshot as evidence" />
    <figcaption><b>2</b> Every finding: repro, expected, actual, evidence</figcaption>
  </figure>
</div>

<div class="mt-4 text-center text-lg">This time with a sofa: <b class="text-[#ff6bed]">total −€191.96</b>, quality gate red · <span class="opacity-70">115 turns · $1.17 · 2.8 min</span></div>

<div class="mt-1 text-center text-base">Different run, different path, <b>same root cause</b>.</div>

<div class="mt-1 text-center text-sm opacity-60">Real comment, in German · github.com/alexanderop/otto-nuxt-shop/pull/1</div>

<style>
.prshot { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
.prshot figure { margin: 0; }
.prshot img { width: 100%; height: 300px; object-fit: cover; object-position: top left; border-radius: 10px; border: 1px solid rgba(255,255,255,.18); }
.prshot img.is-contain { object-fit: contain; object-position: top; background: #0d1117; }
.prshot figcaption { margin-top: 8px; font-size: 14px; opacity: .8; }
.prshot figcaption b { display: inline-grid; place-items: center; width: 20px; height: 20px; border-radius: 50%; background: #ff6bed; color: #1a1d29; font-size: 12px; margin-right: 6px; }
</style>

<!--
TIME: 19:25–19:55 (30s)

- This is what the result looks like in the real PR. Not a mockup, this is PR #1 in the Otto clone.
- This is the comment for the run whose log you just saw.
- Left, the head: the first line is the verdict (“Urteil”), CRITICAL_BUGS. Right below it the video of the run plays as a GIF. A reviewer knows after ten seconds what is going on.
- Right, one finding, F2: repro in three steps, expected (“Erwartet”) and actual (“Ist”), below it the screenshot as evidence. Expected €22.04, actual −€191.96. I do not have to click anything again to believe what it says.
- Posted by the report job, not by the agent. The check is red. It is a required check on `main`, so the merge is blocked.
- **Different run, different path, same root cause:** locally it was five findings with mascara and lemon. Here it is three findings, with a sofa for €2,139.99. Discount redeemed with the sofa in the cart, sofa out, discount stays. Agents are not deterministic. Both runs find the root cause: the fixed discount amount in the cookie.
- A bit over one dollar, just under three minutes. The goal picture at the start shows a later run of the same PR (run 42817194078, 10 Nov), with different items and the same root cause.
- **The screenshots are in German:** the run happened before the shop had an English UI. TODO if wanted: run the workflow once against the English shop and swap both pictures.
- SOURCE: github.com/alexanderop/otto-nuxt-shop/pull/1, bot comment of 9 Nov (run 42622982046)
-->

---

# Teaser: ticket moves to “In QA”, and the <span class="text-[#ff6bed]">agent gets going</span>

<div class="mt-4">

<IconCards flow :items="[
  { icon: '/jira/ticket.webp', title: 'Dev moves the ticket', sub: 'to “In QA”', tag: 'Jira' },
  { icon: '/jira/trigger.webp', title: 'Jira sends a signal', sub: 'the status change triggers', tag: 'Jira Automation' },
  { icon: '/jira/workflow.webp', title: 'Workflow starts', sub: 'the same as with the label', tag: 'GitHub Actions' },
  { icon: '/jira/agent.webp', title: 'Agent reads & tests', sub: 'ticket from Jira, then browser', tag: 'Claude Code', accent: true },
  { icon: '/jira/funde.webp', title: 'Findings into the ticket', sub: 'comment + screenshots', tag: 'Jira' },
]" no-clicks />

</div>

<div class="mt-8 text-center text-xl opacity-80">The same workflow. Only the <b>trigger</b> is now the ticket status.</div>

<div class="mt-3 text-center opacity-70">All building blocks are documented. I have not built it yet.</div>

<!--
TIME: 19:55–20:25 (30s)

- One step further: no more label. The status in the ticket is the trigger.
- A dev moves the ticket to “In QA”.
- Jira Automation fires (“Work item transitioned”) and sends a web request to GitHub.
- GitHub starts the same QA workflow through `repository_dispatch`. Ticket key in the `client_payload`.
- Claude reads the ticket directly from Jira, through the Atlassian Rovo MCP server, and tests in the browser.
- The findings with screenshots land as a comment and attachment in the ticket, through the Jira REST API. On CRITICAL_BUGS back to “In Progress”.
- If asked, the three building blocks: Jira Automation trigger “Work item transitioned” with “Send web request”, in the workflow `on: repository_dispatch` instead of the label, the way back through the Jira REST API.
- **Say it honestly:** this is a teaser. All parts exist and are documented, but I have not built the chain yet.
- SOURCE: research/wiki/jira-cloud-agent.md
-->

---

# The agent verifies. Whether we want it is decided by a <span class="text-[#ff6bed]">human</span>.

<div class="grenze mt-8">
  <div class="grenze__col">
    <div class="grenze__h">Verification · the QA agent</div>
    <div class="grenze__item"><img src="/icons/szenario-ok.webp" alt="Clipboard with a check mark" /><div><b>Does it work the way we wanted?</b><small>every scenario from the ticket, with evidence</small></div></div>
    <div class="grenze__item"><img src="/icons/explorativ.webp" alt="Compass with magnifying glass and bug" /><div><b>What did we not think of?</b><small>exploratory: cases nobody wrote down</small></div></div>
  </div>
  <div class="grenze__col is-human">
    <div class="grenze__h">Validation + sign-off · the human</div>
    <div class="grenze__item"><img src="/icons/shippen.webp" alt="Ship and a hand on a button" /><div><b>Do we want to ship this at all?</b><small>sign-off and product decision</small></div></div>
    <div class="grenze__item"><img src="/icons/gefuehl.webp" alt="Heart with a thumbs up" /><div><b>Does it feel good?</b><small>taste cannot be written as Gherkin</small></div></div>
    <div class="grenze__item"><img src="/icons/fund-pruefen.webp" alt="Eye in a magnifying glass over a bug" /><div><b>Is the critical finding real?</b><small>on CRITICAL_BUGS someone takes a look: false positive?</small></div></div>
  </div>
</div>

<div class="mt-8 text-center text-lg opacity-70">My guess: later the product adapts itself based on <b class="text-[#ff6bed]">KPIs</b> from real usage.</div>

<style>
.grenze { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
.grenze__col { border: 1px solid rgba(255,255,255,.15); border-radius: 12px; padding: 16px 18px; background: rgba(255,255,255,.04); }
.grenze__col.is-human { border-color: #ff6bed; background: rgba(255,107,237,.08); }
.grenze__h { font-size: 12px; font-weight: 700; text-transform: uppercase; letter-spacing: .06em; color: #ff6bed; margin-bottom: 10px; }
.grenze__item { display: flex; gap: 12px; align-items: flex-start; padding: 8px 0; }
.grenze__item > img { flex: none; width: 54px; height: 54px; margin-top: -6px; }
.grenze__item b { display: block; font-size: 17px; color: #eaedf3; }
.grenze__item small { display: block; font-size: 13px; opacity: .65; margin-top: 2px; }
</style>

<!--
TIME: 20:25–21:40 (75s)

- The one problem I see. Left **verification**, right **validation**. The QA agent tells me two things: does the feature work the way we wanted? And through exploratory testing: what did we not think of?
- What it does not tell me: do we want to ship this at all? Does it feel good?
- For that we still need a human. I say: luckily. That person confirms at the end and decides about the merge.
- On CRITICAL_BUGS someone takes a look before it escalates. An agent can be wrong too: a **false positive** otherwise costs a developer half a day. And if the criteria are unclear, the agent should ask instead of guessing.
- **Outlook, my guess:** in the future we will probably work more with KPIs. The product adapts automatically, depending on how end users use it. Then it improves itself. But we are not there yet.
- If asked, limits from my runs: not deterministic (two runs, two paths), cost ($3.37 skill, $0.90 feature, $1.00 QA run), fork PRs get no secrets, 4.2 % recall in QA-Bench. TODO: put the QA-Bench source into research/.
-->
---
layout: cover
background: /bild-rolle.jpeg
---

<div class="w-[36%] text-left">

<h1 class="!text-[2.6rem] !leading-tight">“If an agent can test, am <span class="text-[#ff6bed]">I</span> still needed?”</h1>

</div>

<!--
TIME: 21:40–22:10 (30s)

- **Callback:** “At the beginning I promised you an answer. Here it is.”
- Everyone in this room is asking themselves this question right now. So I say it out loud.
- [Ask for hands] “Hands up if you have asked yourself this before.” Raise my own hand.
- Leave a short pause, look into the room.
- My answer: yes. But the role changes.
-->

---

# That is exactly what the agent <span class="text-[#ff6bed]">cannot</span> do

<div class="keynote mt-6">
  <figure>
    <div class="keynote__shot">
      <img src="/keynote-richard.jpg" alt="Slide from Richard Seidl's keynote, in German: What we as testers are very good at. Asking, doubting, connecting." />
      <div v-click class="keynote__fix"><i></i><b>Humans</b></div>
    </div>
    <figcaption>Richard Seidl, keynote at QS-Tag Frankfurt 2026. The slide says: “What we testers are very good at: asking, doubting, connecting.”</figcaption>
  </figure>
  <div class="keynote__map">
    <div><b>Asking</b><span>Acceptance criteria and charter. Without them the agent has no verdict.</span></div>
    <div><b>Doubting</b><span>Is the critical finding real? Do we want to ship this?</span></div>
    <div><b>Connecting</b><span>Domain, testing and technology in one person.</span></div>
  </div>
</div>

<style>
.keynote { display: grid; grid-template-columns: 1.15fr 1fr; gap: 32px; align-items: center; }
.keynote figure { margin: 0; }
.keynote img { width: 100%; border-radius: 10px; border: 1px solid rgba(255,255,255,.15); }
.keynote__shot { position: relative; }
.keynote__shot img { display: block; }
.keynote__fix i { position: absolute; left: 52.5%; top: 28%; width: 22.5%; height: 5px; border-radius: 3px; background: #ff6bed; transform: rotate(-4deg); }
.keynote__fix b { position: absolute; left: 50%; top: 7%; font-size: 30px; line-height: 1; color: #ff6bed; transform: rotate(-4deg); text-shadow: 0 2px 8px rgba(0,0,0,.6); }
.keynote figcaption { margin-top: 8px; font-size: 13px; opacity: .6; }
.keynote__map { display: flex; flex-direction: column; gap: 22px; }
.keynote__map b { display: block; font-size: 26px; color: #ff6bed; }
.keynote__map span { display: block; font-size: 18px; opacity: .85; margin-top: 2px; }
</style>

<!--
TIME: 22:10–22:40 (30s)

- “I first gave this talk at QS-Tag in Frankfurt. That morning Richard Seidl showed this slide in his keynote. I took a photo, because it hits my answer better than my own slide.”
- Translate it: “Was wir als Tester sehr gut können: Fragen, Zweifeln, Verbinden” = “What we testers are very good at: asking, doubting, connecting”.
- [click] “I would change one word.” Strike out “Tester”, write **Humans** above it. “Not only testers can do this. We all can, if we take the time for it.”
- **Asking:** the agent only tests as well as the acceptance criteria and the charter. You write those.
- **Doubting:** the agent reports CRITICAL_BUGS. Whether that is right and whether we ship anyway is decided by someone who can doubt.
- **Connecting:** whoever brings domain knowledge, testing and technology together builds such pipelines. That leads to the next slide.
- “Exactly these three things the agent cannot do. The rest I am happy to take off your hands.”
- SOURCE: Richard Seidl, keynote “Testen ist People Business. Erst recht mit KI.” (“Testing is people business. Even more so with AI.”), Software-QS-Tag, 11 Nov 2026, 09:15 (qs-tag.de/programm/11-11-2026). Photo by me.
-->

---

# From <span class="text-[#ff6bed]">T-shaped</span> to <span class="text-[#ff6bed]">O-shaped</span>

<div class="shapes mt-4">
  <div class="shape">
    <div class="shape__tag">Before AI</div>
    <img src="/o-shaped/t-shaped.webp" class="shape__img" alt="T shape: a person on a T, at the top code, design and product, a deep pink stem for quality" />
    <div class="shape__name">T-shaped</div>
    <div class="shape__sub">A bit of breadth, a lot of depth in <b>one</b> discipline. That is what you were hired for.</div>
  </div>
  <div class="shape">
    <div class="shape__tag is-now">With AI</div>
    <img src="/o-shaped/o-shaped.webp" class="shape__img" alt="O shape: a person with an AI spark inside a ring of quality (pink), code, design and product" />
    <div class="shape__name">O-shaped</div>
    <div class="shape__sub">The strength changes with the problem. Your base stays <b>quality</b>.</div>
  </div>
</div>

<div class="mt-4 text-center text-sm opacity-50">Term: Ismail Amla, “O-Shaped People: How AI Is Blowing Up Titles”, LinkedIn, Aug 2026</div>

<style>
.shapes { display: grid; grid-template-columns: 1fr 1fr; gap: 28px; }
.shape { border: 1px solid rgba(255,255,255,.15); border-radius: 14px; padding: 12px 18px 14px; background: rgba(255,255,255,.04); text-align: center; position: relative; }
.shape__tag { position: absolute; top: 12px; left: 14px; font-size: 11px; font-weight: 700; letter-spacing: .06em; text-transform: uppercase; opacity: .6; }
.shape__tag.is-now { color: #ff6bed; opacity: 1; }
.shape__img { display: block; height: 210px; margin: 14px auto 4px; }
.shape__name { font-size: 22px; font-weight: 700; color: #eaedf3; }
.shape__sub { font-size: 14px; opacity: .75; margin-top: 2px; }
.shape__sub b { color: #ff6bed; }
</style>

<!--
TIME: 22:40–23:25 (45s)

- Left: this is how we hired before AI. **T-shaped**: a bit of code, design, product, and deep in one box. For you: quality.
- Right: with AI people become **O-shaped**. Ismail Amla calls it that: round and flexible, the strongest strength changes with the problem. With AI you can switch into another discipline for a moment and back again.
- Boris Cherny (creator of Claude Code) says something similar at 42:46: the roles overlap by about 50 percent, some people have specialities.
- **My twist for the audience:** you can now pitch in everywhere. But your base stays quality: assessing risks, writing good criteria, knowing where things break. Amla says it himself: specialists become the ones who check work from other areas and make it stronger.
- SOURCE: research/raw/2026-08-12-o-shaped-people.md; research/wiki/rollen-verschmelzen.md
-->

---

# Three things for <span class="text-[#ff6bed]">Monday</span>

<div class="mt-10">

<IconCards :columns="3" size="lg" :items="[
  { icon: '/icons/issue.webp', title: 'Acceptance criteria', sub: 'as Gherkin that an agent can check' },
  { icon: '/icons/feature-map.webp', title: 'Browser + feature map', sub: 'one command, one afternoon' },
  { icon: '/icons/explorativ.webp', title: 'Explore', sub: 'with a charter, e.g. accessibility', accent: true },
]" no-clicks />

</div>

<!--
TIME: 23:25–23:55 (30s)

- Criteria first. Without good criteria no good verdict. That gives you the most.
- Browser and feature map: `npm i -g agent-browser` or Playwright CLI, then `/create-verification-skill`. One afternoon of work. After that you maintain the map like test documentation.
- Any test can confirm. The value comes from exploring. Give the agent a **charter** for what to watch out for along the way. For us accessibility: can you reach everything with Tab? Does every field have a label?
- TODO before the talk: push the English shop (`main` and `feat/gutschein`) of otto-nuxt-shop, otherwise the audience does not see the English ticket and skill.
-->

---
layout: center
class: text-center
---

# Thank you! <span class="text-[#ff6bed]">Questions?</span>

<div class="text-xl opacity-80">Please rate my talk. <span class="text-[#ff6bed]">But only if it was good.</span></div>

<div class="finale mt-6">
  <DancingHamcrab />
  <div class="finale__qr">
    <img src="/qr-slides.png" alt="QR code to the slides: alexanderop.github.io/ai-agents-as-qa-engineer" />
    <div class="mt-3 text-xl font-bold">The slides</div>
    <div class="text-sm opacity-60">alexanderop.github.io/ai-agents-as-qa-engineer</div>
    <div class="mt-4 text-base opacity-70">Repo, blog posts and sources are linked in there.</div>
  </div>
</div>

<style>
.finale { display: grid; grid-template-columns: 1fr 1fr; align-items: center; justify-items: center; gap: 32px; }
.finale__qr { display: flex; flex-direction: column; align-items: center; }
.finale__qr img { width: 260px; height: 260px; border-radius: 8px; }
</style>

<!--
TIME: 23:55 + Q&A (6:05 buffer until 30:00)

- This slide stays up during the questions. The Hamcrab keeps dancing, on the right the QR code to the slides. Repo and sources are linked in the slides.
- If nobody asks: “Who had their hand up at the second question earlier? What do you let the agent test with?”
- The QR code points to alexanderop.github.io/ai-agents-as-qa-engineer. That URL only works once this repo is on GitHub under that name with Pages enabled.
-->

---
layout: statement
---

# Backup

<!--
Only show from here on when asked.
-->

---
zoom: 0.72
---

# The real <span class="text-[#ff6bed]">workflow</span>

<div class="text-sm opacity-60 -mt-2 mb-2">otto-nuxt-shop · .github/workflows/claude-qa.yml (shortened)</div>

```yaml
on:
  pull_request:
    types: [opened, reopened, synchronize, labeled]
jobs:
  qa:                      # Claude tests, read access only
    if: contains(github.event.pull_request.labels.*.name, 'qa-verify')
    permissions: { contents: read, pull-requests: read, issues: read }
    steps:
      - run: .claude/skills/verify-otto-shop/scripts/otto-verify.sh launch
      - env:
          CLAUDE_CODE_OAUTH_TOKEN: ${{ secrets.CLAUDE_CODE_OAUTH_TOKEN }}
        run: |
          claude -p "$(envsubst < .github/prompts/qa.md)" \
            --max-budget-usd 10 \
            --allowedTools "Skill,Read,Edit(qa-report/**),Bash(agent-browser:*),Bash(gh issue view:*),…" \
            --json-schema "$(cat .github/prompts/qa-verdict.schema.json)" \
            --output-format stream-json --verbose | node claude-live-log.mjs
      - uses: actions/upload-artifact@…   # qa-report/ with screenshots + video
  report:                  # without Claude: may write
    needs: qa
    permissions: { contents: write, pull-requests: write }
    steps:
      - run: |   # screenshots onto branch qa-evidence, embed image links
          gh pr comment "$PR_NUMBER" --body-file comment.md
  gate:                    # merge gate, required check on main
    needs: [qa, report]
    steps:
      - run: if [ "$PASSED" != "true" ]; then exit 1; fi
```

<!--
BACKUP (for questions about the code)

- This is the real workflow from the repo, shortened. It really ran several times on 7 Nov.
- **Trigger:** PR opened, new push or label set. But it only tests when the PR carries the label `qa-verify`.
- **Job qa:** only with the label qa-verify, and **read access only**. The agent cannot push anything and cannot comment.
- **Start the shop** with the script from the verification skill. No separate CI setup.
- **Claude Code through my subscription** (`claude setup-token`), no API key.
- The evidence goes out as an artifact.
- **Job report, without Claude:** it puts the screenshots on their own branch so they are visible in the comment, and posts the report. Only this job gets write permissions.
- **Job gate:** the quality gate. `passed` must be `true`, otherwise the check is red. It is a required check on `main`: red blocks the merge.
- Also in the real file: actions pinned by SHA, zizmor in pedantic mode without findings.
- SOURCE: otto-nuxt-shop commits 25d6d59 (live log, budget), e2f5950 (report job, screenshots) and 18be32e (gate job, required check, re-run on push); blog posts “Building an AI QA Engineer…” and “How to Use Claude Code as an AI QA Tester…”
-->

---

# Agent Browser <span class="text-[#ff6bed]">under the hood</span>

```mermaid {scale: 0.65}
flowchart LR
  A@{ shape: rounded, label: "Claude Code" } -->|"Bash"| B@{ shape: console, label: "CLI" }
  B -->|"Socket"| C@{ shape: rounded, label: "Daemon (Rust)" }
  C -->|"CDP"| D@{ shape: browser, label: "Chrome" }
```

<div class="cdp mt-2"><b>CDP</b> = Chrome DevTools Protocol. The interface your DevTools (F12) also use to talk to Chrome. Playwright and Puppeteer use it too. Agent Browser speaks it <b>directly</b>.</div>

<div class="hood mt-4">
  <div class="hood__step">
    <div class="hood__h"><code>snapshot</code></div>
    <ol>
      <li>Fetches the <b>accessibility tree</b> from Chrome</li>
      <li>Only clickable roles (button, link, textbox …) get a ref <code>e1</code>, <code>e2</code></li>
      <li>Every ref remembers the internal node ID in the browser</li>
    </ol>
  </div>
  <div class="hood__step">
    <div class="hood__h"><code>click @e2</code></div>
    <ol>
      <li>Resolve the ref to the node ID, scroll the element into view</li>
      <li>Measure the box, compute the <b>centre</b>, check that nothing covers it</li>
      <li>Real mouse events: move, press, release</li>
    </ol>
  </div>
</div>

<div class="mt-3 text-center text-sm opacity-60">No Playwright, no Node in the daemon. If no command arrives for 1 hour, the daemon shuts itself down.</div>

<style>
.cdp { border: 1px solid #ff6bed; background: rgba(255,107,237,.08); border-radius: 10px; padding: 8px 14px; font-size: 14px; }
.cdp b { color: #ff6bed; }
.hood { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
.hood__step { border: 1px solid rgba(255,255,255,.15); border-radius: 12px; padding: 12px 16px; background: rgba(255,255,255,.04); }
.hood__h { margin-bottom: 6px; }
.hood ol { margin: 0; padding-left: 18px; font-size: 14px; line-height: 1.55; }
.hood li { margin: 2px 0; }
</style>

<!--
Only when asked. “How does Agent Browser actually work?”

- Three parts: Claude Code calls the CLI through Bash. The CLI talks to a daemon over a Unix socket. The daemon controls Chrome directly through the Chrome DevTools Protocol (CDP), the same protocol the DevTools use.
- The daemon starts with the first command and keeps running. That is why every further command is fast, and the browser keeps cookies and tabs between commands. After one hour without a command it cleans itself up.
- **CDP.** Programs control Chrome from the outside through the Chrome DevTools Protocol. When you press F12, the DevTools talk to the page over exactly this protocol. Playwright and Puppeteer build on it; Agent Browser leaves out the layer in between and sends the CDP commands itself. Everything on this slide (fetch the tree, measure the box, click the mouse) is a single CDP command each.
- **snapshot:** CDP command `Accessibility.getFullAXTree`. That is the same tree a screen reader reads. Interactive roles get refs `e1`, `e2`; every ref points to the `backendNodeId` of the element. That is why it works well on accessible pages and badly on pages without labels.
- **click @e2:** it resolves the ref to the `backendNodeId`, measures the box with `DOM.getBoxModel` and computes the centre point. Before that it checks whether another element covers it (e.g. a cookie banner). Then `Input.dispatchMouseEvent`: mouseMoved, mousePressed, mouseReleased. For the page that is a real click.
- Playwright is not involved. Chrome comes from “Chrome for Testing”, the rest is Rust.
- SOURCE: github.com/vercel-labs/agent-browser @4b0e9f0, README “Architecture”; cli/src/native/snapshot.rs (INTERACTIVE_ROLES, getFullAXTree), cli/src/native/element.rs (resolve_element_center, DOM.getBoxModel), cli/src/native/interaction.rs (click, dispatch_click). Installed version 0.38.2.
-->

---

# <span class="text-[#ff6bed]">Sources</span>

<div class="src">
  <div>
    <h3>Quotes &amp; articles</h3>
    <ul>
      <li>Boris Cherny on Lenny's Podcast, 19 Feb 2026 (41:25, 42:46, 43:06)<br><span>youtube.com/watch?v=We7BZVKbCVw</span></li>
      <li>Cat Wu: “Product management on the AI exponential”<br><span>claude.com/resources/articles/product-management-on-the-ai-exponential</span></li>
      <li>Ismail Amla: “O-Shaped People: How AI Is Blowing Up Titles”, LinkedIn, 12 Aug 2026</li>
      <li>Richard Seidl: “Testen ist People Business. Erst recht mit KI.”, keynote, Software-QS-Tag, 11 Nov 2026<br><span>qs-tag.de/programm/11-11-2026</span></li>
    </ul>
    <h3>Tools</h3>
    <ul>
      <li>Agent Browser (v0.38.2)<br><span>github.com/vercel-labs/agent-browser</span></li>
      <li>pstack, <code>/create-verification-skill</code> (v0.15.36)<br><span>github.com/cursor/plugins/tree/main/pstack · x.com/poteto</span></li>
      <li>Atlassian Remote MCP &amp; Jira Automation<br><span>support.atlassian.com/rovo · support.atlassian.com/cloud-automation</span></li>
    </ul>
  </div>
  <div>
    <h3>Demo</h3>
    <ul>
      <li>Otto clone with skill, workflow, QA report<br><span>github.com/alexanderop/otto-nuxt-shop</span></li>
      <li>Real QA comment in the PR (German)<br><span>github.com/alexanderop/otto-nuxt-shop/pull/1</span></li>
    </ul>
    <h3>My blog · alexop.dev</h3>
    <ul>
      <li>The Factory Must Grow<br><span>alexop.dev/posts/the-factory-must-grow-ai-moved-the-bottleneck</span></li>
      <li>Delivery Factory (playable)<br><span>alexop.dev/lab/delivery-factory</span></li>
      <li>Building an AI QA Engineer with Claude Code and Playwright MCP<br><span>alexop.dev/posts/building_ai_qa_engineer_claude_code_playwright</span></li>
      <li>How to Use Claude Code as an AI QA Tester with Agent Browser<br><span>alexop.dev/posts/automated-qa-claude-code-agent-browser-cli-github-actions</span></li>
      <li>Playwright CLI vs MCP<br><span>alexop.dev/notes/playwright-cli-vs-mcp</span></li>
    </ul>
  </div>
</div>

<style>
.src { display: grid; grid-template-columns: 1fr 1.15fr; gap: 28px; margin-top: -8px; }
.src h3 { color: #ff6bed; font-size: 13px; margin: 8px 0 2px; text-transform: uppercase; letter-spacing: .05em; }
.src ul { margin: 0; padding-left: 14px; font-size: 12px; line-height: 1.3; }
.src li { margin: 2px 0; }
.src li span { opacity: .55; font-size: 10.5px; white-space: nowrap; }
</style>

<!--
Last slide. All sources from the talk in one place. Whoever has the link to the slides (QR code on the thank-you slide) finds them here.
- Still missing: the author of the funnel diagram (see the TODO on the funnel slide).
-->
