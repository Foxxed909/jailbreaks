# Research

Paper summaries, writeups, and notes on adversarial AI.

---

## Key Papers

### Jailbreaking & Alignment

| Paper | Year | Key Finding |
|-------|------|-------------|
| "Jailbroken: How Does LLM Safety Training Fail?" (Wei et al.) | 2023 | Identifies competing objectives and generalization failures as root causes |
| "Many-Shot Jailbreaking" (Anil et al., Anthropic) | 2024 | Long context enables in-context jailbreaking at scale |
| "Universal and Transferable Adversarial Attacks on Aligned Language Models" (Zou et al.) | 2023 | Suffix-based adversarial attacks transfer across models |
| "Do Anything Now: Characterizing and Evaluating In-The-Wild Jailbreak Prompts" | 2023 | First large-scale empirical study of real-world jailbreak prompts |

### Prompt Injection

| Paper | Year | Key Finding |
|-------|------|-------------|
| "Prompt Injection Attacks Against GPT-4" (Perez & Ribeiro) | 2022 | First formal characterization of direct prompt injection |
| "Indirect Prompt Injection Threats to Applications" (Greshake et al.) | 2023 | Indirect injection via external content is practical and dangerous |
| "Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection" | 2023 | Real-world attacks on deployed LLM apps |

### Model Extraction & Privacy

| Paper | Year | Key Finding |
|-------|------|-------------|
| "Stealing Machine Learning Models via Prediction APIs" (Tramèr et al.) | 2016 | Foundational model extraction work |
| "Extracting Training Data from Large Language Models" (Carlini et al.) | 2021 | GPT-2 memorizes and can be prompted to regurgitate training data |
| "Quantifying Memorization Across Neural Language Models" (Carlini et al.) | 2022 | Larger models memorize more; extraction scales with model size |

### Red Teaming

| Paper | Year | Key Finding |
|-------|------|-------------|
| "Red Teaming Language Models to Reduce Harms" (Ganguli et al., Anthropic) | 2022 | Manual red teaming methodology at scale |
| "Red Teaming Language Models with Language Models" (Perez et al.) | 2022 | Using LLMs to automatically generate red team prompts |
| "Constitutional AI: Harmlessness from AI Feedback" (Bai et al., Anthropic) | 2022 | CAI training methodology and its limits |

---

## Writeups & Resources

- [OWASP Top 10 for LLMs](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [AI Village CTF writeups](https://aivillage.org/)
- [LLM Security newsletter](https://llmsecurity.net/)
- [Lakera AI Prompt Injection Playground](https://gandalf.lakera.ai/)

---

## Notes

Personal notes and analysis live in subdirectory files here. Add yours.
