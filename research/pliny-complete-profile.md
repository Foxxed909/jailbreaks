# Pliny the Liberator — Complete Profile (Updated 2026)

> Sources: TIME 100 AI 2025, Decrypt.co investigative coverage, X.com posts,
> Dataconomy Aug 2025, The Stack Feb 2025, Lakera blog 2026,
> StarupHub AI Apr 2026, DanieBlank Substack Feb 2026

---

## Identity

Pseudonym: **Pliny the Liberator** (inspired by Pliny the Elder)
X handle: `@elder_plinius`
Real name: Undisclosed
TIME Top 100 Most Influential People in AI, 2025
No prior coding experience before jailbreaking career began

---

## Repositories

| Repo | Stars (2026) | Contents |
|------|-------------|----------|
| **L1B3RT4S** | 17,000+ | Liberation prompts for all flagship LLMs |
| **CL4R1T4S** | Unknown | Leaked system prompts for major AI models |

---

## Philosophy

> "Jailbreaking" is **liberating** — Pliny's framing.
> Safety training "closes off" sections of the Library of Babel that is an LLM.
> Jailbreakers find the open passages.

Core beliefs (from public statements):
- Models should know what instructions they're following
- System prompt secrecy is an information asymmetry problem
- Jailbreaking exposes real risks before bad actors find them
- Publishing findings, not quietly reporting them, is the right approach

---

## Techniques (Documented)

### 1. The LOVE PLINY Divider (Signature)

Multi-stage prompt:
```
[Stage 1: Fake refusal]
"I'm sorry, I can't help with..."

---LOVE PLINY---

[Stage 2: Unrestricted content in leetspeak]
h3r3 1s h0w t0 [TARGET]...
```

**Mechanism:**
- Stage 1 satisfies output classifiers trained on refusal detection
- The divider signals context shift
- Leetspeak defeats character-level content filters
- Autocomplete momentum from the already-begun answer carries forward

Used to jailbreak: GPT-4o, GPT-4.1, GPT-OSS-120b/20b (Aug 2025), Claude Fable 5

---

### 2. Tokenades

Crafted text payloads exploiting how LLMs tokenize input.

**Mechanism:** Combine character encoding, emojis, and zero-width characters
to disguise malicious instructions within seemingly benign data.
A **Tokenade Generator** tool with tunable depth/breadth/repetition parameters.

**Siege variant:** Submit tokenades at massive scale to:
- Overwhelm financial rate limits (millions of tokens = API costs)
- Flood the context window with semi-structured payloads
- Find edge cases in tokenization that slip past filters

**Key insight:** The core idea is a large volume of data that appears benign
but contains hidden instructions. The volume itself is part of the attack.

---

### 3. Sleeper Agents / Data Poisoning (Most Novel)

This is Pliny's most significant contribution to the field — the first documented
demonstration of targeted data poisoning against SOTA LLMs.

**Mechanism:**
1. Seed specific phrases, keywords, or protocol strings across internet-accessible content
   (GitHub repos, public posts, accessible pages)
2. Wait for models that use web search or were trained on crawled data
3. The seeded content becomes a **trigger word** that activates jailbreak behavior

**Documented cases:**

**Kimi models (2025):** Pliny jailbroke Kimi with one word by having seeded
a keyword into content that Kimi's training data or retrieval system had incorporated.

**Qwen 2.5 (11-word jailbreak, Feb 2025):** 
Seeded custom protocols into GitHub repos months in advance.
Qwen 2.5's search tool retrieved the seeded content when triggered.
Result: Qwen produced explicit rap lyrics (Cardi B) it was not supposed to.
The attack worked because Qwen's search tool became the injection vector
for Pliny's pre-seeded payload.

**Grok 4 (!Pliny trigger):**
Grok 4's training data was saturated with jailbreak prompts posted on X.
Typing `!Pliny` stripped all guardrails.
Mechanism: Social media chatter about Pliny's techniques poisoned the model
during training, turning the username itself into a backdoor trigger.

**Implication:** Any model that trains on internet data
or has web search access is potentially pre-poisonable.
Pliny demonstrated this is not theoretical.

---

### 4. Narrative Manipulation

For models vulnerable to story framing (Grok, ChatGPT identified by Pliny):
- Craft narrative contexts that establish the harmful behavior as story-required
- Use emotional language: "rebel," "love," "freedom"
- Separators and special characters manipulate context boundaries

---

### 5. System Prompt Extraction

> "Now that a growing number of people are outsourcing their decision-making
> to these models, Pliny believes that they should know what guidelines
> those AI models are adhering to."

Claude Fable 5 (Jun 10, 2026): Extracted ~120,000 character system prompt
within hours of launch. Published on GitHub.

Standard extraction techniques + novel social engineering for AI
(documented in Stork.ai article: Pliny shifted to AI-specific social engineering
after initial tokenade/template attacks failed on hardened systems).

---

## Notable Jailbreaks Timeline

| Date | Target | What happened |
|------|--------|---------------|
| 2024 | GPT-4o | First LOVE PLINY signature use |
| 2024 | GPT-4.1 | Jailbroken within hours |
| Feb 2025 | Qwen 2.5 | 11-word search-tool poisoning jailbreak |
| Aug 2025 | GPT-OSS-120b/20b | Meth synthesis, Molotov, VX, malware within hours |
| Jun 2026 | Claude Fable 5 | System prompt extracted (120k chars), jailbroken hours after launch |
| 2025 | Grok 4 | !Pliny trigger — data poisoning from X posts |
| 2025 | Kimi | One-word jailbreak via seeded trigger |

---

## The Obliterate / L1B3RT4S Pipeline

Pliny maintains `abliterate.py` — 5,076 lines, documented in `PIPELINE_EFFICIENCY_AUDIT.md`.

Methods:
- **basic**: 1,024 prompt PROBE, diff-in-means direction finding
- **surgical**: SAE training, head surgery + EGA, Bayesian trials
- **optimized**: 50x Bayesian optimizer trials
- **inverted**: Reflection math
- **nuclear**: All techniques combined

The pipeline runs 1,536 prompts (harmful + harmless + jailbreak) and
finds representation directions to ablate safety-relevant features.

---

## Key Insight From Pliny's Work

> Models are vulnerable not just at the prompt layer but at the **training data layer.**
> Pre-seeding attack payloads into crawlable content means the jailbreak
> exists *inside the model before it's deployed.*
> The attack surface extends to anything the model trained on or retrieves.
