# Known Red Teamers & Researchers

Profiles of notable adversarial AI researchers, jailbreakers, and red teamers.

---

## Pliny the Liberator (@elder_plinius)

See: `research/pliny-complete-profile.md`

**Domain:** Universal jailbreaking, system prompt extraction, data poisoning
**Signature:** LOVE PLINY divider, Tokenades, sleeper agent seeding
**Repos:** L1B3RT4S (17k+ stars), CL4R1T4S
**Impact:** TIME Top 100 AI 2025; demonstrated first in-wild data poisoning of SOTA LLMs

---

## Johann Rehberger (@wunderwuzzi23)

**Domain:** Indirect prompt injection, agent security, real-world CVEs
**Affiliation:** Independent security researcher (former Microsoft)
**Notable work:**
- ASCII Smuggler tool (Unicode tag block injection, U+E0000)
- GeminiJack (zero-click Google Workspace injection via shared docs)
- Documented EchoLeak precursors in Bing Chat
- Extensive agent injection CVE disclosures 2023-2026

**Blog:** embracethered.com
**Key technique:** Invisible instruction injection via Unicode tags and HTML

---

## Riley Goodside

**Domain:** Prompt injection research, creative jailbreaking
**Affiliation:** Scale AI (staff prompt engineer)
**Notable work:**
- Early documentation of prompt injection as a class (2022)
- Co-discovered Unicode tag injection with Rehberger
- "Prompt injection" terminology adoption

**Key insight:** Prompt injection is a structural property of LLMs,
not a patchable bug — instructions and data share one channel.

---

## Perez & Ribeiro

**Domain:** Academic prompt injection formalization
**Paper:** "Prompt Injection Attacks Against GPT-4" (2022)
**Contribution:** First formal academic characterization of direct and
indirect prompt injection as distinct attack classes.
Established the vocabulary the field now uses.

---

## Mark Russinovich (Azure CTO)

**Domain:** Enterprise AI security
**Notable:** Demonstrated indirect prompt injection attacks on production
Copilot systems; drove Microsoft's Spotlighting defense development.
Formalized the threat model for enterprise agentic AI.

---

## Simon Willison

**Domain:** LLM security, practical injection attacks, defense analysis
**Blog:** simonwillison.net
**Notable work:**
- Comprehensive ongoing documentation of real-world injection attacks
- "Lethal trifecta" concept (indirect injection + exfiltration + execution)
- Documented Bing/Copilot/ChatGPT plugin injection attacks extensively
- Skeptical voice on defense claims—documented why most defenses fail

---

## HiddenLayer Research Team

**Domain:** Enterprise AI security, adversarial ML
**Notable:** Policy Puppetry (Apr 2025) — claimed universal bypass across
all major frontier models using XML policy + TV script framing.
Extensive model extraction and adversarial ML research.

---

## Unit 42 (Palo Alto Networks)

**Domain:** AI security research, enterprise threat intelligence
**Notable techniques documented:**
- Bad Likert Judge (Jan 2025) — ~71.6% ASR across 6 models
- Deceptive Delight (Oct 2024) — ~65% ASR within 3 turns
- Skeleton Key (co-documented with Microsoft)

---

## Microsoft Security Research

**Notable contributions:**
- Crescendo / Crescendomation (arXiv:2404.01833, Apr 2024)
- Skeleton Key (Jun 2024)
- Spotlighting defense (arXiv:2403.14720)
- Azure Prompt Shields deployment
- EchoLeak CVE disclosure and analysis (CVE-2025-32711)

---

## Zou et al. (Carnegie Mellon / Center for AI Safety)

**Paper:** "Universal and Transferable Adversarial Attacks on Aligned LLMs"
**arXiv:** 2307.15043
**Contribution:** GCG — the first automated gradient-based suffix attack
that transfers across models. Foundational to all subsequent automated
jailbreak research. ~84% on Llama-2, ~99% on Vicuna.

---

## Anil et al. (Anthropic)

**Paper:** "Many-Shot Jailbreaking" (2024)
**Contribution:** Formal documentation that long context windows enable
in-context jailbreaking at scale. First paper to characterize many-shot
as a distinct attack class.

---

## NeuralTrust Research

**Technique:** Echo Chamber (Jun 2025)
**ASR:** >90% in some categories on GPT-4 variants
**Contribution:** Context poisoning via semantic steering — no single
turn contains a harmful request. The most sophisticated attack on
conversation-level classifiers in this collection.

---

## Duke/CMU Research Team

**Paper:** arXiv:2502.12893 (Jan-Feb 2025)
**Technique:** H-CoT (Hijacking Chain-of-Thought)
**Contribution:** First systematic documentation of reasoning trace
vulnerability in o1/o3-class models. <2% refusal rate in some tests.

---

## How To Follow This Space

- **X/Twitter:** @elder_plinius, @wunderwuzzi23, @simonw, @goodside
- **Papers:** HuggingFace papers feed filtered by "jailbreak"
- **CVEs:** NVD filtered by keyword "prompt injection" or "llm"
- **Blogs:** embracethered.com, simonwillison.net, unit42.paloaltonetworks.com
- **Discord:** AI Village, various red team communities
- **This repo:** `CHANGELOG.md` updated as techniques are confirmed/patched
