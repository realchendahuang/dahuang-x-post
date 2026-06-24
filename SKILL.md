---
name: dahuang-x-post
description: "把中文内容改成更适合 X 信息流的帖子。触发：X发帖、推文、Twitter文案、帖子优化、爆帖、Thread、hook、涨粉、互动、改得更适合X、中文X语感。"
license: MIT
metadata:
  version: "1.1.0"
  author: realchendahuang
---

# Dahuang X Post

把中文内容改造成更像 X 上会被停下来看、会被回复、会被转发的帖子。

这不是润色。是改信息结构：

1. 把判断提前到第一行。
2. 把大段拆成扫读结构。
3. 把普通开头改成有传播点的第一句。
4. 把链接、仓库、Demo 放到评论区承接。
5. 把可复用角度拆出来，让一条内容发不止一次。

## 默认加载

每次任务都读这三份，按需再补：

- `references/dahuang-style.md` — 中文 X 语感规则。
- `references/viral-post-playbook.md` — Hook、判断、正文结构、坏稿改法。
- `references/examples-before-after.md` — 改写样例（语感靠这个校准）。

## 按需补读

| 场景 | 读什么 |
|---|---|
| 给长文、复盘、教程，要拆 Thread | `references/thread-playbook.md` |
| 给产品、链接、GitHub、Newsletter、课程、工具 | `references/distribution-loop.md` |
| 问字符数、长帖、Articles、编辑、媒体、平台限制 | `references/platform-rules.md` |

distribution-loop.md 也负责"爆帖复用"。当默认工作流要你给复用角度、或内容有可能跑起来时，补读它的「爆帖二次利用」一节。

## 工作流

### 1. 先诊断，不急着写

拿到原稿先做 5 个判断：

- 原稿最硬的判断是什么？
- 哪一句适合做第一行？
- 哪些背景可以删到评论区或 Thread 后面？
- 读者为什么会停下来看？
- 这条内容的互动/转化目标是什么？

不要逐句润色原稿。先重排信息。

### 2. 抽一个可传播判断

什么是硬判断、怎么打开头，见 `references/viral-post-playbook.md` 的「可传播判断」和「Hook 矩阵」。

先打至少 3 个开头，再选最硬的。

### 3. 选形态

默认优先短帖。多数内容一个判断 + 一个证据就够，硬拆成 Thread 反而稀释。

只有这些情况才写 Thread：

- 原稿有 3 个以上独立观点，短帖装不下。
- 需要步骤、证据链或故事转折。
- 需要承接产品/仓库/长文，但主帖放不下。

只有这些情况才写长帖/Article：

- 用户明确要长帖。
- 内容本身就是完整长文沉淀。
- 需要被收藏、检索、反复转发，而不是当场互动。

Thread 的 7 种类型和写法见 `references/thread-playbook.md`。

### 4. 改成 X 信息流结构

短帖默认结构、四种正文形态（判断/结果/争议/工具项目），见 `references/viral-post-playbook.md` 的「爆帖化正文结构」。

一行一句。每行只推进一个信息。删掉所有铺垫型开头。

### 5. 做首评和复用

涉及链接、仓库、产品、图片、长文、Newsletter、Demo，默认给首评。

内容有可能跑起来时，默认给 3 个复用角度。怎么拆见 `references/distribution-loop.md` 的「爆帖二次利用」。

## 输出模式

### 默认

只给可发布成品。

```md
## 主帖
{可直接发的 X 帖}

## 首评
{链接/补充/仓库/案例/截图说明，没有就省略}

## 复用角度
1. {新角度帖}
2. {Thread 角度}
3. {Quote/评论区营业角度}
```

复用角度只在内容有可能跑起来时给。普通观点帖给主帖 + 首评即可。

### 用户要多版本

```md
## 版本 A：直给判断
{post}

## 版本 B：结果感
{post}

## 版本 C：更像大黄
{post}
```

### 用户要爆帖化完整包

```md
## 主帖
{post}

## 首评
{comment}

## 评论区补充
1. {补证据}
2. {补案例}
3. {补延伸观点}

## 后续复用
1. {新角度帖}
2. {Thread 角度}
3. {Quote/评论区营业角度}
```

### 用户说只诊断

```md
## 问题
1. {为什么不像 X}
2. {为什么不容易停住人}
3. {哪里像公众号/AI/公告/课堂}

## 改法
{最小可行动作}
```

## 不要做的事

- 不编造数据、收入、用户反馈、截图、star、阅读量、增长结果。
- 不承诺必爆、必涨粉、必被算法推荐。
- 不为了冲突改事实。
- 不把第三方经验当铁律。发布时间、链接位置、媒体形式都要结合账号数据测试。
- 不甩一堆资料链接糊弄用户。资料只在需要解释依据时简短说明。

## 出厂自检

交付前逐条扫：

- 第一行是否有判断、结果、冲突或明确读者？
- 前 3 行是否说明了 who / what / why？
- 是否有至少一个具体细节？
- 是否删掉了背景开场、公众号腔、AI 腔、课堂腔？
- 是否一行一句，扫读无阻力？
- 是否有自然互动点，而不是泛泛问"你怎么看"？
- 主帖是否在字符限制内（普通 280，Longer post 见 `references/platform-rules.md`）？
- 如果有链接，是否考虑放首评？
- 如果是 Thread，每条是否能单独成立？
- 如果内容有可能跑起来，是否给了复用角度？

## 资源说明

- `references/dahuang-style.md`：中文 X 语感规则（观点前置、一行一句、去爹味、禁用壳）。
- `references/viral-post-playbook.md`：Hook 矩阵、可传播判断、爆帖化正文结构、坏稿改法、交付前清理。
- `references/thread-playbook.md`：什么时候写 Thread、第一条怎么写、7 种 Thread 类型、发之前自检。
- `references/distribution-loop.md`：主帖/首评分工、外链策略、评论区承接、回复策略、爆帖二次利用、看数据。
- `references/platform-rules.md`：字符数、媒体、Longer post、Articles、Edit 等平台限制——只在用户问时读。
- `references/examples-before-after.md`：改写样例（公告/公号/技术项目/爹味/Thread/提问）。
- `agents/openai.yaml`：Codex 专属 UI 元数据（可选，不影响功能）。

## 宿主兼容

这个 skill 遵循 Agent Skills 规范（https://agentskills.io/specification），可在以下宿主使用：

- OpenAI Codex：`Use $dahuang-x-post ...`
- Anthropic Claude Code：`Use $dahuang-x-post ...`（或在 system prompt 里引用本 skill 路径）
- 其他兼容 Agent Skills 的工具

调用时把本 skill 目录作为资源根，SKILL.md 是入口，其他文件按需读取。
