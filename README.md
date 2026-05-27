# Fable One-Draft Skill

这是一个 Skill-only 仓库。下载后，整个仓库文件夹可以作为 Codex Skill 安装。

它用于把中文短词条、社会现象词、平台黑话、行业术语或流行短语，自动转成：

- 小红书 9 页漫画分镜
- 真人现实场景无字底图与最终叠字上传图
- 小红书发布文案 Markdown 与 HTML
- 知乎寓言故事成稿 Markdown 与图文插入版 HTML
- 图文插入建议
- 交付目录与 QA 清单

## 安装

把整个仓库文件夹复制到你的 Codex skills 目录，例如：

```text
.codex/skills/fable-one-draft-skill
```

确保复制后目录里能看到：

```text
fable-one-draft-skill/
  SKILL.md
  references/
```

## 使用

在 Codex 新对话中输入：

```text
请使用 fable-one-draft-skill，主题为空，自动选题并完整生成小红书漫画分镜、图片提示词、小红书发布文案 Markdown 与 HTML、知乎寓言成稿 Markdown 与图文插入版 HTML 和 QA。
```

如果当前 Codex 环境有 Image2 / image generation / 图片生成工具，Skill 必须直接调用图片工具逐页生成 9 张无字底图，并继续完成 9 张最终叠字上传图；如果没有，会明确说明不能直接生成图片，并输出完整图片 worker 提示词、负面提示词、叠字清单和 QA 标准。

只生成无字底图不算完成。完整图片交付必须包含：9 张无字底图、9 张最终叠字上传图、contact sheet 和 QA 报告。

只生成图片或只生成 Markdown 也不算完整通过。完整交付还必须包含小红书发布文案 HTML、知乎寓言成稿图文插入版 HTML，并在 QA 中检查这些 HTML 文件真实存在。

## 不包含内容

本仓库不包含私有项目记忆、真实交付图片、飞书页面、账号凭据、token、cookie、验证码、二维码、App Secret、私钥或浏览器状态。

## License

暂未添加开源许可证。未添加 license 时，默认保留所有权利。
