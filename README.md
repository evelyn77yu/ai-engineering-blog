# AI Engineering Notes

工程方法论的公开笔记：LLM Agent 的协作流程、可靠性与评测体系。所有内容均为个人方法论总结，不涉及任何任职组织的业务信息。

**Yu Dian** · NUS AI for Science · [GitHub @evelyn77yu](https://github.com/evelyn77yu)

---

## Posts

### 1. 双 Agent 交替开发：规则文件、滚动评审与漂移治理

让两个 AI Agent（Claude + Codex）在同一个项目里交替工作：一个负责架构与框架，一个负责实现与优化，共享一套机器可检查的规则文件和一份单文件滚动评审日志。核心经验：**一条规则如果无法被机械检查，在有 Agent 参与的项目里约等于不存在**；以及双 Agent 同时持有写权限时，双基线漂移是必然的，只能靠机制管住。

- 阅读：[posts/01-dual-agent-alternating-workflow.md](posts/01-dual-agent-alternating-workflow.md)
- 配图：工作流总览 · 漂移产生与治理

### 2. 提示策略对照评测的复盘：变量控制、双轨评分与可验证性设计

同一模型（Kimi-K2.5）、40 道推理题、四种提示策略、320 次调用，全程留痕。比结论更有价值的是三个工程动作：严格/宽松双轨评分（逻辑排序上"CoT 更差"主要是评分口径假象——8 处判错里 7 处只是冠词差异）、三处数据集标签修正的留痕处理、以及免 API Key 的离线验证脚本 + CI 质量门 + 源哈希清单。

- 阅读：[posts/02-llm-prompting-evaluation-retrospective.md](posts/02-llm-prompting-evaluation-retrospective.md)
- 配图：评测流水线 · 双口径准确率对比

### 3. 受约束的 Agentic Workflow：可靠性设计方法论

从真实工程实践抽象的设计笔记：把目标从"尽可能自主"换成"尽可能可靠"之后，系统该怎么组织——三层职责划分（LLM 决策 / 确定性工具 / 人工审查）、决策路由四分类、失败路径降级链、Trace 分层归因、人工接受率优于生成成功率的评估口径，以及"Multi-Agent 用来解决职责冲突，不是用来解决任务复杂度"的拆分判断。

- 阅读：[posts/03-constrained-agentic-workflow-reliability.md](posts/03-constrained-agentic-workflow-reliability.md)
- 配图：三层职责 · 决策路由与降级链 · Multi-Agent 拆分信号

---

## License

文章与插图以 [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) 提供，转载请注明出处。
