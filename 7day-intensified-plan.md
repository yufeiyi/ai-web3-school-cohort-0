# AI × Web3 School 7 天强化计划

> 全部 Handbook 内容压缩到 7 天，每天一个主题
> 不限制学习时长，只管往前推进

```
Day 1  LLM + Prompt          ← AI 基础（上）
Day 2  Context + RAG + MCP   ← AI 基础（中）
Day 3  Agent + Frameworks    ← AI 基础（下）
Day 4  Network + Crypto + Wallet + Contract  ← Web3 基础（上）
Day 5  AA + DeFi + Oracle + Indexing + Security  ← Web3 基础（下）
Day 6  AI × Web3 Bridge（上） ← 交叉问题（一）
Day 7  AI × Web3 Bridge（下）+ 前沿探索  ← 交叉问题（二）+ 项目
```

---

## Day 1（5/21 周四）— LLM + Prompt

### 读 Handbook
- [Handbook LLM](https://aiweb3.school/zh/handbook/ai/llm/) — 全部
- [Handbook Prompt](https://aiweb3.school/zh/handbook/ai/prompt/) — 全部

### 核心认知
1. LLM 是**概率模型**，输出是候选结果不是事实
2. 模型是推理层，真相源来自数据库/API/链上数据
3. Prompt 是**接口设计**，不是魔法咒语
4. Prompt 是**软约束**，安全边界靠代码层

### 知识清单
| 概念 | 一句话 |
|------|--------|
| Token | 基本单位，中文 1-2 token，代码更贵 |
| Temperature | 0=确定，1+=随机 |
| Hallucination | 编造，要外部校验防 |
| Instruction | 四段式：目标/输入/禁止/格式 |
| Few-shot | 好示例+坏示例比一堆好示例强 |
| CoT | 一步步推理，减少错误 |
| Structured Output | JSON/schema，机器可检查 |
| Prompt Injection | 攻击模型忽略规则→靠代码层防，不靠prompt |

### 实践
1. temperature 对比实验 T=0 / 0.7 / 1.5
2. 写 3 个场景 prompt（交易解释/代码审查/学习助手）
3. 用 CoT 分解一个复杂问题

### 打卡
> Day 1：LLM + Prompt。LLM 是概率模型，Prompt 是接口设计。做了 temperature 对比和 CoT 实验。最大收获：结构化输出让机器可检查，但最终安全靠代码层。

---

## Day 2（5/22 周五）— Context + RAG + MCP

### 读 Handbook
- [Handbook Context](https://aiweb3.school/zh/handbook/ai/context/) — 全部
- [Handbook RAG](https://aiweb3.school/zh/handbook/ai/rag/) — 全部
- [Handbook MCP](https://aiweb3.school/zh/handbook/ai/mcp/) — 速览

### 核心认知
1. Context 是模型能看见的信息空间——信息分层比堆砌更重要
2. 指令层 > 事实层 > 知识层 > 记忆层，逐层隔离
3. RAG 的可靠性取决于**证据链**：chunk → retrieve → rerank → citation → 拒答
4. 向量相似 ≠ 答案正确，metadata 过滤比语义搜索更重要
5. MCP 协议让工具和上下文可以标准化接入

### 知识清单
| 概念 | 一句话 |
|------|--------|
| Context Window | 窗口大 ≠ 会用，要配合检索和摘要 |
| Context Engineering | 设计信息进入模型的方式，不是塞满窗口 |
| Memory | 跨请求保留信息，但不能替代实时授权 |
| Chunking | 按结构切（标题/API/FAQ），不是固定字数 |
| Vector DB | 存向量+metadata（来源/版本/可信度） |
| Retriever | 不能只看语义，还要过滤版本/环境 |
| Rerank | 把更相关/可信的结果排前面 |
| Citation | 答案必须能追溯到原文 |
| MCP | 将工具、上下文、来源协议化 |

### 实践
1. 设计一份 context spec：一个 Agent 读链上数据需要哪些上下文层
2. 做 RAG 实验：选 10 页文档，切 chunk，存向量（用 Python 或线上工具）
3. 测试三类问题：存在答案 / 不存在 / 版本不确定

### 打卡
> Day 2：Context + RAG + MCP。Context 要分层（指令/事实/知识/记忆），RAG 的核心是证据链不止向量搜索。MCP 把工具和上下文标准化。做了 context spec 设计和 RAG 分块实验。

---

## Day 3（5/23 周六）— Agent + Frameworks

### 读 Handbook
- [Handbook Agent](https://aiweb3.school/zh/handbook/ai/agent/) — 全部
- [Handbook Frameworks](https://aiweb3.school/zh/handbook/ai/frameworks/) — 全部
- [Handbook Evaluation](https://aiweb3.school/zh/handbook/ai/evaluation/) — 速览
- [Handbook Vibe Coding](https://aiweb3.school/zh/handbook/ai/vibe-coding/) — 速览
- [Handbook Fine-tuning](https://aiweb3.school/zh/handbook/ai/fine-tuning/) — 速览
- [Handbook Inference](https://aiweb3.school/zh/handbook/ai/inference/) — 速览

### 核心认知
1. Agent = 被约束的执行循环：目标+工具+状态+权限+停止条件，缺一不可
2. 工具比回答更危险：读/写/执行/支付/签名是不同风险等级
3. 框架是系统边界的表达，不是智能本身——先画清楚工作流再选框架
4. 没有 eval 的 Agent 是不可管理的——必须能测试、回放、回归

### 知识清单
| 概念 | 一句话 |
|------|--------|
| Tool Use | Agent 调用外部能力，设计要明确输入schema和权限范围 |
| Planning | 把目标拆步骤，计划只是候选路线不是授权 |
| State | 任务状态必须外置可查，不能只藏在 prompt 历史里 |
| Reflection | 自我检查可提高质量，但不能替确定性检查 |
| Multi-Agent | 多个 Agent 分工，但会放大协调和信任问题 |
| LangChain | 组件库，适合快速接能力，不适合替你定产品边界 |
| LangGraph | 状态图，适合多步/重试/人工确认的复杂工作流 |
| DSPy | prompt 可优化程序，适合有数据集+指标的重复任务 |
| Evaluation | 没有 eval 的 Agent = 不可管理的系统 |
| Vibe Coding | 快速原型可用，生产环境需要独立测试和边界 |

### 实践
1. 设计一个 Agent 架构图（目标→计划→只读工具→检查→写入工具→确认→执行→审计）
2. 同一个任务用两种方式实现：直接调 API vs 用框架
3. 写 5 个 eval 测试用例

### 打卡
> Day 3：Agent + Frameworks。Agent 是被约束的执行循环，工具比回答更危险。框架先画清楚流程再选，eval 是 Agent 可管理的必要条件。设计了 Agent 架构和 eval 测试用例。

---

## Day 4（5/24 周日）— Web3 基础（上）

### 读 Handbook
- [Network](https://aiweb3.school/zh/handbook/web3/network/)
- [Cryptography](https://aiweb3.school/zh/handbook/web3/cryptography/)
- [Wallet](https://aiweb3.school/zh/handbook/web3/wallet/)
- [Smart Contract](https://aiweb3.school/zh/handbook/web3/smart-contract/)
- [Dev Stack](https://aiweb3.school/zh/handbook/web3/dev-stack/)

### 核心认知
1. 区块是时间戳容器，共识决定谁有权记账，L2 把执行和结算分离
2. 哈希是单向指纹，公私钥是身份，签名是授权动作
3. 钱包不只是登录按钮，而是身份和签名入口
4. 智能合约是链上规则，部署后不可篡改（但可升级）
5. RPC 是链和应用之间的通信层

### 知识清单
| 概念 | 一句话 |
|------|--------|
| Block | 打包交易的容器，有时间戳和父哈希 |
| Consensus | 决定谁产生下个区块的规则（PoS/PoW） |
| L2 | 执行层放 L2，结算层放 L1（Optimistic/ZK） |
| RPC | 应用读链上数据的接口 |
| Hash | 单向函数，输出固定长度指纹 |
| Public/Private Key | 公钥=身份地址，私钥=控制权 |
| Signature | 用私钥签名，任何人可用公钥验证 |
| Wallet | 管理私钥+签名的工具 |
| Smart Contract | 部署在链上的程序，EOA 触发执行 |
| Hardhat/Foundry | 开发、测试、部署合约的工具链 |
| Gas | 执行合约的成本，防 spam |

### 实践
1. 连接 Sepolia 测试网，查余额
2. 用 ethers.js 生成一个钱包，签一条消息
3. 读一个简单合约代码（Counter/Vault）
4. 在区块浏览器找一笔交易，读字段含义

### 打卡
> Day 4：Web3 基础（上）。理解了区块共识网络、公私钥签名、钱包身份、智能合约规则、Gas 经济。连接了测试网，生成了钱包并签名，读了一个简单合约。

---

## Day 5（5/25 周一）— Web3 基础（下）

### 读 Handbook
- [Account Abstraction](https://aiweb3.school/zh/handbook/web3/account-abstraction/)
- [DeFi](https://aiweb3.school/zh/handbook/web3/defi/)
- [Oracle](https://aiweb3.school/zh/handbook/web3/oracle/)
- [Indexing](https://aiweb3.school/zh/handbook/web3/indexing/)
- [Security](https://aiweb3.school/zh/handbook/web3/security/)

### 核心认知
1. **AA（账户抽象）**：EOA 是人用的，Smart Account 是程序用的
   - ERC-4337 让合约钱包可以支付 Gas、批量交易、社交恢复
   - Session Key 让 Agent 在有限权限下自动操作
2. **DeFi**：DEX（AMM 自动做市）、借贷（超额抵押）、流动性
   - 资产、流动性、借贷、风险传播是核心
3. **Oracle**：链外数据上链，关键风险在数据源和时效性
4. **Indexing**：链上事件整理成可查询数据（The Graph / Dune）
5. **Security**：重入攻击、闪电贷攻击、权限漏洞

### 知识清单
| 概念 | 一句话 |
|------|--------|
| EOA vs SA | EOA=私钥控制，SA=合约逻辑控制 |
| ERC-4337 | UserOp → Bundler → EntryPoint → Contract |
| Session Key | 有限权限的临时密钥，适合 Agent |
| DEX | 去中心化交易所，AMM 用公式定价 |
| AMM | x*y=k，流动性池定价模型 |
| Oracle | 把链外数据推上链（Chainlink） |
| The Graph | 索引链上事件的 subgraph |
| Reentrancy | 重入攻击，先提款后更新状态 |
| Flash Loan | 闪电贷，同一笔交易内借还 |

### 实践
1. 了解 Safe 钱包（AA 的代表实现）
2. 在 Uniswap 测试网做一笔 swap
3. 读一个 Chainlink 价格预言机合约
4. 找一个历史漏洞案例（如 The DAO 重入）理解攻击原理

### 打卡
> Day 5：Web3 基础（下）。AA 让 Agent 能用 Smart Account 管理权限，DeFi 的 DEX/借贷/Aave 是基本金融协议，Oracle 把现实数据上链，Security 的重入和闪电贷攻击是经典风险。理解了这些后，Agent 做链上操作的基础就已完备。

---

## Day 6（5/26 周二）— AI × Web3 Bridge（上）

### 读 Handbook
- [Chain-aware Context](https://aiweb3.school/zh/handbook/bridge/chain-aware-context/)
- [Web3 Tool Use](https://aiweb3.school/zh/handbook/bridge/web3-tool-use/)
- [Agent Workflow](https://aiweb3.school/zh/handbook/bridge/agent-workflow/)
- [Agent Wallet](https://aiweb3.school/zh/handbook/bridge/agent-wallet/)
- [Machine Payment](https://aiweb3.school/zh/handbook/bridge/machine-payment/)
- [Settlement & Escrow](https://aiweb3.school/zh/handbook/bridge/settlement-and-escrow/)

### 核心认知
1. **Chain-aware Context**：链上状态（余额、交易、事件）必须实时进入 Agent 上下文，不是缓存旧数据
2. **Web3 Tool Use**：RPC 查链、合约读、钱包签、交易推——不同工具有不同权限等级
3. **Agent Workflow**：区分只读步骤（自动）和写入步骤（需 policy + human check）
4. **Agent Wallet**：Agent 的钱包要限制权限——额度、时间、白名单、可撤销
5. **Machine Payment**：机器小额支付用 Superfluid/Sablier 流支付
6. **Settlement**：自动化交易需要 escrow 合约，争议处理需要仲裁逻辑

### 知识清单
| 概念 | 一句话 |
|------|--------|
| 链感知上下文 | Agent 读取链上状态作为决策依据 |
| Web3 工具 | RPC 读 / 合约读 / 签名 / 交易推送 |
| 工作流分离 | 只读自动执行，写入需确认 |
| Session Key | Agent 的限权密钥（额度+白名单+过期） |
| Policy | 定义 Agent 能做什么不能做什么的规则 |
| 流支付 | Superfluid：按秒结算的支付流 |
| Escrow | 托管合约：锁定资产，条件释放 |

### 实践
1. 设计一个 Agent 的链上数据上下文（应该包含哪些实时数据）
2. 画一个 Agent 链上操作的工作流：用户目标 → 只读查询 → 方案生成 → User 确认 → 签名执行 → 记录
3. 设计一个 Session Key 的权限策略（示例：每天 ≤ 0.1 ETH，仅限白名单合约，超限需确认）

### 打卡
> Day 6：AI × Web3 Bridge（上）。链上状态要实时进上下文，Web3 工具按权限分级（只读 vs 写入），Agent Workflow 必须分离只读/写入步骤，Agent Wallet 用 Session Key + Policy 限权，机器支付用流支付。设计了 Agent 的链上工作流和 Session Key 策略。

---

## Day 7（5/27 周三）— AI × Web3 Bridge（下）+ 前沿探索

### 读 Handbook
- [Agent Identity](https://aiweb3.school/zh/handbook/bridge/agent-identity/)
- [Agent Trust & Reputation](https://aiweb3.school/zh/handbook/bridge/agent-trust-and-reputation/)
- [Verifiable AI](https://aiweb3.school/zh/handbook/bridge/verifiable-ai/)
- [AI Security](https://aiweb3.school/zh/handbook/bridge/ai-security/)
- [AI Privacy](https://aiweb3.school/zh/handbook/bridge/ai-privacy/)
- [Governance AI](https://aiweb3.school/zh/handbook/bridge/governance-ai/)
- [前沿探索](https://aiweb3.school/zh/handbook/tracks/) — 选 1-2 个赛道浏览

### 核心认知
1. **Agent Identity**：Agent 需要 DID/链上身份，用于授权、委托和责任追溯
2. **Trust & Reputation**：Agent 行为记录 → 声誉评分 → 可验证可信历史
3. **Verifiable AI**：模型输出、执行过程、结果可验证（EZKL/TEE/opshin）
4. **AI Security**：Prompt Injection、工具滥用、权限隔离、审计日志
5. **AI Privacy**：用户数据、链上身份、模型上下文之间的隐私边界
6. **Governance AI**：AI 辅助 DAO 治理（提案总结、投票分析、协作决策）

### 知识清单
| 概念 | 一句话 |
|------|--------|
| Agent Identity | 链上身份（DID），可授权可追溯 |
| Reputation | 行为记录驱动的可信评分 |
| Verifiable AI | 模型输出能被验证 |
| TEE | 可信执行环境，代码和数据保密 |
| ZK | 零知识证明，验证而不泄露 |
| Prompt Injection | 攻击者让模型忽略原始指令 |
| Guard | 工具调用前的安全检查层 |
| Simulation | 交易模拟，预览链上影响 |
| Privacy | 不能把用户所有数据都丢进模型上下文 |

### 实践（选做 1-2 个）
1. **产品方向**：写 1 页 your AI x Web3 product concept（你想做什么：Web3+AI 游戏？可验证 Agent？）
2. **技术方向**：画一个完整 AI x Web3 Agent 架构（LLM + Context + RAG + Wallet + Simulate + Guard）
3. **社区方向**：给 Handbook 提一个 feedback 到 `handbook-feedback/`
4. **项目方向**：写 hackathon 项目的 one-pager 草稿

### 打卡
> Day 7：Bridge（下）+ 前沿。Agent 需要链上身份和声誉系统，可验证 AI 让模型输出可审计，AI Security 和 Privacy 是产品落地的底线。今天选了方向，写了产品概念/架构图/one-pager。7 天 Handbook 全部跑完！

---

## 7 天路线图总览

```
Day 1  ┌─────────────────────────────────────┐
       │   LLM + Prompt（模型底层逻辑）        │
Day 2  │   Context + RAG + MCP（信息管理）      │
Day 3  │   Agent + Frameworks（执行系统）       │  ← AI 基础
Day 4  │   Network + Crypto + Wallet + Contract│
Day 5  │   AA + DeFi + Oracle + Index + Sec   │  ← Web3 基础
Day 6  │   Chain-aware + Tool + Workflow +     │
       │   Wallet + Payment + Settlement       │  ← Bridge（上）
Day 7  │   Identity + Trust + Verifiable AI +  │
       │   Security + Privacy + Governance     │  ← Bridge（下）+ 方向选择
       └─────────────────────────────────────┘
```

## 每日节奏
```
读 Handbook 章节（把每个知识节点过一遍，不需要全背）
做实践任务（动手试，写代码/画图/设计）
写 daily note（笔记+打卡草稿）
提交打卡
每天结束前回顾当天核心认知，想一下"这跟我的 Web3+AI 游戏方向有什么关系"
```
