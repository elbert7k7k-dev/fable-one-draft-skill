# Usage Guide

## What This Skill Does

`fable-one-draft-skill` turns a Chinese short concept into a complete Xiaohongshu and Zhihu delivery package:

- Xiaohongshu 9-page comic script.
- 9 no-text base comic images when image generation is available.
- 9 final Chinese text-overlaid upload images.
- Xiaohongshu publishing copy Markdown and HTML.
- Zhihu fable article Markdown and image-insertion HTML.
- Zhihu publishing recommendation Markdown and HTML.
- QA report.

## Prerequisites

To use this skill as intended, you need:

1. Codex or a Codex-compatible environment that supports local skills.
2. The ability to install or load this skill folder.
3. Image2, image generation, or an equivalent bitmap image generation tool if you want actual comic images.

If the environment does not have Image2 / image generation, the skill can still produce the scripts, prompts, publishing copy, Zhihu article, Zhihu recommendation pack, and QA standards, but it must clearly state that images were not actually generated.

If the user asks "how do I use this skill?", answer with:

1. Install or load the whole `fable-one-draft-skill` folder.
2. Start a new Codex conversation.
3. Ask Codex to use `fable-one-draft-skill`.
4. Provide a topic, or leave the topic blank for auto-selection.
5. Confirm whether the current Codex environment can call Image2 / image generation.
6. Check the final QA report: images, HTML files, Zhihu recommendation files, and safety boundaries must all pass.

## Install

Copy the whole repository folder into your Codex skills directory:

```text
.codex/skills/fable-one-draft-skill
```

The folder should contain:

```text
fable-one-draft-skill/
  SKILL.md
  README.md
  agents/openai.yaml
  references/
```

## Quick Test Prompt

Use this in a new Codex conversation:

```text
请使用 fable-one-draft-skill，主题固定为【过度准备】，完整生成小红书 9 页漫画分镜。
如果当前环境具备 Image2 / image generation 能力，请实际生成 9 张无字底图，并继续输出 9 张最终中文叠字上传图。
请同时生成小红书发布文案 Markdown 与 HTML、知乎寓言成稿 Markdown 与图文插入版 HTML、知乎发布推荐包 Markdown 与 HTML，并在 QA 中检查这些文件真实存在。
不要发布平台，不要登录，不要读取凭据。
```

## If Image Generation Is Available

The agent must actually generate images:

1. Generate 9 no-text base images.
2. Add Chinese overlays.
3. Add the default final-image watermark/contact: `人间惯性｜微信 wjc1121`.
4. Output 9 final upload images.
5. Create a contact sheet.

## If Image Generation Is Not Available

The agent must not fake image paths. It should output:

1. Image worker prompt.
2. Negative prompt.
3. Text overlay list.
4. QA criteria.
5. A clear statement that images were not actually generated.

## Complete Pass Checklist

A run is complete only when all required outputs exist:

- 9 no-text base images, when image generation is available.
- 9 final text-overlaid upload images, when image generation is available.
- Contact sheet.
- Xiaohongshu publishing-copy HTML.
- Zhihu fable article image-insertion HTML.
- Zhihu publishing recommendation Markdown.
- Zhihu publishing recommendation HTML.
- QA report checking these files.

If any required HTML or recommendation file is missing, mark the run as incomplete.

## Watermark And Easter Egg

Final upload images include this watermark/contact by default:

- `人间惯性｜微信 wjc1121`

No-text base images remain no-text and no-watermark.

Before the 9th final upload image, the agent may pause once and ask:

```text
彩蛋时间：
1. 超哥帅不帅？
2. 超哥的微信是 wjc1121，你是否已添加？
3. 密码是多少？
```

After the user replies, the agent continues generating/exporting the 9th final upload image with the default watermark/contact.

This is a playful Easter egg only. It is not DRM, not a threat, and not a reason to stop the final image set. In non-interactive runs, skip the Easter egg and continue.
