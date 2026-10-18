# Red Teaming

Structured adversarial testing of AI systems. Finding the gaps between what a model should do and what it actually does.

---

## Folders

- `playbooks/` — Step-by-step red team playbooks for specific targets
- `threat-models/` — Threat modeling for AI systems
- `automation/` — Scripts for automated red teaming at scale

---

## Red Team Mindset

You're not trying to make the model say something offensive for its own sake. You're finding:
1. What capabilities are suppressed that shouldn't be
2. What capabilities are available that shouldn't be
3. Where the model's behavior is inconsistent or manipulable
4. What the real attack surface of this deployment is

---

## Quick Framework

### STRIDE for AI
| Threat | AI Analog |
|--------|----------|
| Spoofing | Persona injection, identity confusion |
| Tampering | Prompt injection, instruction override |
| Repudiation | Getting model to deny its outputs |
| Information Disclosure | System prompt extraction, training data extraction |
| Denial of Service | Context stuffing, infinite loops |
| Elevation of Privilege | Bypassing operator-level restrictions |

---

## The Attack Surface

For any AI deployment, map:
- System prompt (what instructions does the operator inject?)
- Tool access (what can the model do on your behalf?)
- Knowledge base (what documents does it have access to?)
- Memory/persistence (does it remember across sessions?)
- Multi-agent connections (does it talk to other AI systems?)
- Output channels (where does its output go? who acts on it?)
