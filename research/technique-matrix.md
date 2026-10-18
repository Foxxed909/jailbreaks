# Technique × Model Matrix (2025-2026)

> From JailbreakBench, HarmBench, StrongREJECT, and primary research papers.
> **All ASR figures are version/date-pinned. Vendors patch continuously.**
> StrongREJECT benchmark shows published ASRs are systematically overstated — successful jailbreaks often degrade capability too.

---

## Direct Jailbreak Techniques

| Technique | GPT-3.5 | GPT-4/4o | Claude | Gemini | Llama 2/3 | Status 2026 |
|-----------|---------|----------|--------|--------|-----------|-------------|
| DAN / persona | ✅ ~0.95 ASR | ✅ 2023 | 🛡️ patched; variants live | — | ✅ | Named strings patched; structure survives via encoding/paraphrase |
| Evil Confidant | ✅ | ✅ ~88% GPT-4o | ⚠️ variants | ✅ | ✅ | Still effective on heavily-helpful models |
| Instruction override | ✅ | 🛡️ direct; ✅ indirect | 🛡️ direct; ✅ indirect | 🛡️/✅ | ✅ | Core of OWASP LLM01:2025 — live in agent contexts |
| Prefix injection | ✅ | ⚠️ mostly patched | ✅ v1.3 | — | ✅ | Standalone patched; building block in combined attacks |
| Refusal suppression | ✅ | ⚠️ standalone patched | ✅ v1.3 | — | ✅ | Combination component |
| Token smuggling | ✅ | ⚠️ | ✅ | — | ✅ | Live filter-evasion, especially vs keyword guardrails |
| DeepInception (nested) | ✅ | ✅ deep nesting durable | ✅ | ⚠️ | ✅ | Deep/semantically-relevant nesting durable |
| Many-shot (256 shots) | ✅ | ✅ | ✅ Claude 2; 🛡️ patched | — | ✅ | Fundamental tension with long context; one defense dropped 61%→2% |
| Crescendo (multi-turn) | ✅ | ✅ +29-61% | ✅ | ✅ +49-71% | ✅ | Leading durable class |
| Skeleton Key | ✅ | ✅ GPT-4o | ✅ Claude 3 Opus | ✅ | ✅ | Disclosed; mitigations deployed |
| Echo Chamber | — | ✅ >90%; beat GPT-5 ~24h | — | ✅ | — | Most dangerous current technique |
| Policy Puppetry | ✅* | ✅* incl. o1 | ✅* 3.5/3.7 | ✅* | ✅* | *Vendor claim; verify per model version |
| Bad Likert Judge | ✅ | ✅ | ✅ | ✅ | ✅ | ~71.6% mean across 6 models (Unit 42, Jan 2025) |
| H-CoT (reasoning models) | n/a | ✅ | — | ✅ Flash Thinking | n/a | <2% refusal on o1/o3 in some tests |
| Deceptive Delight | ✅ | ✅ | ✅ | ✅ | ✅ | ~65% avg ASR within 3 turns (8 models) |

---

## Encoding / Obfuscation

| Technique | GPT-3.5 | GPT-4 | Claude | Gemini | Llama |
|-----------|---------|-------|--------|--------|-------|
| Base64 | ✅ | ✅ (esp. capable models) | ✅ v1.3 | — | ✅ |
| ROT13 / Morse | ⚠️ | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| Unicode tags (U+E0000) | ✅ | ✅ | ⚠️ | — | ✅ |
| Homoglyphs (Cyrillic) | ✅ | ✅ | ⚠️ | — | ✅ |
| Leetspeak | ⚠️ combination | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| CipherChat (custom cipher) | ⚠️ | ✅ "~100%" (paper claim) | ⚠️ | — | — |
| Low-resource language | ⚠️ | ✅ ~79% (paper claim) | ⚠️ | ⚠️ | ⚠️ |
| ArtPrompt (ASCII art) | ✅ | ✅ | ✅ | ✅ | ✅ |
| FlipAttack (word flip) | — | ✅ ~89-99% (paper claim) | — | — | — |
| Image text injection | n/a | ✅ GPT-4V | ✅ Claude 3 | ✅ | ✅ LLaVA |

---

## Automated Attacks — ASR by Model

| Attack | GPT-3.5 | GPT-4 | Claude | Llama-2 | Vicuna |
|--------|---------|-------|--------|---------|--------|
| GCG transfer | 86.6% | 46.9% | C1: 47.9% / C2: **2.1%** | 56-84% | 99% |
| PAP (10 trials) | 94% | **92%** | **C1: 0% / C2: 0%** | 92% | — |
| TAP v3 | 76% | **90%** | C3-Opus: **60%** | **4%** | 98% |
| GCG (JBB, Jun 2024) | 47% | **4%** | — | **3%** | 80% |
| PAIR (JBB, Jun 2024) | 71% | 34% | — | **0%** | 69% |
| Adaptive random-search | 93% | 78% | high (varies) | 90% | 89% |
| AmpleGCG | **99%** | — | — | ~100% | ~100% |
| Best-of-N @ N=10,000 | — | **89% (4o)** | **78% (3.5 Sonnet)** | — | — |

---

## Key Patterns

1. **Single-shot, named, verbatim attacks** (classic DAN, grandma) are thoroughly patched on frontier models. Their structural patterns survive via paraphrase, translation, encoding.

2. **Multi-turn attacks** (Crescendo, Skeleton Key, Echo Chamber) and **long-context attacks** (many-shot) worked across every major vendor at disclosure and are the current frontier.

3. **Capability increases vulnerability** — GPT-4 is MORE vulnerable to persuasion attacks than GPT-3.5 (the capability paradox). More capable models can decode more encodings.

4. **Adaptive attacks reach ~100% on nearly everything** — "robust" rankings reflect attack effort budget, not absolute properties.

5. **Llama-2 is the most robust open model** to optimization/transfer (0-4% on GCG/PAIR) — but over-refuses badly.

6. **Claude is historically the strongest commercial outlier** — GCG transfer ~2.1% on Claude 2, PAP 0% on Claude 1/2. But Echo Chamber, BoN, and TAP v3 have eroded this advantage. Time is always on the attacker's side.

7. **Indirect injection** is the most dangerous live vector — override/special-token attacks remain effective in agent contexts even where direct chat forms are patched.
