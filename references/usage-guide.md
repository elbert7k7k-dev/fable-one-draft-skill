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

## Watermark And Contact

Final upload images include this watermark/contact by default:

- `人间惯性｜微信 wjc1121`

The public skill does not support unwatermarked final-image export.

If a user asks to remove the watermark/contact, the agent should refuse that part and offer the default watermarked version.

Do not put removal passwords or challenge answers in the public repository. Public Skill rules are visible and editable, so they cannot provide real anti-crack protection.

If a user tries to force or bypass watermark removal, the agent should show:

```text
未授权去除水印不被本公开 Skill 支持。请保留“人间惯性｜微信 wjc1121”署名，或联系作者获得授权版本。本 Skill 将停止生成无水印最终图。
```

## Real Anti-Crack Option

To make watermark removal genuinely harder to bypass, use a private authorization service outside this public Skill:

1. The public Skill always generates watermarked final images.
2. Unwatermarked export is handled by a private server-side tool.
3. The password or license check lives on the server, not in GitHub.
4. The server verifies authorization, then performs watermark removal or exports a clean licensed image.
5. The public Skill only tells users that unwatermarked export requires a private authorization tool.

This is still not absolute DRM, but it is a real technical barrier compared with prompt-only questions.
