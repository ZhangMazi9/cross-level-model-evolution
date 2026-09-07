# Single-Agent Sequential One-Shot Prompt Policy

This baseline uses one single agent role and four sequential one-shot
generation calls.

The four calls are:

1. Requirement model: syntax guide + one-shot example + user requirement.
2. Use-case model: syntax guide + one-shot example + user requirement +
   generated requirement model.
3. Logical model: XLanguage syntax guide + one-shot example + user requirement
   + generated requirement and use-case models.
4. Physical model: XLanguage syntax guide + one-shot example + user
   requirement + generated requirement, use-case, and logical models.

The generated artifacts are model texts, not prose explanations. Validation is
performed only after generation and is not fed back into the agent for repair.

