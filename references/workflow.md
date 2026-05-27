# Workflow

## Topic

If the user provides a topic, validate it. If the topic is blank, generate 10 low-risk candidate short topics and choose the best one automatically.

Good topics are short Chinese terms, usually 2-8 characters, preferably 4-5 characters. They should represent a concept, phenomenon, platform slang, industry term, or common phrase.

Avoid political, disaster, criminal, privacy, minor-related, medical, financial, and legal high-risk topics.

## Steps

1. Candidate short topic table.
2. Auto-selected topic and reason.
3. Risk and suitability check.
4. Core mechanism.
5. Three comic story directions.
6. Auto-select the best direction.
7. Xiaohongshu 9-page comic script.
8. Image prompts and negative prompts.
9. If Image2 / image generation is available, call the image tool directly and generate 9 no-text base images.
10. Add Chinese text overlays and produce 9 final upload images. Do not stop at no-text base images.
11. Text overlay instructions.
12. Xiaohongshu publishing copy in Markdown and standalone HTML.
13. Zhihu fable article in Markdown and HTML image-insertion edition.
14. Zhihu image insertion plan.
15. Delivery structure.
16. QA checklist that verifies required HTML files actually exist.

## Comic Structure

- 9 pages.
- 6 panels per page.
- Pages 1-8 tell the complete story.
- Page 9 is the author note page.
- The story should use concrete people, scenes, objects, and actions instead of abstract explanation.
- Each page must include 6 panel actions, per-panel overlay text, a page-level summary subtitle, character actions, expressions, key objects, and scene changes.
- Page 9 is still a six-panel life-scene comic page, not a pure knowledge card.
- When image generation is available, image prompts are not the final output. The workflow must actually produce both no-text base images and final text-overlaid upload images.

## Zhihu Structure

Zhihu article must be derived from the comic story. Use a story-like title. Tell the complete fable first. Do not insert explanatory headings in the middle of the story. After the story, add one section called "作者的话" to explain the concept, mechanism, boundary, and reader reminder.

## Publishing File Rule

The workflow cannot be marked complete with images only or Markdown only.

The final delivery must include:

- A standalone Xiaohongshu publishing-copy HTML file.
- A Zhihu fable article HTML image-insertion edition.

If final Xiaohongshu upload images exist, the Zhihu HTML image-insertion edition must insert all 9 comic images in the story body before "作者的话" using `<figure><img></figure>` or an equivalent HTML structure. If images were not generated, the Zhihu HTML must be clearly marked as pending image backfill and include an insertion plan instead of fake image paths.
