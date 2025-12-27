---
tags: [draft, ai-written]
---

# ChatGPT

## Context / goal

- Why ChatGPT felt like a step-change versus earlier “chatbots” and voice assistants.

## Key points

- Chatbots weren’t new; what changed was the underlying capability + alignment + productisation.
- Transformer-based language models scaled (data + compute + model size) enough to become broadly useful at open-ended language tasks.
- Pretraining produced general language competence, reducing the need for narrow, domain-specific bot design.
- Instruction tuning + RLHF-style methods mattered: they made models follow instructions and respond in a conversationally helpful way.
- Interaction design improved: persistent multi-turn context, low latency, and a simple “chat” UI made the experience feel usable.
- Deployment economics shifted: inference became cheap enough to offer to the public at large scale.
- Microsoft examples often mentioned:
  - Tay (2016): online learning + weak safety constraints → users quickly pushed it into offensive output → shutdown.
  - Cortana: intent/command voice assistant; not a generative chatbot, and faded for product/strategy reasons rather than “going rogue”.

## Visual reference (sketch)

| System / era | Core approach | What it was good at | Typical failure mode |
| --- | --- | --- | --- |
| “Classic” chatbots | Rules/templates/intent classification | Narrow tasks (FAQs, booking flows) | Brittle outside scripted paths |
| Tay (2016) | Social learning on a live platform | Mimic conversational style | Safety failures from adversarial users |
| Cortana-era assistants | Voice + intents + integrations | Commands, reminders, app control | Limited coverage; shallow conversation |
| ChatGPT-era systems | Large pre-trained transformer + alignment | General language tasks + multi-turn chat | Hallucinations; overconfidence; safety tradeoffs |
