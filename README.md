# Claude Certified Architect – Foundations: A Simple Prep Guide 🇮🇳

[![Credly Verified Badge](https://img.shields.io/badge/Credly-Verified%20Badge-orange?logo=credly&logoColor=white)](https://www.credly.com/badges/b0a2b60a-f073-49f5-b106-ce33e8cf8aa4/public_url)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Languages](https://img.shields.io/badge/Languages-EN%20%7C%20HI%20%7C%20TA-brightgreen)](#what-is-this-certification)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

A no-nonsense, beginner-friendly guide to help you clear the **Claude Certified Architect – Foundations** exam by Anthropic — written for people preparing in India, with notes also available in Hindi and Tamil.

> I cleared this certification myself — [view my verified Credly badge ↗](https://www.credly.com/badges/b0a2b60a-f073-49f5-b106-ce33e8cf8aa4/public_url). This repo is my attempt to make the path a little shorter for the next person. It's not official Anthropic material — just a simple map of what to study and in what order.

<a href="https://www.credly.com/badges/b0a2b60a-f073-49f5-b106-ce33e8cf8aa4/public_url">
  <img src="https://images.credly.com/images/f2040db3-3904-4240-8966-e87b1510bea0/linkedin_thumb_blob" alt="Claude Certified Architect - Foundations, issued by Anthropic" width="150">
</a>

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
| 1 | [AI Fluency: Framework & Foundations](https://anthropic.skilljar.com/ai-fluency-framework-foundations) | How to think about working *with* AI, not just prompting it |
| 2 | [Claude 101](https://anthropic.skilljar.com/claude-101) | Product basics — quick one |
| 3 | [Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api) | The core of the exam: tool use, structured output, agent design |
| 4 | [Claude Code in Action](https://anthropic.skilljar.com/claude-code-in-action) | Running real, trustworthy Claude Code sessions |
| 5 | [Introduction to Model Context Protocol](https://anthropic.skilljar.com/introduction-to-model-context-protocol) | MCP building blocks: tools, resources, prompts |
| 6 | [Introduction to Agent Skills](https://anthropic.skilljar.com/introduction-to-agent-skills) | Skills — often under-studied, comes up in the exam |

Optional but useful if your org uses a specific cloud: [Claude with Amazon Bedrock](https://anthropic.skilljar.com/claude-in-amazon-bedrock), [Claude with Google Cloud's Vertex AI](https://anthropic.skilljar.com/claude-with-google-vertex). Skip these if you don't touch that cloud day-to-day.

**Access request for the course/exam portal:** [anthropic.skilljar.com — Claude Certified Architect Foundations access request](https://anthropic.skilljar.com/claude-certified-architect-foundations-access-request) (needs a work/partner email).

---

## Step 2 — Know exactly where the exam puts its weight

This is the official breakdown from Anthropic's own exam guide (v0.1, Feb 2025) — always cross-check against the current version when you register, since these numbers can change:

| Domain | Weight |
|---|---|
| 1. Agentic Architecture & Orchestration (agentic loops, coordinator/subagent patterns, hooks) | 27% |
| 2. Tool Design & MCP Integration (tool interfaces, error responses, tool_choice) | 18% |
| 3. Claude Code Configuration & Workflows (CLAUDE.md, rules, skills, CI/CD) | 20% |
| 4. Prompt Engineering & Structured Output (few-shot, JSON schemas, batch processing) | 20% |
| 5. Context Management & Reliability (long-context handling, escalation, error propagation) | 15% |

The exam draws 4 scenarios (picked at random) out of a published set of 6: customer support agent, Claude Code for dev productivity, multi-agent research system, developer productivity tooling, Claude Code in CI/CD, and structured data extraction. All questions are single-answer multiple choice (4 options); there's no penalty for guessing.

**Rule of thumb the exam rewards again and again:** pick the *simplest* pattern that solves the problem. Augmented single call → Workflow → Agent, in that order of preference. Don't reach for a multi-agent system when one tool call would do.

**Explicitly out of scope** (per the official guide) — don't burn prep time here: fine-tuning, API billing/auth/rate limits, MCP server hosting/infra, model internals/RLHF, vision, computer use, streaming/SSE, and cloud-provider-specific configuration.

**Read these to back up the table above:**
- [Official exam guide (PDF)](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1773274827%2FClaude+Certified+Architect+%E2%80%93+Foundations+Certification+Exam+Guide.pdf) — the actual syllabus/domain breakdown, always cross-check against this
- [Building Effective Agents](https://www.anthropic.com/research/building-effective-agents) — Anthropic's own agent vs. workflow reasoning, the backbone of the "largest" row above
- [Claude Code docs](https://code.claude.com/docs/en/overview) · [CLAUDE.md / memory](https://code.claude.com/docs/en/memory) · [hooks](https://code.claude.com/docs/en/hooks) · [skills](https://code.claude.com/docs/en/skills)
- [Tool use & `tool_choice`](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use)
- [MCP introduction](https://modelcontextprotocol.io/introduction) · [MCP tools](https://modelcontextprotocol.io/docs/concepts/tools) · [MCP resources](https://modelcontextprotocol.io/docs/concepts/resources)
- [Context windows](https://platform.claude.com/docs/en/build-with-claude/context-windows)

---

## Step 3 — Build one small thing before you sit the exam

You don't need anything fancy. A weekend project is enough:

- A **coordinator** that delegates to 2–3 **worker** sub-agents (e.g., a search agent + a summarizer agent).
- One tool exposed via **MCP**, so you feel the difference between a *tool* (model calls it) and a *resource* (you hand content to the model directly).
- One place where you deliberately **force structured output** using `tool_choice`, so you see why "asking nicely" in a prompt isn't the same as a guarantee.

Building this once will make several exam questions feel familiar instead of theoretical.

**Docs to build from:** [Agent SDK overview](https://code.claude.com/docs/en/agent-sdk/overview) · [Tool use implementation guide](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use) · [MCP tools](https://modelcontextprotocol.io/docs/concepts/tools) & [MCP resources](https://modelcontextprotocol.io/docs/concepts/resources)

---

## Step 4 — Where most people actually lose marks

Based on shared experience across people who've taken this exam, these are the classic traps:

1. **Required fields that shouldn't be required.** If a field might genuinely be absent from the input, mark it optional / nullable. A required field with no matching data pressures the model to invent something. ([Tool use docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use))
2. **Relying on prompt wording for structured output.** A well-written instruction is a *request*. `tool_choice` (forcing a specific tool call) is a *guarantee*. If a broken format would break your downstream system, force it — don't ask politely. ([Tool use docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use))
3. **Reaching for an agent when a workflow (or a single call) would do.** More autonomy = less predictability. The exam rewards restraint. ([Building Effective Agents](https://www.anthropic.com/research/building-effective-agents))
4. **Confusing MCP tools and resources.** Not everything the model needs should be a "tool call" — sometimes just handing over the content as a resource is cheaper and more reliable. ([MCP tools](https://modelcontextprotocol.io/docs/concepts/tools) vs. [MCP resources](https://modelcontextprotocol.io/docs/concepts/resources))
5. **Ignoring resumability.** If your multi-step pipeline can't pick up from where it failed, every failure costs you the whole run — and that's a real architecture flaw, not a minor detail. ([Context windows](https://platform.claude.com/docs/en/build-with-claude/context-windows))

---

## Step 5 — Exam day tips

- **Scoring:** results are a scaled score from 100–1,000; you need **720 to pass** (roughly 69% correct). No penalty for guessing an unanswered question, so never leave one blank.
- Expect **two plausible-looking answers** per question. You're usually picking the better trade-off, not spotting an obviously wrong option. Read for the *constraint* stated in the question (compliance, latency, cost, team size) — that constraint decides the answer.
- Don't skip the "boring" topics you think you already know well from real work — that's often where blind spots hide.
- Keep a mental checklist: *Could this be a single call? Could this be a workflow? Do I really need an agent?*
- The exam itself is proctored via Pearson VUE — book/manage your session at [pearsonvue.com/anthropic](https://www.pearsonvue.com/us/en/anthropic.html).

---

## Practice before the real exam

I built a small free app to drill practice questions in the same style as the exam — useful for a final sanity check before you book the real thing.

- **Try it:** [claude-architect-cert-app.streamlit.app](https://claude-architect-cert-app.streamlit.app/)
- **Source:** [github.com/mukilankarthik/claude-architect-cert-app](https://github.com/mukilankarthik/claude-architect-cert-app)

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
