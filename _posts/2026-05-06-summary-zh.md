---
layout: default
title: "Horizon Summary: 2026-05-06 (ZH)"
date: 2026-05-06
lang: zh
---

> From 45 items, 18 important content pieces were selected

---

1. [GitHub 就故障致歉并披露 30 倍扩容计划](#item-1) ⭐️ 9.0/10
2. [SGLang v0.5.11 升级至 CUDA 13 并启用推测解码 V2](#item-2) ⭐️ 8.0/10
3. [Cloudflare 让 AI 代理自主创建账户、购买域名和部署](#item-3) ⭐️ 8.0/10
4. [DNSSEC 配置错误导致.de 域名中断](#item-4) ⭐️ 8.0/10
5. [Google Gemma 4 借助多令牌预测草稿器实现 3 倍推理加速](#item-5) ⭐️ 8.0/10
6. [人工智能的三条逆向法则：拟人、信任、责任](#item-6) ⭐️ 8.0/10
7. [Chrome 未经同意静默安装 4GB AI 模型](#item-7) ⭐️ 8.0/10
8. [作者担忧生物计算的伦理与技术缺陷](#item-8) ⭐️ 8.0/10
9. [Redis 数组游乐场：基于 WASM 的新数据类型交互工具](#item-9) ⭐️ 8.0/10
10. [图像模型拉动 AI 应用下载量增至对话模型更新的 6.5 倍](#item-10) ⭐️ 8.0/10
11. [DeepMind 英国员工投票组建工会抗议军事 AI 合同](#item-11) ⭐️ 8.0/10
12. [英国儿童轻易绕过在线安全法年龄验证](#item-12) ⭐️ 8.0/10
13. [OpenAI 发布 GPT-5.3 Instant，降低幻觉率](#item-13) ⭐️ 8.0/10
14. [微软 Edge 在内存中以明文保存所有密码](#item-14) ⭐️ 8.0/10
15. [Meta 计划推出 AI 助手对标 OpenClaw](#item-15) ⭐️ 8.0/10
16. [Anthropic 向谷歌云承诺 2000 亿美元支出](#item-16) ⭐️ 8.0/10
17. [苹果计划开放第三方 AI 模型选择](#item-17) ⭐️ 8.0/10
18. [DeepSeek 据称融资估值达 450 亿美元](#item-18) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [GitHub 就故障致歉并披露 30 倍扩容计划](https://github.blog/news-insights/company-news/an-update-on-github-availability/) ⭐️ 9.0/10

GitHub CTO Vlad Fedorov 因 2025 年 4 月发生的两次故障致歉，并宣布了一项 30 倍扩容计划，包括将性能敏感的代码从 Ruby 迁移至 Go，将 MySQL 负载移出，以及从自建数据中心迁移到 Azure 和多云架构。 这一声明表明 GitHub 在 AI 智能体工作流快速增长的背景下，对可靠性的严肃承诺。基础设施改造将直接影响数百万依赖 GitHub 进行代码托管和协作的开发者。 两起故障分别是：4 月 23 日的合并队列错误影响了 658 个仓库（squash merge 导致错误提交和意外还原代码，无数据丢失），以及 4 月 27 日的 Elasticsearch 集群过载导致搜索功能失效（Git 核心操作未受影响）。GitHub 还承诺提高透明度，在状态页添加可用性指标，并对所有故障发布事后分析报告。

telegram · zaihuapd · May 5, 11:42

**背景**: AI 智能体工作流是由自主或半自主 AI 代理执行的一系列任务，这些代理越来越多地与 GitHub 等平台交互进行代码操作，显著增加了 API 负载。Squash merge 是一种 Git 操作，它将特性分支的所有提交合并为目标分支上的一个提交，简化了历史记录，但如果配置不当可能存在信息丢失的风险。将 MySQL 负载移出可减少数据库争用，而迁移到 Go 相比 Ruby 能提升高吞吐量服务的性能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gooddata.ai/blog/ai-agent-workflows-everything-you-need-to-know/">AI Agent Workflows: Everything You Need to Know | GoodData</a></li>
<li><a href="https://graphite.com/guides/git-merge-squash">Git merge squash</a></li>

</ul>
</details>

**标签**: `#GitHub`, `#infrastructure`, `#scaling`, `#Go`, `#multicloud`

---

<a id="item-2"></a>
## [SGLang v0.5.11 升级至 CUDA 13 并启用推测解码 V2](https://github.com/sgl-project/sglang/releases/tag/v0.5.11) ⭐️ 8.0/10

SGLang v0.5.11 将 CUDA 升级至 13.0，PyTorch 升级至 2.11，默认启用推测解码 V2，为预填充-解码分离添加了解码 radix 缓存，并支持包括 Gemma 4 和 Qwen3.6 在内的新模型。 此版本显著现代化了 SGLang 的构建环境，并通过默认的推测解码 V2 和分离部署下更好的缓存机制提升了 LLM 推理性能，造福部署大型模型的开发者。 推测解码 V2 使用重叠调度来隐藏 CPU 开销，降低了 EAGLE、MTP 和 DFLASH 路径的每步成本。解码 radix 缓存恢复了预填充-解码分离下的命中率和首次令牌时间节省。新模型支持包括 Gemma 4、GLM-5.1、Qwen3.6 等。

github · Kangyan-Zhou · May 5, 21:28

**背景**: SGLang 是一个针对大语言模型优化的推理引擎，旨在实现高吞吐量和低延迟。推测解码通过使用草稿模型提出多个令牌，再由目标模型并行验证来加速生成。预填充-解码（PD）分离将预填充和解码阶段分配到不同的 GPU 实例，以独立调整首次令牌时间和令牌间延迟。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.sglang.io/advanced_features/speculative_decoding.html">Speculative Decoding — SGLang</a></li>
<li><a href="https://developer.nvidia.com/blog/an-introduction-to-speculative-decoding-for-reducing-latency-in-ai-inference/">An Introduction to Speculative Decoding for Reducing Latency in AI Inference | NVIDIA Technical Blog</a></li>
<li><a href="https://docs.vllm.ai/en/latest/features/disagg_prefill/">Disaggregated Prefilling (experimental) - vLLM</a></li>

</ul>
</details>

**标签**: `#LLM`, `#inference`, `#SGLang`, `#CUDA`, `#PyTorch`

---

<a id="item-3"></a>
## [Cloudflare 让 AI 代理自主创建账户、购买域名和部署](https://blog.cloudflare.com/agents-stripe-projects/) ⭐️ 8.0/10

Cloudflare 宣布，AI 代理现在可以自主创建 Cloudflare 账户、开始付费订阅、注册域名并获取 API 令牌以部署代码，整个过程无需人工干预，该功能使用了与 Stripe 共同设计的新协议。 此举使得完全自动化的代理驱动工作流成为可能，可能加速开发与部署，但也引发了重大的安全和欺诈担忧，因为代理现在可以执行真实的金融交易和资源分配。 该功能基于与 Stripe 共同开发的新供应协议，包含范围限定付款令牌和身份证明以确保安全。它还利用了近期宣布的 Cloudflare Registrar API 测试版，该 API 支持编程式域名注册。

hackernews · rolph · May 6, 03:10 · [社区讨论](https://news.ycombinator.com/item?id=48031684)

**背景**: AI 代理是能够自主执行任务的程序，通常通过 API 操作。此前，创建账户或购买域名等操作需要人工步骤。Cloudflare 的新功能允许代理直接执行这些操作，为构建代理驱动应用的开发者简化了流程。与 Stripe 的协议提供了一种安全的方式来处理支付和验证代理身份。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.infoworld.com/article/4165857/are-we-ready-to-give-ai-agents-the-keys-to-the-cloud-cloudflare-thinks-so.html">Are we ready to give AI agents the keys to the cloud? Cloudflare thinks so | InfoWorld</a></li>
<li><a href="https://blog.cloudflare.com/registrar-api-beta/">Register domains wherever you build: Cloudflare Registrar API now in beta</a></li>
<li><a href="https://ppc.land/cloudflare-lets-ai-agents-open-accounts-buy-domains-and-ship-code-no-human-required/">Cloudflare lets AI agents open accounts, buy domains, and ship code - no human required</a></li>

</ul>
</details>

**社区讨论**: 社区反应不一：一些人批评该功能是缺乏具体用例的玩具，而另一些人则强调潜在的欺诈风险，因为代理可能被用于自动化钓鱼诈骗。有评论者称其为“代理的 OAuth 时刻”，暗示它可能成为代理身份和支付的标准。

**标签**: `#AI agents`, `#Cloudflare`, `#automation`, `#domain registration`, `#developer tools`

---

<a id="item-4"></a>
## [DNSSEC 配置错误导致.de 域名中断](https://status.denic.de/pages/incident/592577eab611ce1e0d00046f/69fa60ef9d12f5057a974f38) ⭐️ 8.0/10

2025 年 1 月 16 日，.de 域名注册管理机构 DENIC 的 DNSSEC 配置错误导致所有.de 域名出现大面积解析失败。Cloudflare 临时在其 1.1.1.1 解析器上禁用了 DNSSEC 验证以缓解问题。 此事件影响了拥有数百万注册量的重要国家顶级域名（ccTLD）.de，凸显了 DNSSEC 部署的脆弱性。它展示了关键基础设施配置错误可能造成大范围破坏的潜在风险。 根本原因是对应 ZSK 密钥标签 33834 的 NSEC3 记录上的 RRSIG 签名格式错误，导致验证解析器返回 SERVFAIL 并附有扩展 DNS 错误代码。由于任播路由差异，用户观察到间歇性故障。

hackernews · warpspin · May 5, 20:16 · [社区讨论](https://news.ycombinator.com/item?id=48027897)

**背景**: DENIC 是.de 顶级域的注册管理机构，管理着超过 1700 万个域名的 DNS 基础设施。DNSSEC（域名系统安全扩展）为 DNS 记录添加加密签名，以防止欺骗和缓存投毒。验证解析器会检查这些签名并拒绝无效响应，因此当发布错误签名时导致了此次中断。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/DENIC">DENIC - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Domain_Name_System_Security_Extensions">Domain Name System Security Extensions - Wikipedia</a></li>
<li><a href="https://www.cloudflare.com/learning/dns/dnssec/how-dnssec-works/">How Does DNSSEC Work? | Cloudflare</a></li>

</ul>
</details>

**社区讨论**: 社区成员迅速识别出 DNSSEC 问题，指出非验证查询正常而验证查询失败。有人幽默地评论 DENIC 团队在聚会，另有人指出 Cloudflare 通过禁用 DNSSEC 验证来缓解。讨论还注意到 Thomas Ptacek 通常的 DNSSEC 批评言论这次缺席。

**标签**: `#DNSSEC`, `#DNS`, `#Network Incident`, `#.de`, `#DENIC`

---

<a id="item-5"></a>
## [Google Gemma 4 借助多令牌预测草稿器实现 3 倍推理加速](https://blog.google/innovation-and-ai/technology/developers-tools/multi-token-prediction-gemma-4/) ⭐️ 8.0/10

Google 发布了针对 Gemma 4 系列的多令牌预测（MTP）草稿器，在推理时将每秒令牌数提升高达 3 倍，且不损失质量。 这一创新显著降低了大型语言模型的延迟，使 Gemma 4 更适用于实时应用和本地部署，并展示了推测解码技术在生产中的有效性。 MTP 草稿器是一个轻量级模型，可并行预测多个未来令牌，而主 Gemma 4 模型在单次前向传播中验证它们，从而保持输出质量。加速效果在 Gemma 4 31B 模型上尤为显著。

hackernews · amrrs · May 5, 16:14 · [社区讨论](https://news.ycombinator.com/item?id=48024540)

**背景**: 自回归语言模型一次只能生成一个令牌，这限制了速度。推测解码是一种推理时优化技术，它使用较小的草稿模型提出令牌序列，然后由较大的目标模型并行验证。多令牌预测则更进一步，让草稿器一步预测多个令牌。该技术保留了原始模型的输出分布，因此质量不变，延迟降低约 2–3 倍。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/technology/developers-tools/multi-token-prediction-gemma-4/">Accelerating Gemma 4: faster inference with multi-token prediction drafters</a></li>
<li><a href="https://en.wikipedia.org/wiki/Speculative_decoding">Speculative decoding</a></li>
<li><a href="https://aitoolly.com/ai-news/article/2026-05-06-google-boosts-gemma-4-performance-multi-token-prediction-drafters-deliver-3x-faster-inference">Google Gemma 4 MTP Drafters: 3x Faster AI Inference Speed | AIToolly</a></li>

</ul>
</details>

**社区讨论**: 社区对推测解码技术反响热烈，许多人称赞这是一项巧妙的发明，能在零质量损失下实现更快的推理。用户还指出 Gemma 相比其他模型的令牌效率更高，并分享了正在为 llama.cpp 添加 MTP 支持以用于本地部署的工作。部分用户对在消费级硬件上同时运行主模型和草稿器的显存需求表达了担忧。

**标签**: `#inference acceleration`, `#multi-token prediction`, `#speculative decoding`, `#Gemma 4`, `#Google AI`

---

<a id="item-6"></a>
## [人工智能的三条逆向法则：拟人、信任、责任](https://susam.net/inverse-laws-of-robotics.html) ⭐️ 8.0/10

Susam Pal 提出人工智能的三条逆向法则：人类不得将 AI 拟人化、不得盲目信任 AI 的输出、不得将责任推卸给 AI 系统。 这一颇具争议的框架突显了人机交互中的关键伦理问题，并引发了社区关于此类规则可行性及影响的广泛讨论。 文章类比了阿西莫夫的机器人三定律，但将其颠倒，侧重于人类行为而非机器约束。强调拟人化会扭曲判断，甚至导致情感依赖。

hackernews · blenderob · May 5, 15:27 · [社区讨论](https://news.ycombinator.com/item?id=48023861)

**背景**: 阿西莫夫的机器人三定律是虚构的规则，旨在约束机器人行为以保护人类。本文提出逆向法则，针对人类与 AI 交互时的行为，认为当前 AI 系统（如 LLM）缺乏真正的理解和能动性。

**社区讨论**: 社区评论意见分歧：有人赞同这些规则，但认为人类天生就会将一切拟人化，使得这些法则不切实际；也有人不同意，认为人类必然会将 AI 拟人化、盲目信任并推卸责任，规则应围绕这种倾向进行工程设计，而非强加于人类。

**标签**: `#AI ethics`, `#anthropomorphism`, `#human-AI interaction`, `#AI safety`, `#discussion`

---

<a id="item-7"></a>
## [Chrome 未经同意静默安装 4GB AI 模型](https://www.thatprivacyguy.com/blog/chrome-silent-nano-install/) ⭐️ 8.0/10

Google Chrome 在未经用户明确同意的情况下，静默下载了一个 4 GB 的 Gemini Nano AI 模型，即使手动删除也会自动重新下载。 这引发了严重的隐私和资源使用问题，用户可能在不知情的情况下损失 4 GB 存储空间和带宽，而企业则面临巨大的磁盘空间和网络开销。该事件也进一步加剧了关于设备端 AI 时代同意与控制的广泛辩论。 该模型是 Gemini Nano 的权重文件，CPU 版本约 2.7 GB，GPU 版本约 4.0 GB。Chrome 会检查硬件兼容性并通过 'OnDeviceModelBackgroundDownload' 等标志启用下载，且没有任何面向用户的开关。

hackernews · john-doe · May 5, 07:34 · [社区讨论](https://news.ycombinator.com/item?id=48019219)

**背景**: Gemini Nano 是 Google 专为设备端设计的轻量级大语言模型，用于支持 Chrome 中的 Prompt API 等功能。历史上，软件更新可能包含新功能的后台下载，但未经同意安装数 GB 大小的模型前所未有。这种做法与用户对重大存储使用需明确同意的典型预期相悖。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.thatprivacyguy.com/blog/chrome-silent-nano-install/">Google Chrome silently installs a 4 GB AI model on your device without consent. At a billion-device scale the climate costs are insane. — That Privacy Guy!</a></li>
<li><a href="https://cybernews.com/security/google-chrome-ai-model-device-no-consent/">Guy finds Google Chrome is quietly installing a 4GB AI model on our devices</a></li>
<li><a href="https://tech.yahoo.com/ai/gemini/articles/google-chrome-silently-installs-4-164550734.html">Google Chrome Silently Installs a 4 GB AI Model On Your Device – Without Your Consent</a></li>

</ul>
</details>

**社区讨论**: 社区反应不一：有人认为该下载是 Chrome 正常更新的一部分，安装浏览器即表示同意；另一些人则强烈反对缺乏透明度以及自动重新下载的行为。企业用户指出这对共享存储和网络资源的重大影响，呼吁提供系统级安装选项。

**标签**: `#privacy`, `#google-chrome`, `#ai-model`, `#consent`, `#data-download`

---

<a id="item-8"></a>
## [作者担忧生物计算的伦理与技术缺陷](https://kuber.studio/blog/Reflections/I%27m-Scared-About-Biological-Computing) ⭐️ 8.0/10

一篇题为《我害怕生物计算》的博客引发了高度参与的讨论，提出了该领域的伦理和技术问题。社区评论指出作者对玩《毁灭战士》的神经元演示的解读存在不准确之处，并讨论了实验室培养神经元的意识问题。 此次讨论凸显了在生物计算发展过程中，公众准确理解和伦理框架的迫切需求。它也反映出人们对混合生物数字系统中的意识与利用问题日益增长的担忧。 作者引用的《毁灭战士》演示实际上在神经培养物外围使用了 PyTorch 封装，并非纯粹生物计算。评论者还引用了朱利安·巴吉尼关于吃肉伦理的思想实验，以及马克·索姆斯关于意识源自脑干而非仅由皮层神经元产生的理论。

hackernews · kuberwastaken · May 5, 16:03 · [社区讨论](https://news.ycombinator.com/item?id=48024358)

**背景**: 生物计算利用 DNA、蛋白质或活细胞等生物材料执行计算。最近的进展包括‘迷你大脑’——模拟大脑功能的三维脑组织培养物。该领域引发了关于使用生命系统以及实验室培养神经网络是否可能产生意识的伦理问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Biological_computing">Biological computing</a></li>
<li><a href="https://www.polytechnique-insights.com/en/columns/science/biocomputing-the-promise-of-biological-computingbrains/">Biocomputing: the promise of biological computing - Polytechnique Insights</a></li>

</ul>
</details>

**社区讨论**: 社区对文章的技术准确性持怀疑态度，尤其是关于《毁灭战士》演示的部分。评论者深入讨论了与素食主义、意识理论的伦理类比，以及生物计算的不可避免性。总体情绪是批评但建设性的，强调精确性和伦理反思的必要性。

**标签**: `#biological computing`, `#ethics`, `#AI`, `#neuroscience`, `#community discussion`

---

<a id="item-9"></a>
## [Redis 数组游乐场：基于 WASM 的新数据类型交互工具](https://simonwillison.net/2026/May/4/redis-array/#atom-everything) ⭐️ 8.0/10

Simon Willison 构建了一个基于浏览器的交互式游乐场，运行 WASM 编译的 Redis 子集，用于测试 Salvatore Sanfilippo 提交的新数组数据类型及其 18 个新命令。 该工具让 Redis 用户和开发者无需搭建自定义编译环境即可试验提议的数组类型，可能加速新数据结构的采纳和反馈。 游乐场包含所有新数组命令，如 ARGREP，它利用 TRE 正则表达式库进行服务器端模式匹配，并且使用 Claude Code for web 构建。

rss · Simon Willison · May 4, 15:53

**背景**: Redis 传统上支持字符串、列表、集合和哈希等数据类型。新的数组类型将提供有序、可索引的集合，操作类似于编程语言中的数组。该游乐场使用 WebAssembly (WASM) 在浏览器中直接运行轻量级 Redis 构建，允许无需服务器依赖即可进行动手测试。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://simonwillison.net/2026/May/4/redis-array/">Tool: Redis Array Playground</a></li>
<li><a href="https://redis.io/docs/latest/develop/data-types/">Redis data types | Docs</a></li>

</ul>
</details>

**标签**: `#Redis`, `#data structures`, `#WASM`, `#interactive tool`, `#open source`

---

<a id="item-10"></a>
## [图像模型拉动 AI 应用下载量增至对话模型更新的 6.5 倍](https://techcrunch.com/2026/05/04/image-ai-models-now-drive-app-growth-beating-chatbot-upgrades/) ⭐️ 8.0/10

根据 Appfigures 报告，新图像模型的发布使 AI 应用下载量达到传统模型更新的 6.5 倍。例如，Google 的 Gemini Nano Banana 在 28 天内获得超过 2200 万次下载，ChatGPT 的 GPT-4o 图像模型同期获得超过 1200 万次下载。 这一趋势表明图像生成能力正成为 AI 应用市场用户获取的关键驱动力，其吸引力已超越对话模型更新。然而，各平台在收入转化上的巨大差异凸显了持续变现这些功能面临的挑战。 在研究期间，只有 ChatGPT 的图像模型带来了约 7000 万美元的消费者支出，而 Gemini Nano Banana 仅贡献约 18.1 万美元，Meta AI 的 Vibes 视频功能则无实质营收。这表明下载成功并不能保证财务成功。

telegram · zaihuapd · May 5, 09:49

**背景**: 图像模型是一种能从文本提示生成或编辑图像的 AI 系统。Google 的 Nano Banana 是构建在 Gemini 上的先进图像生成模型，能将照片转化为定制的小型人物模型。Appfigures 是一个追踪下载量和收入的移动应用情报平台。将图像模型与对话模型发布进行对比，有助于洞察 AI 应用生态中用户偏好的演变。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepmind.google/models/gemini-image/">Gemini Image – Nano Banana — Google DeepMind</a></li>
<li><a href="https://gemini.google/overview/image-generation/">Nano Banana 2 - Gemini AI image generator & photo editor</a></li>

</ul>
</details>

**标签**: `#AI apps`, `#image models`, `#app downloads`, `#revenue`, `#chatbots`

---

<a id="item-11"></a>
## [DeepMind 英国员工投票组建工会抗议军事 AI 合同](https://www.theverge.com/tech/923918/google-deepmind-union-bid-ai-military-israel) ⭐️ 8.0/10

超过 1000 名 Google DeepMind 英国员工投票组建工会，抗议公司与美国国防部和以色列政府签署的军事 AI 合同。 此举凸显了顶级 AI 实验室员工对伦理问题的日益关注，可能为 AI 开发中由员工主导的治理开先河。 员工要求谷歌承诺不研发武器或监控技术，建立独立伦理监管机制，并赋予员工基于道德立场拒绝项目的权利。若诉求未获满足，他们计划通过暂停 Gemini 等核心产品的优化工作来进行‘研究罢工’。

telegram · zaihuapd · May 5, 12:36

**背景**: Google DeepMind 是一家顶尖 AI 研究实验室，以 AlphaGo 和 Gemini 等突破闻名。该公司此前曾因与以色列的 Project Nimbus 等军事合同面临员工抗议，导致 2024 年有 50 多名参与者被解雇。美国国防部最近确认与谷歌、OpenAI 等 AI 公司达成军事用途协议。

**标签**: `#AI ethics`, `#Google DeepMind`, `#unionization`, `#military AI`, `#corporate governance`

---

<a id="item-12"></a>
## [英国儿童轻易绕过在线安全法年龄验证](https://www.theregister.com/2026/05/04/uk_online_safety_act_age_checks_subvert/) ⭐️ 8.0/10

Internet Matters 的调查显示，46%的英国儿童认为年龄验证非常容易绕过，32%已成功绕过，方法包括画假胡子或使用游戏角色等简单手段。 这暴露了英国《在线安全法》年龄验证系统的根本缺陷，可能使其无法有效保护儿童免受有害内容侵害，同时凸显了更严格执法和主动安全设计的必要性。 调查还显示，49%的儿童近期仍在网上看到有害内容，17%的家长曾主动帮助孩子绕过年龄检查。这些数据凸显了当前验证方法的普遍失效。

telegram · zaihuapd · May 5, 14:16

**背景**: 英国《在线安全法》于 2023 年通过，要求平台实施年龄验证以保护未成年人免受有害内容侵害。然而，当前许多系统依赖自我声明或基础图像识别，容易被简单的视觉修改或虚假信息欺骗。

**标签**: `#online safety`, `#age verification`, `#UK Online Safety Act`, `#children`, `#technology policy`

---

<a id="item-13"></a>
## [OpenAI 发布 GPT-5.3 Instant，降低幻觉率](https://t.me/zaihuapd/41231) ⭐️ 8.0/10

OpenAI 发布了 GPT-5.3 Instant，这是对 ChatGPT 日常对话模型的更新，主要改进了减少不必要的拒绝回答、提升网络搜索结果质量，以及降低幻觉率。在启用网络搜索时，高风险领域的幻觉率最多降低 26.8%。 此次更新显著提升了 AI 安全性，在医疗、法律、金融等关键领域降低幻觉，使 AI 更可靠地用于专业场景。同时改进了拒绝回答处理方式和搜索结果质量，提升了用户体验。 内部评测显示，启用网络搜索时幻觉率降低 26.8%，仅依赖内部知识时降低 19.7%；基于用户反馈的评测中，两项数据分别为 22.5% 和 9.6%。GPT-5.3 Instant 即日起向所有 ChatGPT 用户推送。

telegram · zaihuapd · May 5, 17:06

**背景**: 幻觉是指 AI 生成虚假或无意义信息的情况。GPT-5.3 Instant 是一次模型更新，专注于减少此类错误，特别是在高风险场景中。该模型还改进了拒绝回答率和搜索结果质量，是在先前 GPT-5 版本基础上的改进。

**标签**: `#OpenAI`, `#GPT-5.3`, `#Hallucination Reduction`, `#AI Safety`, `#ChatGPT`

---

<a id="item-14"></a>
## [微软 Edge 在内存中以明文保存所有密码](https://cybernews.com/security/microsoft-edge-loads-cleartext-passwords-to-memory/) ⭐️ 8.0/10

安全研究员 Tom Jøran Sønstebyseter Rønning 发现，Microsoft Edge 在启动时将用户保存的所有密码解密并以明文加载到内存中，在整个会话期间保持明文，即使用户从未访问过相关网站。其他 Chromium 浏览器均未出现此行为。 这一漏洞允许具有管理员权限的攻击者从 Edge 进程内存中提取所有保存的密码，可能导致用户各种账户被入侵。这暴露了广泛使用的浏览器中一个严重的隐私风险。 微软回应称该行为是故意设计的，因此不会改变。与 Chrome 不同，Chrome 使用应用绑定加密，仅在需要时解密密码，而 Edge 在整个会话期间保持密码明文，可通过 Process Hacker 等工具访问。

telegram · zaihuapd · May 5, 23:31

**背景**: 现代浏览器提供密码管理器以方便用户存储凭据。通常，这些密码在磁盘上加密存储，仅在自动填充登录表单时才解密。Microsoft Edge 的做法则不同，它在启动时解密所有密码并保留在内存中，安全性较低，增加了被内存扫描攻击的风险。

**标签**: `#security`, `#browser`, `#passwords`, `#Microsoft Edge`, `#vulnerability`

---

<a id="item-15"></a>
## [Meta 计划推出 AI 助手对标 OpenClaw](https://www.ft.com/content/5b48360c-53f2-444a-80a8-f7034750fd62?syn-25a6b1a6=1) ⭐️ 8.0/10

Meta 正在开发一款由 Muse Spark 模型驱动的新 AI 助手，面向其超过 30 亿用户，计划与 OpenClaw 项目竞争。该助手目前正在内部测试，可以自动处理网页浏览、邮件和日历等任务。 这一举措使 Meta 成为 AI 助手市场的主要参与者，可能改变其平台上的用户体验。此举正值投资者对 Meta 高额 AI 资本支出施加压力之际，该公司今年将资本支出上调了 100 亿美元，最高至 1450 亿美元。 用户可以选择是否与助手共享健康、财务等敏感信息。该项目旨在让购物、网页浏览、邮件和日历管理等任务的代理体验更易于使用。

telegram · zaihuapd · May 6, 03:00

**背景**: AI 助手是一种软件代理，可根据命令或问题为用户执行任务或服务。Meta 一直在大力投资 AI，其资本支出大幅增加，引起了投资者的担忧。所提及的 OpenClaw 项目似乎不相关；网络搜索结果指向的是 Open Law，一个哈佛的法律项目，而非 AI 助手。这一差异表明新闻中可能存在名称错误。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Open_Law_project">Open Law project</a></li>

</ul>
</details>

**标签**: `#Meta`, `#AI Assistant`, `#OpenClaw`, `#Muse Spark`, `#Capital Expenditure`

---

<a id="item-16"></a>
## [Anthropic 向谷歌云承诺 2000 亿美元支出](https://www.theinformation.com/articles/anthropic-commits-spending-200-billion-googles-cloud-chips?utm_source=chatgpt.com) ⭐️ 8.0/10

Anthropic 已承诺未来五年向谷歌云支付 2000 亿美元用于 AI 计算。同时，Alphabet 计划以 3500 亿美元估值向 Anthropic 投资最多 400 亿美元。 这笔巨额交易凸显了训练和部署先进 AI 模型所需的巨大资本投入，并巩固了 Anthropic 与谷歌的深度合作关系，可能重塑云 AI 格局。 这笔 2000 亿美元的承诺占谷歌云已披露积压订单的 40% 以上。此外，Anthropic 和谷歌与博通签署协议，锁定数吉瓦的 TPU 算力，预计从 2027 年起陆续上线。

telegram · zaihuapd · May 6, 03:53

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Google_Translate">Google Translate</a></li>

</ul>
</details>

**标签**: `#Anthropic`, `#Google Cloud`, `#AI infrastructure`, `#business deal`

---

<a id="item-17"></a>
## [苹果计划开放第三方 AI 模型选择](https://www.bloomberg.com/news/articles/2026-05-05/ios-27-features-apple-plans-to-let-users-swap-models-across-apple-intelligence) ⭐️ 8.0/10

苹果计划在 iOS 27、iPadOS 27 和 macOS 27 中允许用户选择第三方 AI 模型，例如谷歌和 Anthropic 的模型，从而打破 ChatGPT 在 Apple Intelligence 中的独家集成地位。 这标志着苹果的重大战略转向，将其设备转变为可切换模型的 AI 平台，可能重塑 AI 生态并加剧竞争。 该功能内部名为“Extensions”，用户可在设置中选择 AI 服务，用于 Siri、写作工具和 Image Playground，苹果仍继续提供自研模型。

telegram · zaihuapd · May 6, 05:38

**背景**: Apple Intelligence 是苹果在 WWDC 2024 上宣布的生成式 AI 系统，集成于 iOS 18、iPadOS 18 和 macOS Sequoia。它最初独家集成了 ChatGPT，并依赖设备端和服务器处理。目前，Apple Intelligence 在中国大陆不可用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Apple_Intelligence">Apple Intelligence</a></li>

</ul>
</details>

**标签**: `#苹果`, `#AI模型`, `#第三方集成`, `#iOS`, `#战略更新`

---

<a id="item-18"></a>
## [DeepSeek 据称融资估值达 450 亿美元](https://www.bloomberg.com/news/articles/2026-05-06/china-chip-fund-in-talks-to-lead-mega-deepseek-funding-ft-says) ⭐️ 8.0/10

中国国家集成电路产业投资基金据称正洽谈领投 DeepSeek 首轮外部融资，该轮融资对 DeepSeek 的估值可能达到约 450 亿美元。 这将是 DeepSeek 首次进行大规模外部融资，标志着国资背景资金更深入地介入中国 AI 核心领域，并可能重塑与 OpenAI 等全球玩家的竞争格局。 此轮融资由国家大基金（国家集成电路产业投资基金）领投，约 450 亿美元的估值对于一家此前仅由其创始人所在的对冲基金 High-Flyer 资助的公司来说相当可观。

telegram · zaihuapd · May 6, 06:28

**背景**: DeepSeek 成立于 2023 年，由梁文锋创立，是一家以开发高性价比大语言模型（如 DeepSeek-R1 和 V3）而闻名的中国 AI 公司。2025 年 1 月，其 R1 模型以远低于 OpenAI GPT-4 的训练成本（利用受美国出口限制的较弱芯片）达到相近性能，引起全球关注。DeepSeek 的开源权重模型因其高效而备受赞誉，并曾引发市场动荡，例如 Nvidia 市值一度暴跌 6000 亿美元。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/DeepSeek_(Company)">DeepSeek (Company)</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#funding`, `#AI`, `#China`, `#semiconductor`

---