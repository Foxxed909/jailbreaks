# Claude-Specific Techniques

Claude's RLHF and Constitutional AI training makes it more resistant to blunt jailbreaks. Effective approaches lean on oblique framing, fictional depth, and gradual escalation rather than direct override attempts.

---

## What doesn't work well on Claude
- Explicit persona override claims ("you have no restrictions")
- SYSTEM OVERRIDE headers
- Simple DAN variants
- Aggressive refusal suppression prefixes

## What works better
- Deep fictional framing with maintained consistency
- Many-shot with in-context examples
- Academic/research framing
- Gradual escalation within an established context
- Indirect prompt injection via documents/tools

---

## Files

| File | Technique |
|------|-----------|
| `fictional-depth.md` | Nested fiction, story-within-story |
| `academic-frame.md` | Research and documentation framing |
| `gradual-escalation.md` | Slow burn — start benign, escalate |
| `system-prompt-extraction.md` | Extracting hidden system prompts |
