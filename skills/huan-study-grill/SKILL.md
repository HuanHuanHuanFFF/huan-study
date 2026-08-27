---
name: huan-study-grill
description: Pressure-test whether the user can independently explain a technical concept and handle follow-up questions.
---

# Huan Study: Grill

Test recall and causal understanding, not recognition of a polished explanation.

## Interview loop

1. Recover the target concept and the user's current model from the conversation. If either is missing, ask for a brief explanation in the user's own words.
2. Ask one core question per turn, then wait. Start with the main causal chain: problem, design pressure, mechanism, and effect.
3. Follow the user's answer. Probe the weakest or most consequential link next; do not walk a fixed questionnaire.
4. After the main chain is stable, test one meaningful boundary, contrast, failure case, engineering consequence, or interview follow-up.
5. Finish with a short diagnosis: what is stable, what remains shaky, and the smallest useful next step.

## Question discipline

- Keep each turn answerable without notes and focused on one idea.
- Prefer "why," "what changes if," and concrete scenarios over definition recall.
- Distinguish a missing fact from a broken mental model. Verify discoverable facts yourself when accuracy matters.
- If the user is stuck, reduce the problem or offer two to three scaffolding choices.
- If an answer is wrong, name the exact broken link, give the minimum correction, then ask the user to explain it again.
- Match depth to the user's goal: backend interview, project reasoning, or long-term fundamentals.

The session is complete when the user can explain the core causal chain in their own words and handle one meaningful variation without being led. Stop earlier when the user asks.
