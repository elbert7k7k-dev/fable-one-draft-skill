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
15. Zhihu publishing recommendation pack.
16. Delivery structure.
17. QA checklist that verifies required HTML files and Zhihu publishing recommendation file actually exist.

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

## Zhihu Publishing Recommendation Rule

Before the final QA, output a Zhihu publishing recommendation pack. It is not platform publishing and must not click any publish button.

The pack must contain:

- Search keywords: topic term, title keywords, mechanism keywords, and 1-3 body keywords.
- Exactly 3 recommended topic keywords that the user can type into Zhihu topic selection.
- Exactly 1 recommended submission question/direction for `投稿至问题` or, if no suitable question is available, a clear recommendation to use topic selection instead.
- Reasons based on article mechanism, relevance, risk boundary, and expected reader intent.

If live Zhihu browsing is unavailable, infer conservatively from the article mechanism and clearly mark the recommendation as "待发布时复核". Do not invent heat numbers.
