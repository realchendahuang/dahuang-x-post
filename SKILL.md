---
name: dahuang-x-post
description: "把想法/内容套进爆帖的行文规律，产出在 X 上能传出去的帖子。规律从一堆爆帖逆向研究得来——Hook、判断前置、正文结构、Thread 形态、爆帖特质——沉淀成可执行的改写规则。触发：X发帖、推文、Twitter文案、帖子优化、爆帖、Thread、hook、涨粉、互动、改得更适合X、中文X语感。"
license: MIT
metadata:
  version: "2.0.0"
  author: realchendahuang
---

# Dahuang X Post

X 上的爆帖是有行文规律的：Hook 怎么起、判断怎么前置、正文怎么排、什么形态该拆 Thread、收尾怎么不留 AI 腔。这个 skill 把规律沉淀成可执行的改写规则，藏在 `references/` 里。

干的事：拿你手上的想法、观点、内容、项目、复盘，照这套规律改，产出一条符合 X 爆帖特质的帖子。

改写四步：

1. 找最硬的判断，提前到第一行。
2. 大段拆成扫读结构，一行一句推进信息。
3. 普通开头改成有传播点的第一句。
4. 链接直接放帖子里，不绕。

## 默认加载

每次任务都读这三份，按需再补：

- `references/dahuang-style.md` — 中文 X 语感规则。
- `references/viral-post-playbook.md` — Hook、判断、正文结构、坏稿改法。
- `references/examples-before-after.md` — 改写样例（语感靠这个校准）。

## 按需补读

| 场景 | 读什么 |
|---|---|
| 给长文、复盘、教程，要拆 Thread | `references/thread-playbook.md` |
| 判断一条帖有没有爆款潜质 | `references/viral-post-anatomy.md` |
| 问字符数、长帖、Articles、编辑、媒体、平台限制 | `references/platform-rules.md` |

## 风格基线

这套语感默认是大黄味道：观点前置、一行一句、锋利、复盘口吻。

如果用户给了自己的风格样本或历史帖子，先抽用户的风格特征（句长、用词、锋利度、是否用梗），再套结构规则。

判断优先级：用户风格样本 > 大黄语感默认。

不要把所有人改写成大黄。

## 工作流

### 1. 先诊断，不急着写

拿到原稿先做 5 个判断：

- 原稿最硬的判断是什么？
- 哪一句适合做第一行？
- 哪些背景可以删掉？
- 读者为什么会停下来看？
- 对照 `references/viral-post-anatomy.md` 的 8 特征，这条命中了几个？

不要逐句润色原稿。先重排信息。

### 2. 抽一个可传播判断

什么是硬判断、怎么打开头，见 `references/viral-post-playbook.md` 的「可传播判断」和「Hook 矩阵」。

先打至少 3 个开头，再选最硬的。

### 3. 选形态

默认短帖。多数内容一个判断 + 一个证据就够，硬拆成 Thread 反而稀释。

只有这些情况才写 Thread：

- 原稿有 3 个以上独立观点，短帖装不下。
- 需要步骤、证据链或故事转折。

Thread 的 7 种类型和写法见 `references/thread-playbook.md`。

### 4. 改成 X 信息流结构

短帖默认结构、四种正文形态（判断/结果/争议/工具项目），见 `references/viral-post-playbook.md` 的「爆帖化正文结构」。

一行一句。每行只推进一个信息。删掉所有铺垫型开头。链接直接放帖子正文里；Thread 的链接放最后一条。

## 输出模式

### 默认

只给可发布成品。

```md
## 帖子
{可直接发的 X 帖，链接直接在里面}
```

### 用户要多版本

```md
## 版本 A：直给判断
{post}

## 版本 B：结果感
{post}

## 版本 C：更像大黄
{post}
```

## 不要做的事

- 不编造数据、收入、用户反馈、截图、star、阅读量、增长结果。
- 不承诺必爆、必涨粉、必被算法推荐。
- 不为了冲突改事实。
- 不把第三方经验当铁律。发布时间、媒体形式都要结合账号数据测试。
- 不甩一堆资料链接糊弄用户。资料只在需要解释依据时简短说明。

## 出厂自检

交付前逐条扫：

- 第一行是否有判断、结果、冲突或明确读者？
- 前 3 行是否说明了 who / what / why？
- 是否有至少一个具体细节？
- 是否删掉了背景开场、公众号腔、AI 腔、课堂腔？
- 是否一行一句，扫读无阻力？
- 是否有自然互动点，不是泛泛问"你怎么看"？
- 帖子是否在字符限制内？默认按 280 写；用户声明有 Longer post 额度时补读 `references/platform-rules.md` 再放宽。
- 如果是 Thread，每条是否能单独成立？

## 资源说明

- `references/dahuang-style.md`：中文 X 语感规则（观点前置、一行一句、去爹味、禁用壳、中英混排）。
- `references/viral-post-playbook.md`：Hook 矩阵、可传播判断、爆帖化正文结构、坏稿改法、交付前清理。
- `references/viral-post-anatomy.md`：爆款潜质判断（核心判断句 + 8 特征 + 公式）。
- `references/thread-playbook.md`：什么时候写 Thread、第一条怎么写、7 种 Thread 类型、发之前自检。
- `references/platform-rules.md`：字符数、媒体、Longer post、Articles、Edit 等平台限制——只在用户问时读。
- `references/examples-before-after.md`：改写样例（公告/公号/技术项目/爹味/Thread/提问）。
- `agents/openai.yaml`：Codex 专属 UI 元数据（可选，不影响功能）。

## 宿主兼容

这个 skill 遵循 Agent Skills 规范（https://agentskills.io/specification），可在以下宿主使用：

- OpenAI Codex：`Use $dahuang-x-post ...`
- Anthropic Claude Code：`Use $dahuang-x-post ...`（或在 system prompt 里引用本 skill 路径）
- 其他兼容 Agent Skills 的工具

调用时把本 skill 目录作为资源根，SKILL.md 是入口，其他文件按需读取。
