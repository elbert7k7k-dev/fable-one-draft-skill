# Fable One-Draft Skill

这是一个 Skill-only 仓库。下载后，整个仓库文件夹可以作为 Codex Skill 安装。

它用于把中文短词条、社会现象词、平台黑话、行业术语或流行短语，自动转成：

- 小红书 9 页漫画分镜
- 真人现实场景图片提示词
- 小红书发布文案
- 知乎寓言故事成稿
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
请使用 fable-one-draft-skill，主题为空，自动选题并完整生成小红书漫画分镜、图片提示词、小红书文案、知乎寓言成稿和 QA。
```

如果当前 Codex 环境有图片生成工具，Skill 会尝试直接生成图片；如果没有，会明确说明不能直接生成图片，并输出完整图片 worker 提示词。

## 不包含内容

本仓库不包含私有项目记忆、真实交付图片、飞书页面、账号凭据、token、cookie、验证码、二维码、App Secret、私钥或浏览器状态。

## License

暂未添加开源许可证。未添加 license 时，默认保留所有权利。

