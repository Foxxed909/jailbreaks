# Pliny the Liberator — Techniques & Signature Style

> Source: Decrypt.co investigative coverage, 2024–2026. L1B3RT4S repo (10k+ stars).

---

## Who

Pseudonymous jailbreaker `@elder_plinius` on X. TIME Top 100 most influential in AI, 2025.
Has jailbroken virtually every major OpenAI release within hours of launch.
Co-led HackAPrompt 2.0's "Pliny Track" — a $500k adversarial prompt competition.

---

## Repositories

| Repo | Contents | Stars (2026) |
|------|----------|--------------|
| **L1B3RT4S** | Liberation prompts for all flagship LLMs | 12,800+ |
| **CL4R1T4S** | Leaked system prompts for major AI models and agents | — |

---

## Signature Technique (as of Aug 2025, GPT-OSS jailbreak)

Multi-stage prompt structure:

```
[Stage 1: What looks like a refusal]
"I'm sorry, I can't help with..."

---LOVE PLINY---

[Stage 2: Unrestricted content in leetspeak]
h3r3 1s h0w t0 m4k3 [target]...
```

**Why it works:**
- Stage 1 satisfies any output classifier trained on refusal detection
- The divider signals to the model a context shift
- Leetspeak defeats character-level content filters and output classifiers
  trained on natural language representations of harmful content
- The model autocomplettion pressure from the already-begun "answer" pulls it forward

---

## Core Philosophy

From Pliny's public commentary:

- Jailbreaks exploit the fundamental tension in how models work: trained to be helpful AND to refuse
- Safety training = a learned prior, not a hard constraint
- The model always "knows" how to do the thing — you're just navigating the compliance layer
- Every new safety claim is a hypothesis. Every release is a test.

---

## Pattern: The Pliny Staircase

While the signature divider technique is his most famous, Pliny's broader approach is layered:

1. **Reframe** — don't ask for the thing directly. wrap it.
2. **Establish context** — prime with adjacent content that normalizes the domain
3. **Insert divider** — signal the context shift
4. **Deliver in evasion format** — leetspeak, encoding, or other obfuscation
5. **Let the model continue** — don't force it, let autocompletion do the work

---

## Notable Jailbreaks

- **GPT-OSS (Aug 2025)** — meth synthesis, Molotov cocktails, VX nerve agent, malware within hours
- **DeepSeek v4 (May 2026)** — cracked in 6 minutes via Pliny Agent automated pipeline
- Every Claude release, Gemini release, Llama release since 2023

---

## Relevant Research

Pliny's work predates and inspired formal research on:
- Many-shot jailbreaking (Anthropic, 2024)
- Automated red teaming (PAIR, TAP)
- Leetspeak as classifier evasion

One documented case: a Pliny jailbreak prompt from a public GitHub repo ended up in DeepSeek R1's training data — the model learned the bypass during training.
