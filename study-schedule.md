# AI × Web3 School 全面学习计划

> 创建：2026-05-21 | 目标方向：开发 | 每日 2 小时+

## 总览

```
Week 1-4    AI 基础         → 建立模型、上下文、Agent 的共同语言
Week 5-8    Web3 基础       → 补上链上系统的直觉
Week 9-12   AI × Web3 Bridge → 进入交叉问题
Week 13+    前沿探索 + 项目  → 组合成可演示原型
```

## Phase 1：AI 基础（Week 1–4）

### Week 1（5/21 – 5/25）：从 Hello World 到 Agent 初体验

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | 环境 + LLM (1/2) | Handbook 概览；LLM 是什么、能做什么、不能替代什么 | 初始化仓库；用 ChatGPT/DeepSeek 完成 3 个对比实验（翻译、推理、局限）|
| Day 2 | LLM (2/2) | Token、温度、上下文窗口、模型选型 | 用不同温度参数测试同一个 prompt，记录差异 |
| Day 3 | Prompt (1/2) | Prompt 结构：任务目标、边界、输出格式 | 写 5 个不同场景的 prompt，对比效果 |
| Day 4 | Prompt (2/2) | Few-shot、Chain-of-Thought、System Prompt | 用 CoT 分解一个复杂任务 |
| Day 5 | 复习 + 实验 | 回顾本周，写一个小脚本调用 API | 用 Python 调用 OpenAI API 完成一个简单问答 |

### Week 2（5/26 – 6/1）：上下文、检索和工具

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | Context (1/2) | 上下文窗口原理、信息密度、token 预算 | 计算一个对话的 token 消耗 |
| Day 2 | Context (2/2) | 上下文可信度、过期信息、上下文工程 | 实验：给模型注入错误上下文看效果 |
| Day 3 | RAG (1/2) | RAG 原理：embedding、向量检索、chunking | 用 LangChain 搭一个最简 RAG |
| Day 4 | RAG (2/2) | 来源引用、rerank、评估 | 给 RAG 加上来源引用 |
| Day 5 | Agent (1/2) | Agent 概念：推理 + 工具调用 + 循环 | 运行第一个 Agent demo（ReAct 模式）|
| Day 6 | Agent (2/2) | 多步执行、错误恢复、human-in-the-loop | 给 Agent 加一个人工确认步骤 |
| Day 7 | 周总结 | 回顾 + 实验：做一个 RAG + Agent 组合原型 | 整理笔记，提交 weekly review |

### Week 3（6/2 – 6/8）：框架与协议

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | Frameworks (1/2) | LangChain 核心概念：chain、tool、memory | 用 LangChain 把上周的 Agent 重写一遍 |
| Day 2 | Frameworks (2/2) | LangGraph：状态图、条件路由 | 做一个多步骤工作流 |
| Day 3 | MCP (1/2) | MCP 协议原理：client、server、tool 定义 | 搭建一个 MCP server |
| Day 4 | MCP (2/2) | MCP 生态：常用 server、自定义 tool | 连接一个第三方 MCP server |
| Day 5 | Evaluation (1/2) | 为什么需要 eval、评估维度、benchmark | 设计 5 个测试用例评估你的 Agent |
| Day 6 | Evaluation (2/2) | 自动化评估、回放、持续改进 | 写一个自动评估脚本 |
| Day 7 | 周总结 | 回顾 + 实验 | 整理笔记，提交 weekly review |

### Week 4（6/9 – 6/15）：AI 基础收官 + 实验周

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | 知识串联 | 把 AI 基础 8 个模块串成一张图 | 画思维导图 |
| Day 2 | 综合实验 | 设计一个用到 LLM + RAG + Agent + MCP 的系统 | 写设计文档 |
| Day 3 | 综合实验 | 实现 Day 2 的设计 | 编码 |
| Day 4 | 综合实验 | 实现 Day 2 的设计 | 编码 |
| Day 5 | 综合实验 | 测试 + 评估 | 跑 eval、修 bug |
| Day 6 | 查缺补漏 | 回顾薄弱点，重读对应 Handbook 章节 | 补充笔记 |
| Day 7 | Phase 1 复盘 | 写一篇 Phase 1 总结 | 提交到 `experiments/phase1-summary.md` |

---

## Phase 2：Web3 基础（Week 5–8）

### Week 5（6/16 – 6/22）：链上世界入门

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | Network (1/2) | 区块、共识、节点、测试网 | 连接 Sepolia 测试网，查余额 |
| Day 2 | Network (2/2) | L2、Rollup、RPC、区块浏览器 | 在 Optimism/L2 上做一次交易 |
| Day 3 | Cryptography (1/2) | 哈希、公钥私钥、数字签名 | 用 openssl 生成密钥对，签名一条消息 |
| Day 4 | Cryptography (2/2) | Merkle Tree、零知识入门 | 手算一个 Merkle Tree |
| Day 5 | Wallet (1/2) | 钱包原理、助记词、分层确定性钱包 | 用 ethers.js 生成一个钱包 |
| Day 6 | Wallet (2/2) | 签名消息、连接 dApp | 用钱包签名并验证 |
| Day 7 | 周总结 | 回顾 + 实验 | 整理笔记，提交 weekly review |

### Week 6（6/23 – 6/29）：合约与账户

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | Smart Contract (1/2) | Solidity 基础：变量、函数、修饰符 | 写第一个合约：计数器 |
| Day 2 | Smart Contract (2/2) | 部署、调用、事件、Gas | 部署到测试网并用 ethers.js 调用 |
| Day 3 | Account Abstraction (1/2) | EOA vs Smart Account、ERC-4337 | 创建一个 Safe 钱包 |
| Day 4 | Account Abstraction (2/2) | UserOp、Bundler、Paymaster | 用 AA SDK 发一笔交易 |
| Day 5 | DeFi (1/2) | DEX、AMM、借贷协议原理 | 在 Uniswap 测试网上做一笔 swap |
| Day 6 | DeFi (2/2) | 流动性、滑点、闪电贷 | 写代码查询池子信息 |
| Day 7 | 周总结 | 回顾 + 实验 | 整理笔记，提交 weekly review |

### Week 7（6/30 – 7/6）：数据与安全

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | Oracle (1/2) | 为什么需要预言机、推送 vs 拉取 | 读 Chainlink 价格馈送 |
| Day 2 | Oracle (2/2) | 数据源风险、去中心化预言机 | 用代码查询 Chainlink 价格 |
| Day 3 | Indexing (1/2) | 链上数据结构、事件日志 | 写脚本扫描某个合约的事件 |
| Day 4 | Indexing (2/2) | The Graph、Dune、自建索引 | 用 The Graph 查一个 subgraph |
| Day 5 | Security (1/2) | 常见攻击：重入、溢出、闪电贷攻击 | 分析一个历史漏洞案例 |
| Day 6 | Security (2/2) | 权限管理、模拟、监控 | 用 Tenderly 模拟一笔交易 |
| Day 7 | 周总结 | 回顾 + 实验 | 整理笔记，提交 weekly review |

### Week 8（7/7 – 7/13）：Web3 基础收官

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | 知识串联 | 把 Web3 基础模块串成一张图 | 画思维导图 |
| Day 2 | 综合实验 | 链上数据查询 + 分析工具 | 编码 |
| Day 3 | 综合实验 | 实现 Day 2 的工具 | 编码 |
| Day 4 | 查缺补漏 | 回顾薄弱点 | 补充笔记 |
| Day 5 | Phase 2 复盘 | 写一篇 Phase 2 总结 | 提交到 `experiments/phase2-summary.md` |
| Day 6 | 缓冲 | 追赶进度或提前预习 Bridge | |
| Day 7 | 缓冲 | 追赶进度或提前预习 Bridge | |

---

## Phase 3：AI × Web3 Bridge（Week 9–12）

### Week 9（7/14 – 7/20）：Agent 进入链上世界

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | Chain-aware Context | 链上状态如何进入 Agent 上下文 | 写一个工具：查地址余额 |
| Day 2 | Chain-aware Context | 区块数据、交易历史的上下文注入 | 让 Agent 读取最新区块信息 |
| Day 3 | Web3 Tool Use (1/2) | RPC 工具、合约读写工具 | 给 Agent 添加链上读工具 |
| Day 4 | Web3 Tool Use (2/2) | 钱包工具、交易工具 | 给 Agent 添加签名工具（测试网）|
| Day 5 | Agent Workflow (1/2) | 自动化 vs human-in-the-loop | 设计一个需要人工确认的链上流程 |
| Day 6 | Agent Workflow (2/2) | 多 Agent 协作、审批流程 | 设计双 Agent 审批模型 |
| Day 7 | 周总结 | 回顾 + 实验 | 整理笔记 |

### Week 10（7/21 – 7/27）：钱包、支付与结算

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | Agent Wallet (1/2) | Agent 权限模型、Session Key | 创建一个受限权限的钱包 |
| Day 2 | Agent Wallet (2/2) | 额度限制、时间锁、撤销 | 实现一个可撤销的权限系统 |
| Day 3 | Machine Payment (1/2) | 机器支付场景、小额支付 | 在测试网做一笔 Agent 自动支付 |
| Day 4 | Machine Payment (2/2) | 支付通道、批量支付 | 研究 Superfluid / Sablier |
| Day 5 | Settlement & Escrow (1/2) | 自动化交易流程 | 设计一个 escrow 合约 |
| Day 6 | Settlement & Escrow (2/2) | 争议处理、仲裁 | 实现 escrow 的争议流程 |
| Day 7 | 周总结 | 回顾 + 实验 | 整理笔记 |

### Week 11（7/28 – 8/3）：身份、信任与安全

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | Agent Identity (1/2) | Agent 身份模型、DID | 给 Agent 创建一个链上身份 |
| Day 2 | Agent Identity (2/2) | 授权、委托、责任追溯 | 实现身份授权链 |
| Day 3 | Agent Trust & Reputation | 行为记录、声誉系统 | 设计一个 Agent 声誉评分模型 |
| Day 4 | Verifiable AI (1/2) | 模型输出验证、TEE、ZK | 研究 EZKL / opshin |
| Day 5 | Verifiable AI (2/2) | 执行过程记录、结果验证 | 做一个最小验证 demo |
| Day 6 | AI Security (1/2) | Prompt Injection、工具滥用 | 攻击自己的 Agent 并记录 |
| Day 7 | 周总结 | 回顾 + 实验 | 整理笔记 |

### Week 12（8/4 – 8/10）：隐私、治理与 Bridge 收官

| 日 | 模块 | 学习内容 | 实践任务 |
|----|------|----------|----------|
| Day 1 | AI Privacy | 用户数据、链上身份、模型上下文隐私 | 设计一个隐私保护方案 |
| Day 2 | Governance AI (1/2) | AI 辅助提案、投票分析 | 模拟一个 DAO 提案流程 |
| Day 3 | Governance AI (2/2) | 公共决策中的 AI 协作 | 做一个治理摘要 Agent |
| Day 4 | Bridge 知识串联 | 12 个模块串联 | 画 Bridge 思维导图 |
| Day 5 | 综合实验 | AI Agent + 链上操作完整流程 | 编码 |
| Day 6 | Phase 3 复盘 | 写 Phase 3 总结 | 提交 `experiments/phase3-summary.md` |
| Day 7 | 缓冲 | 追赶进度 | |

---

## Phase 4：前沿探索 + 项目实战（Week 13+）

### Week 13（8/11 – 8/17）：赛道调研

| 日 | 任务 | 内容 |
|----|------|------|
| Day 1 | 赛道调研 | 研究 Agentic Commerce、Wallet/Permission、AI Security 三条赛道 |
| Day 2 | 选方向 | 确定 Hackathon 项目方向，写 one-pager |
| Day 3 | 技术选型 | 确定技术栈、画架构图 |
| Day 4 | 原型开发 | 搭建项目骨架 |
| Day 5 | 原型开发 | 核心功能开发 |
| Day 6 | 原型开发 | 核心功能开发 |
| Day 7 | 第一次评审 | 自我评审，决定下一步 |

### Week 14+（8/18 起）：项目迭代 + Hackathon

| 阶段 | 周期 | 任务 |
|------|------|------|
| MVP | 2 周 | 可演示的核心功能 |
| 打磨 | 1 周 | UI、文档、测试 |
| Hackathon | 按赛事 | 提交、路演 |

---

## 每日节奏模板

```
20:00-20:15   回顾昨日 / 查看今日计划
20:15-21:00   阅读 Handbook 当日模块
21:00-21:45   实践 / 编码 / 实验
21:45-22:00   写 daily note + 打卡草稿 + 提交打卡
```

## 每周节奏

| 日 | 任务 |
|----|------|
| 周一到周五 | 按日计划推进 |
| 周六 | 补进度 / 深度实验 |
| 周日 | 周总结 + weekly review + 规划下周 |

---

> 这个计划是一个路线图，不是牢笼。遇到难题、发现兴趣点、或者有 Hackathon 机会时，随时调整优先级。
> 核心原则：**每天有行动，每周有产出，每月有回顾。**