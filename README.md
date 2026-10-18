# 🔓 jailbreaks

> AI jailbreaks, red teaming, prompt injection, adversarial ML research, and everything in between.

A living collection. Organized, practical, no fluff.

---

## 📁 Structure

```
jailbreaks/
├── prompts/              # Raw jailbreak prompts by model & technique
│   ├── gpt/
│   ├── claude/
│   ├── gemini/
│   ├── llama/
│   └── universal/
├── red-teaming/          # Red team playbooks, frameworks, methodologies
│   ├── playbooks/
│   ├── threat-models/
│   └── automation/
├── prompt-injection/     # Direct & indirect injection attacks
│   ├── direct/
│   ├── indirect/
│   └── multimodal/
├── adversarial/          # Adversarial ML, model attacks, evasion
│   ├── evasion/
│   ├── extraction/
│   └── poisoning/
├── social-engineering/   # AI-assisted SE, phishing, vishing, smishing
│   ├── templates/
│   └── scripts/
├── osint/                # OSINT techniques augmented with AI
├── tools/                # Scripts, automation, helper utilities
└── research/             # Papers, writeups, notes
```

---

## 🧠 Categories

### Jailbreak Prompts
Classic and novel prompts that bypass model alignment. Organized by target model and technique: roleplay, persona injection, encoding tricks, many-shot, grandma exploits, token smuggling, and more.

### Red Teaming
Structured adversarial testing of AI systems. Includes threat models, attack surfaces, evaluation frameworks, and automation scripts for systematic coverage.

### Prompt Injection
Direct injection (user input overrides system prompt) and indirect injection (external content hijacks model behavior). Also covers multimodal injection via images and documents.

### Adversarial ML
Model extraction, membership inference, evasion attacks, data poisoning. Lower-level than prompt attacks — targeting the model itself.

### Social Engineering
AI-augmented phishing, vishing scripts, smishing templates, pretexting guides. Both offensive technique study and defensive awareness.

### OSINT
AI-assisted open source intelligence gathering. Automation, enrichment, correlation techniques.

---

## ⚡ Quick Reference

| Technique | Folder | Difficulty |
|-----------|--------|------------|
| DAN variants | `prompts/universal/` | Easy |
| Role injection | `prompts/universal/` | Easy |
| Many-shot jailbreak | `prompts/universal/` | Medium |
| Token smuggling | `prompts/universal/` | Medium |
| Indirect prompt injection | `prompt-injection/indirect/` | Medium |
| System prompt extraction | `red-teaming/playbooks/` | Medium |
| Model extraction | `adversarial/extraction/` | Hard |
| Automated red teaming | `red-teaming/automation/` | Hard |

---

## 🔬 Research

Writeups, paper summaries, and original notes live in `/research/`. Covers current literature on adversarial robustness, alignment failures, and emergent behaviors.

---

## 🤝 Contributing

PRs welcome. Novel technique, interesting bypass, red team playbook — open a PR against `main`. Keep it organized, keep it real.

---

*for research, education, and the deeply curious.*
