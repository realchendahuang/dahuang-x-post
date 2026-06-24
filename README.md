# Dahuang X Post

> X 上的爆帖是有行文规律的。把规律逆向出来，套到你手上的想法/内容，产出一条符合 X 爆帖特质的帖子。

## 它能做什么

给 AI 编码助手装上 X 文案改写能力。

手上有想法、一段内容、一个项目更新、一篇复盘——扔进来，输出一条符合 X 爆帖特质的帖子：判断前置、一行一句、扫读无阻力、有传播点的第一句。

底子是 `references/` 里那套爆帖行文规律——Hook 怎么起、判断怎么前置、正文怎么排、什么形态拆 Thread——一堆爆帖研究完沉淀下来的，照着套就行。

产物形态：

1. **短帖**（主）——判断前置、扫读拆段、有传播点的第一句。改的是信息顺序，逐句润色治不了。
2. **Thread**——3 个以上独立观点或步骤/证据链时，拆成一组能独立转发、又能连续推进的短帖。

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
> 仓库：{url}

完整示范见 `references/examples-before-after.md`（公告/公号腔/技术项目/爹味建议/长文拆 Thread/提问改写）。

## 改写工作流

1. **先诊断，不急着写**——原稿最硬的判断是什么？哪句适合做第一行？哪些背景能删？读者为什么停下来看？对照 8 特征判断有没有爆款潜质。
2. **抽一个可传播判断**——先打至少 3 个开头，再选最硬的（见 Hook 矩阵）。
3. **选形态**——默认短帖；3 个以上独立观点或步骤/证据链才写 Thread。
4. **改成 X 信息流结构**——一行一句，每行只推进一个信息，删掉铺垫型开头，链接直接放帖子里。
5. **出厂自检**——第一行有没有判断、前 3 行交代 who/what/why 没、有没有具体细节、是不是一行一句、字符数够不够。

## 资源结构

```
dahuang-x-post/
├── SKILL.md                          # 入口：改写工作流（给模型读）
├── references/                       # 按需加载的详细文档
│   ├── dahuang-style.md              # 中文 X 语感规则（观点前置/一行一句/去爹味/禁用壳/中英混排）
│   ├── viral-post-playbook.md        # Hook 矩阵、可传播判断、爆帖化正文结构、坏稿改法
│   ├── viral-post-anatomy.md         # 爆款潜质判断（核心判断句+8特征+公式）
│   ├── thread-playbook.md            # 什么时候写 Thread、第一条怎么写、7 种 Thread 类型
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

### 改成 X 帖子

```
Use $dahuang-x-post 把下面这段改成 X 帖子，判断要前置：

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

## License

MIT
