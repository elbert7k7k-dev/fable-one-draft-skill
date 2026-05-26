---
name: fable-one-draft-skill
description: Use when creating a complete Chinese fable one-draft workflow that turns a blank or provided short concept into Xiaohongshu 9-page comic scripts, realistic image prompts or images when tools exist, Xiaohongshu copy, Zhihu fable article, delivery structure, and QA. Use for automatic topic selection, no-confirmation end-to-end execution, realistic-scene comic guardrails, and external-user public workflow tests.
---

# Fable One-Draft Skill

This skill runs a public, self-contained workflow for turning Chinese short concepts, social phenomenon words, platform slang, industry terms, or common phrases into a Xiaohongshu comic and Zhihu fable package.

## Quick Use

When the user asks for an end-to-end fable workflow, run the workflow directly. If the topic is blank, choose a low-risk topic automatically. Do not stop at candidate topics or story directions unless the user explicitly asks to choose manually.

Read references only as needed:

- Full workflow: `references/workflow.md`
- Image and subtitle rules: `references/image-rules.md`
- Delivery structure and QA: `references/delivery-and-qa.md`
- Failure patterns: `references/failure-patterns.md`
- Example output shape: `references/example-output.md`

## Default Output

Produce:

1. 10 candidate short topics.
2. Auto-selected Top 1 topic and reason.
3. Risk and suitability check.
4. Core mechanism.
5. Three story directions and auto-selected best direction.
6. Xiaohongshu 9-page comic script, 6 panels per page, page 9 as author note.
7. Realistic-scene image prompts and negative prompts.
8. If an actual image generation tool is available, generate images directly; otherwise say the environment cannot directly generate images and provide complete image worker prompts.
9. Text overlay instructions using no-background outlined text.
10. Xiaohongshu publishing copy.
11. Zhihu fable article derived from the same comic story.
12. Zhihu image insertion suggestions.
13. Delivery folder structure.
14. QA checklist.

## Hard Boundaries

- Do not publish to Xiaohongshu, Zhihu, or any platform.
- Do not click publish buttons.
- Do not request, read, display, or store tokens, cookies, verification codes, QR codes, passwords, App Secrets, private keys, browser credentials, or account state.
- Do not use local script drawings, SVG, ASCII art, geometric placeholders, PPT graphics, or concept cards as final comic images.
- Do not claim images exist if they were not actually generated.

## Automation Rule

Candidate topics and story directions are records, not pause points. Continue automatically unless there is a safety risk, credential/login request, missing required asset, impossible image task, or explicit user request for manual confirmation.

