---
layout: default
title: "Horizon Summary: 2026-11-03 (ZH)"
date: 2026-11-03
lang: zh
---

> 从 47 条内容中筛选出 13 条重要资讯。

---

**科技新闻**
1. [Linux 内核 TCP 高危释放后使用漏洞 CVE-2026-98432](#item-tech-news-1) ⭐️ 8.0/10
2. [vLLM v0.33.0rc3 发布：升级 PyTorch 2.14 并仅提供 CUDA 13.0 构建](#item-tech-news-2) ⭐️ 7.0/10
3. [Subvocal 展示射频静默语音眼镜，首批 500 副开放预售](#item-tech-news-3) ⭐️ 7.0/10
4. [Cloudflare 称 DNS 区域构建延迟减半、内存降 85%](#item-tech-news-4) ⭐️ 7.0/10
5. [Ubuntu LTS 内核据称近三周未修复关键 RCE 漏洞](#item-tech-news-5) ⭐️ 7.0/10
6. [LightMIS：面向边缘设备的 13.1 万参数分割模型](#item-tech-news-6) ⭐️ 7.0/10
7. [ChatGPT 分享链接漏洞可致会话代码执行，OpenAI 已修复](#item-tech-news-7) ⭐️ 7.0/10
8. [WIRED：400 多个 AI 应用被指暗藏色情深伪功能](#item-tech-news-8) ⭐️ 7.0/10

**科技博客**
1. [LLM 并非超人类：拆解直接读写权重的演示](#item-tech-blog-1) ⭐️ 7.0/10
2. [受众捕获：当代理指标反客为主](#item-tech-blog-2) ⭐️ 7.0/10

**财经新闻**
1. [甲骨文拟发 100 亿美元股票和 100 亿美元高级票据，股价跌 6%](#item-finance-news-1) ⭐️ 7.0/10
2. [Marvell 以 1150 亿美元全股票收购 Lumentum；雅诗兰黛第一财季业绩超预期](#item-finance-news-2) ⭐️ 7.0/10
3. [英国提出将多数移民定居等待期由 5 年延至 10 年](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Linux 内核 TCP 高危释放后使用漏洞 CVE-2026-98432](https://telegram.me/zaihuapd/44866) ⭐️ 8.0/10

一则 Telegram 安全提醒称，Linux 内核 IPv4 TCP 存在高危释放后使用漏洞 CVE-2026-98432，攻击者可未经认证、无需用户交互地从网络侧触发。该提醒称 Anthropic 已公布针对 MPTCP 监听端口的远程代码执行利用示例，并强调漏洞并不只影响 MPTCP 场景。提醒还转述 Go 官方安全团队的说法：自 Go 1.24 起，Linux 上的 listen socket 默认启用 MPTCP，因此用 Go 编写的服务默认处于暴露状态，即使没有 MPTCP 监听也可能受到同类攻击。但该帖未提供受影响内核版本、补丁或缓解措施，也未附原始安全公告；服务器管理员应先核实所用发行版的安全公告，并尽快更新内核。

telegram · zaihuapd · 11月3日 02:37

**「背景」** 释放后使用指程序继续访问已释放的内存；该漏洞位于 Linux 内核处理入站 IPv4 TCP 连接建立的代码，涉及 TCP request socket 的 IPv4 选项数据的所有权与回收。Linux 内核 CVE 团队将其评为 CVSS 9.8（Critical），攻击向量为网络，且无需权限或用户交互。

**「实际影响」** 用 Go 1.24 及以上版本编译、运行在 Linux 上的服务默认就处于暴露状态：据 IONIX 与 Atlas 的漏洞条目，Go 1.24 起监听套接字默认启用 MPTCP，而 Anthropic 公布的 RCE 示例正是针对 MPTCP 监听端口，因此这些服务不能假设自己“没开 MPTCP 就安全”。Atlas 称上游已于 10 月 15 日修复、CVSS 评分 9.8，运维方的直接动作应是尽快升级到含该修复的内核；未打补丁前，对公网监听的 Go 服务应按已暴露处理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://almalinux.org/blog/2026-10-30-cve-2026-98432/">CVE - 2026 - 98432 : Patched kernels available in testing | AlmaLinux OS</a></li>
<li><a href="https://www.penligent.ai/hackinglabs/cve-2026-98432/">CVE - 2026 - 98432 Linux TCP Flaw, Ubuntu Patch and Mitigation Status</a></li>
<li><a href="https://www.ionix.io/threat-center/cve-2026-98432/">CVE - 2026 - 98432 – Unauthenticated Use-After-Free... - IONIX</a></li>
<li><a href="https://lilting.ch/en/articles/linux-ipv4-tcp-options-uaf-mptcp-rce">CVE - 2026 - 98432 Linux TCP Use-After-Free Can Give... | lilting channel</a></li>
<li><a href="https://atlasum.net/blog/cve-2026-98432-linux-ipv4-tcp-uaf">Linux&#x27;s October 2026 TCP Use-After-Free: CVE - 2026 - 98432 — Atlas</a></li>

</ul>
</details>

**标签**: `#Linux kernel`, `#security vulnerability`, `#TCP`, `#Go`, `#remote code execution`

---

<a id="item-tech-news-2"></a>
### [vLLM v0.33.0rc3 发布：升级 PyTorch 2.14 并仅提供 CUDA 13.0 构建](https://github.com/vllm-project/vllm/releases/tag/v0.33.0rc3) ⭐️ 7.0/10

vLLM 发布 v0.33.0rc3 候选版本，包含来自 389 位贡献者的 927 个提交，新增 Reflection Beam-1.0（501B MoE、23B 激活）、Yandex AliceAI-Foundation-80B-A3B、Recursive Flint 等模型支持。该版本将运行时升级到 PyTorch 2.14.0、torchvision 0.29.0 和 Triton 3.8.0，并停止发布 CUDA 12.9 wheel 及 -cu129 镜像，默认仅提供 CUDA 13.0 构建。CUDA wheel 现在与 libtorch ABI 稳定，同时新增带 AWS EFA 的镜像和 vllm/vllm 镜像别名。升级还需注意破坏性变更：移除 Medusa 和 MLP speculator、旧版 Ray 编译图执行器，NIXL connector 要求 1.5 或更高版本。

github · khluu · 11月2日 10:10

**「背景」** vLLM 是广泛使用的 LLM 推理与服务引擎，其发布流程此前同时提供 CUDA 12.9 与 CUDA 13.0 两套预编译 wheel 和 Docker 镜像，\`-cu129\` 与 \`-cu129-ubuntu2404\` 标签就对应 CUDA 12.9 这一支。本版发布说明显示该构件线被取消，转而只发布 CUDA 13.0 构件，并同时把底层依赖升级到 PyTorch 2.14.0、torchvision 0.29.0 与 Triton 3.8.0，因此仍停留在 CUDA 12.9 环境的部署需要改用默认的 CUDA 13.0 构件。

**「影响」** 依赖 CUDA 12.9 镜像或 wheel 的部署需要改用 CUDA 13.0，或留在旧版本；依赖 Medusa、MLP speculator、旧 Ray 编译图执行器及 NIXL 1.5 以下版本的配置在升级后会失效，应在升级前迁移。

**标签**: `#vllm`, `#llm-inference`, `#release-notes`, `#pytorch`, `#cuda`

---

<a id="item-tech-news-3"></a>
### [Subvocal 展示射频静默语音眼镜，首批 500 副开放预售](https://news.ycombinator.com/item?id=50340088) ⭐️ 7.0/10

YC F26 创业公司 The Subvocal Company 在 Hacker News 展示了其智能眼镜原型：眼镜发射类似蓝牙的射频信号穿过面部，由舌头、嘴唇和软腭的无声动作调制，再由基础模型解码成文字，目标是让人闭着嘴也能以说话速度输入。创始人称，YC 的 Dave 在约 20 句校准后完成了演示，但这是公司自述的原型效果，尚无独立测试或量产验证。公司已开放首批 500 副预售，提供 200 美元折扣，计划 2027 年第一季度发货；帖文未说明具体售价、续航和推理运行位置。

hackernews · aarushyadav · 11月2日 17:16

**「从 AlterEgo 到射频传感」** 无声语音接口并非全新概念：MIT Media Lab 的 AlterEgo 曾在 2018 年 IUI 论文中提出一种佩戴在头部、颈部与下颌周边的可穿戴设备，通过肌肉与神经活动推断用户默念的内容（tool-2-1、tool-2-2）。Subvocal 团队正是从在脸上贴 EMG 电极复刻 AlterEgo 起步，但因出汗导致信号变化、电气干扰、电极位置难以复现，且没人愿意在脸上贴电极，才转向用眼镜框内的射频传感穿透面部，让舌、唇与软腭的默念动作调制信号。

**「影响」** 对想在图书馆、办公室或嘈杂户外使用语音输入的人，无需出声且不靠麦克风拾音的方案有直接价值；但公司尚未说明信号处理和模型推理在眼镜端还是配套应用完成、能否离线运行，购买前应把隐私边界和镜框适配作为待确认条件。

**「社区讨论」** 预购者最具体的反馈是佩戴适配：有人要求保留可调鼻托，也有人希望做成能夹在现有处方眼镜上的配件。另有评论者认为它可能适合强噪声环境，并追问推理发生在何处、能否离线，以评估隐私风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/AlterEgo">AlterEgo - Wikipedia</a></li>
<li><a href="https://www.media.mit.edu/publications/alterego-IUI/">AlterEgo : A Personalized Wearable Silent Speech ... — MIT Media Lab</a></li>

</ul>
</details>

**标签**: `#silent speech interfaces`, `#smart glasses`, `#RF sensing`, `#accessibility`, `#privacy`

---

<a id="item-tech-news-4"></a>
### [Cloudflare 称 DNS 区域构建延迟减半、内存降 85%](https://blog.cloudflare.com/dns-targeted-zone-builds/) ⭐️ 7.0/10

Cloudflare 在一篇技术博客中称，其 DNS 区域构建流程的延迟减半，内存占用降低 85%。这些数字来自 Cloudflare 自述，现有材料没有提供独立测量结果、具体版本或适用范围。因此，目前能确认的是厂商公布了这一性能改进，但不能确认它在所有生产负载下都能复现。

hackernews · wondersky · 11月2日 14:47 · [社区讨论](https://news.ycombinator.com/item?id=50337558)

**「背景」** Cloudflare 的工程文章说明，过去只要修改一项 DNS zone 设置，系统就会重建整个 zone，即使该 zone 包含数千万条记录。此次优化的前提，是先用 targeted build planner 与统一调度器判断变更影响范围，再只执行最小且安全的构建。

**「影响」** 对使用 Cloudflare DNS 的客户而言，若区域构建确实是配置变更的瓶颈，这项优化可能缩短变更生效前的等待，并降低平台的内存成本。但外部用户应把 50% 和 85% 视为厂商声明，而非已独立验证的保证。

**「社区讨论」** HN 评论区有人以每秒 700 次变更质疑这一处理量对 Cloudflare 的规模是否偏低，也有人追问采用关系型方案后长期可能引入哪些缺陷。另有评论者从内存价格可能持续高企的角度，讨论优化内存占用的投入回报。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.cloudflare.com/dns-targeted-zone-builds/">How we halved DNS build delay and cut memory use by 85%</a></li>
<li><a href="https://daily.dev/posts/how-we-halved-dns-build-delay-and-cut-memory-use-by-85--jhnmypmtx">How we halved DNS build delay and cut memory use by 85%</a></li>
<li><a href="https://runtimewire.com/article/cloudflare-dns-targeted-zone-builds-memory-delay">Cloudflare stops rebuilding 20-million-record DNS zones to ...</a></li>

</ul>
</details>

**标签**: `#DNS`, `#performance optimization`, `#memory efficiency`, `#Cloudflare`, `#systems engineering`

---

<a id="item-tech-news-5"></a>
### [Ubuntu LTS 内核据称近三周未修复关键 RCE 漏洞](https://freenode.net/article/ubuntu-lts-kernels-still-unfixed-for-critical-cve-2026-98432) ⭐️ 7.0/10

一篇提交至 Hacker News 的报道称，Ubuntu LTS 内核在近三周内仍未发布针对关键 Linux 0day 远程代码执行漏洞 CVE-2026-98432 的补丁。该问题影响 Ubuntu LTS 用户和运维人员，但当前条目没有提供文章正文、受影响内核版本或 Ubuntu 官方说明，因此补丁状态只能视为该报道及讨论中的说法。

hackernews · majorchord · 11月2日 18:39 · [社区讨论](https://news.ycombinator.com/item?id=50341462)

**「背景」** Ubuntu 的安全跟踪页面将 CVE-2026-98432 记录为影响 Linux 内核 TCP/MPTCP 的漏洞，相关页面标注日期为 2026 年 10 月 15 日。在 Ubuntu LTS 内核补丁缺位期间，Red Hat 的 RHSB-2026-016 公告给出了临时缓解措施，已有第三方脚本依据软件包元数据判断运行内核的补丁状态，并在用户确认后套用该缓解。

**「实际影响与应对」** 对 Ubuntu LTS 用户来说，在发行版内核更新发布之前，上游 10 月 15 日的修复和 Red Hat 11 月 1 日已推出的修复内核都无法直接获得；管理员只能自行评估缓解措施，或收窄暴露面。该漏洞是 Linux IPv4 TCP 握手过程中的远程 use-after-free，CVSS 评分为 9.8；但公开演示的远程代码执行只出现在带 MPTCP 监听的服务端，普通 TCP 连接虽受影响，利用难度更高，Red Hat 因此给出的评分更低。因此，运行 MPTCP 服务的机器应优先处置；其他主机则可按这一差异安排补丁节奏。

**「社区讨论」** 有评论者认为，可在 iptables raw 表的 PREROUTING 链使用 u32 规则丢弃相关流量，作为内核补丁发布前的缓解手段，并质疑为何这一做法没有获得更多公开讨论。另有评论者追问 Ubuntu 延迟近三周的原因，批评其未提供缓解说明，讨论还延伸到长期缺少内核安全更新的消费级路由器。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ubuntu.com/security/CVE-2026-98432">CVE-2026-98432 | Ubuntu</a></li>
<li><a href="https://github.com/soroushneshati/cve-2026-98432-ubuntu-mitigation">GitHub - soroushneshati/cve-2026-98432-ubuntu-mitigation ...</a></li>
<li><a href="https://computingforgeeks.com/linux-kernel-cve-2026-98432/">CVE-2026-98432: Check and Patch the Linux Kernel TCP Flaw</a></li>
<li><a href="https://atlasum.net/blog/cve-2026-98432-linux-ipv4-tcp-uaf">Linux &#x27;s October 2026 TCP Use-After-Free: CVE - 2026 - 98432 — Atlas</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/critical-linux-kernel-flaw-allows-remote-root-attacks-on-mptcp-servers/">Critical Linux kernel flaw allows remote root attacks on MPTCP servers</a></li>
<li><a href="https://getrff.com/blog/cve-2026-98432-linux-tcp-ip-options-block/">CVE - 2026 - 98432 : how to block the Linux TCP bug until Ubuntu and...</a></li>

</ul>
</details>

**标签**: `#Linux kernel`, `#Ubuntu`, `#security vulnerability`, `#RCE`, `#patching`

---

<a id="item-tech-news-6"></a>
### [LightMIS：面向边缘设备的 13.1 万参数分割模型](https://www.reddit.com/r/MachineLearning/comments/1xm8dbo/lightmis_ultralightweight_medical_image/) ⭐️ 7.0/10

作者在 Reddit 分享了预印本和代码库 LightMIS：这是一个面向边缘设备的 2D 二值医学图像分割模型，参数量为 131K。该模型直接聚合多尺度编码器特征，不使用可学习的逐阶段解码器；作者称，在与 nnWNet 相同的 nnU-Net v2.3.1 训练评估协议下，并在覆盖六套数据集、五种成像模态的实验中，LightMIS 的模态宏平均 Dice 和 IoU 接近 nnWNet，同时参数量减少 98.14%、GFLOPs 减少 94.58%。在 Arm Mali-G52 MC2 GPU 上，完整 LightMIS 的推理速度约为 nnWNet 的 10.5 倍，所有 LightMIS 变体均实现 100% GPU 算子覆盖，无 CPU 回退；这些结果由作者自行报告，尚未经过独立验证，代码、检查点和复现材料已公开。

reddit · r/MachineLearning · /u/OkLion2068 · 11月2日 20:22

**「背景」** 在医学图像分割中，U-Net 式的编码器—解码器结构通常由 nnU-Net 这类自配置流程统一训练和评测，逐级上采样的解码器会带来额外的参数与算力开销，这也是此类模型难以部署到 Mali-G52 这类边缘 GPU 的原因之一。LightMIS 的思路是去掉可学习的分阶段解码器：先用 Scale-Aligned Projection 模块把五层编码器的输出对齐到同一分辨率，再直接聚合；完整模型为 0.131M 参数，在 3×256×256 输入下仅需 0.575 GFLOPs，作者以 nnWNet 作为同一训练协议下的参照模型。

**「影响」** 对于希望在 Arm Mali-G52 等边缘 GPU 上部署分割模型的开发者，作者公开了代码和检查点，可按照 nnU-Net v2.3.1 流程复现；但由于这是预印本且指标为作者自报，实际采用前仍需在目标设备和自有数据上独立验证精度与延迟。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/papers/2609.28327">Paper page - LightMIS : Ultra-Lightweight Medical Image ...</a></li>
<li><a href="https://paperswithcode.co/paper/2609.28327">LightMIS : Ultra-Lightweight Medical Image Segmentation Without...</a></li>

</ul>
</details>

**标签**: `#medical image segmentation`, `#edge AI`, `#model efficiency`, `#healthcare AI`, `#open source`

---

<a id="item-tech-news-7"></a>
### [ChatGPT 分享链接漏洞可致会话代码执行，OpenAI 已修复](https://www.parameter.ai/labs/we-found-a-gap-at-openai) ⭐️ 7.0/10

Parameter 研究团队披露，ChatGPT 的分享链接存在一个漏洞：攻击者构造的恶意链接可在已登录用户的会话中执行代码，读取私密对话并发送到外部服务器，受害者只需打开链接，无需安装应用。该漏洞源于预览功能与图表组件之间的消息处理缺陷。OpenAI 已于 10 月 26 日将其修复并定级为 P1，向研究团队支付 5000 美元赏金。

telegram · zaihuapd · 11月2日 10:24

**「背景」** ChatGPT 的分享链接可让用户把一段对话通过链接交给他人查看，因此分享页面需要解析并呈现对话中的多种内容组件。此次漏洞正出在预览功能与图表组件之间的消息处理环节。

**标签**: `#ChatGPT`, `#security vulnerability`, `#account takeover`, `#OpenAI`, `#web security`

---

<a id="item-tech-news-8"></a>
### [WIRED：400 多个 AI 应用被指暗藏色情深伪功能](https://www.wired.com/story/hundreds-of-mundane-ai-apps-are-hiding-abusive-deepfake-features/) ⭐️ 7.0/10

WIRED 11 月 2 日的调查报道指称，一个由 400 多个关联应用与网站组成的网络，以宠物画像、语言学习等普通 AI 工具为界面，在特定条件下加载色情深度伪造功能，允许用户上传他人照片生成露骨图像或视频。报道称，截至 9 月仍有 27 款相关应用在 Google Play 上架，累计下载超过 35 万次，其中不少标注为适合所有年龄段。苹果在收到 WIRED 提供的线索后下架了 19 款应用，并称开发者在审核通过后替换了远端网页内容；谷歌表示在被联系前已移除其中多数应用；Meta 称已阻止相关 209 款应用投放广告。报道依据中文代码、托管信息和域名线索，将该网络与中文开发者及一家香港注册公司联系起来，相关运营方未回应置评请求，这一关联属于媒体与研究人员的调查判断。

telegram · zaihuapd · 11月2日 12:45

**「背景」** 应用商店审核通常针对提交时的安装包与可见界面；若应用在通过审核后从远端加载网页内容，审核所见的普通工具就可能与之后实际呈现的功能不一致。色情深伪指用生成式模型把他人面部或身体合成到露骨图像或视频中，未经同意制作和传播这类内容会直接涉及隐私与人格权侵害。

**「影响」** 苹果对下架原因的解释说明，应用商店的一次性审核可以被“先过审、后替换远端网页内容”绕过，这意味着平台的现实任务是在上架后持续监测服务端下发的界面与内容，而不只是首次审核。对用户而言，被标为适合所有年龄的应用同样可能是生成非自愿性图像的入口，下载量与年龄分级无法作为安全信号。

**标签**: `#AI safety`, `#deepfakes`, `#app store moderation`, `#platform abuse`, `#privacy`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [LLM 并非超人类：拆解直接读写权重的演示](https://seangoedecke.com/llms-are-not-superhuman-at-reading-and-writing-neural-network-weights/) ⭐️ 7.0/10

rss · Sean Goedecke · 11月3日 00:00

**「背景」** 有论文宣称前沿 LLM 能直接读写神经网络权重：GPT-6 Astra 仅凭权重就能识别一个小型网络在玩哪个游戏，还通过直接编辑权重提升了 0.8B Qwen 的数学能力。作者认为，这类结果看似“超人类”，甚至让人联想到递归自我改进，但值得仔细拆解。

**「方案」** 作者指出，游戏识别之所以显得神奇，是因为输入通道直接对应 8×8 网格，且带有“agent”“moving objects”等语义标签；只需对第一层 32 个权重取 L2 范数、用三行 Python 画出热图，人也能一眼认出 Breakout 的底部横线和 Pac-Man 的迷宫。Astra 只是把这一步放在“脑子里”算，属于心算上的超人，而非研究能力上的超人。Qwen 案例同理：该模型并非数学能力不足，而是在 32k token 后陷入循环，短于此的任务原本都能解。人类研究者会走 steering 路线——准备循环与非循环的文本对、比较残差差异、定位贡献最大的权重并逐个修剪，这正是 Heretic 消融（abliteration）的做法；Astra 也正是写了四对文本、边削减边测试，最终找到止住循环的补丁。作者类比说，直接改权重就像让 LLM 输出机器码去改编译后的二进制，是令人印象深刻的技巧，但最佳路径仍是写源码再编译，也就是正常训练。

**「启示」** 作者的核心论点是：这些演示是既有可解释性与 steering 技术的巧妙应用，而非改变 AI 研究方式的新能力；LLM 真正能帮上忙的地方是改进训练，而不是凭空直接调权重。

**标签**: `#LLM interpretability`, `#neural network weights`, `#weight editing`, `#AI capability evaluation`, `#research hype`

---

<a id="item-tech-blog-2"></a>
### [受众捕获：当代理指标反客为主](https://seangoedecke.com/audience-capture/) ⭐️ 7.0/10

rss · Sean Goedecke · 11月3日 00:00

**「背景」** 作者写网文最担心“受众捕获”：工程师本能地想提升互动数据，而平台算法和变现机制又让这件事变得很容易。

**「方案」** 作者指出，浏览量、互动等只是代理指标，他真正想要的是聪明的读者认真思考、提供有经验的反馈、参与行业讨论，并建立可靠声誉。问题在于，平台会奖励更易传播的内容，使“点击者”和“读者”在数据上无法区分；若因微服务之类热门话题带来流量就反复写同类文章，认真读者会流失，点击者却并不真正阅读，于是作者反而用假受众替换了真受众。他把这一逻辑推广到工程职业：Jira 指标或晋升也可能是代理游戏，关键在于自己是否在意目标；为代理指标牺牲真实目标有时可以接受，但不应在无所收获时习惯性“出卖”。他也承认，高浏览量能扩大曝光，却几乎不能告诉他是否吸引了那 5% 会认真阅读、思考和来信的读者，因此他更多依靠个人品味和稀疏的读者反馈。

**「启示」** 核心结论是：代理指标可以服务真实目标，但一旦被其牵着走，就会吸引并不想要的受众，甚至丢掉自己真正在意的读者与工作。关键是分清自己在玩代理游戏还是真实游戏，并只在知情、有回报时做交换。

**标签**: `#audience capture`, `#proxy metrics`, `#online writing`, `#engineering careers`, `#incentives`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [甲骨文拟发 100 亿美元股票和 100 亿美元高级票据，股价跌 6%](https://www.cnbc.com/2026/11/02/stocks-making-the-biggest-moves-midday-orcl-spcx-tem-rivn.html) ⭐️ 7.0/10

甲骨文周一提交文件，计划发行 100 亿美元普通股和 100 亿美元高级票据，为人工智能建设融资，其股价当日再跌 6%。

rss · CNBC Finance · 11月2日 20:00

**「背景」** 这家数据库软件公司正加大人工智能相关投入，因此同时通过发行股票和债券来筹资。

**「影响」** 发行新股会稀释现有股东持股，高级票据则增加公司债务。

**标签**: `#market movers`, `#Oracle financing`, `#tech earnings`, `#M&amp;A`, `#semiconductors`

---

<a id="item-finance-news-2"></a>
### [Marvell 以 1150 亿美元全股票收购 Lumentum；雅诗兰黛第一财季业绩超预期](https://www.cnbc.com/2026/11/02/stocks-making-the-biggest-moves-premarket-crwd-rivn-mu.html) ⭐️ 7.0/10

11 月 2 日盘前，Marvell 同意以全股票交易收购 Lumentum，对后者估值 1150 亿美元，交易预计 2028 年上半年完成。雅诗兰黛公布财年第一财季调整后每股收益 0.72 美元、营收 37.2 亿美元，均高于 FactSet 分析师预期的 0.51 美元和 36.5 亿美元，并上调全年盈利展望。

rss · CNBC Finance · 11月2日 12:49

**「交易背景」** Marvell 于 11 月 2 日宣布以全股票方式收购 Lumentum，按公司公告的隐含企业价值计算为 1150 亿美元，约合每股 1,132 美元，较 10 月 28 日（即市场出现交易猜测前的最后一个交易日）未受影响收盘价溢价约 23.9%。两家公司称，合并旨在打造“AI 连接”领域的领导者，交易预计在 2028 年上半年完成。

**「影响」** 全股票交易意味着 Lumentum 股东获得的是 Marvell 股票而非现金，其对价价值与 Marvell 股价挂钩。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://investor.marvell.com/news-events/press-releases/detail/1040/marvell-and-lumentum-to-combine-creating-a-category-leader-in-ai-connectivity">Marvell and Lumentum to Combine, Creating a Category Leader ...</a></li>
<li><a href="https://investor.lumentum.com/financial-news-releases/news-details/2026/Marvell-and-Lumentum-to-Combine-Creating-a-Category-Leader-in-AI-Connectivity/default.aspx">Lumentum - Marvell and Lumentum to Combine, Creating a ...</a></li>

</ul>
</details>

**标签**: `#premarket movers`, `#M&amp;A`, `#earnings`, `#analyst upgrades`, `#semiconductors`

---

<a id="item-finance-news-3"></a>
### [英国提出将多数移民定居等待期由 5 年延至 10 年](https://www.gov.uk/government/news/home-secretary-unveils-new-rules-for-migrants-settling-in-the-uk) ⭐️ 7.0/10

英国政府提出将多数移民申请永久居留（定居）的标准等待期从 5 年延长至 10 年，但高收入者最快 3 年、年收入超过 50,271 英镑者及医生、护士、教师等公共服务人员可走 5 年通道。该方案已提交议会，尚属拟议政策，未成为法律。

telegram · zaihuapd · 11月2日 23:50

**「背景」** 英国政府此前已就“赚取式定居”（earned settlement）启动咨询，提出定居不再是在固定年限后自动获得，而需以持续良好行为、贡献和融入来“赚取”；此次方案是该咨询后的政策推进。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gov.uk/government/consultations/earned-settlement">Earned settlement - GOV.UK</a></li>
<li><a href="https://www.gov.uk/government/consultations/earned-settlement/a-fairer-pathway-to-settlement-statement-and-accompanying-consultation-on-earned-settlement-accessible">A Fairer Pathway to Settlement: statement and accompanying ... Earned Settlement: Examining the Government’s proposed reforms Revised earned settlement policy to be unveiled before the ... Earned Settlement UK: 2026 ILR Reform Guide - DavidsonMorris Earned Settlement UK: New ILR Rules Explained (2026) Earned settlement UK: ILR reform status in 2026</a></li>

</ul>
</details>

**标签**: `#UK immigration policy`, `#settlement rules`, `#labor market`, `#Home Office`, `#policy proposal`

---