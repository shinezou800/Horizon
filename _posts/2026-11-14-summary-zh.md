---
layout: default
title: "Horizon Summary: 2026-11-14 (ZH)"
date: 2026-11-14
lang: zh
---

> 从 41 条内容中筛选出 2 条重要资讯。

---

**科技新闻**
1. [开发者利用 GPU 加速 SDR 实时监控航空无线电频段](#item-tech-news-1) ⭐️ 7.0/10

**财经新闻**
1. [商务部长劳特尼克因英伟达关联面临审查](#item-finance-news-1) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [开发者利用 GPU 加速 SDR 实时监控航空无线电频段](https://orcasairband.com/) ⭐️ 7.0/10

开发者分享了一款基于 Ettus B210 硬件与双 NVIDIA RTX 4090 GPU 构建的实时航空无线电频段监控工具。该系统利用 CUDA 编写的多相通道化器（polyphase channelizer）捕获整个航空频段，完成解调和传输检测。在当地突发地面停航（ground stop）事件期间，该工具被用于实时收听并记录相关空域的无线电通话。

hackernews · mmaunder · 11月13日 22:04 · [社区讨论](https://news.ycombinator.com/item?id=50490593)

**「背景」** 航空无线电频段（airband）通常采用模拟调幅（AM）通信，覆盖范围广且数据量大。通过软件定义无线电（SDR）结合 GPU 加速进行多通道并行处理，可以实现对整个频段的实时监听与信道分离。

**「影响」** 该项目展示了高性能 SDR 与 GPU 计算在实时空域监控中的实际应用价值，为开发者和航空爱好者提供了一种处理密集型射频信号的高效方案。

**「社区讨论」** 评论区讨论了该工具在突发地面停航期间捕捉到的具体管制通话记录。此外，有用户对航空无线电音频信号的嘈杂程度表示惊讶，并讨论了类似 SDR 项目在船舶 AIS 追踪等其他领域的应用潜力。

**标签**: `#software engineering`, `#hardware`, `#gpu computing`, `#cuda`, `#sdr`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [商务部长劳特尼克因英伟达关联面临审查](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

美国商务部长霍华德·劳特尼克因其家族企业坎托·菲茨杰拉德与英伟达的深厚业务联系而面临审查，此前有报道称其曾抵制对涉嫌向中国走私人工智能芯片的公司的打击行动。

rss · CNBC Finance · 11月13日 23:42

**「背景」** 在英伟达前首席执行官黄仁勋辞职及美国对先进半导体出口实施国家安全限制的背景下，劳特尼克因前家族企业的投资与英伟达融资交易而引发外界对其潜在利益冲突的质疑。

**标签**: `#Nvidia`, `#Howard Lutnick`, `#Semiconductors`, `#Geopolitics`, `#Regulation`

---