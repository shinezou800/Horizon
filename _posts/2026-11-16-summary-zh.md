---
layout: default
title: "Horizon Summary: 2026-11-16 (ZH)"
date: 2026-11-16
lang: zh
---

> 从 39 条内容中筛选出 6 条重要资讯。

---

**科技新闻**
1. [uBlock Origin 元素选择器曝出通用跨站脚本漏洞](#item-tech-news-1) ⭐️ 8.0/10
2. [大语言模型中的位置编码技术解析](#item-tech-news-2) ⭐️ 8.0/10
3. [Qwen4-Max 发布与社区讨论](#item-tech-news-3) ⭐️ 8.0/10
4. [Meta FAIR 与 NYU 研究表明多模态视觉编码器预训练可选但专用参数不可或缺](#item-tech-news-4) ⭐️ 8.0/10
5. [开发者推出针对 B300 的 cudaMemcpy 调优工具，使传输速度提升五倍](#item-tech-news-5) ⭐️ 8.0/10
6. [使用 Protomaps 和 PMTiles 实现低成本自托管地图瓦片](#item-tech-news-6) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [uBlock Origin 元素选择器曝出通用跨站脚本漏洞](https://iter.ca/post/ubo-uxss/) ⭐️ 8.0/10

uBlock Origin 被曝出存在由网站驱动的元素选择器引发的通用跨站脚本（UXSS）漏洞。用户需要将 uBlock Origin 更新至 1.76.4 或更高版本，或将 uBO Lite 更新至 2026.1110.1816 及更高版本以修复此问题。此次漏洞凸显了浏览器扩展将交互界面注入网站 DOM 所带来的架构安全挑战。

hackernews · zaik · 11月16日 02:04 · [社区讨论](https://news.ycombinator.com/item?id=50513160)

**「背景」** 浏览器扩展为了能够直接与网页元素进行交互和操作，通常需要将自身的界面元素注入到目标网站的 DOM 当中。这种设计模式虽然赋予了扩展强大的页面控制能力，但也容易引发特权提升或跨站脚本等安全风险。

**「影响」** 仍在使用旧版本扩展的用户面临安全风险，建议尽快检查并升级至安全版本，部分评论还建议通过重建浏览器配置文件等方式进行深度清理。

**「社区讨论」** 评论者指出这类漏洞反映了扩展将界面放入网站 DOM 的固有架构缺陷，并讨论了将其移至浏览器 chrome 层的可行性，同时有用户分享了受影响的具体版本号及清理配置文件的建议。

**标签**: `#security`, `#browser extensions`, `#vulnerabilities`, `#uBlock Origin`, `#web development`

---

<a id="item-tech-news-2"></a>
### [大语言模型中的位置编码技术解析](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 8.0/10

本文深入分析了现代大语言模型中位置 embeddings 的具体实现机制与工作原理。文章剖析了不同位置编码方案在神经网络架构中的应用与技术细节。读者可以通过该分析更好地理解位置信息是如何被编码并输入到模型中的。

hackernews · vismit2000 · 11月15日 12:14 · [社区讨论](https://news.ycombinator.com/item?id=50506376)

**「背景」** 由于 Transformer 架构本身具有置换不变性，无法自动识别输入序列中词元的先后顺序，因此必须引入位置编码来为模型提供序列的相对或绝对位置信息。

**「社区讨论」** 有评论指出，除了文章所讲的实现细节外，真正理解位置编码还需要掌握其背后的群论理论，例如将旋转位置编码视为平移群的表示。该评论认为，从群表示的角度出发才能更好地理解如何参数化并使其具有可微性和可学习性。

**标签**: `#artificial intelligence`, `#machine learning`, `#large language models`, `#neural networks`

---

<a id="item-tech-news-3"></a>
### [Qwen4-Max 发布与社区讨论](https://qwen.ai/blog?id=qwen4-max) ⭐️ 8.0/10

Qwen4-Max 已正式发布，引发了社区对其基准性能、推理努力设置和生成速度的广泛关注与讨论。据社区评论指出，其在 Artificial Analysis 上得分为 43 分，平均成本为每百万 tokens 3.27 美元，并引入了包括无推理努力在内的多档调节选项。

hackernews · ilreb · 11月16日 02:14 · [社区讨论](https://news.ycombinator.com/item?id=50513215)

**「背景」** Qwen 系列大语言模型此前推出了 Qwen 3.8 等版本，用户在实际应用中对其推理表现、生成速度及多档配置进行了长期测试与评估。

**「社区讨论」** 社区用户对比了 Qwen4-Max 的评测得分、运行成本以及新增的推理努力选项（如无推理、低、高、极高）。部分评论者还探讨了其与早期版本（如 Qwen 3.8 Max）及竞争对手模型在速度和性能上的差异。

**标签**: `#artificial intelligence`, `#machine learning`, `#large language models`, `#open source`

---

<a id="item-tech-news-4"></a>
### [Meta FAIR 与 NYU 研究表明多模态视觉编码器预训练可选但专用参数不可或缺](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

Meta FAIR 与纽约大学（NYU）的研究人员通过从头训练 200 多个多模态大语言模型（MLLM），系统评估了视觉编码器的预训练与参数配置。实验发现在匹配算力预算下，独立的视觉编码器预训练并非必须，采用四种不同目标预训练的编码器表现并不优于与大模型从头共同训练的编码器。然而，视觉专用参数是必需的，完全抛弃编码器的模型在各规模下性能均落后且需约 3 倍算力追赶。此外，将视觉专用权重通过“内融合”（In-fusion）直接加入大模型前 8 层，其效果可与传统独立编码器相媲美，同时减少了首字延迟。

reddit · r/MachineLearning · /u/trungh98 · 11月15日 17:38

**「背景」** 当前不同实验室在多模态视觉架构的选择上存在分歧，部分模型选择放弃独立编码器，部分选择从头训练编码器，而另一些则重新引入编码器。由于已发布模型在数据、算力和架构上存在诸多差异，业界此前难以孤立评估视觉编码器预训练及参数配置的具体作用。

**「影响与兼容性」** 这项研究为多模态模型架构设计提供了经验依据，表明研发人员可以通过取消独立的视觉编码器预训练来节省算力，但仍需为视觉模态保留专用参数或采用内融合策略以确保多模态理解性能。

**标签**: `#artificial intelligence`, `#machine learning`, `#computer vision`, `#multimodal models`

---

<a id="item-tech-news-5"></a>
### [开发者推出针对 B300 的 cudaMemcpy 调优工具，使传输速度提升五倍](https://www.reddit.com/r/MachineLearning/comments/1xx2n25/making_cudamemcpy_5x_faster_on_a_b300_p/) ⭐️ 8.0/10

一名开发者推出了一款名为 cudamemcpy-tuner 的调优工具，能够将 B300 系统上 CPU 到 GPU 的 pageable（可分页）cudaMemcpy 数据传输速度提升 5 倍。实测在传输 1 GB 张量时，优化前的速度为 10.2 GB/s，而使用该工具调优后达到了 51.5 GB/s。该项目目前已开源并发布了相关博客说明。

reddit · r/MachineLearning · /u/makneeee · 11月15日 18:20

**「背景」** 在 CUDA 编程中，cudaMemcpy 负责在主机（CPU）和设备（GPU）之间复制数据。默认情况下，针对未锁页内存（pageable memory）的传输通常需要经过中间缓冲区，从而限制了传输带宽和性能。

**「影响」** 使用 B300 硬件且频繁依赖 CPU 到 GPU 数据传输的开发者和研究人员，可以通过集成该调优工具来减少数据搬运的耗时，从而提升整体工作负载的执行效率。

**标签**: `#CUDA`, `#GPU`, `#Machine Learning Hardware`, `#Performance Optimization`, `#Systems`

---

<a id="item-tech-news-6"></a>
### [使用 Protomaps 和 PMTiles 实现低成本自托管地图瓦片](https://bruceroettgers.eu/blog/protomaps/) ⭐️ 7.0/10

Protomaps 和 PMTiles 的兴起使得自托管地图瓦片基础设施变得更加便宜和简单。这种方法允许开发者利用现代格式和云存储独立托管地图数据，从而降低对商业地图服务的依赖。

hackernews · bcye · 11月15日 19:26 · [社区讨论](https://news.ycombinator.com/item?id=50509837)

**「背景」** 过去自托管地图瓦片通常需要复杂的瓦片服务器和昂贵的基础设施。PMTiles 等新技术的出现简化了这一过程，使得单文件存档和对象存储的直接读取成为可能。

**「影响」** 开发者和组织可以更低廉的成本搭建私有地图服务，提升隐私保护和访问控制能力。

**「社区讨论」** 社区成员分享了多个自托管地图的开源实例与类似项目，例如使用 PMTiles 托管虚构世界地图的实现、提供免费服务的 OpenFreeMap，以及 VersaTiles 等替代方案。

**标签**: `#GIS`, `#Open Source`, `#Web Development`, `#Self-Hosting`, `#Mapping`

---