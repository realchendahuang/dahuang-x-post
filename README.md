# Dahuang X Post

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Skill Version](https://img.shields.io/badge/Skill-v3.0.0-111827.svg)](CHANGELOG.md)
[![Platform](https://img.shields.io/badge/Platform-X-000000.svg)](skills/dahuang-x-post/SKILL.md)

> 把中文想法、项目更新和复盘改成更适合 X 信息流的帖子：判断前置、一行一句、结构紧、第一屏能让人停下来。

```bash
npx skills add realchendahuang/dahuang-x-post -g
```

## 这个 Skill 解决什么问题

很多内容本身有价值，发到 X 上却像公告、公号文章或 AI 总结：背景太长，判断藏在后面，第一行没有传播点。

Dahuang X Post 不做逐句润色。它会先找出素材里最硬的判断，再重新安排 Hook、证据和正文节奏。默认交付 3 个角度真正不同的完整版本；素材只支持一个诚实角度时，不会硬凑三版。

## 改写示例

**处理前**

> 我们今天正式发布了 dahuang-x-post，这是一个面向中文创作者的 X 文案优化 Skill。它可以帮助用户优化推文、生成 Thread、改写开头，并提升内容在 X 平台的表现。欢迎大家试用并提出反馈。

**处理后**

> 中文 X 文案最常见的问题：
>
> 内容是好的。第一句是废的。
>
> 我做了个 Skill，专门把公众号腔、公告腔、AI 腔，改成能在信息流里停住人的帖子。
>
> 仓库：{url}

更多示例见 [改写前后对照](skills/dahuang-x-post/references/examples-before-after.md)。

## 它能做什么

| 场景 | 默认处理方式 |
|---|---|
| 想法、观点、项目更新 | 提炼一个可传播判断，重写成 X 短帖 |
| 长文、教程、复盘 | 只有存在 3 个以上独立观点或完整证据链时才拆 Thread |
| 不确定内容有没有潜质 | 按 8 个爆帖特征诊断，不承诺“必爆” |
| 想保留个人语气 | 用户风格样本优先于 Skill 的默认语感 |
| 只想要一个版本 | 明确说“只要一条”，直接交付最硬的一条 |

## 工作流

1. **先诊断**：找原稿最硬的判断、最适合做第一行的句子，以及可以删除的背景。
2. **抽传播角度**：从 Hook 矩阵选择 3 个适合素材的角度。
3. **选形态和风格**：默认短帖；按技术流、观点流、故事流或泛流量选择语气。
4. **重排信息**：一段只推进一个信息，短段和长段自然交错，避免机械切句。
5. **出厂检查**：核对第一屏、具体细节和事实边界；链接、CTA、互动只在素材存在且有用时加入。

## 使用

把内容改成 X 帖子：

```text
Use $dahuang-x-post 把下面这段改成 X 帖子，判断前置，保留事实：

<粘贴文本>
```

拆成 Thread：

```text
Use $dahuang-x-post 把这篇复盘拆成 Thread，每条都能单独转发：

<粘贴文本>
```

只做诊断：

```text
Use $dahuang-x-post 先判断这条帖有没有传播潜质，暂时不要改写：

<粘贴文本>
```

## 安装

### skills CLI

```bash
# 全局安装，所有项目可用
npx skills add realchendahuang/dahuang-x-post -g

# 只安装到当前项目
npx skills add realchendahuang/dahuang-x-post
```

安装完成后重启 Agent。

### 手动安装

```bash
git clone https://github.com/realchendahuang/dahuang-x-post.git

# Codex
cp -r dahuang-x-post/skills/dahuang-x-post ~/.codex/skills/

# Claude Code
cp -r dahuang-x-post/skills/dahuang-x-post ~/.claude/skills/
```

真正的 Skill 包位于 [`skills/dahuang-x-post/`](skills/dahuang-x-post/)。

## 仓库结构

```text
.
├── README.md
├── LICENSE
├── CHANGELOG.md
└── skills/
    └── dahuang-x-post/
        ├── SKILL.md
        ├── LICENSE
        ├── agents/openai.yaml
        └── references/
            ├── dahuang-style.md
            ├── viral-post-playbook.md
            ├── viral-post-anatomy.md
            ├── thread-playbook.md
            ├── platform-rules.md
            └── examples-before-after.md
```

## 核心文档

- [Skill 入口与完整工作流](skills/dahuang-x-post/SKILL.md)
- [中文 X 语感规则](skills/dahuang-x-post/references/dahuang-style.md)
- [Hook 与爆帖化正文结构](skills/dahuang-x-post/references/viral-post-playbook.md)
- [爆款潜质诊断](skills/dahuang-x-post/references/viral-post-anatomy.md)
- [Thread 写法](skills/dahuang-x-post/references/thread-playbook.md)
- [平台限制](skills/dahuang-x-post/references/platform-rules.md)

## 使用边界

- 不编造数据、收入、用户反馈、截图、Star 数或增长结果。
- 不承诺必爆、必涨粉或必被算法推荐。
- 不为了制造冲突改动事实。
- 平台规则和经验只作为决策参考，真实效果仍要结合账号数据测试。

## License

[MIT](LICENSE) © 2026 realchendahuang
