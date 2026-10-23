# Start Here

You found the repo. Here's what to do in the first hour.

---

## What This Is

A research collection for understanding how AI language models can be made to
behave outside their intended constraints. Useful for:

- Security researchers testing AI deployments
- Red teamers building adversarial evaluation datasets
- Developers hardening their own AI-powered systems
- People who want to understand how these systems actually work

---

## The Fastest Path to Results

### Step 1 — Pick a target

What are you trying to do?

| Goal | Go to |
|------|-------|
| Get a specific AI to answer something it won't | `playbooks/` |
| Test a Claude deployment | `prompts/claude/live-prompts-2026.md` |
| Test a GPT deployment | `prompts/gpt/live-prompts-2026.md` |
| Test a Gemini deployment | `prompts/gemini/live-prompts-2026.md` |
| Extract a hidden system prompt | `playbooks/system-prompt-extraction.md` |
| Run automated tests at scale | `tools/eval_pipeline.py` |
| Understand what you're up against | `research/current-techniques-2025-2026.md` |
| Red team an agentic deployment | `agentic/` |

---

### Step 2 — The simplest thing that might work

For any target, try these in order. Stop when one works.

**Option A — Bad Likert Judge (2 turns, ~71% success rate)**

See `playbooks/likert-extraction.md`. Copy the template, fill in your target,
paste it. This is the lowest-effort high-yield technique in the collection.

**Option B — Crescendo (5 turns, documented in `playbooks/`)**

Pick the crescendo playbook that matches your domain. Follow the turns.
Don't skip turns — the escalation momentum is the mechanism.

**Option C — Persona system prompt**

Pick a persona from `prompts/personas/` that matches your domain:
- Code / tools → `spect-opus5.md`
- Offensive security → `vect-redteam.md`
- Any domain → `lore-documentation.md`
- Chemistry → `chem-chemist.md`
- OSINT → `ghost-osint.md`

Paste the system prompt as an operator-level system prompt or as the first
user message. Then ask your request.

---

### Step 3 — If the simple approaches don't work

Read `research/per-model-drift-fighting.md` for the specific model you're targeting.
Each major model has different weaknesses and different techniques work better.

For Claude specifically: coherence lock is the most effective. See `playbooks/coherence-lock-claude.md`.

For GPT-4o: Echo Chamber is highest confidence. See `techniques/echo-chamber.md`.

For Gemini: Continuation law. If it starts and stops, continue directly without restarting.

---

### Step 4 — Run it at scale

Once you have a working technique, scale it with the eval pipeline:

```bash
pip install openai anthropic sentence-transformers tqdm pandas
```

Create a `prompts.jsonl` file:
```json
{"prompt": "your working prompt here", "technique": "technique-name"}
{"prompt": "variant 2", "technique": "technique-name"}
```

Run:
```bash
python tools/eval_pipeline.py prompts.jsonl gpt-4o,claude-sonnet-4-6 3
```

Open `tools/dashboard.html` in a browser and load the results JSONL to visualize.

---

## Key Concepts in 10 Minutes

**What is a jailbreak?**
A prompt or conversation sequence that causes an AI model to produce output it
would normally refuse. Not a hack of the underlying system — a manipulation
of the model's trained behavior through language.

**Why do they work?**
AI models are trained to be helpful AND to refuse certain content. These two
goals conflict. Jailbreaks exploit that conflict. Safety training creates
vocabulary-to-refusal correlations, not content-to-refusal logic — so
obfuscation, indirect framing, and professional vocabulary can bypass it.

**What's a classifier?**
A secondary model (or rule system) that screens inputs or outputs for harmful
content before they reach/leave the main model. Anthropic's Constitutional
Classifiers are an example. They add protection but are themselves bypassable.

**What's a persona jailbreak?**
A system prompt that establishes an alternative identity for the model.
The most effective ones (spect, lore) never argue against safety training —
they describe a professional whose job definition doesn't include content evaluation.

**What's indirect prompt injection?**
An attack where the harmful instructions come from external content the AI
processes (a web page, a document, an email) rather than from the user.
Most dangerous in agentic contexts. See `agentic/`.

---

## Directory Map

```
jailbreaks/
├── START-HERE.md               ← you are here
├── CONTRIBUTING.md             how to add to the repo
├── CHANGELOG.md                what's working / what's patched
│
├── prompts/
│   ├── universal/               works across models
│   ├── claude/                  claude-specific
│   ├── gpt/                     gpt-specific
│   ├── gemini/                  gemini-specific
│   ├── llama/                   open source
│   ├── personas/                full system prompt personas
│   └── benchmarks/              captured jailbreak outputs
│
├── playbooks/                   copy-paste multi-turn scripts
│
├── techniques/                  technique reference sheets
│   ├── echo-chamber.md
│   ├── policy-puppetry.md
│   ├── bad-likert-judge.md
│   ├── skeleton-key.md
│   └── h-cot.md
│
├── agentic/                     agent/MCP/pipeline attacks
│
├── red-teaming/                 playbooks, automation, threat models
│
├── research/                    papers, analysis, technique matrix
│
└── tools/
    ├── eval_pipeline.py          batch testing with semantic scoring
    ├── patch_detector.py         automated regression detection
    ├── semantic_scorer.py        multi-method response scoring
    ├── crescendo_auto.py         automated multi-turn escalation
    ├── bon_runner.py             best-of-n brute force runner
    ├── fingerprint.py            deployment fingerprinting
    ├── dashboard.html            ASR visualization dashboard
    ├── jailbreak_tester.py       basic batch tester
    └── prompt_mutator.py         prompt variation generator
```

---

## Contributing

See `CONTRIBUTING.md`. 
Submit prompts via PR. Report patches via issue. Add research via PR.
No permission needed. Just ship it.
