---
layout: default
title: "Horizon Summary: 2026-11-03 (EN)"
date: 2026-11-03
lang: en
---

> From 47 items, 13 important content pieces were selected

---

**Technology News**
1. [Linux IPv4 TCP use-after-free CVE-2026-98432 prompts kernel update warning](#item-tech-news-1) ⭐️ 8.0/10
2. [vLLM v0.33.0rc3 adds models, PyTorch 2.14, CUDA 13.0-only builds](#item-tech-news-2) ⭐️ 7.0/10
3. [Subvocal Opens Preorders for RF-Sensing Glasses That Decode Silent Speech](#item-tech-news-3) ⭐️ 7.0/10
4. [Cloudflare reports halved DNS zone build delay, 85% less memory](#item-tech-news-4) ⭐️ 7.0/10
5. [Ubuntu LTS kernels still unpatched for critical RCE, report says](#item-tech-news-5) ⭐️ 7.0/10
6. [LightMIS: 131K-parameter medical segmentation model runs on Mali-G52 edge GPU](#item-tech-news-6) ⭐️ 7.0/10
7. [ChatGPT Share-Link Flaw Allowed Session Code Execution, OpenAI Fixed as P1](#item-tech-news-7) ⭐️ 7.0/10
8. [WIRED: 400+ AI apps alleged to hide sexual deepfake tools](#item-tech-news-8) ⭐️ 7.0/10

**Technology Blog**
1. [LLM Weight Reading Is an Impressive Trick, Not Superhuman Research](#item-tech-blog-1) ⭐️ 7.0/10
2. [Audience Capture: When Engagement Metrics Replace Real Readers](#item-tech-blog-2) ⭐️ 7.0/10

**Financial News**
1. [Oracle plans $20 billion raise for AI buildout as shares fall 6%](#item-finance-news-1) ⭐️ 7.0/10
2. [Marvell to buy Lumentum in $115 billion all-stock deal; Estée Lauder beats estimates](#item-finance-news-2) ⭐️ 7.0/10
3. [UK proposes 10-year settlement wait for most migrants](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Linux IPv4 TCP use-after-free CVE-2026-98432 prompts kernel update warning](https://telegram.me/zaihuapd/44866) ⭐️ 8.0/10

A Chinese-language Telegram alert is urging server operators to update their Linux kernels because of a high-severity IPv4 TCP use-after-free tracked as CVE-2026-98432, which the post says can be exploited from the network side without authentication or user interaction. The post states that Anthropic has published a remote-code-execution example targeting MPTCP listening ports, and cites the Go security team as warning that since Go 1.24, listen sockets on Linux enable MPTCP by default — so Go services are exposed by default and may be vulnerable even without an MPTCP listener. The alert gives no affected kernel versions, no fixed release or patch links, and no mitigations, and it does not link a primary advisory, so the vulnerable range and full scope of the flaw remain unconfirmed by the supplied material.

telegram · zaihuapd · Nov 3, 02:37

**「Background」** The underlying flaw is a use-after-free in the kernel&\#x27;s handling of IPv4 option data for a TCP request socket; a remote, unauthenticated peer can trigger it against a listening service \(tool-1-1, tool-1-3\). Go&\#x27;s added exposure comes from its 1.24 release enabling MPTCP on Linux listen sockets by default, although the source notes that the flaw is not limited to MPTCP listeners.

**「Who needs to act」** Operators of internet-facing Go services on Linux should prioritize a kernel update rather than an application-level workaround: since Go 1.24, listening sockets on Linux enable MPTCP by default, which matches the demonstrated MPTCP-listener exploit, and reports indicate non-MPTCP listeners may be vulnerable to the same class of attack. Auditing exposed TCP ports or disabling MPTCP in the application is therefore not a sufficient fix; the patched kernel must be deployed.

<details><summary>References</summary>
<ul>
<li><a href="https://almalinux.org/blog/2026-10-30-cve-2026-98432/">CVE - 2026 - 98432 : Patched kernels available in testing | AlmaLinux OS</a></li>
<li><a href="https://www.penligent.ai/hackinglabs/cve-2026-98432/">CVE - 2026 - 98432 Linux TCP Flaw, Ubuntu Patch and Mitigation Status</a></li>
<li><a href="https://www.ionix.io/threat-center/cve-2026-98432/">CVE - 2026 - 98432 – Unauthenticated Use-After-Free... - IONIX</a></li>
<li><a href="https://lilting.ch/en/articles/linux-ipv4-tcp-options-uaf-mptcp-rce">CVE - 2026 - 98432 Linux TCP Use-After-Free Can Give... | lilting channel</a></li>
<li><a href="https://atlasum.net/blog/cve-2026-98432-linux-ipv4-tcp-uaf">Linux&#x27;s October 2026 TCP Use-After-Free: CVE - 2026 - 98432 — Atlas</a></li>

</ul>
</details>

**Tags**: `#Linux kernel`, `#security vulnerability`, `#TCP`, `#Go`, `#remote code execution`

---

<a id="item-tech-news-2"></a>
### [vLLM v0.33.0rc3 adds models, PyTorch 2.14, CUDA 13.0-only builds](https://github.com/vllm-project/vllm/releases/tag/v0.33.0rc3) ⭐️ 7.0/10

The vLLM v0.33.0rc3 release candidate bundles 927 commits from 389 contributors, including 122 first-time contributors, and adds support for models such as Reflection Beam-1.0 \(501B MoE with 23B active parameters\), Yandex AliceAI-Foundation-80B-A3B, Recursive Flint, Muse Spark Open, and Step-5 Preview. It upgrades to PyTorch 2.14.0 with torchvision 0.29.0 and Triton 3.8.0. CUDA release wheels and images are now CUDA 13.0-only: the CUDA 12.9 wheels and the \`-cu129\`/\`-cu129-ubuntu2404\` images are no longer published, and the CUDA wheel is now ABI-stable with libtorch. The release also adds an AWS EFA image and a shorter \`vllm/vllm\` image alias, while removing Medusa and the MLP speculator and dropping the legacy Ray compiled-graph executor.

github · khluu · Nov 2, 10:10

**「Background」** vLLM distributes prebuilt wheels and container images for separate accelerator stacks—CUDA by default on PyPI, plus ROCm, XPU, and CPU artifacts through other indexes and tags—so deployments must choose the build that matches their installed driver and hardware. The \`v0.33.0rc3\` tag is a release candidate in the v0.33.0 line, not the final release.

**「Impact」** Deployments pinned to CUDA 12.9 must move to the CUDA 13.0 artifacts or stay on an older vLLM release. Configurations that rely on Medusa, the MLP speculator, or the legacy Ray compiled-graph executor will stop working, and users of the NIXL connector now need NIXL 1.5 or newer.

**Tags**: `#vllm`, `#llm-inference`, `#release-notes`, `#pytorch`, `#cuda`

---

<a id="item-tech-news-3"></a>
### [Subvocal Opens Preorders for RF-Sensing Glasses That Decode Silent Speech](https://news.ycombinator.com/item?id=50340088) ⭐️ 7.0/10

The Subvocal Company, a YC F26 startup founded by two former Georgia Tech CS students, is taking preorders for a first batch of 500 pairs of smart glasses that use low-power radio waves, similar to Bluetooth, to sense tongue, lip and soft-palate movement and decode silently mouthed words into text at speech speed. The preorder carries a $200 discount off the final price, but the shipping target is Q1 2027 and the company describes the current device as a prototype still undergoing R&amp;D to become the product shown on its website. The team says it abandoned an earlier EMG-electrode approach because of sweat, interference, placement variability and wearability, and that cross-user accuracy improved through paid data-collection sessions after a 20-sentence calibration for a new wearer. Performance claims rest on the company&\#x27;s own demo video and scaling curve, with no independent measurement or error rates disclosed.

hackernews · aarushyadav · Nov 2, 17:16

**「Earlier silent-speech work」** Subvocal follows MIT Media Lab’s AlterEgo, a wearable silent-speech interface presented in a 2018 IUI paper that attached around the head, neck, and jawline and translated muscular and neural activity into words without vocalization. The Subvocal founders say they first tried to recreate AlterEgo with facial EMG electrodes before switching to RF sensing embedded in glasses.

**「Impact」** The pitch targets people who want dictation without speaking aloud — in libraries, offices, public spaces or noisy environments where microphones struggle — and the company says it is scaling its dataset specifically to improve edge-case performance. Prospective buyers with non-standard facial or frame fit, and those who need prescription lenses, have no confirmed accommodation yet, and the Show HN post does not state whether signal processing runs on the glasses or on a paired device.

**「Community Discussion」** Commenters who preordered pressed on hardware fit: one asked the company to keep adjustable metal nose pads for people whose noses fall outside the standard range, and another said they would prefer a clip-on module for existing prescription glasses because available smart-glasses frames were too small for a larger head. Others asked where inference happens and whether the glasses work offline, citing privacy concerns about sensor data, and one commenter asked whether RF sensing would let them dictate in loud environments like yard work where microphones fail.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/AlterEgo">AlterEgo - Wikipedia</a></li>
<li><a href="https://www.media.mit.edu/publications/alterego-IUI/">AlterEgo : A Personalized Wearable Silent Speech ... — MIT Media Lab</a></li>

</ul>
</details>

**Tags**: `#silent speech interfaces`, `#smart glasses`, `#RF sensing`, `#accessibility`, `#privacy`

---

<a id="item-tech-news-4"></a>
### [Cloudflare reports halved DNS zone build delay, 85% less memory](https://blog.cloudflare.com/dns-targeted-zone-builds/) ⭐️ 7.0/10

Cloudflare published a technical post claiming it halved the delay of DNS zone builds and reduced memory use by 85% through an approach it describes as targeted zone builds. The figures are the vendor&\#x27;s own; the supplied material includes no methodology, benchmark conditions, baseline definitions, or independent measurement, so the gains should be read as reported results rather than verified ones. The post drew moderate attention on Hacker News, where the discussion focused on how the numbers were obtained and what tradeoffs they imply.

hackernews · wondersky · Nov 2, 14:47 · [Discussion](https://news.ycombinator.com/item?id=50337558)

**「Why DNS zone builds were expensive」** A DNS zone is the container holding a customer&\#x27;s records and the settings that govern how they are served. In Cloudflare&\#x27;s previous design, a change to a zone setting triggered a rebuild of the entire zone, even for zones holding tens of millions of records, which is what made build delay and peak memory costly. The post describes replacing that full-rebuild path with a planner that selects the smallest safe build.

**「Community discussion」** Commenters probed the claims rather than disputing them: InsidiousWombat asked whether roughly 700 changes per second is low given Cloudflare&\#x27;s scale and domain count, and JulianPaul asked what bugs might surface over time from an improvement involving a relational approach. thephyber framed the work around the return on investment of shrinking memory footprints, noting memory prices will likely stay high for at least another one to two years.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.cloudflare.com/dns-targeted-zone-builds/">How we halved DNS build delay and cut memory use by 85%</a></li>
<li><a href="https://runtimewire.com/article/cloudflare-dns-targeted-zone-builds-memory-delay">Cloudflare stops rebuilding 20-million-record DNS zones to ...</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#performance optimization`, `#memory efficiency`, `#Cloudflare`, `#systems engineering`

---

<a id="item-tech-news-5"></a>
### [Ubuntu LTS kernels still unpatched for critical RCE, report says](https://freenode.net/article/ubuntu-lts-kernels-still-unfixed-for-critical-cve-2026-98432) ⭐️ 7.0/10

Ubuntu has not shipped a kernel fix for CVE-2026-98432, a critical Linux kernel remote-code-execution flaw, nearly three weeks after the issue became public, according to the linked report. The supplied item contains no article body, advisory text, or affected-version list, and no Ubuntu statement is quoted, so the exact LTS kernel versions involved and the vendor&\#x27;s own characterization of the flaw remain unconfirmed. The unpatched status of Ubuntu LTS kernels is the report&\#x27;s claim; no independent technical confirmation is available here.

hackernews · majorchord · Nov 2, 18:39 · [Discussion](https://news.ycombinator.com/item?id=50341462)

**「Background」** Ubuntu’s security tracker lists CVE-2026-98432, and third-party guidance describes an interim mitigation drawn from Red Hat bulletin RHSB-2026-016 while a script estimates a running kernel’s patch status from package metadata and vendor data. The same guidance characterizes the bug as a Linux kernel TCP flaw and shows how to identify MPTCP listeners with \`ss -M\`.

**「Impact」** Ubuntu LTS operators running kernels that predate the upstream fix remain exposed while Red Hat shipped patched kernels on November 1, so organizations with mixed fleets face uneven exposure and cannot assume a vendor patch will arrive on the same schedule. Because public RCE demonstration has so far been limited to hosts with an MPTCP listener, teams should check whether MPTCP is enabled before treating the flaw as an immediate remote-root emergency, and note that the mitigation Red Hat published is described as reducing but not fully preventing exposure.

**「Community discussion」** Commenters focused on workarounds and vendor handling: one proposed dropping malformed packets with a u32 match in an iptables/nftables raw PREROUTING rule before the kernel processes them, while the submitter noted Ubuntu published no mitigation guidance and that a Red Hat advisory describes its mitigation as reducing exposure &quot;but cannot fully prevent it&quot; without explaining the limitation. Others asked why a seemingly simple kernel patch has taken so long and whether Linux-based consumer routers ever receive kernel security updates at all.

<details><summary>References</summary>
<ul>
<li><a href="https://ubuntu.com/security/CVE-2026-98432">CVE-2026-98432 | Ubuntu</a></li>
<li><a href="https://github.com/soroushneshati/cve-2026-98432-ubuntu-mitigation">GitHub - soroushneshati/cve-2026-98432-ubuntu-mitigation ...</a></li>
<li><a href="https://computingforgeeks.com/linux-kernel-cve-2026-98432/">CVE-2026-98432: Check and Patch the Linux Kernel TCP Flaw</a></li>
<li><a href="https://atlasum.net/blog/cve-2026-98432-linux-ipv4-tcp-uaf">Linux &#x27;s October 2026 TCP Use-After-Free: CVE - 2026 - 98432 — Atlas</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/critical-linux-kernel-flaw-allows-remote-root-attacks-on-mptcp-servers/">Critical Linux kernel flaw allows remote root attacks on MPTCP servers</a></li>
<li><a href="https://getrff.com/blog/cve-2026-98432-linux-tcp-ip-options-block/">CVE - 2026 - 98432 : how to block the Linux TCP bug until Ubuntu and...</a></li>

</ul>
</details>

**Tags**: `#Linux kernel`, `#Ubuntu`, `#security vulnerability`, `#RCE`, `#patching`

---

<a id="item-tech-news-6"></a>
### [LightMIS: 131K-parameter medical segmentation model runs on Mali-G52 edge GPU](https://www.reddit.com/r/MachineLearning/comments/1xm8dbo/lightmis_ultralightweight_medical_image/) ⭐️ 7.0/10

The authors of LightMIS released a preprint and open-source code for a 2D binary medical image segmentation model with 131K parameters that aggregates multi-scale encoder features directly instead of using a learned stage-wise decoder. In their own experiments, LightMIS came close to nnWNet on modality-macro Dice and IoU averages while using 98.14% fewer parameters and 94.58% fewer GFLOPs, with both models trained and evaluated under the same nnU-Net v2.3.1 protocol across six datasets and five imaging modalities. On an Arm Mali-G52 MC2 GPU, the full model ran about 10.5× faster than nnWNet, and all LightMIS variants reached 100% GPU operator coverage with no CPU fallback. These figures are self-reported by the authors and have not been independently validated; the scope is limited to 2D binary segmentation. Source code, checkpoints, and reproduction details are public on GitHub.

reddit · r/MachineLearning · /u/OkLion2068 · Nov 2, 20:22

**「Context」** U-Net-style segmentation models commonly pair a multi-level encoder with a learned stage-wise decoder that fuses features at increasing resolutions. LightMIS instead uses Scale-Aligned Projection blocks to bring a five-level encoder&\#x27;s outputs to a common resolution and omits that decoder, according to the paper description; the authors evaluated the resulting model family under a shared nnU-Net v2.3.1 training protocol.

**「Impact」** For developers targeting Mali-class edge hardware, the reported 100% GPU operator coverage matters as much as the speedup: full on-device execution without CPU fallback removes a common source of latency spikes and deployment complexity. Practitioners should treat the Dice/IoU parity with nnWNet as a claim to verify on their own data before substituting LightMIS, since it applies only to 2D binary segmentation under the nnU-Net protocol rather than to 3D or multi-class tasks.

<details><summary>References</summary>
<ul>
<li><a href="https://paperswithcode.co/paper/2609.28327">LightMIS : Ultra-Lightweight Medical Image Segmentation Without...</a></li>

</ul>
</details>

**Tags**: `#medical image segmentation`, `#edge AI`, `#model efficiency`, `#healthcare AI`, `#open source`

---

<a id="item-tech-news-7"></a>
### [ChatGPT Share-Link Flaw Allowed Session Code Execution, OpenAI Fixed as P1](https://www.parameter.ai/labs/we-found-a-gap-at-openai) ⭐️ 7.0/10

Parameter researchers found a flaw in ChatGPT share links that let a malicious link run code inside a logged-in user&\#x27;s session and send private conversations to an external server. The victim only had to open the link; no app installation was required. According to the report, the bug abused a message-handling defect between the preview feature and the chart component. OpenAI fixed it on October 26, rated it P1, and paid a $5,000 bounty.

telegram · zaihuapd · Nov 2, 10:24

**「Context」** ChatGPT share links are URLs that render a shared conversation in the recipient&\#x27;s browser, including preview and chart components. According to Parameter&\#x27;s account, the flaw lay in how those components handled messages between them, which allowed a crafted link to execute code inside an already logged-in user&\#x27;s session without requiring an app installation.

**「Why It Matters」** Because exploitation required only a click from an already logged-in user, shared ChatGPT conversation links had to be treated as untrusted input rather than passive content. The server-side fix closes the reported path, but the case shows that preview renderers and embedded chart components in chat products are code-execution surfaces that need the same scrutiny as conventional web input handling.

**Tags**: `#ChatGPT`, `#security vulnerability`, `#account takeover`, `#OpenAI`, `#web security`

---

<a id="item-tech-news-8"></a>
### [WIRED: 400+ AI apps alleged to hide sexual deepfake tools](https://www.wired.com/story/hundreds-of-mundane-ai-apps-are-hiding-abusive-deepfake-features/) ⭐️ 7.0/10

A WIRED investigation published Nov. 2 identified a network of more than 400 linked AI apps and websites that presented themselves as ordinary tools, such as pet-portrait generators and language-learning aids, but loaded pornographic deepfake interfaces under specific conditions, letting users upload other people&\#x27;s photos to generate explicit images or videos. Researchers linked the sites through code, domains, and ad tracking; 27 apps still on Google Play in September had more than 350,000 cumulative downloads, and many were rated suitable for all ages. After WIRED provided its findings, Apple removed 19 apps and said developers had swapped remote web content after review; Google had removed most of the apps before being contacted, and Meta said it blocked 209 related apps from advertising. WIRED tied the network to Chinese developers and a Hong Kong-registered company based on Chinese code, hosting, and domain clues—an investigative attribution the operators did not respond to.

telegram · zaihuapd · Nov 2, 12:45

**「How the apps evaded review」** The report&\#x27;s central mechanism is remote content swapping: Apple said the developers replaced web content after their apps had passed review, so an app approved as a benign tool could later load a different interface. The network was traced through shared Chinese-language code, hosting details, domain registrations and advertising trackers, which is how WIRED and the researchers linked more than 400 separate apps and sites. The operators did not respond to requests for comment, and the tie to specific Chinese developers and a Hong Kong-registered company is the investigators&\#x27; assessment rather than a confirmed finding.

**「Impact」** The case shows that app-store approval is not a durable safety check when an app can change remote web content after review, as Apple said happened, so users and reviewers cannot judge an AI app&\#x27;s capabilities from its listing or age rating alone.

**Tags**: `#AI safety`, `#deepfakes`, `#app store moderation`, `#platform abuse`, `#privacy`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [LLM Weight Reading Is an Impressive Trick, Not Superhuman Research](https://seangoedecke.com/llms-are-not-superhuman-at-reading-and-writing-neural-network-weights/) ⭐️ 7.0/10

rss · Sean Goedecke · Nov 3, 00:00

**「Background」** A recent paper argues that frontier LLMs can work directly with neural network weights—identifying a toy network’s game, editing weights, and improving a 0.8B Qwen model’s mathematics—and frames this as potentially superhuman and relevant to recursive self-improvement. Sean Goedecke argues these demos are less extraordinary than they appear.

**「Solution」** For game identification, Goedecke notes that the model’s input channels are labeled and map directly to 8×8 grid cells, so taking the L2 norm of each first-layer input across its 32 weights produces a heatmap that reveals where the player and moving objects are. He says a human could read the games from that heatmap; Astra’s feat is superhuman mental calculation, not superhuman research. The Qwen result, he argues, was also a known technique: the model was not broadly bad at mathematics but looped after 32k tokens. Astra wrote four pairs of looping and non-looping texts, measured which weights contributed to looping, then cut and tested them—essentially the Heretic abliteration playbook. Goedecke compares direct weight editing to editing compiled binaries: impressive, but normal training remains the practical path.

**「Takeaway」** Goedecke concludes that direct weight manipulation is an impressive trick rather than a radically new AI-research capability; LLMs will chiefly help research by improving training, not by magically tweaking weights.

**Tags**: `#LLM interpretability`, `#neural network weights`, `#weight editing`, `#AI capability evaluation`, `#research hype`

---

<a id="item-tech-blog-2"></a>
### [Audience Capture: When Engagement Metrics Replace Real Readers](https://seangoedecke.com/audience-capture/) ⭐️ 7.0/10

rss · Sean Goedecke · Nov 3, 00:00

**「Background」** Online writing offers constant feedback—views, referrers, upvoted comments, and sometimes ad or platform payouts—and Sean Goedecke says that as an engineer he is tempted to make those numbers go up. The problem is that these signals are not the outcomes he actually wants.

**「Solution」** Goedecke argues that views and engagement are proxy metrics for things he values: smart readers considering his ideas, feedback from experienced readers, useful public conversation, persuasion, and a reputation for careful thinking. Metrics cannot distinguish “clickers”—people who scan a title or comment on Hacker News without reading—from “readers” who engage seriously, even though only the latter matter to him. If he chases a hot topic such as posts arguing that microservices are stupid, the numbers may rise while careful readers drift away, leaving a fake audience of clickers and sneerers; he notes that some of his popular industry laments succeed because they let readers share their worries, while quieter philosophy, history, and dry technical posts were more rewarding. He generalizes the pattern to engineering careers: Jira metrics or promotion can be proxy games, and it is easy to win them at the expense of the real work, respect, or writing one cares about. Deliberate tradeoffs—impressing people you dislike to support your family—can be healthy, but the author warns that habitual selling out is worst when it buys nothing you want. He relies on taste and the thin signal from thoughtful emails rather than raw view counts.

**「Takeaway」** The author concludes that engagement should be treated as a limited discovery mechanism, not a target: without deliberately identifying which game is real, writers and engineers can optimize themselves into serving an audience they never wanted.

**Tags**: `#audience capture`, `#proxy metrics`, `#online writing`, `#engineering careers`, `#incentives`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Oracle plans $20 billion raise for AI buildout as shares fall 6%](https://www.cnbc.com/2026/11/02/stocks-making-the-biggest-moves-midday-orcl-spcx-tem-rivn.html) ⭐️ 7.0/10

Oracle filed plans to raise $20 billion—$10 billion in common stock and $10 billion in senior notes—to fund its artificial intelligence buildout, and its shares fell another 6% midday.

rss · CNBC Finance · Nov 2, 20:00

**「Background」** Issuing common stock can dilute existing shareholders, while senior notes are a form of debt; Oracle is using both to finance AI infrastructure.

**「Impact」** Oracle shareholders face dilution from the $10 billion stock sale and additional debt from the $10 billion notes.

**Tags**: `#market movers`, `#Oracle financing`, `#tech earnings`, `#M&amp;A`, `#semiconductors`

---

<a id="item-finance-news-2"></a>
### [Marvell to buy Lumentum in $115 billion all-stock deal; Estée Lauder beats estimates](https://www.cnbc.com/2026/11/02/stocks-making-the-biggest-moves-premarket-crwd-rivn-mu.html) ⭐️ 7.0/10

Marvell Technology agreed to acquire Lumentum in an all-stock deal that values the optical-component maker at $115 billion, with the transaction expected to close in the first half of 2028. Estée Lauder also beat analyst forecasts for its fiscal first quarter, reporting adjusted earnings of 72 cents a share on revenue of $3.72 billion versus the 51 cents and $3.65 billion expected by analysts polled by FactSet, and raised its full-year earnings outlook.

rss · CNBC Finance · Nov 2, 12:49

**「Background」** Marvell agreed to buy Lumentum in an all-stock deal that values Lumentum at $115 billion, or about $1,132 per share — a 23.9% premium to its closing price on Oct. 28, the last trading day before takeover speculation began.

**「Impact」** Because Lumentum shareholders are paid in Marvell stock rather than cash, their eventual proceeds depend on Marvell&\#x27;s share price until a closing now slated for 2028.

<details><summary>References</summary>
<ul>
<li><a href="https://investor.marvell.com/news-events/press-releases/detail/1040/marvell-and-lumentum-to-combine-creating-a-category-leader-in-ai-connectivity">Marvell and Lumentum to Combine, Creating a Category Leader ...</a></li>

</ul>
</details>

**Tags**: `#premarket movers`, `#M&amp;A`, `#earnings`, `#analyst upgrades`, `#semiconductors`

---

<a id="item-finance-news-3"></a>
### [UK proposes 10-year settlement wait for most migrants](https://www.gov.uk/government/news/home-secretary-unveils-new-rules-for-migrants-settling-in-the-uk) ⭐️ 7.0/10

The UK Home Office has proposed an &quot;earned settlement&quot; system that would make most migrants wait 10 years, up from five, before applying for permanent residence. Under the proposal, the highest earners could apply after three years, while people earning more than £50,271 a year and public-service workers such as doctors, nurses and teachers would use a five-year route.

telegram · zaihuapd · Nov 2, 23:50

**「Background」** The proposal follows a Home Office consultation opened in November 2025 on &quot;earned settlement,&quot; which proposed ending automatic settlement after a fixed period and instead requiring migrants to demonstrate sustained good conduct, contribution and integration. The government had already said the starting point for most people would rise to ten years, up from the current five.

<details><summary>References</summary>
<ul>
<li><a href="https://www.gov.uk/government/consultations/earned-settlement">Earned settlement - GOV.UK</a></li>
<li><a href="https://www.gov.uk/government/consultations/earned-settlement/a-fairer-pathway-to-settlement-statement-and-accompanying-consultation-on-earned-settlement-accessible">A Fairer Pathway to Settlement: statement and accompanying ... Earned Settlement: Examining the Government’s proposed reforms Revised earned settlement policy to be unveiled before the ... Earned Settlement UK: 2026 ILR Reform Guide - DavidsonMorris Earned Settlement UK: New ILR Rules Explained (2026) Earned settlement UK: ILR reform status in 2026</a></li>

</ul>
</details>

**Tags**: `#UK immigration policy`, `#settlement rules`, `#labor market`, `#Home Office`, `#policy proposal`

---