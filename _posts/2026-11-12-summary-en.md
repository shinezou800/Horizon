---
layout: default
title: "Horizon Summary: 2026-11-12 (EN)"
date: 2026-11-12
lang: en
---

> From 48 items, 13 important content pieces were selected

---

**Technology News**
1. [Voltage glitching a mining card to unlock A100-class GPU resources](#item-tech-news-1) ⭐️ 8.0/10
2. [Anthropic IPO roadshow touts four-chip Claude strategy and AI-written AMD kernels](#item-tech-news-2) ⭐️ 8.0/10
3. [False Smoke Alarm at Jane Street&\#x27;s Sole NYC Datacenter](#item-tech-news-3) ⭐️ 7.0/10
4. [Can Linear Programming Edit LLM Weights?](#item-tech-news-4) ⭐️ 7.0/10
5. [Google launches Gemini Decisions API for scored multimodal choices](#item-tech-news-5) ⭐️ 7.0/10
6. [AWS&\#x27;s official emulator enables local service testing without a paid API key](#item-tech-news-6) ⭐️ 7.0/10
7. [Tim Peters, author of Zen of Python and Timsort, dies](#item-tech-news-7) ⭐️ 7.0/10
8. [AMD&\#x27;s Mext AI paging moves cold memory to NVMe, claims 83% server cost cut](#item-tech-news-8) ⭐️ 7.0/10
9. [ByteDance Reportedly Prepares Muse-Like AI Agent, Targets 2030 Frontier](#item-tech-news-9) ⭐️ 7.0/10
10. [Report alleges Alice Huang helped divert 240,000 Nvidia chips to China](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [Goolsbee calls October inflation report &\#x27;borderline disturbing&\#x27; as Fed weighs faster hikes](#item-finance-news-1) ⭐️ 8.0/10
2. [China ends transition period for offshore trust income tax; over RMB 160 billion declared](#item-finance-news-2) ⭐️ 8.0/10
3. [Stripe 宣布将 OpenRouter 并入旗下](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Voltage glitching a mining card to unlock A100-class GPU resources](https://blog.kate.land/posts/using-voltage-glitching-to-unlock-the-a100/) ⭐️ 8.0/10

A technical blog post describes using voltage glitching—briefly manipulating a chip&\#x27;s supply voltage—to unlock A100-class GPU resources on a mining card. It presents the approach as a hardware reverse-engineering technique for hardware hackers and mining-card owners, rather than a software-only modification. The supplied material does not specify the exact card model, how much memory or compute is recovered, whether the unlock persists across reboots, or how reliably the procedure works.

hackernews · lae · Nov 11, 10:48 · [Discussion](https://news.ycombinator.com/item?id=50451903)

**「Background」** The card in question is NVIDIA&\#x27;s CMP 170HX, a GA100-based mining GPU that shipped with HBM capacity, compute, and PCIe links deliberately restricted. Earlier 2026 community reports described firmware exploits and hardware modifications intended to remove some of those limits, and open-source tools aimed at re-enabling factory-disabled HBM2e, turning 8GB or 10GB cards into theoretical 64GB or 80GB configurations.

**「Practical impact」** For people buying cheap CMP 170HX mining cards to recover A100-class HBM capacity, unlock results have not been uniformly stable: a GitHub issue thread reports one 10GB card running error-free in tests when unlocked to 40GB, but hitting occasional GPU-burn errors at 80GB. Because the fuse-blowing approach described in the post is irreversible, card owners would need to validate stability at their target capacity before depending on an unlocked card for real workloads, and community commenters describe the fuse method as substantially riskier than software-only unlocking attempts.

**「Community discussion」** Commenters debate whether the disabled resources reflect product segmentation or chips with fabrication faults; one speculates that NVIDIA would more likely reserve fully working A100s for datacenter sales and fuse off faulty parts for mining cards. A commenter working on a CMP 170HX reports two weeks of unsuccessful software-only attempts at an 80 GB unlock and calls the hardware approach riskier, while another suggests using an external PCIe riser and separate power supply so only the target card cycles during repeated attempts.

<details><summary>References</summary>
<ul>
<li><a href="https://knightli.com/en/2026/07/22/cmp-170hx-80gb-memory-unlock-ai-gpu-buying-risk/">Is the CMP 170HX 80GB Memory Unlock Reliable? AI Mining GPU ...</a></li>
<li><a href="https://mineraleyt.com/en/posts/nvidia-cmp-170hx-vram-unlock/">NVIDIA CMP 170HX: Unlocking Hidden VRAM and Why It&#x27;s an AI ...</a></li>
<li><a href="https://github.com/dartraiden/NVIDIA-patcher/issues/73">170 hx （any cmp hx card ） can run higher and higher fp32 flops than...</a></li>

</ul>
</details>

**Tags**: `#voltage glitching`, `#GPU hacking`, `#hardware reverse engineering`, `#NVIDIA A100`, `#mining cards`

---

<a id="item-tech-news-2"></a>
### [Anthropic IPO roadshow touts four-chip Claude strategy and AI-written AMD kernels](https://simonwillison.net/2026/Nov/11/anthropic-ipo-roadshow/) ⭐️ 8.0/10

In Anthropic&\#x27;s IPO roadshow video, co-founder Tom Brown said the company now trains and serves Claude across all four major chip families: AWS Trainium, Google TPUs, NVIDIA GPUs and AMD GPUs, describing an early &quot;unconventional bet&quot; on a multi-chip strategy that requires a tailored software and inference stack per chip. He said that when Anthropic began working with AMD GPUs this year, a system referred to as Mythos got Claude running on AMD in three days with &quot;basically no human intervention,&quot; writing or porting almost 100% of the kernels — work that previously took dozens of engineers months. Brown also framed &quot;compute multipliers&quot; as stacking advantages, and said Anthropic believes Claude will eventually discover such multipliers entirely by itself. These are company claims made in an investor presentation, not independently verified results; there is no official transcript, and the quoted excerpts come from a transcript Simon Willison produced with MacWhisper.

rss · Simon Willison · Nov 11, 15:11

**「Prior context」** Running a model on any given accelerator family requires its own tailored software and inference stack, which is why supporting several chip types is normally expensive and slow — Anthropic says bringing on a new platform previously took dozens of engineers months. The company had already signalled a multi-vendor setup: as the source notes, a postmortem of three recent issues described bugs that affected only its TPU deployments. The new material comes from the &quot;Approach to compute&quot; section of the roadshow video, presented by co-founder Tom Brown.

**「Why the chip mix matters」** If the claimed three-day AMD bring-up holds, the practical bottleneck for adding a new accelerator family shifts from hand-written kernels toward the tooling that generates them — which is the argument Anthropic is making to investors for why it can absorb capacity wherever it is available rather than depending on a single supplier. The post also notes that Anthropic&\#x27;s multi-chip setup was already visible in its September postmortem of three incidents, where the described bugs affected only its TPU deployments, meaning chip-specific failure modes are a real operational cost of the strategy.

**Tags**: `#Anthropic`, `#AI infrastructure`, `#multi-chip training`, `#IPO`, `#Claude`

---

<a id="item-tech-news-3"></a>
### [False Smoke Alarm at Jane Street&\#x27;s Sole NYC Datacenter](https://michael.bacarella.com/2026/11/10/false-smoke-alarm-jane-street-datacenter/) ⭐️ 7.0/10

An author&\#x27;s incident account describes a false smoke alarm at Jane Street&\#x27;s only New York City datacenter and the operational response it triggered. The account is a first-person operations narrative rather than an announcement of a service change or outage; the supplied material does not specify the alarm&\#x27;s cause, any equipment damage, or how long systems were affected. Its useful technical content is the response narrative and the questions it raises about alarm, cooling, and emergency power-off procedures.

hackernews · mbac32768 · Nov 11, 16:38 · [Discussion](https://news.ycombinator.com/item?id=50455394)

**「Background」** Datacenter fire-safety designs commonly tie smoke detectors to suppression systems and to air-handler shutdowns; as one commenter notes, the International Mechanical Code allows large cooling units serving a single space to keep running on alarm because they do not spread smoke through a building. The trade-off is that halting cooling while servers keep drawing power can turn a false alarm into a heat emergency. In this case, construction dust is reported to have tripped the alarm at Jane Street&\#x27;s only New York datacenter, prompting staff to cut power before sprinklers discharged.

**「Community Discussion」** Commenters focused on emergency power-off and smoke-alarm interlocking: one questioned whether the site had a physical EPO button and an automatic smoke-alarm link, while another said their data-hall sequence of operations deliberately does not shut down CRACs on smoke detection, citing an International Mechanical Code allowance for large air handlers serving a single space. Others reported proximity-based emergency-response experience, including hauling diesel up stairs during Hurricane Sandy and being the nearby employee called in to shut down servers.

<details><summary>References</summary>
<ul>
<li><a href="https://michael.bacarella.com/2026/11/10/false-smoke-alarm-jane-street-datacenter/">How a false smoke alarm almost drowned Jane Street ’s only NYC ...</a></li>
<li><a href="https://dzen.ru/b/avSsqBnX-RwkJu2p">Ложная пожарная тревога едва не затопила серверы Jane Street ...</a></li>

</ul>
</details>

**Tags**: `#datacenter operations`, `#incident response`, `#reliability engineering`, `#fire safety`, `#infrastructure`

---

<a id="item-tech-news-4"></a>
### [Can Linear Programming Edit LLM Weights?](https://nathan.rs/posts/weight-space-lp/) ⭐️ 7.0/10

A blog post on nathan.rs examines whether linear programming can be used for direct weight-space programming in large language models, framing behavior control as linear constraints — remove one behavior while preserving another — rather than as a reward signal. The piece is an exploratory analysis, not a reported experimental result or a released tool, and the Hacker News discussion treats the idea as promising rather than validated. Commenters extend the concept to sparse weight edits, weight-space distillation, and training-time regularization.

hackernews · emschwartz · Nov 11, 12:30 · [Discussion](https://news.ycombinator.com/item?id=50452655)

**「Prior context」** The post follows MIT CSAIL&\#x27;s &quot;Sparks of Weight-Space Programming,&quot; published the week before, which framed model behavior change as a direct edit to weights rather than prompting. Weight-space programming asks whether a target behavior can be produced by modifying parameters directly, and the new post takes up one narrow version of that question: whether the choice of an edit direction can be posed and solved as a linear program, and how the result compares with an ordinary steering vector.

**「Impact」** For developers working on behavior editing, the proposal would shift effort from tuning rewards and penalties to expressing each desired behavior change as a linear constraint, with a solver then searching for sparse weight edits that satisfy it; the practical constraint is that behaviors must be formulable in that linear form.

**「Community Discussion」** jsw97 argues the solver is most useful as a guided tool — given constraints to eliminate or preserve behaviors, it could make weight-editing methods more effective — while mirekrusin proposes applying it to weight-space distillation by collecting paired examples, discovering behavioral directions, and finding sparse edits. dansitu contends the simplicity of the idea suggests it belongs inside training as a regularizer, and whatever1 asserts that traditional math programming will replace or override the RL loop because rewards and penalties cannot enforce strict constraints across multiple objectives.

<details><summary>References</summary>
<ul>
<li><a href="https://nathan.rs/posts/weight-space-lp/">Can a Linear Program Do Weight - Space Programming ?</a></li>

</ul>
</details>

**Tags**: `#linear programming`, `#LLM weight editing`, `#weight-space optimization`, `#model behavior control`, `#Hacker News`

---

<a id="item-tech-news-5"></a>
### [Google launches Gemini Decisions API for scored multimodal choices](https://blog.google/innovation-and-ai/technology/developers-tools/gemini-decisions-api/) ⭐️ 7.0/10

Google has released the Gemini Decisions API, built on a new Gemini Decision 1 model, for closed-ended decisions such as tool selection, policy checks, and model routing. The API accepts text, images, audio, video, and PDFs and can score up to 1,000 questions in one request, returning probabilities and confidence scores with roughly 150–250 ms end-to-end latency. It costs $0.10 per million input tokens with no charge for output tokens, and Google says it is nearly five times cheaper than a Gemini 3.5 Flash-Lite setup. It is available in Google AI Studio.

hackernews · iamdelirium · Nov 11, 18:32 · [Discussion](https://news.ycombinator.com/item?id=50456791)

**「Background」** Decision models target closed-ended judgments—true/false checks, multiple-choice selection, or rubric scoring—rather than free-form generation. The Gemini Decision 1 model behind this API returns a structured answer plus a confidence value for each question, with support for up to 255 choices and 255 score levels. That structure is what lets developers ask many small, bounded questions about one input in a single pass.

**「Impact」** For developers, adopting the API means restructuring calls around a closed set of candidate decisions and reading probability scores rather than free-form model output, which fits tool-selection or routing layers that need to rank many options at once. The vendor&\#x27;s cost comparison and the reported latency still need independent validation for latency-sensitive production use.

**「Community discussion」** Commenters questioned how the model derives probabilities and asked how decision models are being used in coding harnesses. Others said the API is pricier than rival decision models but saw value in its audio and video inputs, while one developer praised respan/span-02 and remained optimistic about this release despite the cost.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/technology/developers-tools/gemini-decisions-api/">Gemini Decisions API : Fast multimodal decisions</a></li>
<li><a href="https://openrouter.ai/google/gemini-decision-1">Gemini Decision 1 - API Pricing &amp; Providers | OpenRouter</a></li>

</ul>
</details>

**Tags**: `#Gemini API`, `#decision models`, `#Google AI`, `#developer tools`, `#Hacker News`

---

<a id="item-tech-news-6"></a>
### [AWS&\#x27;s official emulator enables local service testing without a paid API key](https://github.com/aws/aws-emulator) ⭐️ 7.0/10

AWS has published an official emulator that lets developers run tests against local clones of its services without provisioning a paid API key. The project is written in Rust and, according to Simon Willison&\#x27;s post, drew 29,684 commits in its first three weeks from a large swarm of AI agents; Swaminathan Sivasubramanian described its origins in a guest post on Werner Vogels&\#x27; blog. On macOS and Windows it currently requires Docker, so it is not yet a single downloadable binary for use in standard test suites.

hackernews · super\_linear · Nov 11, 18:21 · [Discussion](https://news.ycombinator.com/item?id=50456631)

**「Why local AWS emulators exist」** Local AWS emulators address a common testing problem: rather than provisioning real cloud resources, developers run a program that serves an AWS-compatible API endpoint on their own machine and point the AWS CLI or an SDK at it through environment variables, so tests do not require live credentials or a paid API key \[tool-2-2\]. AWS&\#x27;s official release enters a niche already served by third-party emulators such as LocalStack, Floci, Fakecloud and Ministack, which Hacker News commenters cite as their existing alternatives.

**「Practical impact」** Developers can run local AWS service tests without a paid API key, but the project&\#x27;s security guidance, as quoted in the discussion, says not to use the emulator for IAM policies, resource-based policies, KMS key policies, cross-account or cross-Region access, or other security controls; those authorization tests still need real AWS. On macOS and Windows the emulator also requires Docker, so it cannot yet be a single-binary dependency for local test suites on those platforms.

**「Community discussion」** Commenters questioned whether the emulator is a product AWS will maintain or an exercise, and one recommended Floci with Testcontainers, saying Floci has worked well for them and also supports GCP and Azure, though they have used it only in a limited capacity. Another commenter quoted AWS&\#x27;s security page warning against using the emulator to test IAM policies, resource-based policies, KMS key policies, cross-account or cross-Region access, or other security controls; others debated the agent-written Rust code, with one arguing AI agents made the project feasible and another criticizing the language choice.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/aws/aws-emulator">GitHub - aws / aws - emulator : AWS Emulator is a local emulator of...</a></li>

</ul>
</details>

**Tags**: `#AWS`, `#cloud emulation`, `#local development`, `#software testing`, `#developer tools`

---

<a id="item-tech-news-7"></a>
### [Tim Peters, author of Zen of Python and Timsort, dies](https://discuss.python.org/t/in-memoriam-tim-peters-1952-2026/110028) ⭐️ 7.0/10

Tim Peters, a major Python contributor known for writing the Zen of Python and creating Timsort, has died, according to an in-memoriam post on the Python discussion forum. The post identifies him as 1952–2026 and has prompted community remembrance of his work in CPython and open source. The announcement is an obituary, not a release or technical change.

hackernews · ayhanfuat · Nov 11, 07:03 · [Discussion](https://news.ycombinator.com/item?id=50450488)

**「Background」** Peters was a major Python contributor best known for writing the Zen of Python, the set of design aphorisms displayed by \`import this\`, and for Timsort, a sorting algorithm he contributed to CPython. Those works gave him a lasting influence on Python&\#x27;s design culture and on the standard library&\#x27;s sorting behavior.

**「Community discussion」** Commenters quoted the Zen of Python via \`import this\` and recalled Peters&\#x27; role with Gary Robinson in turning Paul Graham&\#x27;s &quot;A Plan for Spam&quot; into SpamBayes, with one commenter noting Robert Woodhead also shares credit. Others described his willingness to foster wide-ranging technical discussion, including his contributions to the Python Cookbook 2nd Edition and discussions of voting systems.

**Tags**: `#Python`, `#Tim Peters`, `#obituary`, `#open source`, `#CPython`

---

<a id="item-tech-news-8"></a>
### [AMD&\#x27;s Mext AI paging moves cold memory to NVMe, claims 83% server cost cut](https://www.theregister.com/systems/2026/11/11/amd-where-were-going-we-dont-need-as-much-dram/5308953) ⭐️ 7.0/10

AMD is promoting Mext, software built from acquired technology, that uses an AI model to page memory between DRAM and cheaper NVMe flash before the operating system or applications notice, reducing how much DRAM a server needs. AMD claims that replacing half of a server&\#x27;s DRAM with flash still retains up to 99% of performance, and it estimates the approach can cut enterprise server costs by up to 83%. A Mext license must be purchased together with Epyc servers. These figures are vendor claims: the source offers no independent benchmarks, nor details on how pages are selected, what latency the paging adds, or which workloads were tested.

telegram · zaihuapd · Nov 11, 11:15

**「Background」** MEXT entered AMD through an acquisition announced in June 2026, which AMD described as expanding its AI portfolio with memory-optimization technology intended to improve performance and reduce total cost of ownership. AMD&\#x27;s own product description characterizes MEXT as a software-only solution that uses AI to make low-cost, high-capacity flash appear as DRAM-speed memory, creating a cheaper price-performance tier to reduce reliance on volatile DRAM. The current report concerns AMD&\#x27;s effort to commercialize that acquired technology as software licensed alongside Epyc servers.

**「Licensing and workload fit determine real savings」** Because Mext is licensed together with a new Epyc server, the DRAM reduction has to be weighed against license cost, and the 83% figure comes from AMD&\#x27;s internal data rather than independent testing. The company also ties the savings to cold-page optimization on specific hardware, so operators should measure how much of their own workload actually sits in cold pages before cutting installed DRAM in half.

<details><summary>References</summary>
<ul>
<li><a href="https://www.amd.com/en/blogs/2026/amd-acquires-mext-for-memory-optimization.html">AMD Acquires MEXT to Advance Memory Optimization</a></li>
<li><a href="https://www.amd.com/en/products/software/mext.html">AMD MEXT Predictive Memory Software</a></li>
<li><a href="https://www.theregister.com/systems/2026/11/11/amd-where-were-going-we-dont-need-as-much-dram/5308953">AMD: Where we&#x27;re going we don&#x27;t need (as much) DRAM</a></li>
<li><a href="https://www.ainvest.com/news/amd-mext-cut-server-memory-costs-83-real-story-eats-dram-supercycle-2611/">AMD says MEXT can cut server memory costs 83% - the real ...</a></li>

</ul>
</details>

**Tags**: `#AMD`, `#memory tiering`, `#NVMe`, `#server hardware`, `#cost reduction`

---

<a id="item-tech-news-9"></a>
### [ByteDance Reportedly Prepares Muse-Like AI Agent, Targets 2030 Frontier](https://www.bloomberg.com/news/articles/2026-11-11/bytedance-prepares-muse-like-agent-in-push-to-close-ai-gap) ⭐️ 7.0/10

ByteDance is reportedly preparing to release a Meta Muse-like AI assistant within weeks, according to a Telegram digest of Bloomberg and Economic Times reporting. At an internal all-hands, co-founder Zhang Yiming told the company&\#x27;s AI team that ByteDance aims to match Anthropic and OpenAI at the frontier by 2029 or 2030, not sooner. The company plans to invest up to $70 billion in its Seedance video AI platform and says it does not intend to rely on model distillation. The account describes plans and an internal target; it does not show a shipped product or independent confirmation.

telegram · zaihuapd · Nov 11, 12:31

**「Background」** Meta&\#x27;s Muse, the comparison point in ByteDance&\#x27;s plan, is a personal AI agent launched in September 2026 that runs on a dedicated secure VM with its own browser and works across a user&\#x27;s everyday apps on their behalf. The $70 billion figure is not new: Bloomberg reported in May 2026 that ByteDance was weighing capital spending of as much as that amount in an AI push, and the current reporting ties the sum specifically to building Seedance into its main video AI platform.

<details><summary>References</summary>
<ul>
<li><a href="https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/">Introducing Muse : The World’s First Personal AI Agent Built for...</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-05-27/bytedance-weighs-capex-of-as-much-as-70-billion-in-ai-push">ByteDance Weighs Capex of as Much as $70 Billion in AI Push</a></li>

</ul>
</details>

**Tags**: `#ByteDance`, `#AI agents`, `#AI video`, `#OpenAI`, `#industry investment`

---

<a id="item-tech-news-10"></a>
### [Report alleges Alice Huang helped divert 240,000 Nvidia chips to China](https://www.tomshardware.com/tech-industry/policy/alice-huang-reportedly-instrumental-in-securing-over-usd7-5-billion-of-nvidia-ai-gpu-imports-during-three-year-relationship-with-jensen-huang-helped-move-240-000-banned-chips-into-china-mostly-h100-and-h200) ⭐️ 7.0/10

An investigation by The Information, as summarized in a Telegram digest, alleges that Alice Huang used her relationship with Nvidia CEO Jensen Huang to help about 240,000 restricted Nvidia chips enter China, mostly H100 and H200 GPUs. The digest says the imports were valued at roughly $7.5 billion and involved companies including Shanghai Century Litong and Singapore-based Megaspeed. The supplied material does not independently verify the allegations or include a response from Nvidia or the named companies.

telegram · zaihuapd · Nov 11, 14:41

**「Background」** U.S. export controls bar the sale of advanced Nvidia data-center accelerators such as the H100 and H200 to China without a license, which is why the chips in the report are described as banned. The investigation centers on Alice Huang, whom the New York Times reports U.S. intelligence assessed to be a Chinese asset and who moved from Shanghai finance into control of Singapore-based Megaspeed, a company already tied to U.S. probes of AI-chip exports.

<details><summary>References</summary>
<ul>
<li><a href="https://www.tomshardware.com/tech-industry/policy/alice-huang-reportedly-instrumental-in-securing-over-usd7-5-billion-of-nvidia-ai-gpu-imports-during-three-year-relationship-with-jensen-huang-helped-move-240-000-banned-chips-into-china-mostly-h100-and-h200">Alice Huang reportedly instrumental in securing over $7.5 ...</a></li>
<li><a href="https://www.nytimes.com/2026/11/10/technology/alice-huang-megaspeed-nvidia-jensen-huang.html">Who Is Alice Huang, the Woman in the Middle of Nvidia’s Spy ...</a></li>
<li><a href="https://www.globalbankingandfinance.com/alice-huang-chinese-businesswoman-tied-nvidia-ceo-went/">Alice Huang: Chinese Financier Linked to Nvidia CEO and AI ...</a></li>

</ul>
</details>

**Tags**: `#nvidia`, `#export-controls`, `#ai-hardware`, `#china`, `#semiconductor-policy`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Goolsbee calls October inflation report &\#x27;borderline disturbing&\#x27; as Fed weighs faster hikes](https://www.cnbc.com/2026/11/11/goolsbee-october-inflation-fed-rates-disturbing-distressing.html) ⭐️ 8.0/10

Chicago Fed President Austan Goolsbee called October’s inflation report “borderline disturbing” after the consumer price index rose 0.4% for the month—above economists’ forecasts and the third straight month of outsized increases—and said the Fed has a real inflation issue to deal with. Fed funds futures now unanimously expect a rate increase at the December meeting, with 15% odds of a half-point move, according to CME’s FedWatch tool.

rss · CNBC Finance · Nov 11, 16:49

**「Background」** The Fed had raised its benchmark rate by a quarter point in September to a range of 3.75%-4% and held it steady in October.

**Tags**: `#Federal Reserve`, `#inflation`, `#interest rates`, `#monetary policy`, `#CPI`

---

<a id="item-finance-news-2"></a>
### [China ends transition period for offshore trust income tax; over RMB 160 billion declared](https://www.news.cn/20261111/9bcce99c779b4a6197ff45bbbc3e4c50/c.html) ⭐️ 8.0/10

China&\#x27;s State Taxation Administration said on Nov 11 that the 90-day transition period for taxing offshore trust income ended with more than RMB 160 billion in personal income tax declared in total, including over RMB 120 billion paid in October alone — an inflow the authority said lifted national personal income tax revenue by nearly 90% that month. The transition, announced by the Ministry of Finance and the tax authority on July 24, 2026, waived late-payment surcharges for those who declared and paid within the window.

telegram · zaihuapd · Nov 11, 10:35

**「Background」** China’s Ministry of Finance and State Taxation Administration issued individual income tax rules for offshore trusts on July 24, 2026, opening a 90-day window during which taxpayers could declare outstanding 2023–2025 tax without late-payment interest.

**「Impact」** Beneficiaries of offshore trusts who did not declare, or who filed inaccurately, now face demands to pay back taxes plus late-payment surcharges and, if they still do not correct their filings, formal tax audits, the authority said.

<details><summary>References</summary>
<ul>
<li><a href="https://www.morganlewis.com/pubs/2026/07/china-establishes-new-individual-income-tax-rules-for-offshore-trusts">China Establishes New Individual Income Tax Rules for ...</a></li>
<li><a href="https://kpmg.com/cn/en/insights/2026/07/china-tax-alert-05.html">New Individual Income Tax Rules for Offshore Trusts ...</a></li>

</ul>
</details>

**Tags**: `#offshore trusts`, `#personal income tax`, `#tax enforcement`, `#China fiscal policy`, `#wealth management`

---

<a id="item-finance-news-3"></a>
### [Stripe 宣布将 OpenRouter 并入旗下](https://x.com/stripe/status/2120240651778355306) ⭐️ 7.0/10

Stripe announced that OpenRouter, a platform that routes requests across different AI models, is being brought under its umbrella as part of its stated push to build &quot;economic infrastructure&quot; for AI, saying the two will help businesses test new models and manage token routing and usage. No deal terms or valuation were disclosed.

telegram · zaihuapd · Nov 11, 09:45

**「Background」** OpenRouter runs an AI &quot;model gateway,&quot; a service that routes companies&\#x27; requests across different AI models and tracks their usage; Stripe said in August 2026 that it had agreed to acquire the company. Bloomberg reported the deal price at more than $7 billion, citing people familiar with the matter.

**「Impact」** Businesses that use OpenRouter to route requests across AI models could have model access, usage measurement and billing linked directly to Stripe&\#x27;s payment infrastructure, according to Fintech Observe&\#x27;s description of the deal.

<details><summary>References</summary>
<ul>
<li><a href="https://stripe.com/newsroom/news/stripe-agrees-to-acquire-openrouter">Stripe agrees to acquire OpenRouter to help businesses ...</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/stripe-acquires-openrouter-7b-turning-091812340.html?fr=sycsrp_catchall">Stripe Acquires OpenRouter for $7B+, Turning Model Routing ...</a></li>
<li><a href="https://fintechobserve.com/fintech-daily-briefing-stripe-openrouter-stablecoins/">Stripe ’s reported OpenRouter deal leads fintech’s push into AI ...</a></li>

</ul>
</details>

**Tags**: `#Stripe`, `#OpenRouter`, `#acquisition`, `#AI infrastructure`, `#fintech`

---