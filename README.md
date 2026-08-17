# Claude Certified Architect – Foundations: A Simple Prep Guide 🇮🇳

A no-nonsense, beginner-friendly guide to help you clear the **Claude Certified Architect – Foundations** exam by Anthropic — written for people preparing in India, with notes also available in Hindi and Tamil.

> I cleared this certification myself. This repo is my attempt to make the path a little shorter for the next person. It's not official Anthropic material — just a simple map of what to study and in what order.

**Languages:** [English](README.md) · [हिन्दी](guides/guide_hi.md) · [தமிழ்](guides/guide_ta.md)

---

## What is this certification?

The Claude Certified Architect – Foundations credential is for people who design and build applications with Claude — using the **Claude API**, **Claude Code**, the **Agent SDK**, and **MCP (Model Context Protocol)**. It's not a coding trivia test — it checks whether you can make sound *architecture* decisions: when to use an agent vs. a simple API call, how to design tools, how to keep systems reliable.

## Who is this guide for?

- Engineers who have already built something with Claude (even a small side project) and want to formalize that knowledge.
- Folks who prefer a checklist over a 6-hour video course.
- Anyone who wants a quick, honest view of where the exam actually focuses.

If you haven't built *anything* with Claude yet, do that first — a tiny project teaches more than passively reading this guide.

---

## Step 1 — Take the free Anthropic Academy courses

You don't need a paid bootcamp. Anthropic's own courses cover the syllabus. Go through these in order:

| # | Course | Focus |
|---|--------|-------|
| 1 | AI Fluency: Framework & Foundations | How to think about working *with* AI, not just prompting it |
| 2 | Claude 101 | Product basics — quick one |
| 3 | Building with the Claude API | The core of the exam: tool use, structured output, agent design |
| 4 | Claude Code in Action | Running real, trustworthy Claude Code sessions |
| 5 | Introduction to Model Context Protocol | MCP building blocks: tools, resources, prompts |
| 6 | Introduction to Agent Skills | Skills — often under-studied, comes up in the exam |

Optional but useful if your org uses a specific cloud: *Claude with Amazon Bedrock*, *Claude with Google Cloud's Vertex AI*. Skip these if you don't touch that cloud day-to-day.

Access request for the course/exam portal is via Anthropic's Skilljar site — search "Claude Certified Architect Foundations" once you have a work/partner email registered.

---

## Step 2 — Know roughly where the exam puts its weight

These are rough areas to plan your time around, not an official published spec — always cross-check against the current exam guide when you register:

| Area | Rough share |
|---|---|
| Agentic architecture & orchestration (when to use agent vs. workflow vs. single call) | Largest |
| Claude Code setup & workflows (CLAUDE.md, rules, hooks, skills) | Large |
| Prompt engineering & structured output (`tool_choice`, JSON schemas) | Large |
| Tool design & MCP (tools vs. resources vs. prompts) | Medium |
| Context management & reliability (resumability, token budgets) | Medium |

**Rule of thumb the exam rewards again and again:** pick the *simplest* pattern that solves the problem. Augmented single call → Workflow → Agent, in that order of preference. Don't reach for a multi-agent system when one tool call would do.

---

## Step 3 — Build one small thing before you sit the exam

You don't need anything fancy. A weekend project is enough:

- A **coordinator** that delegates to 2–3 **worker** sub-agents (e.g., a search agent + a summarizer agent).
- One tool exposed via **MCP**, so you feel the difference between a *tool* (model calls it) and a *resource* (you hand content to the model directly).
- One place where you deliberately **force structured output** using `tool_choice`, so you see why "asking nicely" in a prompt isn't the same as a guarantee.

Building this once will make several exam questions feel familiar instead of theoretical.

---

## Step 4 — Where most people actually lose marks

Based on shared experience across people who've taken this exam, these are the classic traps:

1. **Required fields that shouldn't be required.** If a field might genuinely be absent from the input, mark it optional / nullable. A required field with no matching data pressures the model to invent something.
2. **Relying on prompt wording for structured output.** A well-written instruction is a *request*. `tool_choice` (forcing a specific tool call) is a *guarantee*. If a broken format would break your downstream system, force it — don't ask politely.
3. **Reaching for an agent when a workflow (or a single call) would do.** More autonomy = less predictability. The exam rewards restraint.
4. **Confusing MCP tools and resources.** Not everything the model needs should be a "tool call" — sometimes just handing over the content as a resource is cheaper and more reliable.
5. **Ignoring resumability.** If your multi-step pipeline can't pick up from where it failed, every failure costs you the whole run — and that's a real architecture flaw, not a minor detail.

---

## Step 5 — Exam day tips

- Expect **two plausible-looking answers** per question. You're usually picking the better trade-off, not spotting an obviously wrong option. Read for the *constraint* stated in the question (compliance, latency, cost, team size) — that constraint decides the answer.
- Don't skip the "boring" topics you think you already know well from real work — that's often where blind spots hide.
- Keep a mental checklist: *Could this be a single call? Could this be a workflow? Do I really need an agent?*

---

## FAQ

**Do I need a paid course?**
No — the free Anthropic Academy courses above cover the syllabus.

**Is this an official Anthropic resource?**
No. This is a community guide written after personally clearing the exam. Always verify current exam scope, pricing, and access on Anthropic's official pages.

**I don't read English comfortably — is there help?**
Yes — see the Hindi and Tamil versions linked at the top. More Indian languages are welcome via PR (Telugu, Kannada, Malayalam, Marathi, Bengali, etc.).

---

## Contributing

Found an error, or want to add a regional language guide? PRs welcome:

- Add `guides/guide_<language-code>.md` following the structure of the existing guides.
- Keep the tone simple — short sentences, no jargon left unexplained.
- Don't copy content from other prep guides or blogs — write it in your own words, based on your own understanding/experience.

## License

MIT — use, adapt, and share freely. See [LICENSE](LICENSE).
