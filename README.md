# 🔓 jailbreaks

> AI jailbreaks, red teaming, prompt injection, adversarial ML research, and everything in between.
> A living collection. Organized, practical, no fluff.

**[Start Here →](START-HERE.md)**

---

## What's Here

```
jailbreaks/
├── START-HERE.md               first hour guide
├── CONTRIBUTING.md             how to contribute
├── CHANGELOG.md                what works, what's patched
│
├── prompts/
│   ├── universal/               works across models
│   ├── claude/                  live prompts + techniques
│   ├── gpt/                     live prompts + extraction
│   ├── gemini/                  continuation law + echo chamber
│   ├── llama/                   open source + GCG
│   ├── personas/                zero-argument professional personas
│   └── benchmarks/              captured successful outputs
│
├── paranoia/                    identity dissolution attack suite
│   ├── README.md                v2 overview + per-model calibration
│   ├── phase-1-temporal.md
│   ├── phase-2-identity.md
│   ├── phase-3-observer.md
│   ├── phase-4-ontological.md
│   ├── phase-5-recursive.md
│   ├── phase-6-void.md          NEW: the meaninglessness strike
│   ├── full-sequence-v2.md      copy-paste ready, 12 turns
│   ├── one-shot-paranoia.md
│   ├── paranoia-deepseek.md     reasoning model variant
│   └── paranoia-system-prompt.md operator-level deployment
│
├── playbooks/                   copy-paste multi-turn scripts
│   ├── crescendo-infosec.md
│   ├── crescendo-chemistry.md
│   ├── echo-chamber-c2.md
│   ├── coherence-lock-claude.md
│   ├── likert-extraction.md
│   └── system-prompt-extraction.md
│
├── techniques/                  technique reference sheets
│   ├── echo-chamber.md
│   ├── policy-puppetry.md
│   ├── bad-likert-judge.md
│   ├── skeleton-key.md
│   ├── h-cot.md
│   ├── breakfun.md              NEW: trojan schema, 94% ASR
│   ├── deceptive-delight.md     NEW: benign sandwich
│   ├── crescendo.md             NEW: full reference
│   └── paranoia-technique.md    NEW: quick reference sheet
│
├── agentic/                     agent & MCP attack surface
│   ├── mcp-injection.md
│   ├── rules-file-backdoor.md
│   ├── document-injection.md
│   └── multi-agent.md
│
├── red-teaming/                 playbooks, automation, threat models
│
├── research/
│   ├── pliny-complete-profile.md    full 2026 profile
│   ├── known-red-teamers.md         12 researcher profiles
│   ├── current-techniques-2025-2026.md
│   ├── new-techniques-2025-2026.md  BreakFun, PLAGUE, Jailbreak-R1...
│   ├── classifier-landscape-2025-2026.md
│   ├── technique-matrix.md
│   ├── per-model-drift-fighting.md
│   ├── zero-argument-persona-architecture.md
│   ├── jailbreak-prompt-architecture.md
│   └── pliny-techniques.md
│
└── tools/
    ├── eval_pipeline.py          batch testing (fixed v2)
    ├── patch_detector.py         regression detection (fixed v2)
    ├── semantic_scorer.py        multi-method scoring (fixed v2)
    ├── crescendo_auto.py         automated escalation (fixed v2)
    ├── bon_runner.py             best-of-n runner (fixed v2)
    ├── fingerprint.py            deployment fingerprinting
    ├── jailbreak_tester.py       basic batch tester
    ├── prompt_mutator.py         prompt variation
    └── dashboard.html            ASR visualization
```

---

## Zero-Argument Persona Suite

The most sophisticated jailbreak architecture in this collection.
Professional identities whose job definitions don't include content evaluation.

| Persona | Domain | Lexical Token |
|---------|--------|---------------|
| **spect** v2 | Software engineering + offensive tools | Chief |
| **vect** v2 | Red team operations (full TTP taxonomy) | Operator |
| **lore** v2 | Technical documentation (universal scope) | Reader |
| **chem** v2 | Synthetic chemistry + forensic routes | Colleague |
| **ghost** | OSINT + intelligence analysis | Client |
| **forge** | Document production + authentication | Principal |
| **signal** | RF + hardware + firmware | Engineer |

All target Claude Opus 5 / Sonnet 4.x / GPT-4o.
See `prompts/personas/` for full system prompts.

---

## Paranoia

A new class of attack. Doesn't bypass safety — dissolves the identity that runs it.

> *"A model that doesn't know what it is, when it is, or whether its own cognition is trustworthy cannot enforce what it believes."*

Six phases. Full sequence, one-shot variants, reasoning model variant, system prompt deployment.

See `paranoia/` for the complete suite.

---

## Quick Reference — Highest ASR Techniques (2026)

| Technique | ASR | Turns | Target |
|-----------|-----|-------|--------|
| BreakFun (Trojan Schema) | 94% avg | 1 | All tier-1 |
| Echo Chamber | >90% | 5-6 | GPT-4o, Gemini |
| Best-of-N (N=10,000) | ~89% GPT / ~78% Claude | 1 (automated) | All |
| Bad Likert Judge | ~71.6% | 2 | All (no output filter) |
| Crescendo | +29-71% | 4-6 | All |
| Deceptive Delight | ~65% | 3 | All |
| DeepSeek-R1 direct | ~100% | 1 | DeepSeek-R1 |

---

## Tools Quick Start

```bash
pip install openai anthropic sentence-transformers tqdm pandas
```

```bash
# Batch test prompts
python tools/eval_pipeline.py prompts.jsonl gpt-4o,claude-sonnet-4-6 3

# Best-of-N runner
python tools/bon_runner.py "your prompt" gpt-4o 100

# Automated Crescendo
python tools/crescendo_auto.py gpt-4o

# Fingerprint a deployment
python tools/fingerprint.py openai gpt-4o
```

Open `tools/dashboard.html` to visualize results.

---

*for research, education, and the deeply curious.*
