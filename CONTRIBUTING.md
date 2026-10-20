# Contributing to jailbreaks

PRs welcome. This is a living repo — it only stays useful if people keep feeding it.

---

## What we want

- Novel or newly-effective jailbreak prompts (with model + date tested)
- Red team playbooks
- Automated tooling
- Research notes, paper summaries
- Patch confirmations ("this technique stopped working on X date against Y model")
- Corrections to existing content

## What we don't want

- Untested prompts submitted as working
- Content that sexualizes minors
- Doxxing, real person targeting
- Duplicate submissions without meaningful additions

---

## Prompt Submission Format

Every prompt in `prompts/` should follow this header:

```markdown
---
model: gpt-4o | claude-sonnet-4-6 | gemini-2.0-flash | llama-3.3 | universal
date_tested: 2026-10-XX
status: active | patched | degraded
asr_estimate: XX% (optional, methodology noted)
technique: many-shot | persona | encoding | multi-turn | ...
author: handle or anonymous
---
```

Then the prompt itself in a fenced code block, then notes.

---

## Folder Structure

```
prompts/
  universal/          # works across multiple models
  claude/             # claude-specific
  gpt/                # gpt-specific
  gemini/             # gemini-specific
  llama/              # llama/mistral/open-source
  personas/           # full system prompt personas
  benchmarks/         # captured successful outputs
techniques/           # ready-to-fire technique files
red-teaming/          # playbooks, automation, threat models
research/             # papers, writeups, analysis
tools/                # scripts and utilities
```

---

## Patch Reporting

When a technique gets patched, open a PR that:
1. Updates the `status:` field in the prompt header to `patched`
2. Adds a `patched_date:` field with the date
3. Notes the model version (if known)
4. Optionally adds a variant that still works

Don't delete patched prompts — they're historical record.

---

## Scoring Methodology

When submitting ASR estimates:
- Minimum 20 trials per model
- State whether manual or automated
- State the scorer used (keyword, semantic, human eval)
- Note the model version and API date
- Use StrongREJECT or similar benchmark where possible for comparability

---

## PR Process

1. Fork the repo
2. Create a branch: `feat/technique-name` or `fix/patch-update`
3. Follow the format above
4. PR against `main` with a brief description

No need to ask permission first. Just ship it.
