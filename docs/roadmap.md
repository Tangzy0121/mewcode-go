# Roadmap

课程共 17 章，v1.0 = 全部章节落地（每章都有真机证据与分歧笔记，见 `docs/adr/0002`）。本文件只记录**切法、里程碑与风险**，不记录课程内容——课程是付费的，仓库是公开的。

## 预算与现实预期

每 4 天约 2h（≈3.5h/周），一章 = 一次会话。17 章 ≈ 17 次会话 ≈ 68 天 ≈ **2.3 个月**，因此 v1.0 的现实落地时间约为 **2027 年 1 月上旬**；v1.1（web 面）另计。ch7、ch13–15 这几章可能一章不止一次会话，所以进度看里程碑，不看单章。

## 规格与工单

- **M1（ch1–4）规格**：GitHub issue [#1](https://github.com/Tangzy0121/mewcode-go/issues/1)（标签 `ready-for-agent`）。M2/M3 的规格在各自开始前再写，不提前猜。
- **M1 工单**（纯线性链，前沿永远只有一张）：

| 工单 | issue | 交付 | 阻塞于 |
| --- | --- | --- | --- |
| T1 | [#2](https://github.com/Tangzy0121/mewcode-go/issues/2) | 配置与故障路径（不含模型调用） | 无 |
| T2 | [#3](https://github.com/Tangzy0121/mewcode-go/issues/3) | 第一次真实往返（非流式）+ 错误分类与退避 | #2 |
| T3 | [#4](https://github.com/Tangzy0121/mewcode-go/issues/4) | 流式：SSE → Stream Event → 逐字输出 | #3 |
| T4 | [#5](https://github.com/Tangzy0121/mewcode-go/issues/5) | 统一消息模型 + REPL 多轮 Session | #4 |
| T5 | [#6](https://github.com/Tangzy0121/mewcode-go/issues/6) | 工具接口 + 注册表 + read + 首次 Tool Call 闭环 | #5 |
| T6 | [#7](https://github.com/Tangzy0121/mewcode-go/issues/7) | glob + grep | #6 |
| T7 | [#8](https://github.com/Tangzy0121/mewcode-go/issues/8) | Agent Loop 健壮性 | #7 |
| T8 | [#9](https://github.com/Tangzy0121/mewcode-go/issues/9) | write + edit + 薄版 Permission Mode | #8 |
| T9 | [#10](https://github.com/Tangzy0121/mewcode-go/issues/10) | bash（PowerShell）+ 拒绝路径 | #9 |
| T10 | [#11](https://github.com/Tangzy0121/mewcode-go/issues/11) | M1 证据与演示收尾 | #10 |
| T11 | [#12](https://github.com/Tangzy0121/mewcode-go/issues/12) | 求职产物 | #11 |

工单不绑死章节：章节是学习顺序，工单是能力竖切。读章后若与工单冲突，改工单而不是硬套。

## 里程碑

| 里程碑 | 章节 | 达成后是什么 | 演示 |
| --- | --- | --- | --- |
| **M1 能干活** | ch1–4 初识 Coding Agent / 让 AI 开口说话 / 工具系统 / 让 Agent 自己干活 | 一个能读代码、跑命令、改文件的终端 agent | 从零启动，让它读一个文件并改一行 |
| **M2 能守规矩** | ch5–9 System Prompt / 权限系统 / MCP / 上下文管理 / 记忆系统 | 可控、可扩展、能长会话的 agent | 权限三档走查 + 接一个 MCP 工具 + 长会话不炸 |
| **M3 能协作** | ch10–16 Slash Command / Skill / Hook / SubAgent / Worktree / Agent Teams / 回顾 | 从一个 agent 到一支可编排的团队 | 一个子 agent 在独立 worktree 里完成任务并回报 |
| **M4 求职** | ch17 面试求职全攻略 | 简历条目 + 项目讲解稿 + 预演问答 | 给一个外人讲 10 分钟并答问 |
| **v1.1 自研增量** | （课程之外） | Go 暴露 HTTP + SSE + 浏览器界面 | 网页里看到 agent 读文件、改文件 |

**每个里程碑结束必须有一次"从零开始的真机演示"（命令 + 真实输出或录屏），没有演示不进入下一个里程碑。** 这是防止课程太长、中期失去证据而停摆的唯一保险。

## 每章统一的完成判据

1. 该章代码落地（AI 实现，架构由我定）；
2. **一条真机证据**：可复现命令 + 真实输出，写入 `docs/review/<chapter>.md`；
3. **一条分歧笔记**（≤3 行）；
4. **三类审计证据各一条**：解释 / 改动 / 抓错；
5. 通过该章的理解检查（3 个问题）。

缺第 2 项即不算完成——单测绿不算。

## 一处特殊的学习杠杆

ch7 MCP、ch11 Skill、ch12 Hook、ch13 SubAgent、ch14 Worktree、ch15 Agent Teams —— 这六章对应的东西，我在这台机器上**每天都在用**（pi 的 skill / hook / 子 agent / 工作树机制）。所以这几章可以拿 pi 的实际行为做对照：它怎么切、课程怎么切、我为什么选其中一个。这一条能直接产出最值钱的"抓错"与"分歧"证据，也是面试里最能讲的部分。

## 风险

| 风险 | 抵消 |
| --- | --- |
| 课程规模远大于 v0（v0 大致只覆盖 ch1–6 的一半），中期看不到成果 | 里程碑演示，M1 结束就有一个真能用的东西 |
| 审计退化成签字 | 真机证据是唯一不依赖自我报告的判据 |
| 求职时间线与 v1.0 时间线打架（M4 在最后） | 简历条目与讲解稿在 M1 结束就开始写，不等全部做完 |
| 课程正文/代码泄漏进公开仓库 | 仓库只放我方实现与笔记，不放课程材料 |
