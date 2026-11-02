---
layout: default
title: "Horizon Summary: 2026-11-02 (EN)"
date: 2026-11-02
lang: en
---

> From 28 items, 5 important content pieces were selected

---

**Technology News**
1. [Terence Tao: Mathematics Has Changed. Let’s Act Like It](#item-tech-news-1) ⭐️ 8.0/10
2. [Lenovo&\#x27;s &\#x27;encrypted&\#x27; fingerprint USB reportedly holds a bare SD card](#item-tech-news-2) ⭐️ 7.0/10
3. [SemiAnalysis: 2028 Datacenter Buildout Faces Election-Driven Permit Risk](#item-tech-news-3) ⭐️ 7.0/10
4. [Theory paper: RLVR pass@1 gains provably cost some prompts](#item-tech-news-4) ⭐️ 7.0/10

**Technology Blog**
1. [Reliable LLM Alignment Is Impossible in Principle](#item-tech-blog-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Terence Tao: Mathematics Has Changed. Let’s Act Like It](https://terrytao.wordpress.com/2026/11/01/mathematics-has-changed-lets-act-like-it/) ⭐️ 8.0/10

In a November 1 essay, mathematician Terence Tao argues that AI has fundamentally changed mathematical practice and that the field should revise its norms and workflows in response. The piece is an argument about research practice, not a report of a new theorem prover or a measured capability result.

hackernews · smilelamp · Nov 1, 18:28 · [Discussion](https://news.ycombinator.com/item?id=50328251)

**「Prior context」** Terence Tao has argued for months that mathematics is shifting away from the mere production of results toward digesting and communicating them, a thread Hacker News commenters identify as a recurring theme in his recent writing. The essay is posted on Tao&\#x27;s blog, though a Telegram channel that circulated the link describes it as a guest post by Frank Calegari, so the item&\#x27;s title alone does not settle who wrote it.

**「Impact」** For research mathematicians, the essay’s argument implies that credit and training may need to recognize problem selection, verification and digestion of AI-generated proofs, and follow-up questions as substantive work, not only the production of a new proof ingredient.

**「Community Discussion」** Commenters debated whether AI marks a shift from mathematical craftsmanship to industrial production, with one arguing that the discussion underestimates capabilities beyond theorem proving. Others reported that mathematicians are discouraged by long, ugly proofs and by changes to the field’s social foundations.

<details><summary>References</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50328251">Mathematics has changed . Let &#x27; s act like it | Hacker News</a></li>
<li><a href="https://t.me/kmp500/756">kmp+ – Telegram</a></li>

</ul>
</details>

**Tags**: `#AI for mathematics`, `#theorem proving`, `#LLM agents`, `#research workflows`, `#scientific discovery`

---

<a id="item-tech-news-2"></a>
### [Lenovo&\#x27;s &\#x27;encrypted&\#x27; fingerprint USB reportedly holds a bare SD card](https://www.reddit.com/r/technology/comments/1xl2pr3/lenovos_encrypted_fingerprint_usb_drive_is_just/) ⭐️ 7.0/10

A teardown of a Lenovo USB drive marketed as an encrypted, fingerprint-protected stick reportedly found an ordinary unencrypted SD card inside a plastic case, meaning the biometric reader gates access to the enclosure rather than encrypting the data. The finding circulated on Reddit&\#x27;s r/technology and Hacker News, but no primary write-up was supplied with this item, so the specific model, test method, and Lenovo&\#x27;s response are not documented here. Commenters refer to the device as the &quot;FU100&quot; and note they could only find listings on Chinese sites such as Alibaba, a claim that has not been independently verified. Lenovo has not been confirmed to have responded.

hackernews · entryleveljobsc · Nov 1, 14:34 · [Discussion](https://news.ycombinator.com/item?id=50326099)

**「Fingerprint lock vs. encryption」** Fingerprint-enabled USB drives can use the reader as an access gate while relying on a separate controller or software to encrypt the data. The Lenovo ThinkPlus FU100 was sold as an AES-256-encrypted device, but researcher Xusheng Li reported that the fingerprint only enabled USB access and that the internal SD card held unencrypted files, allowing the card to be read directly.

**「Why it matters」** If the teardown is accurate, anyone holding the drive can bypass the fingerprint check by removing the SD card and reading it directly, so the product offers no protection for data at rest regardless of what the packaging claims. Buyers who need encrypted portable storage should verify encryption themselves — for example, by reading the media outside the device — rather than relying on a biometric unlock prompt as evidence of encryption.

**「Community reaction」** Commenters were sharply skeptical that the design could have passed any security or design review, with charles\_f asking how Lenovo could still be trusted to build secured hardware, while matheusmoreira argued that free-software cryptography applied on top of commodity storage is the sound approach. thayne noted the product name reads like a joke at customers&\#x27; expense and said listings appeared only on Chinese sites like Alibaba, an observation offered without supporting links.

<details><summary>References</summary>
<ul>
<li><a href="https://www.tomshardware.com/tech-industry/cyber-security/lenovo-fingerprint-usb-stick-sold-as-aes-256-encrypted-had-a-plain-sd-card-inside-ai-assisted-follow-up-finds-a-backdoor-and-hardcoded-keys-in-other-secure-usb-products">Lenovo&#x27;s &#x27;encrypted&#x27; fingerprint USB drive is just an ...</a></li>
<li><a href="https://windowsforum.com/news/lenovo-thinkplus-usb-security-flaws-fu100-encryption-claim-and-other-drive-risks.450478/">Lenovo ThinkPlus USB Security Flaws: FU100 Encryption Claim ...</a></li>

</ul>
</details>

**Tags**: `#hardware security`, `#encryption`, `#consumer devices`, `#Lenovo`, `#product teardown`

---

<a id="item-tech-news-3"></a>
### [SemiAnalysis: 2028 Datacenter Buildout Faces Election-Driven Permit Risk](https://newsletter.semianalysis.com/p/the-datacenter-backlash-goes-bipartisan) ⭐️ 7.0/10

SemiAnalysis argues that the 2027 US datacenter buildout is largely insulated from next week&\#x27;s midterms because about three-quarters of the 33.8 GW due across its top 20 states is already under construction, while the 2028 pipeline is where election-driven policy risk concentrates. Its model projects 62.2 GW of US net additions in 2028, most of which has not started construction; 13 states account for 43.5 GW, or 70% of the national total, and 10 of those 13 elect governors on Nov. 3. Since September, Texas froze Texas Commission on Environmental Quality permits on Sept. 21 and Oregon expanded its state-land freeze to air and water-discharge permits on Oct. 9 through July 1, 2027; Texas alone accounts for close to 30% of 2028 US GW, making the length of the TCEQ pause the biggest risk to the forecast. SemiAnalysis frames the Texas choice as a restart after ERCOT&\#x27;s targeted Dec. 10 report versus Gina Hinojosa&\#x27;s proposed moratorium tied to legislation in the 2027 session, with Gov. Greg Abbott able to reopen permitting sooner.

rss · Semianalysis · Nov 1, 18:40

**「Background」** SemiAnalysis&\#x27;s September analysis had argued that local datacenter moratoriums were not blocking the US buildout — of roughly 20 GW inside local restrictions, it estimated only about 1.5 GW faced delay — and its Oct. 16 article forecast a global +50 GW year for 2027. The restrictions have since widened: on Sept. 21, 2026, Governor Greg Abbott directed the Texas Commission on Environmental Quality to pause issuing permits for datacenter projects until ERCOT completes its review, a hold layered on top of the interconnection-queue audit begun Aug. 3. ERCOT has targeted Dec. 10 for a filing covering its verification and audit work, but that target is not a binding end to the permit freeze, and each permit still requires approval after any decision to resume issuance.

**「Permitting timeline becomes the binding constraint」** For developers holding 2028 capacity in Texas — close to 30% of the model&\#x27;s US net additions — the TCEQ permit freeze, not the election outcome alone, is the binding constraint: a restart after ERCOT&\#x27;s targeted Dec. 10 report leaves a short interruption some projects can absorb, while waiting for legislation in the Jan. 12–May 31, 2027 session extends the freeze to roughly eight months, or close to a year if new rules take effect in late summer. Because Gina Hinojosa has publicly called for a moratorium until the legislature passes guardrails, projects that need TCEQ air, water-discharge, or onsite-power approvals before construction should treat 2028 schedules as contingent and plan around an approval gap of five to nine additional months versus a December restart.

<details><summary>References</summary>
<ul>
<li><a href="https://pacificsoftwareventures.com/newsroom/texas-tceq-data-center-permit-halt-commercial-real-estate">Texas TCEQ Data Center Permit Halt: The CRE Read | PSV</a></li>
<li><a href="https://blockspace.media/insight/texas-data-center-permit-freeze/">Texas imposes open-ended freeze on data - center ... - Blockspace</a></li>
<li><a href="https://www.elpasotimes.com/story/news/politics/elections/2026/07/24/hinojosa-calls-for-data-center-moratorium-in-texas-gina-hinojosa-greg-abbott/91024223007/">Hinojosa calls on Abbott to sign data center moratorium in Texas</a></li>
<li><a href="https://www.cnbc.com/2026/08/20/ai-data-center-election-backlash.html">AI data center outrage is showing up everywhere from ads to elections</a></li>

</ul>
</details>

**Tags**: `#data centers`, `#AI infrastructure`, `#technology policy`, `#US elections`

---

<a id="item-tech-news-4"></a>
### [Theory paper: RLVR pass@1 gains provably cost some prompts](https://www.reddit.com/r/MachineLearning/comments/1xlnu1y/r_there_is_no_free_lunch_in_rlvr_under_strategy/) ⭐️ 7.0/10

A theory paper \(arXiv 2610.39295, posted to r/MachineLearning with a code and verification package that script-checks every number\) argues that under &quot;strategy specialization,&quot; RLVR updates that raise pass@1 must strictly lower success on some prompts, with a Stiemke duality condition — a strictly positive price on prompts that equalizes strategy fitness — as the exact condition. The model treats RLVR as an exponential tilt of the base policy over solution strategies shared across prompts, described as exact for mirror descent, with GRPO staying within 3e-4 TV of it at matched entropy in simulation; being the best strategy on each prompt is shown to be insufficient via a 3x3 free-lunch counterexample. The paper bounds the number of pass@1/pass@k crossings by the sign variation of the per-prompt success shift \(Karlin total positivity\), reports the bound as tight for 1 to 6 crossings, and recovers the known single-crossover result in the order-preserving case. It includes no new training runs, and applied to published GRPO numbers for Omni-MATH \(transcribed and labeled indicative only\) it finds one crossing between k=64 and k=256; the author notes the forced crossover requires a coverage assumption and the paper gives the regime where it fails.

reddit · r/MachineLearning · /u/SwimmingAmbition5148 · Nov 2, 04:30

**「Why the pass@1 vs. pass@k gap matters」** RLVR \(reinforcement learning with verifiable rewards\) fine-tunes a pretrained model against automatically checkable rewards such as math answer matches or passing unit tests, and pass@k measures whether any of k sampled attempts succeeds, so large k probes the coverage of a model&\#x27;s reasoning rather than its sampling efficiency. The specific predecessor the paper builds on is Yue et al. \(arXiv 2504.13837, April 2025\), which reported that RLVR-trained models beat their base models at small k such as k = 1, while base models score higher at large k, concluding that the gains originate from and remain bounded by the base model&\#x27;s existing capacity; a related study of RLVR across math, coding, and vision benchmarks similarly found fine-tuning improves sampling efficiency without expanding reasoning capacity. The post&\#x27;s question is whether that pattern is an artifact of insufficient training or a structural property, which it addresses with a theory model rather than new training runs.

**「Impact」** Because the diagnostic needs only per-prompt base and RL success rates already present in standard evaluation logs, teams can read off the crossing count, the bound, and the worst-case pass@k loss without retraining. The paper also frames the tradeoff as a frontier: imposing a per-prompt floor traces the optimal pass@1-versus-pass@k trade, while forbidding any per-prompt loss removes the crossover together with the pass@1 gain. The open compatibility concern is that the analysis rests on a population-limit shared-strategy abstraction, so its predictions on finite per-prompt logs remain unvalidated — the author explicitly asks for logs showing 2+ crossings.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2504.13837">[2504.13837] Does Reinforcement Learning Really Incentivize ...</a></li>
<li><a href="https://limit-of-rlvr.github.io/">Limit of RLVR</a></li>

</ul>
</details>

**Tags**: `#reinforcement learning`, `#RLVR`, `#pass@k`, `#LLM evaluation`, `#theory`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Reliable LLM Alignment Is Impossible in Principle](https://seangoedecke.com/alignment-is-impossible/) ⭐️ 7.0/10

rss · Sean Goedecke · Nov 2, 00:00

**「Background」** Powerful AI could act unpredictably, and “solving alignment” would mean being confident that a superintelligent system will never do so. Sean Goedecke argues that for LLMs this goal is not merely difficult but conceptually incoherent, because we cannot articulate what success would even look like.

**「Solution」** Older safety thinking treated AI as a blind optimizer with a fixed goal, so alignment meant specifying the right goal. LLMs instead imitate a vast human corpus and switch among many personas, leaving no fixed formal goal to constrain. The author argues we must therefore understand them well enough to trust them, but “full understanding of motive” is unattainable: tracing weights does not explain why in human terms, and motives bottom out. Mechanistic interpretability cannot close the gap for three reasons. It labels patterns from observed behavior, while the feared sudden harmful action is by definition unobserved; its labels may be wrong, as with Kripke’s indistinguishable “kindness unless…” variants; and interpreting every feature combination per token is too complex for humans. Even a hypothetical predictive interpretability would face near-infinite inputs and outputs and require another model to check, ad infinitum. Chain-of-thought monitoring, sandboxing, human oversight, and feature watching help, but Goedecke says they are insufficient against superintelligence.

**「Takeaway」** Goedecke’s core conclusion is that because LLM “motives” are not a stable formal object, no human-comprehensible understanding can provide certainty that a model is aligned. We can define alignment behaviorally—the model never does anything bad—but not what it would mean to know it is aligned.

**Tags**: `#AI alignment`, `#mechanistic interpretability`, `#LLM safety`, `#AI risk`, `#philosophy of mind`

---