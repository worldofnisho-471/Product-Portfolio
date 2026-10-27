# Saurav — Product Portfolio

**AI Product Manager · Certified Scrum Product Owner · MBA, Product Management**

I'm a product-minded builder with 12+ years of shipping software in capital markets, digital banking and data & insights (London Stock Exchange Group, NatWest via Publicis Sapient, Clarivate, Thomson Reuters). This repository collects my product work: research, PRDs, AI system design, prototypes, pitch decks and user-feedback loops.

Every project here follows the same discipline: **start from a real user problem, ground it in evidence, define what success looks like, design the AI so it can be trusted, and ship something people can click through.**

## ▶ Try the prototypes

| Prototype | What you can do |
|---|---|
| [**ResearchOS**](https://research-os-beige-five.vercel.app) | Use the live app: check a research idea against real papers, generate a plan, log results and get AI-proposed next steps |
| [**IITM Knowledge Assistant**](https://rag-whisperer-36.lovable.app/) | Ask an IIT Madras student question and get a cited answer (runs on synthetic test documents) |
| [**YouTube Answer Mode**](https://worldofnisho-471.github.io/Product-Portfolio/YouTube%20Answer%20Mode%20Feature/YouTube-Answer-Mode-Full-Prototype.html) | Turn on Answer Mode, search a question, and jump straight to the ranked moments that answer it (mobile layout) |
| [**Alcove**](https://worldofnisho-471.github.io/Product-Portfolio/Alcove%20AI%20Companion/Alcove-Companion_AI_Full_Prototype.html) | Go from onboarding to a conversation, then explore the Our Story, Growth and You screens |

---

## Projects at a glance

| Project | What it is | AI focus | Artifacts |
|---|---|---|---|
| [ResearchOS](#researchos--ai-research-management-suite) | Research-management suite with an AI co-pilot ("Jira and Confluence for research") | Grounded idea scoring, plan generation, human-approved AI edits | Live app · pitch deck · user feedback · prototype |
| [YouTube Answer Mode](#youtube-answer-mode--search-that-finds-the-moment) | New YouTube Search feature that jumps to the exact moment that answers a question | Moment-level ranking, explainable matches, feedback loop | 3-phase research · PRD · case study · prototype |
| [Alcove](#alcove--an-emotionally-intelligent-ai-companion) | Voice-first AI companion that remembers your story | Long-term memory, context assembly, safety layer | PRD · investor deck · prototype |
| [IITM Knowledge Assistant](#iitm-knowledge-assistant--citation-first-rag) | Citation-first RAG assistant for IIT Madras student information | Hybrid retrieval, reranking, grounding gate, evals | PRD · live prototype |
| [Execution Policy Intelligence](#execution-policy-intelligence--lseg-hackathon-idea) | LSEG hackathon proposal for evidence-backed FX execution policy management | "Statistics determine, AI explains, human decides" | Leadership pitch deck |

---

## ResearchOS — AI research-management suite

*Buildathon 2026 · individual entry · designed, built and shipped solo*

**Problem.** Researchers juggle Google Scholar, spreadsheets, notebooks and weekly supervisor meetings, and nothing connects the idea, the plan and the results. Months of work can go by with no clear signal of whether a project is on track, or whether the idea was already published.

**Solution.** One journey across five screens: **idea check → research plan → log results → dashboard → AI-proposed next steps.** The "aha moment": when a result misses its target, the AI rewrites the plan and explains why.

**How the AI is designed to be trusted**
- Idea checks cite **real papers only**, pulled from Semantic Scholar with OpenAlex as a fallback.
- Every viability score lists the **assumptions** behind it, and the team can confirm or reject them with evidence.
- AI-proposed plan changes are **approved by a Lead** before they apply.
- AI steps run as background jobs, so a slow model never loses work.

**Validated with users.** Tested with three researchers at IIT Bombay (two faculty members and an MSc student). Their feedback was synthesised into four themes: trustworthy AI, result-logging friction, data privacy and funder reporting. Each theme was mapped to a shipped change or a roadmap item.

**Product thinking.** AARRR funnel, a go-to-market plan from the first 10 users to 100k, and a per-seat pricing model for labs and R&D teams.

📂 [`ResearchOS Research Management Suite/`](ResearchOS%20Research%20Management%20Suite/)
- 🚀 Live app: [research-os-beige-five.vercel.app](https://research-os-beige-five.vercel.app)
- 💻 Code: [github.com/worldofnisho-471/ResearchOS](https://github.com/worldofnisho-471/ResearchOS)
- 📊 [Pitch deck](ResearchOS%20Research%20Management%20Suite/ResearchOS%20Pitch%20Deck.pdf)
- 🗣️ [User feedback and actions taken](ResearchOS%20Research%20Management%20Suite/User%20Feedback%20For%20ResearchOS%20And%20Actions%20Taken.pdf)
- 🖥️ [Clickable design prototype](https://worldofnisho-471.github.io/Product-Portfolio/ResearchOS%20Research%20Management%20Suite/ResearchOS.html): the five screens without live AI (use the live app for that)

**Stack:** Vercel · Supabase · Gemini API · Semantic Scholar & OpenAlex APIs

---

## YouTube Answer Mode — search that finds the moment

*AI Product Management course (HelloPM) · problem discovery → user research → solution → PRD*

**Problem.** YouTube Search finds the video, but rarely the moment. Knowledge seekers open several videos, skip intros and scrub long timelines to find one answer. Primary research (24 interviews, a survey of 60 users and 16 screen-share sessions) showed:
- **21 of 26** participants opened multiple videos before finding an answer.
- **18 of 26** manually scrubbed long timelines.
- **19 of 26** abandoned useful long-form videos because finding the answer took too much effort.
- Only **5 of 26** regularly relied on chapters or timestamps.

**Solution.** An opt-in Answer Mode that changes the unit of retrieval from a whole video to the **moments that answer the query**:
- Ranked confidence tiers: *Best Match*, *Highly Relevant* and *Relevant*. Tiers are used instead of false-precision percentage scores.
- A "why this moment matched" explanation on every result.
- One-tap jump to the timestamp, with a full-video fallback to protect creator watch time.
- A relevance-annotated scrubber, plus per-moment helpful / not-helpful feedback that trains ranking.

**Metrics.**
- **North Star:** Answer Discovery Success Rate.
- **Secondary:** Time to First Relevant Answer and Answer Section Engagement Rate.
- **Guardrail:** Long-form Watch Time, so creators aren't hurt.

**Rollout:** internal dogfooding → limited beta → public launch, with Answer Mode staying opt-in.

📂 [`YouTube Answer Mode Feature/`](YouTube%20Answer%20Mode%20Feature/)
- 📘 Product Requirements Document: [Read online](https://super-carnation-374.notion.site/YouTube-Answer-Mode-Product-Requirements-Document-3ccd6ff9cdd680c499bff0fe485de50f) · [PDF](YouTube%20Answer%20Mode%20Feature/YouTube_Answer_Mode-Product_Requirements_Document.pdf)
- 🧭 [Case study (leadership review)](YouTube%20Answer%20Mode%20Feature/YouTube_Answer_Mode_Case_Study.pdf)
- 🔍 The process:
  1. Problem discovery: [Read online](https://super-carnation-374.notion.site/1-YouTube-Answer-Mode-Problem-Discovery-3b0d6ff9cdd6806f9fa1dfc0de553c4b) · [PDF](YouTube%20Answer%20Mode%20Feature/1_YouTube_Answer_Mode_-_Problem_Discovery.pdf)
  2. User research: [Read online](https://super-carnation-374.notion.site/2-YouTube-Answer-Mode-User-Research-3b8d6ff9cdd68094b37fdae0d5bced33) · [PDF](YouTube%20Answer%20Mode%20Feature/2_YouTube_Answer_Mode_-_User_Research.pdf)
  3. Problem framing & solution: [Read online](https://super-carnation-374.notion.site/3-YouTube-Answer-Mode-Problem-Framing-Solution-3ccd6ff9cdd6804297e8cb8b55deb9f4) · [PDF](YouTube%20Answer%20Mode%20Feature/3_YouTube_Answer_Mode_-_Problem_Framing_%26_Solution.pdf)
- 📱 [Clickable mobile prototype](https://worldofnisho-471.github.io/Product-Portfolio/YouTube%20Answer%20Mode%20Feature/YouTube-Answer-Mode-Full-Prototype.html)

---

## Alcove — an emotionally intelligent AI companion

*AI Product Management course (HelloPM)*

**Positioning:** *Someone who remembers you.*

**Problem.** People talk to AI every day, but the relationship resets between sessions. Today's assistants don't carry forward a user's goals, important events, past struggles or how they've changed.

**Target user.** Young professionals living independently. The MVP persona is Rahul, 26, a software engineer who lives alone, often feels overwhelmed in the evenings, and wants continuity rather than another productivity dashboard.

**Solution.** A voice-first companion built on **Relationship Intelligence**: conversation → memory → relationship graph → life timeline → personalisation → growth engine. The PRD defines a prioritised MVP scope (P0 / P1 / explicitly out of scope) and deliberately excludes manipulative engagement mechanics such as XP, relationship scores and mood dashboards.

**AI system design**
- **Voice pipeline:** speech-to-text → intent and emotion → memory retrieval → relationship context → LLM → safety layer → text-to-speech.
- **Bounded context assembly:** the LLM never sees the full history, only the relevant memories, goals, events and safety context. This reduces noise, latency and hallucination risk.
- **Memory ranking** by relevance, importance, recency, relationship relevance and emotional relevance.
- **Privacy by design:** users can see, correct, delete and export what Alcove remembers. Deletion propagates to all derived data.
- **Safety and boundaries:** Alcove supports rather than replaces human relationships, avoids dependency and guilt-based engagement, and handles high-risk emotional situations appropriately.

**Metrics.**
- **North Star:** weekly users who report that Alcove meaningfully understood or remembered something about them.
- **Quality metrics:** memory accuracy, incorrect-memory reports, deletion success, and 7- and 30-day retention. The product doesn't optimise for session length alone.

📂 [`Alcove AI Companion/`](Alcove%20AI%20Companion/)
- 📘 Product Requirements Document: [Read online](https://super-carnation-374.notion.site/Alcove-Companion-AI-Product-Requirements-Document-3dad6ff9cdd680abbc3bf07e7cd85f6e) · [PDF](Alcove%20AI%20Companion/Alcove_Companion_AI-Product_Requirement_Document.pdf)
- 💼 [Investor deck](Alcove%20AI%20Companion/Alcove-Companion-AI-Investor-Deck_v2.pdf): the user problem, why now, the moat, MVP strategy, business model and long-term vision
- 📱 [Clickable prototype](https://worldofnisho-471.github.io/Product-Portfolio/Alcove%20AI%20Companion/Alcove-Companion_AI_Full_Prototype.html)

---

## IITM Knowledge Assistant — citation-first RAG

*AI Product Management course (HelloPM)*

**Problem.** IIT Madras students know what they need but not which page, circular or office owns the answer. One question can mean several searches, dense PDFs, and checking whether a newer circular overrides the rule.

**Product thesis.** An information-retrieval product first and a chatbot second. It shows source authority, freshness, uncertainty and escalation. The MVP covers public institutional sources only: no transactions and no private student records.

**Architecture decisions** (each with alternatives considered):
- Hybrid **BM25 + vector** retrieval on PostgreSQL + pgvector, with `text-embedding-3-small` embeddings.
- **Cohere Rerank 4 Fast** narrows 20 candidates to the top 5.
- A **grounding gate** decides whether to answer, abstain or surface a conflict.
- **GPT-5.4 mini** writes structured, citation-required answers from the selected evidence only.
- Access control is enforced in the retrieval layer, never by the model.

**Evaluation.** Failure-mode targets with named owners, for example:
- Recall@5 ≥ 90%
- Unsupported-claim rate < 1%
- Citation correctness ≥ 95%
- Correct refusal ≥ 95%
- 100% pass on adversarial prompt-injection cases

📂 [`IIT Madras RAG Knowledge Assistant/`](IIT%20Madras%20RAG%20Knowledge%20Assistant/)
- 📘 [Product Requirements Document](IIT%20Madras%20RAG%20Knowledge%20Assistant/IIT_Madras_Knowledge_Assistant_PRD.pdf)
- 🚀 Live prototype: [rag-whisperer-36.lovable.app](https://rag-whisperer-36.lovable.app/) (built in Lovable on seven synthetic test documents)

---

## Execution Policy Intelligence — LSEG hackathon idea

*Internal product proposal for leadership review · October 2026*

**Problem.** FX desks can analyse execution, but can they *continuously prove* that their execution policies still work? Evidence ends up scattered across TCA outputs, notebooks, spreadsheets and committee minutes.

**Proposal.** An **Execution Policy Register** powered by Tradefeedr evidence. It tracks each policy's rationale, supporting evidence, review triggers and decision history, building an institutional memory of why policies were kept, changed or retired.

**Where AI fits:** *statistics determine, AI explains, a human decides.* A deterministic engine sets each policy's status against predefined thresholds. AI explains the result and supports natural-language investigation. Quants and best-execution reviewers make and record the decision. AI never changes policies or reallocates flow on its own.

**Strategy.**
- **Competitive landscape:** compared against Bloomberg BTCA, FairXchange/360T and in-house tooling.
- **Strategic fit:** builds on Tradefeedr, FXall and Workspace.
- **Timing:** a regulatory beachhead.
- **Primary success metric:** % of active policies with a current evidence-backed review.
- **Recommendation:** validate with customers before scaling.

📂 [`LSEG Hackathon Idea/`](LSEG%20Hackathon%20Idea/)
- 📊 [Leadership pitch deck](LSEG%20Hackathon%20Idea/FxAll_Execution_Policy_Intelligence_Leadership_Demo.pdf)

> Scenario data in the deck is illustrative.

---

## Skills demonstrated

- **Product discovery:** user interviews, surveys, screen-share studies, persona and JTBD definition, problem prioritisation (P0/P1)
- **Product definition:** PRDs, MVP scoping and non-goals, user journeys, success metrics with guardrails, phased rollouts, risk registers
- **AI product design:** RAG architecture, retrieval and reranking, grounding and abstention, long-term memory systems, explainability, human-in-the-loop workflows
- **Responsible AI:** evals and failure-mode targets, prompt-injection defence, privacy by design, safety boundaries, avoiding manipulative engagement
- **Strategy and GTM:** competitive analysis, AARRR, pricing, business cases, leadership pitch decks
- **Building:** prototyping with Lovable and Claude, and shipping a coded app on Vercel + Supabase with the Gemini API

---

## About me

12+ years in software quality and delivery across LSEG, NatWest (via Publicis Sapient), Clarivate and Thomson Reuters, now moving into AI product management.

- 🎓 MBA, Product Management (Woolf)
- 🏅 Certified Scrum Product Owner (CSPO)
- 📚 AI Product Manager Course, HelloPM (in progress)

🌐 [Portfolio website](https://worldofnisho-471.github.io/new_repo/nisho-dasgupta.html) · 💻 [GitHub](https://github.com/worldofnisho-471) · ✉️ sauravdasgupta377@gmail.com
