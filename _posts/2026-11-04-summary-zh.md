---
layout: default
title: "Horizon Summary: 2026-11-04 (ZH)"
date: 2026-11-04
lang: zh
---

> 从 507 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [大规模运行 Mac 的运维变通方案](#item-tech-news-1) ⭐️ 8.0/10
2. [Postman 被指静默安装 AI 插件并共享 API 数据](#item-tech-news-2) ⭐️ 8.0/10
3. [简单特征在代码后门基准上胜过多数 LLM 监控器](#item-tech-news-3) ⭐️ 8.0/10
4. [从噪声测量中学习干净生成过程](#item-tech-news-4) ⭐️ 8.0/10
5. [自构建实验室：从高层目标自动搭建实验平台](#item-tech-news-5) ⭐️ 8.0/10
6. [AWM：从环境探索到 Lean 4 形式化证明](#item-tech-news-6) ⭐️ 8.0/10
7. [研究：GPT-4o 或能识别未授权的付费书籍内容](#item-tech-news-7) ⭐️ 8.0/10
8. [PCM 用 Lean 4 为 MLIP 提供可证伪安全证书](#item-tech-news-8) ⭐️ 8.0/10
9. [DialFork：评估对话智能体的程序性幻觉](#item-tech-news-9) ⭐️ 8.0/10
10. [统一黑盒攻击可绕过多种统计式大模型水印](#item-tech-news-10) ⭐️ 8.0/10
11. [Anthropic 发布 FlashProve 原型：用 zkSNARK 证明模型来源](#item-tech-news-11) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [大规模运行 Mac 的运维变通方案](https://namespace.so/blog/mac-at-any-scale) ⭐️ 8.0/10

namespace.so 的博客文章《Mac at any scale》详细讨论了在基础设施和持续集成（CI）场景中大规模运行 Mac 硬件的做法，重点是为 Apple 平台的限制寻找变通方案。所给材料未包含独立性能测量，因此文章更接近运维经验总结，而不是产品发布或基准测试。该文在 Hacker News 上引发了显著讨论，评论者主要从 Apple 生态的自动化、代码签名和服务器可用性角度补充了各自的经验。

hackernews · Hacker News · 11月3日 14:53 · [社区讨论](https://news.ycombinator.com/item?id=50352758)

**「背景」** 面向 iOS/macOS 的云端构建与测试需要真实的 Mac 硬件，无法只靠常规虚拟化扩容：Namespace 为此在数据中心里使用数百台 MacBook Pro 承担构建和测试任务。这一选择有其具体原因：该公司 1 月下单的 Mac mini 直到 7 月才到货，而客户又需要更早用上更新的芯片；其文档目前列出 macOS 实例运行在 M4 Pro 或 M5 Max 处理器上。

**「影响」** 对依赖 macOS 做 CI/CD 的团队，这意味着不能把 Mac 当作标准 Linux 服务器来管理：无头启动后的解锁、代码签名和自动化工具链都可能需要额外的人工作业或定制脚本，从而抬高整体运维成本。

**「社区讨论」** 评论普遍把文章视为 Apple 生态运维痛点的例证：有人称即便 Apple 推出价格翻倍但性能相当于 Mac mini 的 Xserve 仍会有人买，也有人批评 Xcode Cloud 以及签名和证书流程繁琐；一位读者还提到，Mac mini 作服务器时，启动后的密码解锁会成为无头运行的硬门槛。上述内容均为评论者观点或个人经验，并非文章或 Apple 的确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://dzen.ru/b/auobbcRL2iIDzEZm">Namespace поставила сотни MacBook в стойки вместо Mac ... | Дзен</a></li>
<li><a href="https://namespace.so/docs/architecture/compute/macos">macOS - Namespace Documentation</a></li>

</ul>
</details>

**标签**: `#macOS`, `#infrastructure`, `#CI/CD`, `#Apple ecosystem`, `#data center operations`

---

<a id="item-tech-news-2"></a>
### [Postman 被指静默安装 AI 插件并共享 API 数据](https://github.com/postmanlabs/postman-app-support/issues/14370) ⭐️ 8.0/10

一个 Postman GitHub 支持仓库的 issue 指控 Postman 静默自动安装 AI 插件，并试图共享全部 API 数据；相关讨论随后在 Hacker News 上展开。上述说法来自 issue 标题和讨论，所给材料没有提供 Postman 的回应或独立验证，因此应视为尚未证实的指控。争议的核心是这款广泛使用的 API 开发工具对插件安装、请求数据和网络外联的控制权。

hackernews · Hacker News · 11月3日 17:22 · [社区讨论](https://news.ycombinator.com/item?id=50354960)

**「背景」** GitHub 议题 \#14370 的提交者报告称，Postman Desktop 12.33.4 在启动后自动安装了 Codex 插件 1.1.0 和 Claude Code 插件 2.0.1，并写入了用户级插件、启动钩子和远程 MCP 连接。相关日志把触发来源显示为 \`auto-existing-upgrade\`，但这些细节目前来自议题提交者及后续报道，尚不能视为独立验证的结论。

**「影响」** 对把密钥写入 \{\{...\}\} 模板变量的用户，评论者报告的实际风险是 Postman 可能将展开后的真实值发送到其服务器；该评论者还称，阻断相关日志端点会让应用无法正常工作。

**「社区讨论」** 多名评论者批评 Postman 因商业化和功能膨胀而变慢，并报告已迁移到 Bruno，理由包括可把请求定义存入 Git；一名医疗行业用户还称其网络安全团队因此取消了对 Postman 的认证。这些是个人经验和观点，不是对自动安装插件或数据共享指控的独立验证；另有评论者把问题归因于公司融资和估值压力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/postmanlabs/postman-app-support/issues/14370">[SEVERE] Desktop auto-installs Codex/Claude plugins; installer ... - GitHub</a></li>
<li><a href="https://aiweekly.co/alerts/postman-desktop-silently-installs-plugins-into-codex-claude-code">Postman Desktop Silently Installs Plugins Into Codex, Claude Code | AI ...</a></li>

</ul>
</details>

**标签**: `#postman`, `#privacy`, `#security`, `#developer-tools`, `#api-clients`

---

<a id="item-tech-news-3"></a>
### [简单特征在代码后门基准上胜过多数 LLM 监控器](https://arxiv.org/abs/2610.41713) ⭐️ 8.0/10

这篇 arXiv 论文（2610.41713）显示，在一个标准的带后门代码检测基准上，无需运行代码的简单代码特征与问题特征，排名超过了 24 个开源权重 LLM 监控器中的 20 个。论文指出，该数据集通过两种方式泄露标签：诚实解法由人编写，后门由较旧的模型生成，因此代码风格本身就会暴露类别；能被 LLM 植入后门的问题也具有不同特征，仅凭题目基本信息即可区分。将其中一类样本替换为 Claude Sonnet 5 生成的代码后，人类代码与 Sonnet 5 后门之间的区分度达到 0.95，高于原始配对的 0.79；标准测试集中每七个后门就有一个未通过有效性检查，这会扭曲攻击者之间的比较。作者报告，一个 Sonnet 5 监控器看似能捕获旧模型 77% 的后门，却只捕获 Sonnet 5 后门的 37%，经双方验证后为 78% 对 61%；他们并未证明已发布监控器依赖这些捷径，但认为此类数据集上的高分本身不足以证明具备破坏检测能力，并发布了重建数据集与检查工具。

rss · arXiv cs.AI · 11月3日 05:00

**「背景：AI 控制与监控器评测」** AI 控制协议是一类防御机制，用于阻止自主运行中的不可信 LLM 智能体造成危害，监控器则负责检查这些智能体是否暗中完成植入后门等有害子任务。因此，监控器能否区分诚实代码与后门代码，是评估控制协议有效性的关键环节；这类评测通常使用成对的诚实代码和后门代码来衡量监控器的识别能力。

**「影响」** 对使用该基准评估 AI 控制监控器的团队来说，单个高分不能直接作为检测能力或部署决策的证据；应使用重建数据、匹配作者与代码风格，并报告后门标签的有效性检查，否则不同攻击者之间的比较会被污染。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2510.09462">Adaptive Attacks on Trusted Monitors Subvert AI Control Protocols</a></li>

</ul>
</details>

**标签**: `#AI control`, `#benchmark validity`, `#code backdoors`, `#LLM evaluation`, `#data leakage`

---

<a id="item-tech-news-4"></a>
### [从噪声测量中学习干净生成过程](https://arxiv.org/abs/2610.42036) ⭐️ 8.0/10

论文提出一种仅用独立噪声观测学习干净图像生成模型的方法，将 Noise2Noise 回归与一致性约束结合，用于扩散过程及其非高斯噪声推广。作者指出，Noise2Noise 只能在训练数据噪声水平及以上学到后验预测；为生成干净图像，他们要求预测等于继续采样后的期望，并推导出一致性唯一确定向干净图像分布延拓的条件。这些条件在泊松、二项、伽马和负二项测量下得到验证；CIFAR-10、光子计数显微和合成孔径雷达实验显示，后验预测可仅从噪声视图学习，且一致性关系能修复超出数据噪声水平的延拓，而无一致性时该延拓会严重退化。

rss · arXiv cs.AI · 11月3日 05:00

**「背景」** 扩散模型及其向非高斯噪声的推广，需要在每个噪声水平上给出后验预测，才能完成从噪声到干净图像的采样。Noise2Noise 类回归方法允许仅用相互独立的噪声观测来训练去噪器，但源摘要指出，这类监督只在训练数据所处噪声水平及以上有效。该论文的工作正是针对这一缺口：在低于训练噪声水平的区间引入“预测应等于继续采样后其期望”的一致性约束，并针对泊松、二项、Gamma 与负二项测量推导该约束唯一确定延续至干净图像分布的条件。

**「影响」** 对于只有噪声观测、缺少干净参考的显微成像或合成孔径雷达应用，这项工作提供了一条不依赖干净训练对的生成模型训练路径；但其适用性目前受限于论文验证的泊松、二项、伽马和负二项噪声模型，以及摘要中报告的实验范围。

**标签**: `#diffusion models`, `#generative models`, `#denoising`, `#Noise2Noise`, `#computational imaging`

---

<a id="item-tech-news-5"></a>
### [自构建实验室：从高层目标自动搭建实验平台](https://arxiv.org/abs/2610.23826) ⭐️ 8.0/10

arXiv 预印本 2610.23826v2 提出“自构建实验室”（SBL）：给定高层科学目标后，系统能自行设计、配置并运行实验装置；它可从空房间或已有的自驱动实验室出发，补齐实验室布局、数字孪生、机器人技能和实验工作流。作者称，该系统已在不同机器人和装置上演示，规模覆盖从单工作站到多机器人协同，并用真实量子点合成实验完成端到端验证。该文目前是预印本，摘要未提供同行评审、独立复现或详细性能数据。

rss · arXiv cs.AI · 11月3日 05:00

**「背景」** 自驱动实验室（SDL）把实验执行和参数优化自动化，但现有系统通常只能运行为其专门搭建的流程；换用新实验时，往往还需人工重新设计布局、编写机器人技能和实验工作流，灵活性因此成为扩大发现规模的瓶颈。据 AI Accelerator Institute 报道，已有自驱动实验室用四台 AI 驱动机器人并行运行 96 个微型钙钛矿量子点实验，但整套装置仍是针对一种明确的化学体系定制的。

**「影响」** 按摘要描述，对已经运行自驱动实验室的团队，SBL 的目标是复用现有条件、补齐缺失能力，从而减少为每个新实验重新手工配置和编程自动化装置的工作；但摘要没有给出兼容性、所需人工介入程度或失败率等可操作指标。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2610.23826">[2610.23826] Self-Building Labs - arXiv.org</a></li>
<li><a href="https://www.aiacceleratorinstitute.com/self-building-labs-hand-ai-agents-the-keys-to-the-whole-lab/">Self-building labs: AI agents that build their own lab</a></li>

</ul>
</details>

**标签**: `#self-driving laboratories`, `#lab automation`, `#robotics`, `#AI agents`, `#scientific discovery`

---

<a id="item-tech-news-6"></a>
### [AWM：从环境探索到 Lean 4 形式化证明](https://arxiv.org/abs/2610.40503) ⭐️ 8.0/10

arXiv 预印本（v2）提出代数世界模型（AWM）：它先在陌生环境中探索，生成可执行的 Python 假设，并依据观察反复修正；随后把这些假设组织为带类型的对象和共享规则，经范畴论引导的简化后写入 Lean 4，以证明目标可达或不可达。作者称，在两个不可通关的游戏关卡上，AWM 的六次运行均构造出封闭、经内核检查的 Lean 证明，排除所有合法获胜序列；作为对照，配备编码工具的 Claude Opus 5.5 和 GPT-6 Astra 在十二次基线运行中均未产出此类证明。AWM 初始给出的六个上界中四个正确（Opus 5.5 为一个、GPT-6 Astra 为零），仅收到“存在更省步数的获胜方式”的反馈后，它修改规则并达到六项全对。论文还称，在全部 25 个公开 ARC-AGI-3 游戏中，这些模型让 Lean 重放全部 183 个关卡的获胜轨迹，并能预测未见过的状态转移和检测游戏机制变化；配合 Claude Opus 5，AWM 通关所有关卡、得分 99.9，其经认证的获胜轨迹仅用人类基线 43% 的动作。

rss · arXiv cs.AI · 11月3日 05:00

**「背景」** 此前，AI 在数学领域的进展多建立在预先给定的定义和形式化规格之上，Lean 4 证明也通常针对这些既定对象进行机器核验。AWM 面对的是没有现成数学描述、只能通过交互观察的陌生环境，因此需要先把探索中得到的规律转化为可执行、可检查的模型，再交由证明器验证。

**「影响」** 对使用 Lean 4 的形式化方法与 AI 推理研究者而言，AWM 的关键后果是把探索得到的规则转成可检查、可逐步测试的模型，并尝试证明探索范围之外的不可达性。但这是尚未独立复现的预印本结果，采用前应核对证明脚本、基线配置和 ARC-AGI-3 评测条件，而不能只依据论文中的对比数字。

**标签**: `#AI for mathematics`, `#formal verification`, `#Lean 4`, `#world models`, `#program synthesis`

---

<a id="item-tech-news-7"></a>
### [研究：GPT-4o 或能识别未授权的付费书籍内容](https://arxiv.org/abs/2505.00020) ⭐️ 8.0/10

一项 arXiv 预印本研究用 DE-COP 成员推断攻击测试 OpenAI 模型是否认识其未获授权训练的付费内容，数据集为合法获得的 34 本 O&\#x27;Reilly Media 版权书籍、共 13,962 个段落。结果显示，GPT-4o 对非公开书籍的识别 AUROC 为 0.82（95% 自助法置信区间 0.60–0.96），高于随机猜测；GPT-3.5 Turbo 和 GPT-4o Mini 分别为 0.54 和 0.56，接近随机。作者称结果在 Gemma、Qwen 改写和留一书籍敏感性分析下保持稳健，并用训练截止日期同为 2023 年 10 月的 GPT-4o 与 GPT-4o Mini 控制语言随时间变化的影响，但强调样本仅 34 本书、可能存在后截止控制污染及模型差异，结论仍是初步的。

rss · arXiv cs.AI · 11月3日 05:00

**「背景：DE-COP 方法与本次测试对象的变化」** DE-COP 是 2024 年提出的一种成员推断方法：它向模型提出多项选择题，选项同时包含原文片段和对应的改写版本，再依据模型是否系统性地偏好原文，判断该内容是否出现在训练数据中。此前该工作主要用于检测语言模型训练数据中的受版权保护内容；本研究把测试对象换成 34 本需要付费订阅的 O&\#x27;Reilly 图书，因此除了判断内容“是否被用于训练”，还试图识别模型是否接触过未获授权的非公开材料。

**「影响」** 若这一信号在更大样本中得到验证，依赖版权内容的企业在模型采购和审计中就不能只依赖供应商的公开数据声明，而应要求披露预训练数据来源与授权记录；作者据此主张建立正式的培训内容许可市场和数据来源披露要求。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2402.09910">[2402.09910] DE-COP: Detecting Copyrighted Content in ... DE-COP: Detecting Copyrighted Content in Language Models ... DE-COP: Detecting Copyrighted Content in Language Models ... Beyond public access in LLM pre-training data - AI and Ethics Beyond public access in LLM pre-training data | AI Sec Watch Did OpenAI train on copyrighted book content? Beyond Public Access in LLM Pre-Training Data: Non-public ...</a></li>
<li><a href="https://proceedings.mlr.press/v235/duarte24a.html">DE-COP: Detecting Copyrighted Content in Language Models ...</a></li>

</ul>
</details>

**标签**: `#membership inference`, `#LLM training data`, `#copyright`, `#OpenAI`, `#model auditing`

---

<a id="item-tech-news-8"></a>
### [PCM 用 Lean 4 为 MLIP 提供可证伪安全证书](https://arxiv.org/abs/2603.12183) ⭐️ 8.0/10

arXiv 预印本（尚未经同行评审）《Proof-Carrying Materials》提出一套三阶段流程：跨成分空间的对抗性证伪、带 95% 置信区间的 bootstrap 包络细化，以及 Lean 4 形式化认证，为机器学习原子间势（MLIP）给出可证伪的可靠性保证。作者报告，在 25,000 种材料的基准上，若把单个 MLIP 当作稳定性过滤器，会漏掉 93% 的 DFT 稳定材料（召回率 0.07）。对 CHGNet、TensorNet 与 MACE 的审计显示，不同架构存在各自的盲区，两两误差相关性接近零（r ≤ 0.13，n = 5,000），并由 Quantum ESPRESSO 独立验证（20/20 收敛，DFT/CHGNet 力中位数比为 12 倍）。基于 PCM 所发现特征训练的风险模型能预测未见材料的失败，AUC-ROC 为 0.938 ± 0.004；跨架构迁移时 AUC-ROC 约 0.70，特征重要性相关 r = 0.877。在热电材料筛选案例中，经 PCM 审计的流程比单 MLIP 筛选多找到 62 种稳定材料，作者称发现率提升 25%。

rss · arXiv cs.AI · 11月3日 05:00

**「背景」** 机器学习原子间势（MLIP）通过拟合第一性原理势能面，以接近 DFT 的精度支撑大规模原子尺度模拟；CHGNet、MACE、TensorNet 等通用势已被用于高通量材料筛选。由于这些模型来自数据拟合，其预测误差通常没有可证明的界限；此前对通用 MLIP 的系统评估也主要停留在与 DFT 的数值比对层面。

**「对筛选流程的影响」** 对使用单一 MLIP 做稳定性筛选的团队而言，最直接的后果是筛选流程的漏检率被量化：在 25,000 种材料的基准上，单一模型只召回 0.07 的 DFT 稳定材料；而 PCM 审计后的协议在热电筛选案例中多找到 62 种稳定材料，发现率提高 25%。但跨架构风险模型的 AUC-ROC 仅约 0.70（同架构为 0.938），意味着用一个架构训练出的失效预测器迁移到 CHGNet、TensorNet、MACE 时判别能力明显下降，实际部署中仍需逐架构重新做对抗证伪与置信区间校准。此外，Lean 4 形式化认证给流程增加了证明维护成本；该结论来自预印本，尚未经独立复现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.researchgate.net/publication/392371374_DistMLIP_A_Distributed_Inference_Platform_for_Machine_Learning_Interatomic_Potentials">(PDF) DistMLIP: A Distributed Inference Platform for Machine ...</a></li>
<li><a href="https://www.emergentmind.com/topics/machine-learning-interatomic-potentials-fa45c36b-1537-4d6c-b9f9-89cc66c0bc8c">ML Interatomic Potentials</a></li>
<li><a href="https://www.academia.edu/172040697/Systematic_assessment_of_various_universal_machine_learning_interatomic_potentials">(PDF) Systematic assessment of various universal machine - learning ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Machine-learned_interatomic_potential">Machine - learned interatomic potential - Wikipedia</a></li>
<li><a href="https://arxiv.org/abs/2603.12183v2">[2603.12183v2] Proof-Carrying Materials : Falsifiable Safety...</a></li>

</ul>
</details>

**标签**: `#machine-learned interatomic potentials`, `#formal verification`, `#Lean 4`, `#materials science`, `#AI reliability`

---

<a id="item-tech-news-9"></a>
### [DialFork：评估对话智能体的程序性幻觉](https://arxiv.org/abs/2610.21561) ⭐️ 8.0/10

论文作者发布 DialFork，一个用于测量对话智能体“程序性幻觉”的基准：智能体的话术流畅、事实也看似合理，却偏离既定对话流程。该基准通过在受控轮次切分合规对话并注入四类幻觉，构建了覆盖 12 个领域、24 项任务的 36,278 段对话，并由 30 名人工标注者验证。它定义三项评估任务，分别衡量一组对话整体偏离程度、单段对话偏离程度，以及对话首次偏离发生的轮次；前两项配套提出 FlowKL 与 FlowScore。该工作目前为 arXiv 预印本，作者所称“首个”及效果尚未经独立验证；代码与数据以开放许可发布。

rss · arXiv cs.AI · 11月3日 05:00

**「背景」** 对话式智能体常被要求按照既定流程办事，但既有幻觉评测主要检查单条陈述是否符合事实，难以捕捉“每句话都合理、步骤却走偏”的失败。DialFork 将这种对预定对话流程的偏离称为程序性幻觉，并以合规对话在受控轮次分叉、注入错误的方式构造样本，再按对话如何展开而非内容相似度来度量偏离。

**「影响」** 对部署对话智能体的团队而言，仅靠语义相似度做监控或检索可能漏掉流程偏离；论文报告在七种编码器上，FlowScore 在对话级评估中显著优于所有基线，可作为流程感知评估的候选指标，但仍需在自有业务和预印本复现条件下验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/papers/2610.21561">Paper page - DialFork : Going Beyond Factuality to Evaluate...</a></li>

</ul>
</details>

**标签**: `#LLM evaluation`, `#conversational agents`, `#hallucination`, `#benchmark`, `#dialogue systems`

---

<a id="item-tech-news-10"></a>
### [统一黑盒攻击可绕过多种统计式大模型水印](https://arxiv.org/abs/2610.27653) ⭐️ 8.0/10

一篇 arXiv 预印本（2610.27653v2）提出一种统一的黑盒攻击框架，声称可同时绕过 KGW 及其变体、GumbelSoft、DipMark、ITS 和 SynthID 等主流统计式大模型水印。作者称这些方案存在“分数-比率对齐”（score-ratio alignment）的共同弱点：检测分数与生成过程中引入的 token 概率偏移之间存在固定关联，攻击者只需黑盒查询模型，无需知道密钥或模型权重，就能生成既流畅自然又逃避检测的文本。作者进一步给出最优性证明，称该攻击在覆盖的水印族中均为最优，并论证这一弱点具有内在性——任何以最大化统计检测力为目标的水印都会制造出可被利用的结构。实验覆盖七种生成式水印方案、三个大模型及多类任务，报告所有设置下检测率被压至至多 0.05 且保持文本质量；这些结论来自尚未经同行评审的预印本，属作者自述结果。

rss · arXiv cs.AI · 11月3日 05:00

**「背景」** 统计式大语言模型水印通常在生成每一步修改下一 token 的采样，将可统计检测的信号嵌入文本；KGW 是这一路线的经典学术方案。此类方法因此能用于追溯生成内容，但其对采样过程的干预会直接改变模型输出分布，使检测信号与生成时的概率调整相互关联。

**「对水印溯源的实际影响」** 对使用 KGW 及其变体、GumbelSoft、DipMark、ITS 或 SynthID 等统计水印做 AI 文本溯源的部署方，该预印本报告在黑盒查询、无需密钥或模型权重的条件下，把七种方案、三个模型及多任务设置下的检测率压到不超过 0.05，说明仅凭这类水印分数判定文本来源的取证流程在对抗性规避面前可能失效。论文据此主张检测分数与 token 概率偏移必须解耦；在采信结论前，相关团队应复现实验结果，并把对抗性改写纳入上线前的检测评估，因为该工作仍是未经同行评审的 arXiv 预印本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.linkedin.com/pulse/llm-watermarking-2026-how-thing-actually-works-what-its-good-zakyf">LLM Watermarking in 2026: How the Thing Actually Works, What...</a></li>
<li><a href="https://files.sri.inf.ethz.ch/website/papers/rieff26marking.pdf">Marking the Wrong Symptoms: Evaluating LLM</a></li>

</ul>
</details>

**标签**: `#LLM watermarking`, `#AI security`, `#adversarial attacks`, `#generative models`, `#arXiv`

---

<a id="item-tech-news-11"></a>
### [Anthropic 发布 FlashProve 原型：用 zkSNARK 证明模型来源](https://www.reddit.com/r/artificial/comments/1xn4g6l/anthropics_flashprove_cryptographic_proof_that_a/) ⭐️ 8.0/10

Anthropic 于 11 月 2 日（与 EPFL、MIT 等机构合作者）公布名为 FlashProve 的可验证推理研究原型，它用 zkSNARK 证明一条回复确实由某组已承诺的模型权重产生，同时不公开这些权重，从而让评估者或终端用户核查自己拿到的是被承诺的模型，并发现 token 流在中途被篡改。公布的数据显示，在 Llama 4 Maverick（400B 参数混合专家模型、4-bit 权重）上，生成证明的耗时约为 vLLM 运行该模型的 70 至 95 倍 GPU 时间。代码和 Lean 形式化证明以 Apache 2.0 协议开源。Anthropic 明确称其为研究原型，限制包括：上下文最长仅 1,024 token，证明针对的是贪心解码下的整数版模型，且模型架构本身并未隐藏。

reddit · r/artificial · /u/winer666 · 11月3日 20:37

**「背景」** 可验证推理针对的问题是：托管模型的提供方可能在不告知用户的情况下替换模型，或篡改返回的 token 流。zkSNARK（零知识简洁非交互式知识论证）允许证明者向验证者证明某段计算被正确执行，同时不暴露计算所用的私有输入；用于大模型推理时，就是把权重承诺和逐 token 的解码过程纳入可验证的计算。Anthropic 在公布 FlashProve 时也把这一密码学工具作为实现可验证推理的基础。

**「影响」** 按目前的 70 至 95 倍开销和 1,024 token 上下文上限，这类证明更现实的用途是审计、合规核查和抽样验证，而非在线上服务中为每条回复实时生成；验证方还需要能取得被承诺的具体权重版本才能完成校验，这意味着它难以直接用于普通用户日常判断托管模型是否可信。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/research/provable-inference">Progress on provable inference for large language models</a></li>
<li><a href="https://www.aicentralresources.com/news/anthropic-provable-inference-flashprove-zksnark">Anthropic Unveils Provable Inference Breakthrough via FlashProve</a></li>

</ul>
</details>

**标签**: `#verifiable inference`, `#zkSNARKs`, `#AI provenance`, `#Anthropic`, `#open-source research`

---