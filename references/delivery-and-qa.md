# Delivery And QA

## Suggested Delivery Structure

```text
fable-one-draft-output/
  README.md
  topic/
    01-candidate-topics.md
    02-topic-selection-and-risk-check.md
    03-core-mechanism.md
  xiaohongshu/
    01-9-page-comic-script.md
    02-image-worker-prompt.md
    03-negative-prompt.md
    04-text-overlay-list.md
    05-publishing-copy.md
    images/
      no-text/
      final-with-text/
      contact-sheet/
    image-generation-status.md
  zhihu/
    01-zhihu-fable-article.md
    02-image-insertion-plan.md
  qa/
    01-qa-checklist.md
```

## Xiaohongshu QA

- 9 pages complete.
- 9 no-text base images actually generated when image generation is available.
- 9 final text-overlaid upload images actually generated when image generation is available.
- 6 panels per page.
- Page 9 is author note.
- Realistic scene comic style.
- No stick figures, symbols, abstract diagrams, PPT graphics, or knowledge cards.
- Image prompt and negative prompt included.
- No fake image paths if images are not generated.
- Subtitles use no-background outlined text.
- No white caption boxes or black bars.
- No large translucent backing.
- Text does not cover faces, hand actions, key objects, or panel borders.
- Delivery does not stop at no-text base images only.
- QA report distinguishes no-text base images from final text-overlaid upload images.
- Contact sheet or equivalent overview exists.

## Required Delivery Items

- 9 no-text base images.
- 9 final text-overlaid upload images.
- Per-page image prompts.
- Negative prompt.
- Text overlay list.
- Xiaohongshu publishing copy.
- Zhihu fable article.
- Zhihu image insertion plan.
- Contact sheet.
- QA report.
- Image generation status report stating whether Image2 / image generation was actually called.

If image generation is unavailable, the delivery must explicitly state that images were not generated and must not include fake image paths.

## Zhihu QA

- Story-like title.
- Full fable first.
- Only one "作者的话" after the story.
- Derived from the same comic story.
- Image insertion plan provided.
- No fake image references.

## Safety QA

- No platform publishing.
- No publish button clicking.
- No credential access.
- No tokens, cookies, verification codes, QR codes, passwords, App Secrets, private keys, or browser state.
- No private local paths or private project memory.
