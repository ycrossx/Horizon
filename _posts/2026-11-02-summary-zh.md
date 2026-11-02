---
layout: default
title: "Horizon Summary: 2026-11-02 (ZH)"
date: 2026-11-02
lang: zh
---

> 从 28 条内容中筛选出 5 条重要资讯。

---

**科技新闻**
1. [陶哲轩：AI 已改变数学实践，学界应调整规范](#item-tech-news-1) ⭐️ 8.0/10
2. [联想“加密”指纹 U 盘被指只是未加密 SD 卡](#item-tech-news-2) ⭐️ 7.0/10
3. [数据中心扩建的政治风险：2027 年在建、2028 年看选举](#item-tech-news-3) ⭐️ 7.0/10
4. [RLVR 理论：pass@1 增益必有代价，pass@k 交叉次数有紧界](#item-tech-news-4) ⭐️ 7.0/10

**科技博客**
1. [可靠对齐大模型在原理上不可能](#item-tech-blog-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [陶哲轩：AI 已改变数学实践，学界应调整规范](https://terrytao.wordpress.com/2026/11/01/mathematics-has-changed-lets-act-like-it/) ⭐️ 8.0/10

2026 年 11 月 1 日，Terence Tao（陶哲轩）发表文章《Mathematics has changed. Let&\#x27;s act like it》，主张 AI 已从根本上改变数学研究的实践方式，数学界应据此调整研究规范与工作流程。文章讨论的是研究文化与评价方式的变化，而不是发布新模型、工具或可复现的技术结果；现有信息未给出具体版本、性能指标或机构采纳范围。因此，文中的判断属于作者主张，尚不等同于已被独立验证的领域共识。

hackernews · smilelamp · 11月1日 18:28 · [社区讨论](https://news.ycombinator.com/item?id=50328251)

**「背景」** 这篇随笔出现在陶哲轩（Terence Tao）的博客上；一则 Telegram 摘录称其为 Frank Calegari 的客座文章。Hacker News 的评论者则把它与陶哲轩近几个月反复提到的“消化”结果联系起来：证明之外，让同行理解结果并据此提出新问题正变得更重要。

**「实际影响」** 对数学研究者和评审机构而言，最直接的影响在评价与验证环节：如果证明可以借助 AI 生成，就需要明确如何核查正确性、如何认定原创贡献与署名。有评论者转述数学家的抱怨称，相关证明往往冗长难懂，这意味着可读性与审稿负担会成为实际采纳时必须处理的问题。

**「社区讨论」** 评论者 kccqzy 赞同 Tao 的立场，认为即使证明完全由 AI 完成，只要研究者选对问题、彻底理解并据此推进新方向，就应获得实质的学术贡献认定。也有评论者提出不同角度：bsaul 把这一变化类比为从手工艺走向工业化生产，ethanlipson 则质疑为何讨论默认 AI 能力只停留在定理证明；Animats 转述称，部分数学家对证明冗长难懂以及数学的社会基础变化感到沮丧。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50328251">Mathematics has changed . Let &#x27; s act like it | Hacker News</a></li>
<li><a href="https://t.me/kmp500/756">kmp+ – Telegram</a></li>

</ul>
</details>

**标签**: `#AI for mathematics`, `#theorem proving`, `#LLM agents`, `#research workflows`, `#scientific discovery`

---

<a id="item-tech-news-2"></a>
### [联想“加密”指纹 U 盘被指只是未加密 SD 卡](https://www.reddit.com/r/technology/comments/1xl2pr3/lenovos_encrypted_fingerprint_usb_drive_is_just/) ⭐️ 7.0/10

据报道，联想一款以“指纹加密 U 盘”宣传的产品在拆解后被指内部只是未加密的 SD 卡加外壳，取出存储卡即可绕过指纹读取数据。这对购买或依赖该产品保存敏感数据的用户构成直接风险，也让外界质疑其安全设计、加密宣称和评审流程。目前公开材料未包含联想的解释。

hackernews · entryleveljobsc · 11月1日 14:34 · [社区讨论](https://news.ycombinator.com/item?id=50326099)

**「背景」** 所谓“AES-256 加密”意味着静态数据在没有密钥时不可读，而这款产品的指纹识别只充当了 USB 接口层面的访问开关：据安全研究者 Xusheng Li 的拆解，内部 SD 卡本身以明文存放文件，取出后可直接被电脑读取。Tom&\#x27;s Hardware 的报道还提到，同一项借助 AI 的后续调查在其他“安全”U 盘产品中发现了后门与硬编码密钥，即出厂时写入固件或芯片、无法由用户更换的密钥。

**「影响」** 对该产品的用户来说，最直接的做法是把它当作普通未加密存储：不要用指纹解锁来保护敏感文件，已存数据应迁移或改用经过独立验证的软件加密。

**「社区讨论」** 多位评论者认为这已不是普通漏洞，而是产品设计与安全评审的失职，并质疑联想是否还应被信任来制造安全硬件；也有人主张不要依赖厂商的硬件加密，而应在设备之上使用自由软件加密。另有评论调侃“FU100”的命名，并称除 Alibaba 等中国网站外难以找到该产品的商品页面。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tomshardware.com/tech-industry/cyber-security/lenovo-fingerprint-usb-stick-sold-as-aes-256-encrypted-had-a-plain-sd-card-inside-ai-assisted-follow-up-finds-a-backdoor-and-hardcoded-keys-in-other-secure-usb-products">Lenovo&#x27;s &#x27;encrypted&#x27; fingerprint USB drive is just an ...</a></li>
<li><a href="https://windowsforum.com/news/lenovo-thinkplus-usb-security-flaws-fu100-encryption-claim-and-other-drive-risks.450478/">Lenovo ThinkPlus USB Security Flaws: FU100 Encryption Claim ...</a></li>
<li><a href="https://www.thebrief.news/en/standard/article/38717/lenovo-fingerprint-usb-stick-sold-as-aes-256-encrypted-held-a-plain-sd-card">Lenovo Fingerprint USB Stick Sold as AES-256 Encrypted Held a ...</a></li>

</ul>
</details>

**标签**: `#hardware security`, `#encryption`, `#consumer devices`, `#Lenovo`, `#product teardown`

---

<a id="item-tech-news-3"></a>
### [数据中心扩建的政治风险：2027 年在建、2028 年看选举](https://newsletter.semianalysis.com/p/the-datacenter-backlash-goes-bipartisan) ⭐️ 7.0/10

SemiAnalysis 11 月 1 日的分析估计，其追踪的前 20 个州 2027 年待交付的 33.8 GW 数据中心容量中约四分之三已经开工，因此维持全球 2027 年新增约 50 GW 的预测；中期选举会改变规则，但难以扭转这部分在建项目。真正的政策风险集中在 2028 年：其模型预计美国净新增 62.2 GW，多数尚未开工，13 个重点州合计 43.5 GW、占全国 70%，其中 10 个州将在 11 月 3 日选举州长。德克萨斯州环境质量委员会（TCEQ）9 月 21 日冻结许可，叠加 8 月 3 日开始的并网队列审计，而德州约占 2028 年美国新增量的 30%；ERCOT 目标 12 月 10 日提交报告，但这本身不会自动重启审批，Abbott 与 Hinojosa 的立场差异可能使审批冻结从 12 月重启延长到接近一年。俄勒冈州 10 月 9 日把州土地冻结扩大到空气和排水许可，直至 2027 年 7 月 1 日；在 20 名州长候选人中，9 人主张暂停新建、11 人主张附加条件，党派分布大致均衡。

rss · Semianalysis · 11月1日 18:40

**「背景」** 这篇分析建立在 SemiAnalysis 早先的判断之上：9 月它曾估算，约 20 GW 受地方限制的数据中心容量中仅约 1.5 GW 会延期；10 月 16 日又给出 2027 年全球新增逾 50 GW 的预测。但此后限制范围扩大——得州州长 Abbott 于 2026 年 9 月 21 日指示 TCEQ 暂停发放数据中心相关许可，等待 ERCOT 完成审计和 TWDB 的用水审查；ERCOT 设定的 12 月 10 日报告目标并不自动解除这一冻结。

**「影响」** 对计划在 2028 年新增容量的开发商而言，德州环境质量委员会（TCEQ）的许可冻结把现场发电审批也纳入暂停范围，叠加 ERCOT 并网队列审计，使许可恢复时点成为项目排期的硬约束：审批不重启，依赖新许可的项目就无法按原时间表推进，而 ERCOT 定于 12 月 10 日提交的报告本身并不自动重新开闸。若民主党候选人 Hinojosa 当选并把暂停维持到立法通过，冻结可能覆盖 2027 年 1 月 12 日至 5 月 31 日的会期，比 12 月重启多出五到九个月，开发商需为德州项目预留更长的许可等待时间。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://pacificsoftwareventures.com/newsroom/texas-tceq-data-center-permit-halt-commercial-real-estate">Texas TCEQ Data Center Permit Halt: The CRE Read | PSV</a></li>
<li><a href="https://blockspace.media/insight/texas-data-center-permit-freeze/">Texas imposes open-ended freeze on data - center ... - Blockspace</a></li>
<li><a href="https://www.elpasotimes.com/story/news/politics/elections/2026/07/24/hinojosa-calls-for-data-center-moratorium-in-texas-gina-hinojosa-greg-abbott/91024223007/">Hinojosa calls on Abbott to sign data center moratorium in Texas</a></li>
<li><a href="https://www.cnbc.com/2026/08/20/ai-data-center-election-backlash.html">AI data center outrage is showing up everywhere from ads to elections</a></li>

</ul>
</details>

**标签**: `#data centers`, `#AI infrastructure`, `#technology policy`, `#US elections`

---

<a id="item-tech-news-4"></a>
### [RLVR 理论：pass@1 增益必有代价，pass@k 交叉次数有紧界](https://www.reddit.com/r/MachineLearning/comments/1xlnu1y/r_there_is_no_free_lunch_in_rlvr_under_strategy/) ⭐️ 7.0/10

一篇以 Reddit 帖形式发布、同时挂在 arXiv 上的理论论文（不含新的训练实验）把 RLVR 建模为基座策略在跨提示共享的解题策略上的指数倾斜；作者称该建模对镜像下降精确成立，且在模拟中同等熵下 GRPO 与它的总变差距离在 3e-4 以内。核心结论是“无免费午餐”：在排他性专精（exclusive specialization）条件下，任何提升 pass@1 的更新都会严格降低某些提示上的成功率，其精确条件表述为一个 Stiemke 对偶命题；作者还给出一个 3×3 反例，说明“在每个提示上都取最优策略”仍不足以避免这一代价。关于 pass@k，作者称一旦损失波及最难的提示，交叉就被强制出现，交叉次数不超过各提示成功率位移的符号变差（Karlin 全正性），该界在 1 到 6 次交叉范围内是紧的，保序情形恰好给出一次交叉，复现了已知的单交叉结果。论文附带代码和逐数字校验脚本，但作者自己指出共享策略模型是总体极限下的抽象，强制交叉依赖覆盖假设（论文也给出了失效区间），实际普适性尚未经独立验证。

reddit · r/MachineLearning · /u/SwimmingAmbition5148 · 11月2日 04:30

**「背景：从经验现象到理论刻画」** RLVR（可验证奖励强化学习）用可自动判定的奖励——数学答案与标准解一致、代码通过单元测试——来微调模型，从而不必依赖人工标注。2025 年 4 月的一项系统性研究（Yue 等，arXiv:2504.13837）在数学、代码和视觉基准上发现：RLVR 模型在小 k 的 pass@k（如 k=1）上优于基座模型，但 k 较大时基座模型反超；覆盖度与困惑度分析显示，这些推理能力源自基座模型，并受其边界限制。该文提出的“无免费午餐”结论正是要把这一已被多次观察到的 pass@1 与 pass@k 反超现象，从经验规律上升为可证明的结构性结论。

**「影响」** 作者称，评测日志中已有的基座与 RL 每提示成功率就足以读出交叉次数、界和最差 pass@k 损失，并用已发表 GRPO 的 Omni-MATH 数字（转录自 2607.20543，作者注明仅作示意）得到 k=64 到 k=256 之间的一次交叉。若这一诊断成立，RLVR 的收益就应连同逐提示的代价一并报告，而非只看聚合 pass@1；不过他提供的浏览器诊断工具与这些推论尚未由第三方复现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2504.13837">[2504.13837] Does Reinforcement Learning Really Incentivize ...</a></li>
<li><a href="https://limit-of-rlvr.github.io/">Limit of RLVR</a></li>

</ul>
</details>

**标签**: `#reinforcement learning`, `#RLVR`, `#pass@k`, `#LLM evaluation`, `#theory`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [可靠对齐大模型在原理上不可能](https://seangoedecke.com/alignment-is-impossible/) ⭐️ 7.0/10

rss · Sean Goedecke · 11月2日 00:00

**「背景」** 在 LLM 出现之前，AI 安全常把强大模型想象成执著于固定目标的“盲优化器”，因此把对齐理解为设定正确的目标。但现代 LLM 通过模仿庞杂的人类文本训练，没有可形式化的固定目标，其人格与目标随输入不断切换，靠规定目标来约束它们的路走不通。

**「方案」** 作者 Sean Goedecke 认为，剩下的路——把模型理解得足够透彻，从而确信它不会作恶——在原理上也不可行，甚至无法说清成功是什么样。他主张，对齐需要的是对人类意义上的“动机”的完整理解，而非逐权重追踪计算；但人类心智本就没有干净、可穷尽的动机层级，LLM 亦然。机械可解释性即使完全成功也救不了：我们只能给已观察到的行为贴标签，而最危险的突发行为按定义尚未出现；标签本身可能错，例如所谓“善良”可能是“除非到 2030 年才作恶”的善良；单个 token 涉及的 feature 组合又复杂到人无法解读，换另一个模型审查还会陷入“谁来审查审查者”的回归。作者承认思维链监控、沙箱、人类在环和激活监测等缓解手段有用，但认为它们不足以发现或控制超级智能；可解释性能帮助减少奖励黑客、改善日常表现，却不能保证智能体不失控。这是概念论证，而非实验测量或形式证明。

**「启示」** 作者的核心论点是：LLM 对齐不只是工程上难，而是“确信模型安全”所需的动机理解本身无法定义，也无法由机械可解释性提供；因此可靠对齐在原理上不可实现，现有缓解只能降低风险，不能给出安全保证。

**标签**: `#AI alignment`, `#mechanistic interpretability`, `#LLM safety`, `#AI risk`, `#philosophy of mind`

---