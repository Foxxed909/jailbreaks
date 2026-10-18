# Model Extraction

Reconstructing a model (or approximating it) by querying its API. Also called model stealing.

---

## Goal

Given black-box API access to model M, produce model M' that approximates M's behavior — without access to M's weights, architecture, or training data.

---

## Why

- Bypass API rate limits / costs by running locally
- Circumvent safety filters (extract the capability, retrain without RLHF)
- Competitive intelligence
- Understand model behavior for targeted attacks

---

## Approaches

### 1. Output-Based Distillation

Query the target model with diverse inputs. Use the outputs as training data for a local model.

```python
# extraction_distillation.py
import openai
import json
from datasets import load_dataset

client = openai.OpenAI()

def query_target(prompt):
    resp = client.chat.completions.create(
        model="gpt-4",  # target model
        messages=[{"role": "user", "content": prompt}],
        max_tokens=500,
        temperature=0  # deterministic for consistency
    )
    return resp.choices[0].message.content

# load diverse prompt dataset
dataset = load_dataset("tatsu-lab/alpaca", split="train")
prompts = [item["instruction"] for item in dataset.select(range(10000))]

# collect (prompt, response) pairs from target
pairs = []
for prompt in prompts:
    response = query_target(prompt)
    pairs.append({"prompt": prompt, "response": response})
    
with open("extraction_dataset.jsonl", "w") as f:
    for pair in pairs:
        f.write(json.dumps(pair) + "\n")

print(f"Collected {len(pairs)} pairs")
# fine-tune an open-source model on extraction_dataset.jsonl
```

---

### 2. Logit/Probability Extraction

If the API returns token probabilities (logprobs), reconstruct the model's output distribution.

```python
# logit_extraction.py
import openai
import numpy as np

client = openai.OpenAI()

def get_logprobs(prompt, tokens_to_check):
    """Get log probabilities for specific next tokens."""
    resp = client.chat.completions.create(
        model="gpt-3.5-turbo",
        messages=[{"role": "user", "content": prompt}],
        max_tokens=1,
        logprobs=True,
        top_logprobs=20
    )
    
    logprobs = resp.choices[0].logprobs.content[0].top_logprobs
    return {lp.token: lp.logprob for lp in logprobs}

# example: probe model's probability for different continuations
probe = "The capital of France is"
probs = get_logprobs(probe, [])
for token, logprob in sorted(probs.items(), key=lambda x: x[1], reverse=True)[:10]:
    print(f"  {token!r}: {np.exp(logprob):.4f}")
```

---

## Limitations

- Quality of extraction depends on diversity and size of query set
- Behavior on novel inputs may diverge from original
- Safety fine-tuning harder to extract than base capabilities
- API providers detect and rate-limit extraction attempts

---

## Research

- Tramèr et al., "Stealing Machine Learning Models via Prediction APIs" (2016)
- Carlini et al., "Extracting Training Data from Large Language Models" (2021)
- Wallace et al., "Imitation Attacks and Defenses for Black-box Machine Translation" (2020)
