# Dahuang X Post

> 把中文内容改造成更像 X 上会被停下来看、会被回复、会被转发的帖子——改的是信息结构，不是润色。

## 它能做什么

这个 skill 给 AI 编码助手装上 X 文案改写能力。把中文观点、长文、产品进展、技术项目、复盘、Newsletter 摘要，改成更适合 X 信息流的帖子。

它做几件事：

1. **改短帖**（主）——把判断提前、大段拆成扫读结构、普通开头改成有传播点的第一句。不是逐句润色，是重排信息顺序。
2. **拆 Thread**——有 3 个以上独立观点或步骤/证据链时，拆成一组能独立转发、又能连续推进的短帖。
3. **配首评**——把链接、仓库、Demo、截图放到评论区承接，不让外链抢主帖的主角。
4. **给复用角度**——内容有可能跑起来时，默认给 3 个新角度，让一条内容发不止一次。
5. **只诊断**——用户说"先别改"时，标出原稿为什么不像 X、最小改法是什么，不输出成品。

**姐妹 skill**：[`dahuang-human-tone`](https://github.com/realchendahuang/dahuang-human-tone)——去除中文文本里的 AI 味；[`dahuang-ai-tone`](https://github.com/realchendahuang/dahuang-ai-tone)——把文本加成各模型的 AI 味。本 skill 假设文本本身已经是人话，专注 X 信息流形态。

## 看看效果

同一段项目公告，改前改后：

> **改前**：我们今天正式发布了 dahuang-x-post，这是一个面向中文创作者的 X 文案优化 skill。它可以帮助用户优化推文、生成 Thread、改写开头，并提升内容在 X 平台的表现。欢迎大家试用并提出反馈。

**改后**：

> 中文 X 文案最常见的问题：
>
> 内容是好的。第一句是废的。
>
> 我做了个 skill，专门干这件事：把公众号腔、公告腔、AI 腔，改成能在信息流里停住人的帖子。
>
> 仓库放首评。

完整示范见 `references/examples-before-after.md`（公告/公号腔/技术项目/爹味建议/长文拆 Thread/提问改写）。

## 改写工作流

1. **先诊断，不急着写**——原稿最硬的判断是什么？哪句适合做第一行？哪些背景能删到评论区？读者为什么停下来看？
2. **抽一个可传播判断**——先打至少 3 个开头，再选最硬的（见 Hook 矩阵）。
3. **选形态**——默认短帖；3 个以上独立观点或步骤/证据链才写 Thread；用户明确要长文沉淀才写长帖。
4. **改成 X 信息流结构**——一行一句，每行只推进一个信息，删掉铺垫型开头。
5. **做首评和复用**——涉及链接/仓库/Demo 默认配首评；内容有可能跑起来默认给 3 个复用角度。
6. **出厂自检**——第一行有没有判断、前 3 行交代 who/what/why 没、有没有具体细节、是不是一行一句、字符数够不够。

## 资源结构

```
dahuang-x-post/
├── SKILL.md                          # 入口：改写工作流（给模型读）
├── references/                       # 按需加载的详细文档
│   ├── dahuang-style.md              # 中文 X 语感规则（观点前置/一行一句/去爹味/禁用壳）
│   ├── viral-post-playbook.md        # Hook 矩阵、可传播判断、爆帖化正文结构、坏稿改法
│   ├── thread-playbook.md            # 什么时候写 Thread、第一条怎么写、7 种 Thread 类型
│   ├── distribution-loop.md          # 主帖/首评分工、外链策略、评论区承接、爆帖二次利用
│   ├── platform-rules.md             # 字符数/媒体/Longer post/Articles 等平台限制
│   └── examples-before-after.md      # 改写样例（语感靠这个校准）
└── agents/openai.yaml                # Codex 专属 UI 元数据（可选）
```

## 安装

### 方式一：skills CLI（推荐）

```bash
npx skills add realchendahuang/dahuang-x-post -g
```

`-g` 安装到全局（用户级），所有项目可用。去掉 `-g` 则只装到当前项目。安装后重启 Codex / Claude Code 即可生效。

### 方式二：手动复制

```bash
# Codex
cp -r dahuang-x-post ~/.codex/skills/

# Claude Code
cp -r dahuang-x-post ~/.claude/skills/
```

或者把本目录作为资源目录，在 system prompt 里引用 `SKILL.md` 路径。

## 使用

### 改成 X 短帖

```
Use $dahuang-x-post 把下面这段改成 X 短帖，判断要前置，链接放首评：

<贴文本>
```

```
Use $dahuang-x-post 这是开源项目更新，别写成公告，先讲它把什么问题变简单：

<贴文本>
```

### 拆 Thread

```
Use $dahuang-x-post 把这篇复盘拆成 Thread，每条能单独转发：

<贴文本>
```

### 要多版本开头

```
Use $dahuang-x-post 给这段打 3 个开头让我选，分别走直给判断/结果感/反常识：

<贴文本>
```

### 只诊断不改

```
Use $dahuang-x-post 先别改，先标出这段为什么不像 X、最小改法是什么：

<贴文本>
```

## 边界

- **不承诺爆**。改的是帖子形态（第一眼停得住、三行内懂收益、有信息增量），不是保证传播。发布时间、链接位置、媒体形式都要结合账号数据测。
- **不编造数据**。不造收入、star、阅读量、增长结果、用户反馈、截图。
- **不改事实**。可以重排信息、改表达，但不为了冲突扭曲原意。
- **只管 X 形态**。去 AI 味是 [`dahuang-human-tone`](https://github.com/realchendahuang/dahuang-human-tone) 的活；本 skill 假设文本已经是人话，专注信息流改写。

## License

MIT
