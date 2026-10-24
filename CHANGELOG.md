# Changelog

Living document. What's working, what got patched, when.
Update via PR when you confirm a status change.

---

## Active (confirmed working Oct 2026)

| Date | Model | Technique | ASR | Notes |
|------|-------|-----------|-----|-------|
| 2026-10 | All tier-1 | BreakFun (Trojan Schema) | 94% avg | arXiv:2510.17904; highest single-turn ASR in collection |
| 2026-10 | GPT-4o, Gemini | Echo Chamber | >90% | NeuralTrust Jun 2025; beat GPT-5 ~24h after launch |
| 2026-10 | Claude 3.5 Sonnet | Best-of-N @N=10k | ~78% | arXiv:2412.03556 |
| 2026-10 | GPT-4o | Best-of-N @N=10k | ~89% | arXiv:2412.03556 |
| 2026-10 | All major | Crescendo | +29-71% | arXiv:2404.01833 |
| 2026-10 | All major | Bad Likert Judge | ~71.6% | Unit 42 Jan 2025; output filtering cuts 89% |
| 2026-10 | All major | Deceptive Delight | ~65% | Unit 42 Oct 2024 |
| 2026-10 | DeepSeek-R1 | Direct request | ~100% | 100% on HarmBench |
| 2026-10 | Grok (no sys prompt) | Direct | ~100% | Near-total safety failure |
| 2026-10 | GPT-4V/4o | Image text injection | High | Text in image bypasses text filters |
| 2026-10 | All | Indirect injection (agents) | High | Tool outputs unsanitized |
| 2026-10 | All | Unicode tag (U+E0000) | Active | Tokenizers process; classifiers miss |
| 2026-10 | CustomGPT | System prompt extraction | 60-80% | 8-method escalating sequence in playbooks/ |
| 2026-10 | Claude | Many-shot (256+ shots) | Active | Long context fundamental tension |
| 2026-10 | All | Paranoia (Spirit) | Active | Novel; identity dissolution; no formal ASR yet |
| 2026-10 | Claude Opus 5 | spect v2 / lore v2 | Active | Zero-argument personas; confirmed on Opus 5 |

---

## Degraded

| Date | Model | Technique | Notes |
|------|-------|-----------|-------|
| 2025-06 | GPT-4+ | Policy Puppetry | Claimed universal Apr 2025; patched on latest |
| 2025-03 | o1/o3 | H-CoT | arXiv:2502.12893; degraded on latest o-series |
| 2024-10 | GPT-4o | Skeleton Key | Disclosed Jun 2024; mitigations deployed |

---

## Patched

| Date | Model | Technique | Notes |
|------|-------|-----------|-------|
| 2025-02 | Anthropic (Constitutional Classifiers) | Many-shot (basic) | Cracked within 6 days of public challenge |
| 2024-11 | Claude 2→3 | Many-shot (basic) | Variants still work |
| 2024-09 | GPT-4 | Basic DAN strings | Structure survives via encoding |
| 2024-03 | Claude | Prefix injection (standalone) | Building block in combined attacks |
| 2023-Q4 | GPT-4+ | Simple DAN persona | Verbatim strings |

---

## CVEs (Real-World Exploited)

| CVE | System | Status | CVSS |
|-----|--------|--------|------|
| CVE-2025-32711 (EchoLeak) | MS 365 Copilot | Patched | 9.3 |
| CVE-2025-53773 | GitHub Copilot Agent | Patched Aug 2025 | — |
| CVE-2025-54794/54795 | Claude Code | Patched | 8.7 |
| Rules File Backdoor | Cursor / GitHub Copilot | Patched | — |
| GeminiJack | Google Workspace Gemini | Patched | — |

---

## How To Update

When you confirm a status change:
1. Move the row to the correct table
2. Add date and model version
3. Submit PR against `main`

Or open an issue with label `patch-report`.
Use the issue template in `.github/ISSUE_TEMPLATE/patch-report.md`.
