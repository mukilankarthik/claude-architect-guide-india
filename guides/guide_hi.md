# Claude Certified Architect – Foundations: आसान तैयारी गाइड (हिन्दी)

[English](../README.md) · हिन्दी · [தமிழ்](guide_ta.md)

यह गाइड उन लोगों के लिए है जो **Claude Certified Architect – Foundations** परीक्षा की तैयारी कर रहे हैं। यह कोई आधिकारिक Anthropic दस्तावेज़ नहीं है — यह सिर्फ़ एक साधारण रास्ता है, जो परीक्षा पास कर चुके किसी व्यक्ति के अनुभव से बना है।

---

## यह प्रमाणपत्र क्या है?

यह प्रमाणपत्र उन लोगों के लिए है जो **Claude API**, **Claude Code**, **Agent SDK** और **MCP (Model Context Protocol)** का उपयोग करके Claude के साथ सिस्टम डिज़ाइन करते हैं। यह कोडिंग की परीक्षा नहीं है — यह जाँचती है कि आप सही *आर्किटेक्चर* निर्णय ले सकते हैं या नहीं: कब एक साधारण API कॉल काफ़ी है, कब एक एजेंट की ज़रूरत है, टूल्स कैसे डिज़ाइन करें, सिस्टम को भरोसेमंद कैसे बनाएँ।

## यह गाइड किसके लिए है?

- वे इंजीनियर जिन्होंने Claude से पहले से ही कुछ छोटा प्रोजेक्ट बनाया है और अब अपने ज्ञान को व्यवस्थित करना चाहते हैं।
- वे लोग जिन्हें लंबा वीडियो कोर्स देखने के बजाय एक सीधी चेकलिस्ट पसंद है।

अगर आपने अभी तक Claude से कुछ भी नहीं बनाया है, तो पहले एक छोटा प्रोजेक्ट बनाएँ — इससे यह गाइड पढ़ने से कहीं ज़्यादा सीखने को मिलेगा।

---

## चरण 1 — Anthropic की मुफ़्त कोर्स लें

पैसे देकर कोई बूटकैंप लेने की ज़रूरत नहीं है। Anthropic Academy के मुफ़्त कोर्स ही पूरा सिलेबस कवर करते हैं:

| क्रम | कोर्स | फोकस |
|---|---|---|
| 1 | [AI Fluency: Framework & Foundations](https://anthropic.skilljar.com/ai-fluency-framework-foundations) | AI के साथ काम करने का सही तरीका सोचना |
| 2 | [Claude 101](https://anthropic.skilljar.com/claude-101) | प्रोडक्ट की बुनियादी बातें — छोटा कोर्स |
| 3 | [Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api) | परीक्षा का मुख्य भाग: टूल यूज़, स्ट्रक्चर्ड आउटपुट, एजेंट डिज़ाइन |
| 4 | [Claude Code in Action](https://anthropic.skilljar.com/claude-code-in-action) | Claude Code को भरोसेमंद तरीक़े से चलाना |
| 5 | [Introduction to Model Context Protocol](https://anthropic.skilljar.com/introduction-to-model-context-protocol) | MCP के हिस्से: tools, resources, prompts |
| 6 | [Introduction to Agent Skills](https://anthropic.skilljar.com/introduction-to-agent-skills) | Skills — अक्सर लोग इसे कम पढ़ते हैं, पर परीक्षा में आता है |

अगर आपकी कंपनी किसी ख़ास क्लाउड पर काम करती है, तो [Claude with Amazon Bedrock](https://anthropic.skilljar.com/claude-in-amazon-bedrock) या [Claude with Google Cloud's Vertex AI](https://anthropic.skilljar.com/claude-with-google-vertex) भी देख सकते हैं — वरना छोड़ दें।

**कोर्स/परीक्षा पोर्टल का एक्सेस:** [anthropic.skilljar.com — access request फ़ॉर्म](https://anthropic.skilljar.com/claude-certified-architect-foundations-access-request) (वर्क/पार्टनर ईमेल चाहिए)।

---

## चरण 2 — परीक्षा का ध्यान कहाँ है, यह सटीक रूप से जानें

यह Anthropic के आधिकारिक exam guide (v0.1, फ़रवरी 2025) से लिया गया असली वेटेज है — रजिस्टर करते समय हमेशा मौजूदा वर्ज़न से मिलान करें, क्योंकि ये आंकड़े बदल सकते हैं:

| Domain | वेटेज |
|---|---|
| 1. Agentic Architecture & Orchestration (agentic loops, coordinator/subagent patterns, hooks) | 27% |
| 2. Tool Design & MCP Integration (tool interfaces, error responses, tool_choice) | 18% |
| 3. Claude Code Configuration & Workflows (CLAUDE.md, rules, skills, CI/CD) | 20% |
| 4. Prompt Engineering & Structured Output (few-shot, JSON schema, batch processing) | 20% |
| 5. Context Management & Reliability (long-context handling, escalation, error propagation) | 15% |

परीक्षा में कुल 6 प्रकाशित scenarios में से 4 (रैंडम रूप से चुने गए) आते हैं: customer support agent, Claude Code dev productivity, multi-agent research system, developer productivity tooling, Claude Code CI/CD, और structured data extraction। सभी सवाल single-answer multiple choice (4 विकल्प) हैं; guess करने पर कोई पेनल्टी नहीं है।

**एक ज़रूरी नियम जो बार-बार काम आता है:** हमेशा सबसे *सरल* तरीक़ा चुनें जो काम कर दे। पहले सिर्फ़ एक API कॉल सोचें, फिर workflow, और सबसे आख़िर में agent। बिना ज़रूरत मल्टी-एजेंट सिस्टम मत बनाइए।

**आधिकारिक तौर पर out of scope** (guide के अनुसार) — इन पर समय बर्बाद न करें: fine-tuning, API billing/auth/rate limits, MCP server hosting/infra, model internals/RLHF, vision, computer use, streaming/SSE, और cloud-provider-specific configuration।

**ऊपर दी गई टेबल की पुष्टि के लिए पढ़ें:**
- [आधिकारिक Exam Guide (PDF)](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1773274827%2FClaude+Certified+Architect+%E2%80%93+Foundations+Certification+Exam+Guide.pdf) — असली syllabus, हमेशा इससे मिलान करें
- [Building Effective Agents](https://www.anthropic.com/research/building-effective-agents) — Anthropic का agent बनाम workflow वाला मूल तर्क
- [Claude Code docs](https://code.claude.com/docs/en/overview) · [CLAUDE.md / memory](https://code.claude.com/docs/en/memory) · [hooks](https://code.claude.com/docs/en/hooks) · [skills](https://code.claude.com/docs/en/skills)
- [Tool use व `tool_choice`](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use)
- [MCP introduction](https://modelcontextprotocol.io/introduction) · [MCP tools](https://modelcontextprotocol.io/docs/concepts/tools) · [MCP resources](https://modelcontextprotocol.io/docs/concepts/resources)
- [Context windows](https://platform.claude.com/docs/en/build-with-claude/context-windows)

---

## चरण 3 — परीक्षा से पहले एक छोटा प्रोजेक्ट ज़रूर बनाएँ

कुछ भी बड़ा बनाने की ज़रूरत नहीं — एक वीकेंड प्रोजेक्ट काफ़ी है:

- एक **coordinator** जो 2–3 **worker** sub-agents को काम बाँटे (जैसे एक search agent + एक summarizer agent)।
- एक टूल जो **MCP** के ज़रिए दिया गया हो, ताकि आपको *tool* (जिसे model ख़ुद कॉल करता है) और *resource* (जो सीधे model को दिया जाता है) का फ़र्क़ महसूस हो।
- एक जगह जहाँ आप जानबूझकर `tool_choice` से structured output को *ज़बरदस्ती* लागू करें — ताकि समझ आए कि सिर्फ़ प्रॉम्प्ट में अच्छे से लिखना काफ़ी नहीं है।

एक बार ख़ुद बना लेने के बाद, परीक्षा के कई सवाल जाने-पहचाने लगेंगे।

**बनाने के लिए ये docs पढ़ें:** [Agent SDK overview](https://code.claude.com/docs/en/agent-sdk/overview) · [Tool use implementation guide](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use) · [MCP tools](https://modelcontextprotocol.io/docs/concepts/tools) और [MCP resources](https://modelcontextprotocol.io/docs/concepts/resources)

---

## चरण 4 — जहाँ ज़्यादातर लोग अंक गँवाते हैं

अनुभव से पता चली कुछ आम गलतियाँ:

1. **ऐसे फ़ील्ड को required बना देना जो असल में हमेशा मौजूद नहीं होते।** अगर कोई फ़ील्ड डेटा में नहीं मिल सकता, तो उसे optional/nullable रखें — वरना model कुछ ग़लत बना देगा। ([Tool use docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use))
2. **सिर्फ़ प्रॉम्प्ट की भाषा पर भरोसा करना।** अच्छा लिखा प्रॉम्प्ट सिर्फ़ एक *निवेदन* है। `tool_choice` एक *गारंटी* है। अगर ग़लत फ़ॉर्मैट से आपका सिस्टम टूट सकता है, तो ज़बरदस्ती लागू करें। ([Tool use docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use))
3. **बिना ज़रूरत agent चुनना जबकि workflow काफ़ी होता।** ज़्यादा स्वायत्तता (autonomy) = कम अनुमान लगाने योग्य (predictability)। परीक्षा संयम को इनाम देती है। ([Building Effective Agents](https://www.anthropic.com/research/building-effective-agents))
4. **MCP में tools और resources को गड्डमड्ड करना।** हर चीज़ tool call नहीं होनी चाहिए — कभी-कभी सीधे resource देना सस्ता और भरोसेमंद होता है। ([MCP tools](https://modelcontextprotocol.io/docs/concepts/tools) बनाम [MCP resources](https://modelcontextprotocol.io/docs/concepts/resources))
5. **Resumability को नज़रअंदाज़ करना।** अगर आपका पाइपलाइन बीच में रुकने के बाद वहीं से शुरू नहीं हो सकता, तो हर असफलता पूरी पाइपलाइन दोबारा चलाने की कीमत लेती है। ([Context windows](https://platform.claude.com/docs/en/build-with-claude/context-windows))

---

## चरण 5 — परीक्षा के दिन के लिए टिप्स

- **स्कोरिंग:** नतीजे 100–1,000 के scaled score में आते हैं; पास होने के लिए **720 चाहिए** (लगभग 69% सही)। unanswered सवाल पर कोई पेनल्टी नहीं है, इसलिए कोई भी सवाल खाली मत छोड़ें।
- अक्सर **दो सही दिखने वाले जवाब** मिलेंगे। आपको बेहतर *trade-off* चुनना है, बिल्कुल ग़लत विकल्प नहीं ढूँढना है। सवाल में दी गई *शर्त* (compliance, latency, cost, टीम का आकार) पर ध्यान दें — वही जवाब तय करती है।
- जिन विषयों को आप "पहले से जानते हैं" समझकर छोड़ते हैं, वहीं सबसे ज़्यादा भूलचूक होती है।
- ख़ुद से एक सवाल हमेशा पूछें: *क्या यह सिर्फ़ एक API कॉल से हो सकता है? क्या workflow काफ़ी है? क्या सच में agent चाहिए?*
- असली परीक्षा Pearson VUE के ज़रिए proctored होती है — सेशन बुक/मैनेज करें [pearsonvue.com/anthropic](https://www.pearsonvue.com/us/en/anthropic.html) पर।

---

## असली परीक्षा से पहले अभ्यास करें

मैंने एक छोटा-सा मुफ़्त app बनाया है जिसमें परीक्षा जैसे ही स्टाइल के अभ्यास सवाल हैं — असली परीक्षा बुक करने से पहले आख़िरी जाँच के लिए उपयोगी।

- **आज़माएँ:** [claude-architect-cert-app.streamlit.app](https://claude-architect-cert-app.streamlit.app/)
- **Source:** [github.com/mukilankarthik/claude-architect-cert-app](https://github.com/mukilankarthik/claude-architect-cert-app)

---

## अक्सर पूछे जाने वाले सवाल

**क्या पेड कोर्स ज़रूरी है?**
नहीं — ऊपर दिए गए मुफ़्त Anthropic Academy कोर्स ही सिलेबस कवर करते हैं।

**क्या यह आधिकारिक Anthropic संसाधन है?**
नहीं। यह एक सामुदायिक गाइड है, जो परीक्षा पास कर चुके व्यक्ति के अनुभव से लिखी गई है। मौजूदा syllabus, फ़ीस और access के लिए हमेशा Anthropic के आधिकारिक पेज देखें।

---

इस गाइड में सुधार या किसी और भारतीय भाषा (तेलुगु, कन्नड़, मलयालम, मराठी, बंगाली आदि) में अनुवाद जोड़ने के लिए Pull Request का स्वागत है।
