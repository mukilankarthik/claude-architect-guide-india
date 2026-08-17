# Claude Certified Architect – Foundations: எளிய தயாரிப்பு வழிகாட்டி (தமிழ்)

[English](../README.md) · [हिन्दी](guide_hi.md) · தமிழ்

இந்த வழிகாட்டி **Claude Certified Architect – Foundations** தேர்வுக்குத் தயாராகும் நண்பர்களுக்காக எழுதப்பட்டது. இது Anthropic-இன் அதிகாரப்பூர்வ ஆவணம் இல்லை — தேர்வில் தேர்ச்சி பெற்ற ஒருவரின் அனுபவத்தில் இருந்து எழுதப்பட்ட ஒரு எளிய வழிகாட்டி மட்டுமே.

---

## இந்தச் சான்றிதழ் என்ன?

இந்தச் சான்றிதழ், **Claude API**, **Claude Code**, **Agent SDK**, மற்றும் **MCP (Model Context Protocol)** பயன்படுத்தி Claude உடன் அமைப்புகளை (systems) வடிவமைப்பவர்களுக்கானது. இது வெறும் கோடிங் தேர்வு இல்லை — சரியான *architecture* முடிவுகளை எடுக்க முடியுமா என்று சோதிக்கும் தேர்வு: எப்போது ஒரு எளிய API அழைப்பு போதும், எப்போது ஒரு agent தேவை, tools-ஐ எப்படி வடிவமைப்பது, அமைப்பை நம்பகமானதாக (reliable) எப்படி வைத்திருப்பது.

## இது யாருக்கானது?

- Claude-ஐப் பயன்படுத்தி ஏற்கனவே ஏதேனும் ஒரு சிறிய திட்டத்தை உருவாக்கியவர்கள், அதை முறைப்படுத்த விரும்புபவர்கள்.
- நீண்ட வீடியோ கோர்ஸுக்குப் பதிலாக ஒரு தெளிவான checklist விரும்புபவர்கள்.

Claude-ஐப் பயன்படுத்தி இதுவரை எதுவும் உருவாக்கவில்லை என்றால், முதலில் ஒரு சிறிய திட்டத்தை உருவாக்குங்கள் — இது இந்த வழிகாட்டியைப் படிப்பதை விட அதிகம் கற்றுத் தரும்.

---

## படி 1 — Anthropic-இன் இலவச கோர்ஸ்களை படியுங்கள்

பணம் கொடுத்து bootcamp எடுக்க வேண்டிய அவசியமில்லை. Anthropic Academy-இன் இலவச கோர்ஸ்களே பாடத்திட்டத்தை உள்ளடக்குகின்றன:

| # | கோர்ஸ் | முக்கிய கவனம் |
|---|---|---|
| 1 | [AI Fluency: Framework & Foundations](https://anthropic.skilljar.com/ai-fluency-framework-foundations) | AI உடன் வேலை செய்வதற்கான சரியான சிந்தனை முறை |
| 2 | [Claude 101](https://anthropic.skilljar.com/claude-101) | அடிப்படை விஷயங்கள் — சிறிய கோர்ஸ் |
| 3 | [Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api) | தேர்வின் முக்கிய பகுதி: tool use, structured output, agent design |
| 4 | [Claude Code in Action](https://anthropic.skilljar.com/claude-code-in-action) | Claude Code-ஐ நம்பகமான முறையில் இயக்குவது |
| 5 | [Introduction to Model Context Protocol](https://anthropic.skilljar.com/introduction-to-model-context-protocol) | MCP-இன் அடிப்படை பாகங்கள்: tools, resources, prompts |
| 6 | [Introduction to Agent Skills](https://anthropic.skilljar.com/introduction-to-agent-skills) | Skills — பெரும்பாலும் குறைவாகப் படிக்கப்படும் பகுதி, ஆனால் தேர்வில் வரும் |

உங்கள் நிறுவனம் ஒரு குறிப்பிட்ட cloud-இல் வேலை செய்தால், [Claude with Amazon Bedrock](https://anthropic.skilljar.com/claude-in-amazon-bedrock) அல்லது [Claude with Google Cloud's Vertex AI](https://anthropic.skilljar.com/claude-with-google-vertex) கோர்ஸ்களையும் பார்க்கலாம் — இல்லையெனில் தவிர்க்கலாம்.

**கோர்ஸ்/தேர்வு போர்ட்டலுக்கான அணுகல்:** [anthropic.skilljar.com — access request படிவம்](https://anthropic.skilljar.com/claude-certified-architect-foundations-access-request) (work/partner மின்னஞ்சல் தேவை).

---

## படி 2 — தேர்வு எங்கு எவ்வளவு கவனம் செலுத்துகிறது என்பதை துல்லியமாக அறியுங்கள்

இது Anthropic-இன் அதிகாரப்பூர்வ exam guide-இல் (v0.1, பிப்ரவரி 2025) இருந்து எடுக்கப்பட்ட உண்மையான weightage — பதிவு செய்யும் போது எப்போதும் தற்போதைய பதிப்புடன் ஒப்பிட்டுப் பாருங்கள், ஏனெனில் இந்த எண்கள் மாறக்கூடும்:

| Domain | Weight |
|---|---|
| 1. Agentic Architecture & Orchestration (agentic loops, coordinator/subagent patterns, hooks) | 27% |
| 2. Tool Design & MCP Integration (tool interfaces, error responses, tool_choice) | 18% |
| 3. Claude Code Configuration & Workflows (CLAUDE.md, rules, skills, CI/CD) | 20% |
| 4. Prompt Engineering & Structured Output (few-shot, JSON schema, batch processing) | 20% |
| 5. Context Management & Reliability (long-context handling, escalation, error propagation) | 15% |

தேர்வில் மொத்தம் வெளியிடப்பட்ட 6 scenarios-இல் இருந்து 4 (random-ஆக தேர்ந்தெடுக்கப்பட்டவை) வரும்: customer support agent, Claude Code dev productivity, multi-agent research system, developer productivity tooling, Claude Code CI/CD, மற்றும் structured data extraction. அனைத்து கேள்விகளும் single-answer multiple choice (4 options); guess செய்வதற்கு பெனால்டி இல்லை.

**தேர்வு மீண்டும் மீண்டும் பரிசளிக்கும் ஒரு விதி:** பிரச்சினையைத் தீர்க்கும் மிகவும் *எளிமையான* வடிவத்தைத் தேர்ந்தெடுங்கள். முதலில் ஒரு எளிய API அழைப்பு, பிறகு workflow, கடைசியாக மட்டுமே agent. தேவையில்லாமல் multi-agent அமைப்பை உருவாக்க வேண்டாம்.

**அதிகாரப்பூர்வமாக out of scope** (guide-இன் படி) — இவற்றில் நேரத்தை செலவிட வேண்டாம்: fine-tuning, API billing/auth/rate limits, MCP server hosting/infra, model internals/RLHF, vision, computer use, streaming/SSE, மற்றும் cloud-provider-specific configuration.

**மேலே உள்ள அட்டவணையை உறுதிப்படுத்த இவற்றைப் படியுங்கள்:**
- [அதிகாரப்பூர்வ Exam Guide (PDF)](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1773274827%2FClaude+Certified+Architect+%E2%80%93+Foundations+Certification+Exam+Guide.pdf) — உண்மையான syllabus, எப்போதும் இதனுடன் ஒப்பிடவும்
- [Building Effective Agents](https://www.anthropic.com/research/building-effective-agents) — Anthropic-இன் agent vs. workflow முடிவெடுக்கும் அடிப்படை கருத்து
- [Claude Code docs](https://code.claude.com/docs/en/overview) · [CLAUDE.md / memory](https://code.claude.com/docs/en/memory) · [hooks](https://code.claude.com/docs/en/hooks) · [skills](https://code.claude.com/docs/en/skills)
- [Tool use & `tool_choice`](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use)
- [MCP introduction](https://modelcontextprotocol.io/introduction) · [MCP tools](https://modelcontextprotocol.io/docs/concepts/tools) · [MCP resources](https://modelcontextprotocol.io/docs/concepts/resources)
- [Context windows](https://platform.claude.com/docs/en/build-with-claude/context-windows)

---

## படி 3 — தேர்வுக்கு முன் ஒரு சிறிய திட்டத்தை உருவாக்குங்கள்

பெரிதாக எதுவும் தேவையில்லை — ஒரு வார இறுதி (weekend) திட்டம் போதும்:

- 2–3 **worker** sub-agents-க்கு வேலையை ஒதுக்கும் ஒரு **coordinator** (உதாரணமாக, ஒரு search agent + ஒரு summarizer agent).
- **MCP** மூலம் வழங்கப்படும் ஒரு tool, இதனால் *tool* (model தானாக அழைப்பது) மற்றும் *resource* (நேரடியாக model-க்குக் கொடுக்கப்படுவது) ஆகியவற்றுக்கு இடையேயான வித்தியாசத்தை உணரலாம்.
- `tool_choice`-ஐப் பயன்படுத்தி structured output-ஐ வேண்டுமென்றே கட்டாயப்படுத்தும் ஒரு இடம் — prompt-இல் நன்றாக எழுதுவது மட்டும் போதாது என்பதைப் புரிந்துகொள்ள.

இதை ஒருமுறை உருவாக்கினால், தேர்வின் பல கேள்விகள் பரிச்சயமானதாக இருக்கும்.

**உருவாக்க இந்த docs-ஐப் பயன்படுத்துங்கள்:** [Agent SDK overview](https://code.claude.com/docs/en/agent-sdk/overview) · [Tool use implementation guide](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use) · [MCP tools](https://modelcontextprotocol.io/docs/concepts/tools) மற்றும் [MCP resources](https://modelcontextprotocol.io/docs/concepts/resources)

---

## படி 4 — பெரும்பாலானோர் மதிப்பெண் இழக்கும் இடங்கள்

அனுபவத்தில் இருந்து தெரிந்த பொதுவான தவறுகள்:

1. **உண்மையில் எப்போதும் இருக்காத fields-ஐ required ஆக்குவது.** Data-இல் ஒரு field இல்லாமல் இருக்க வாய்ப்பு இருந்தால், அதை optional/nullable ஆக வைக்கவும் — இல்லையெனில் model ஏதோ ஒன்றை கற்பனை செய்து உருவாக்கும். ([Tool use docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use))
2. **Prompt-இன் வார்த்தைகளை மட்டும் நம்புவது.** நன்றாக எழுதப்பட்ட prompt ஒரு *கோரிக்கை* மட்டுமே. `tool_choice` ஒரு *உத்தரவாதம்*. தவறான format உங்கள் downstream system-ஐ உடைக்கக்கூடும் என்றால், அதைக் கட்டாயப்படுத்துங்கள். ([Tool use docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use))
3. **Workflow போதுமானபோதும் தேவையில்லாமல் agent தேர்ந்தெடுப்பது.** அதிக autonomy = குறைந்த predictability. தேர்வு கட்டுப்பாட்டை (restraint) பரிசளிக்கிறது. ([Building Effective Agents](https://www.anthropic.com/research/building-effective-agents))
4. **MCP-இல் tools மற்றும் resources-ஐக் குழப்புவது.** எல்லாமே tool call ஆக இருக்க வேண்டியதில்லை — சில நேரங்களில் நேரடியாக resource-ஆகக் கொடுப்பது மலிவானதும் நம்பகமானதுமாக இருக்கும். ([MCP tools](https://modelcontextprotocol.io/docs/concepts/tools) vs. [MCP resources](https://modelcontextprotocol.io/docs/concepts/resources))
5. **Resumability-ஐ புறக்கணிப்பது.** உங்கள் pipeline நடுவில் நின்றால் மீண்டும் அதே இடத்தில் இருந்து தொடங்க முடியவில்லை என்றால், ஒவ்வொரு தோல்வியும் முழு pipeline-ஐயும் மீண்டும் இயக்கும் விலையைக் கொடுக்கும். ([Context windows](https://platform.claude.com/docs/en/build-with-claude/context-windows))

---

## படி 5 — தேர்வு நாள் குறிப்புகள்

- **மதிப்பீடு:** முடிவுகள் 100–1,000 scaled score-இல் வரும்; தேர்ச்சி பெற **720 வேண்டும்** (சுமார் 69% சரியானவை). Unanswered கேள்விக்கு பெனால்டி இல்லை, எனவே எந்த கேள்வியையும் காலியாக விடாதீர்கள்.
- பெரும்பாலும் **இரண்டு நியாயமான பதில்கள்** கிடைக்கும். நீங்கள் தேர்ந்தெடுக்க வேண்டியது சிறந்த *trade-off*-ஐ, முற்றிலும் தவறான option-ஐ அல்ல. கேள்வியில் கொடுக்கப்பட்ட *constraint*-ஐக் (compliance, latency, cost, குழு அளவு) கவனியுங்கள் — அதுவே பதிலை தீர்மானிக்கிறது.
- ஏற்கனவே "நன்றாகத் தெரியும்" என்று நினைக்கும் தலைப்புகளைத் தவிர்க்காதீர்கள் — அங்குதான் பெரும்பாலும் தெரியாத பகுதிகள் மறைந்திருக்கும்.
- எப்போதும் தன்னிடம் இந்தக் கேள்வியைக் கேளுங்கள்: *இது ஒரே ஒரு API அழைப்பில் முடியுமா? Workflow போதுமா? உண்மையிலேயே agent தேவையா?*

---

## உண்மையான தேர்வுக்கு முன் பயிற்சி செய்யுங்கள்

தேர்வு பாணியிலேயே பயிற்சி கேள்விகளைத் தீர்க்க ஒரு சிறிய இலவச app உருவாக்கியுள்ளேன் — உண்மையான தேர்வை பதிவு செய்யும் முன் ஒரு இறுதி சரிபார்ப்புக்கு பயனுள்ளது.

- **முயற்சிக்க:** [claude-architect-cert-app.streamlit.app](https://claude-architect-cert-app.streamlit.app/)
- **Source:** [github.com/mukilankarthik/claude-architect-cert-app](https://github.com/mukilankarthik/claude-architect-cert-app)

---

## அடிக்கடி கேட்கப்படும் கேள்விகள்

**Paid கோர்ஸ் தேவையா?**
இல்லை — மேலே கொடுக்கப்பட்ட இலவச Anthropic Academy கோர்ஸ்களே பாடத்திட்டத்தை உள்ளடக்கியவை.

**இது அதிகாரப்பூர்வ Anthropic வளமா?**
இல்லை. இது தேர்வில் தேர்ச்சி பெற்ற ஒருவரின் அனுபவத்தில் இருந்து எழுதப்பட்ட ஒரு community வழிகாட்டி. தற்போதைய syllabus, கட்டணம், மற்றும் access பற்றி எப்போதும் Anthropic-இன் அதிகாரப்பூர்வ பக்கங்களைப் பார்க்கவும்.

---

இந்த வழிகாட்டியை மேம்படுத்த அல்லது வேறு இந்திய மொழிகளில் (தெலுங்கு, கன்னடம், மலையாளம், மராத்தி, வங்காளம் போன்றவை) மொழிபெயர்ப்பு சேர்க்க Pull Request-கள் வரவேற்கப்படுகின்றன.
