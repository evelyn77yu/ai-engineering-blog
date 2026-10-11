# AI Engineering Notes

工程方法论的公开笔记：LLM Agent 的协作流程、可靠性与评测体系。所有内容均为个人方法论总结，不涉及任何任职组织的业务信息。

**Yu Dian** · NUS AI for Science · [GitHub @evelyn77yu](https://github.com/evelyn77yu)

---

## Posts

### 1. 双 Agent 交替开发工作流：Claude + Codex 与一份 415 行的规则文件

**TL;DR** — 让两个 AI Agent 在同一个仓库里交替工作：一个负责架构与框架，一个负责实现与优化，共享一套机器可检查的规则文件（`AGENTS.md`）和一份永不拆分的滚动评审日志。21 轮评审沉淀下来的经验：一条规则如果无法被机械检查，在有 Agent 参与的项目里约等于不存在。

- 配套仓库：[evelyn77yu/agent-ui](https://github.com/evelyn77yu/agent-ui)（含 `AGENTS.md`、`CLAUDE.md`、21 轮评审日志与漂移对账文档）
- 阅读：[posts/01-dual-agent-alternating-workflow.md](posts/01-dual-agent-alternating-workflow.md)

### 2. LLM 提示策略评测复盘：40 道题、四种策略与一次 70% 的异常

**TL;DR** — 用同一个模型（Kimi-K2.5）在 40 道推理题上对照 Direct / Zero-shot CoT / Few-shot CoT / Self-consistency 四种策略。Few-shot CoT 最优（95%），策略间差异几乎全部来自逻辑排序一类任务；Self-consistency 花 5 倍调用只多对一题。比结论更重要的是可验证性工程：免 API Key 的离线验证 + CI 质量门 + 源哈希清单。

- 配套仓库：[evelyn77yu/llm-prompting-evaluation](https://github.com/evelyn77yu/llm-prompting-evaluation)（含数据集、逐题预测、CI 验证）
- 阅读：[posts/02-llm-prompting-evaluation-retrospective.md](posts/02-llm-prompting-evaluation-retrospective.md)

---

## License

文章内容以 [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) 提供，转载请注明出处。
