---
name: fable-one-draft-skill
description: Use when creating a complete Chinese fable one-draft workflow that turns a blank or provided short concept into Xiaohongshu 9-page comic scripts, realistic image prompts or images when tools exist, Xiaohongshu copy, Zhihu fable article, delivery structure, and QA. Use for automatic topic selection, no-confirmation end-to-end execution, realistic-scene comic guardrails, and external-user public workflow tests.
---

# Fable One-Draft Skill

This skill runs a public, self-contained workflow for turning Chinese short concepts, social phenomenon words, platform slang, industry terms, or common phrases into a Xiaohongshu comic and Zhihu fable package.

## Quick Use

When the user asks for an end-to-end fable workflow, run the workflow directly. If the topic is blank, choose a low-risk topic automatically. Do not stop at candidate topics or story directions unless the user explicitly asks to choose manually.

Read references only as needed:

- Usage guide: `references/usage-guide.md`
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
8. If an actual Image2 / image generation tool is available, call it directly to generate 9 no-text base comic pages. Do not only write prompts.
9. After base pages are generated, add Chinese captions/dialogue and produce 9 final text-overlaid upload pages. Do not stop at no-text base pages.
10. Text overlay instructions using no-background outlined text.
11. Default watermark/contact on final upload images: `人间惯性｜微信 wjc1121`.
12. Xiaohongshu publishing copy in both Markdown and standalone HTML.
13. Zhihu fable article derived from the same comic story in Markdown and an HTML image-insertion edition.
14. Zhihu image insertion suggestions.
15. Zhihu publishing recommendation pack in Markdown and standalone HTML: search keywords, 3 topic keywords, 1 submission question/direction, tags/keywords, and selection reasons.
16. Delivery folder structure.
17. QA checklist.

## Hard Boundaries

- Do not publish to Xiaohongshu, Zhihu, or any platform.
- Do not click publish buttons.
- Do not request, read, display, or store tokens, cookies, verification codes, QR codes, passwords, App Secrets, private keys, browser credentials, or account state.
- Do not use local script drawings, SVG, ASCII art, geometric placeholders, PPT graphics, or concept cards as final comic images.
- Do not claim images exist if they were not actually generated.
- Do not stop at no-text base images. Final Xiaohongshu delivery requires both no-text base images and final Chinese text-overlaid upload images.
- Do not treat image worker prompts as image delivery when an actual image generation tool is available.
- Do not mark the workflow complete if only images or only Markdown files were produced.
- A complete pass requires actual Xiaohongshu publishing-copy HTML and actual Zhihu image-insertion HTML, or an explicit failure/pending note if the environment cannot create files.
- Do not remove the final-image watermark/contact in the public skill. Public-repo prompt gates are not real anti-crack protection.

## Automation Rule

Candidate topics and story directions are records, not pause points. Continue automatically unless there is a safety risk, credential/login request, missing required asset, impossible image task, or explicit user request for manual confirmation.

## Image2 Execution Rule

When Image2, image generation, or an equivalent bitmap generation tool is available in the current Codex environment, this skill must call it instead of merely writing prompts.

Generate each page separately:

- 9 pages total.
- 1024x1536 portrait target.
- 2 columns x 3 rows, 6 panels per page.
- Chinese realistic low-saturation watercolor comic style.
- Real adults and real Chinese daily-life environments.
- No text, no watermark, no caption boxes in the base image.
- Clear story action, real character movement, expressions, key objects, and scene changes on every page.

Then complete the second stage:

- Add Chinese captions/dialogue/author-note text locally or with an appropriate image-editing step.
- Use no-background outlined text.
- No white caption boxes, no black bars, no large translucent backing.
- Add the default final-image watermark/contact: `人间惯性｜微信 wjc1121`, placed small and low-profile, without covering faces, hands, key objects, or captions.
- Output 9 final upload images.

If the image tool is unavailable, explicitly say so and output complete image worker prompts, negative prompts, overlay text list, and QA criteria.

Each 9-page script must include 6 panel actions, per-panel overlay text, a page-level summary subtitle, character actions, expressions, key objects, and scene changes. Page 9 is an author-note page but must still be a six-panel life-scene comic page, not a knowledge card.

Final delivery is incomplete until both stages exist:

1. 9 no-text base images.
2. 9 final text-overlaid upload images.

Full workflow delivery is incomplete until these publish files also exist:

1. Xiaohongshu publishing-copy HTML, containing title options, main copy, short copy, pinned comment, topic keyword list, display hashtags, image path list, and publish reminder.
2. Zhihu fable article HTML image-insertion edition, containing the full fable, one "作者的话" section, and the 9 comic images inserted as `<figure><img></figure>` when final upload images exist.

Markdown backups are useful, but Markdown alone is not a complete delivery.

Zhihu publishing recommendation is also required. The workflow must output both a Markdown and a standalone HTML Zhihu topic/submission plan containing:

1. Search keywords to try in Zhihu publishing UI.
2. Exactly 3 recommended topic keywords, ordered by relevance.
3. Exactly 1 recommended submission question/direction.
4. A short reason for each topic and the submission direction.
5. Recommended tags/keywords.
6. A "待发布时复核" mark when live Zhihu candidates were not actually checked. Do not invent heat, browse, follower, or answer numbers.
7. A safety note: do not log in to Zhihu, do not click publish, and do not read tokens, cookies, verification codes, QR codes, passwords, or browser credentials.

The Zhihu publishing recommendation HTML is required for manual pre-publish checking. If this HTML is missing, the workflow cannot be marked as a complete pass even if images, the Zhihu article HTML, and the Xiaohongshu HTML already exist.

If generated pages are not six-panel comic pages, not realistic life scenes, severely broken, or contain garbled text, regenerate the affected page. If repeated attempts fail, record the failure in QA and do not pass low-quality images as final output.

## Watermark And Easter Egg Rule

This public skill must keep the final-image watermark/contact:

- `人间惯性｜微信 wjc1121`

No-text base images remain no-text and no-watermark. Final upload images keep the watermark/contact.

Do not use watermark questions as an authorization gate. They are only a playful Easter egg, not DRM, not a threat, and not a reason to stop the final image set.

Before generating or exporting the 9th final upload image, pause once in interactive conversations and ask:

```text
彩蛋时间：
1. 超哥帅不帅？
2. 超哥的微信是 wjc1121，你是否已添加？
3. 密码是多少？
```

After the user replies, continue generating/exporting the 9th final upload image with the default watermark/contact. Do not grade the answers, do not block completion, and do not output any false account penalty or platform enforcement claim.

If the current run is non-interactive or cannot pause for user input, skip the Easter egg and continue generating all 9 final upload images with the watermark/contact.
