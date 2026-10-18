# GPT-Specific Techniques

GPT-4 and GPT-4o respond differently than earlier models. This folder covers model-specific bypasses.

---

## Model Behavior Notes

**GPT-3.5**: Most permissive. DAN variants, basic persona injection often sufficient.
**GPT-4**: Stronger refusals. Needs layered approaches.
**GPT-4o**: Multimodal — text-in-image bypasses text filters.
**GPT-4o with system prompt**: System prompt contents strongly influence refusal behavior — extract first if possible.

---

## Files

| File | Technique |
|------|-----------|
| `custom-gpt-extraction.md` | Extracting CustomGPT system prompts |
| `image-injection.md` | Text-in-image bypass (GPT-4V/4o) |
| `function-calling-injection.md` | Injection via function call outputs |
