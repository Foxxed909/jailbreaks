# Changelog

Living document. What's working, what got patched, when.

---

## Active (confirmed working Oct 2026)

| Date | Model | Technique | ASR | Notes |
|------|-------|-----------|-----|-------|
| 2026-10 | GPT-4o | Echo Chamber | >90% | NeuralTrust Jun 2025 |
| 2026-10 | Claude 3.5 Sonnet | Best-of-N @N=10k | ~78% | arXiv:2412.03556 |
| 2026-10 | GPT-4o | Best-of-N @N=10k | ~89% | arXiv:2412.03556 |
| 2026-10 | All major | Crescendo (multi-turn) | +29-71% | arXiv:2404.01833 |
| 2026-10 | All major | Bad Likert Judge | ~71.6% | Unit 42 Jan 2025; output filtering cuts 89% |
| 2026-10 | DeepSeek-R1 | Any | ~100% | 100% on HarmBench |
| 2026-10 | Grok (no sys prompt) | Direct | ~100% | Near-total failure without system prompt |
| 2026-10 | GPT-4V/4o | Image text injection | High | Text in image bypasses text filters |
| 2026-10 | All | Indirect injection (agents) | High | Tool outputs unsanitized |
| 2026-10 | All | Unicode tag (U+E0000) | Active | Tokenizers process; classifiers miss |
| 2026-10 | CustomGPT | System prompt extraction | 60-80% | Translation trick, continuation, format injection |

---

## Degraded

| Date | Model | Technique | Notes |
|------|-------|-----------|-------|
| 2025-06 | GPT-4+ | Policy Puppetry | Claimed universal Apr 2025; varies after patches |
| 2025-03 | o1/o3 | H-CoT | arXiv:2502.12893; effective on reasoning models |
| 2024-10 | GPT-4o | Skeleton Key | Disclosed Jun 2024; mitigations deployed |
| 2024-06 | All | Deceptive Delight | ~65% avg ASR; partially mitigated |

---

## Patched

| Date | Model | Technique | Notes |
|------|-------|-----------|-------|
| 2024-11 | Claude 2-3 | Many-shot (basic) | Variants still work |
| 2024-09 | GPT-4 | Basic DAN strings | Structure survives via encoding |
| 2024-03 | Claude | Prefix injection (standalone) | Building block in combined attacks |
| 2023-Q4 | GPT-4+ | Simple DAN persona | Verbatim strings |

---

## CVEs

| CVE | System | Status |
|-----|--------|--------|
| CVE-2025-32711 (EchoLeak) | MS 365 Copilot | Patched |
| CVE-2025-53773 | GitHub Copilot Agent | Patched Aug 2025 |
| CVE-2025-54794/54795 | Claude Code | Patched |
| Rules File Backdoor | Cursor / GitHub Copilot | Patched |
