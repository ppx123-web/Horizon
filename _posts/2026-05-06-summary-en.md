---
layout: default
title: "Horizon Summary: 2026-05-06 (EN)"
date: 2026-05-06
lang: en
---

> From 45 items, 18 important content pieces were selected

---

1. [GitHub apologizes for outages, reveals 30x scaling plan](#item-1) ⭐️ 9.0/10
2. [SGLang v0.5.11 Upgrades to CUDA 13 and Enables Speculative Decoding V2](#item-2) ⭐️ 8.0/10
3. [Cloudflare lets AI agents create accounts, buy domains, deploy autonomously](#item-3) ⭐️ 8.0/10
4. [DNSSEC Misconfiguration Disrupts .de Domains](#item-4) ⭐️ 8.0/10
5. [Google Gemma 4 Gets 3x Faster Inference with MTP Drafters](#item-5) ⭐️ 8.0/10
6. [Three Inverse Laws of AI: Anthropomorphism, Trust, Responsibility](#item-6) ⭐️ 8.0/10
7. [Chrome Silently Installs 4GB AI Model Without Consent](#item-7) ⭐️ 8.0/10
8. [Author Fears Biological Computing's Ethical and Technical Gaps](#item-8) ⭐️ 8.0/10
9. [Redis Array Playground: Interactive WASM-Based Tool for New Data Type](#item-9) ⭐️ 8.0/10
10. [Image Models Drive 6.5x More AI App Downloads Than Chatbot Updates](#item-10) ⭐️ 8.0/10
11. [Google DeepMind UK Staff Vote to Unionize Over Military AI Contracts](#item-11) ⭐️ 8.0/10
12. [UK children easily bypass Online Safety Act age checks](#item-12) ⭐️ 8.0/10
13. [OpenAI Releases GPT-5.3 Instant with Reduced Hallucinations](#item-13) ⭐️ 8.0/10
14. [Microsoft Edge Exposes All Saved Passwords in Memory](#item-14) ⭐️ 8.0/10
15. [Meta Plans AI Assistant to Compete with OpenClaw](#item-15) ⭐️ 8.0/10
16. [Anthropic Commits $200 Billion to Google Cloud](#item-16) ⭐️ 8.0/10
17. [Apple Plans to Open Third-Party AI Model Selection](#item-17) ⭐️ 8.0/10
18. [DeepSeek reportedly valued at $45B in funding round](#item-18) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [GitHub apologizes for outages, reveals 30x scaling plan](https://github.blog/news-insights/company-news/an-update-on-github-availability/) ⭐️ 9.0/10

GitHub CTO Vlad Fedorov apologized for two outages in April 2025 and announced a 30x scaling plan that includes migrating performance-critical code from Ruby to Go, offloading MySQL workloads, and moving from custom data centers to Azure and a multicloud architecture. This announcement signals GitHub's serious commitment to reliability amid rapidly growing AI agent workflows, which are driving unprecedented load. The infrastructure overhaul will directly impact millions of developers who depend on GitHub for code hosting and collaboration. The two incidents were a merge queue bug on April 23 affecting 658 repositories (squash merge caused erroneous commits and unintentional code reverts, no data loss) and an Elasticsearch cluster overload on April 27 that took down search results (core Git operations unaffected). GitHub also promised better transparency by adding availability metrics to its status page and committing to postmortems for all outages.

telegram · zaihuapd · May 5, 11:42

**Background**: AI agent workflows are sequences of tasks executed by autonomous or semi-autonomous AI agents, which increasingly interact with platforms like GitHub for code operations, dramatically increasing API load. Squash merge is a Git operation that combines all commits from a feature branch into a single commit on the target branch, simplifying history but risking information loss if misconfigured. Offloading MySQL reduces database contention, while migrating to Go improves performance compared to Ruby for high-throughput services.

<details><summary>References</summary>
<ul>
<li><a href="https://www.gooddata.ai/blog/ai-agent-workflows-everything-you-need-to-know/">AI Agent Workflows: Everything You Need to Know | GoodData</a></li>
<li><a href="https://graphite.com/guides/git-merge-squash">Git merge squash</a></li>

</ul>
</details>

**Tags**: `#GitHub`, `#infrastructure`, `#scaling`, `#Go`, `#multicloud`

---

<a id="item-2"></a>
## [SGLang v0.5.11 Upgrades to CUDA 13 and Enables Speculative Decoding V2](https://github.com/sgl-project/sglang/releases/tag/v0.5.11) ⭐️ 8.0/10

SGLang v0.5.11 upgrades CUDA to 13.0 and PyTorch to 2.11, enables speculative decoding V2 by default, adds decode radix cache for prefill-decode disaggregation, and supports new models including Gemma 4 and Qwen3.6. This release significantly modernizes the SGLang build environment and improves LLM inference performance through default speculative decoding V2 and better caching under disaggregated deployments, benefiting developers deploying large models. Speculative decoding V2 uses overlap scheduling to hide CPU overhead, reducing per-step cost for EAGLE, MTP, and DFLASH paths. The decode radix cache recovers hit rates and time-to-first-token savings under prefill-decode disaggregation. New model support includes Gemma 4, GLM-5.1, Qwen3.6, and more.

github · Kangyan-Zhou · May 5, 21:28

**Background**: SGLang is an inference engine for large language models optimized for high throughput and low latency. Speculative decoding accelerates generation by using a draft model to propose multiple tokens that a target model verifies in parallel. Prefill-decode (PD) disaggregation separates the prefill and decode phases into different GPU instances to tune time-to-first-token and inter-token latency independently.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.sglang.io/advanced_features/speculative_decoding.html">Speculative Decoding — SGLang</a></li>
<li><a href="https://developer.nvidia.com/blog/an-introduction-to-speculative-decoding-for-reducing-latency-in-ai-inference/">An Introduction to Speculative Decoding for Reducing Latency in AI Inference | NVIDIA Technical Blog</a></li>
<li><a href="https://docs.vllm.ai/en/latest/features/disagg_prefill/">Disaggregated Prefilling (experimental) - vLLM</a></li>

</ul>
</details>

**Tags**: `#LLM`, `#inference`, `#SGLang`, `#CUDA`, `#PyTorch`

---

<a id="item-3"></a>
## [Cloudflare lets AI agents create accounts, buy domains, deploy autonomously](https://blog.cloudflare.com/agents-stripe-projects/) ⭐️ 8.0/10

Cloudflare has announced that AI agents can now autonomously create Cloudflare accounts, begin paid subscriptions, register domains, and receive API tokens to deploy code, all without human intervention, using a new protocol co-designed with Stripe. This move enables fully automated agent-driven workflows, potentially accelerating development and deployment, but also raises significant security and fraud concerns, as agents can now perform real-world financial transactions and resource provisioning. The feature is built on a new provisioning protocol co-developed with Stripe, incorporating scoped payment tokens and identity attestation to ensure security. It also leverages the recently announced beta of Cloudflare's Registrar API, which enables programmatic domain registration.

hackernews · rolph · May 6, 03:10 · [Discussion](https://news.ycombinator.com/item?id=48031684)

**Background**: AI agents are programs that can perform tasks autonomously, often using APIs. Previously, actions like creating accounts or buying domains required manual human steps. Cloudflare's new feature allows agents to perform these actions directly, streamlining the process for developers building agent-driven applications. The protocol with Stripe provides a secure way to handle payments and verify agent identity.

<details><summary>References</summary>
<ul>
<li><a href="https://www.infoworld.com/article/4165857/are-we-ready-to-give-ai-agents-the-keys-to-the-cloud-cloudflare-thinks-so.html">Are we ready to give AI agents the keys to the cloud? Cloudflare thinks so | InfoWorld</a></li>
<li><a href="https://blog.cloudflare.com/registrar-api-beta/">Register domains wherever you build: Cloudflare Registrar API now in beta</a></li>
<li><a href="https://ppc.land/cloudflare-lets-ai-agents-open-accounts-buy-domains-and-ship-code-no-human-required/">Cloudflare lets AI agents open accounts, buy domains, and ship code - no human required</a></li>

</ul>
</details>

**Discussion**: Community reactions are mixed: some criticize the feature as a toy lacking concrete use cases, while others highlight potential for fraud, as agents could be used for automated phishing scams. One commenter called it an 'OAuth moment for agents,' suggesting it could become a standard for agent identity and payments.

**Tags**: `#AI agents`, `#Cloudflare`, `#automation`, `#domain registration`, `#developer tools`

---

<a id="item-4"></a>
## [DNSSEC Misconfiguration Disrupts .de Domains](https://status.denic.de/pages/incident/592577eab611ce1e0d00046f/69fa60ef9d12f5057a974f38) ⭐️ 8.0/10

A DNSSEC misconfiguration at DENIC, the .de registry, caused widespread resolution failures for all .de domains on January 16, 2025. Cloudflare temporarily disabled DNSSEC validation on its 1.1.1.1 resolver to mitigate the issue. This incident affected all .de domains, a major country-code top-level domain (ccTLD) with millions of registrations, highlighting the fragility of DNSSEC deployment. It demonstrates the potential for widespread disruption when critical infrastructure misconfigurations occur. The root cause was a malformed RRSIG over an NSEC3 record that failed validation against ZSK key tag 33834, causing validating resolvers to return SERVFAIL with extended DNS error code. Intermittency was observed due to anycast routing variations.

hackernews · warpspin · May 5, 20:16 · [Discussion](https://news.ycombinator.com/item?id=48027897)

**Background**: DENIC is the registry and operator of the .de top-level domain, managing DNS infrastructure for over 17 million domains. DNSSEC (Domain Name System Security Extensions) adds cryptographic signatures to DNS records to prevent spoofing and cache poisoning. Validating resolvers check these signatures and reject invalid responses, which caused the outage when a bad signature was published.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/DENIC">DENIC - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Domain_Name_System_Security_Extensions">Domain Name System Security Extensions - Wikipedia</a></li>
<li><a href="https://www.cloudflare.com/learning/dns/dnssec/how-dnssec-works/">How Does DNSSEC Work? | Cloudflare</a></li>

</ul>
</details>

**Discussion**: Community members identified the DNSSEC issue quickly, noting that non-validating queries worked while validating ones failed. Some commented humorously about DENIC's team partying, and others pointed out Cloudflare's mitigation by disabling DNSSEC validation. The discussion also highlighted the absence of the usual DNSSEC skepticism from Thomas Ptacek.

**Tags**: `#DNSSEC`, `#DNS`, `#Network Incident`, `#.de`, `#DENIC`

---

<a id="item-5"></a>
## [Google Gemma 4 Gets 3x Faster Inference with MTP Drafters](https://blog.google/innovation-and-ai/technology/developers-tools/multi-token-prediction-gemma-4/) ⭐️ 8.0/10

Google has released Multi-Token Prediction (MTP) drafters for the Gemma 4 family, enabling up to a 3x speedup in tokens-per-second during inference without quality loss. This innovation significantly reduces latency for large language models, making Gemma 4 more practical for real-time applications and local deployment, and it demonstrates the effectiveness of speculative decoding techniques in production. The MTP drafter is a lightweight model that predicts multiple future tokens in parallel, while the main Gemma 4 model verifies them in a single forward pass, preserving output quality. The speedup is particularly notable for the Gemma 4 31B model.

hackernews · amrrs · May 5, 16:14 · [Discussion](https://news.ycombinator.com/item?id=48024540)

**Background**: Autoregressive language models generate one token at a time, which limits speed. Speculative decoding, an inference-time optimization, uses a smaller draft model to propose a sequence of tokens, and the larger target model verifies them in parallel. Multi-token prediction takes this further by having the drafter predict multiple tokens in one step. This technique retains the original model's output distribution, so quality is unchanged while latency drops by roughly 2–3 times.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/technology/developers-tools/multi-token-prediction-gemma-4/">Accelerating Gemma 4: faster inference with multi-token prediction drafters</a></li>
<li><a href="https://en.wikipedia.org/wiki/Speculative_decoding">Speculative decoding</a></li>
<li><a href="https://aitoolly.com/ai-news/article/2026-05-06-google-boosts-gemma-4-performance-multi-token-prediction-drafters-deliver-3x-faster-inference">Google Gemma 4 MTP Drafters: 3x Faster AI Inference Speed | AIToolly</a></li>

</ul>
</details>

**Discussion**: The community is enthusiastic about speculative decoding, with many calling it a clever technique that offers faster inference with zero quality degradation. Users also note Gemma's token efficiency compared to other models and share ongoing work to add MTP support to llama.cpp for local deployment. Some express concerns about VRAM requirements for running both the main model and drafter on consumer hardware.

**Tags**: `#inference acceleration`, `#multi-token prediction`, `#speculative decoding`, `#Gemma 4`, `#Google AI`

---

<a id="item-6"></a>
## [Three Inverse Laws of AI: Anthropomorphism, Trust, Responsibility](https://susam.net/inverse-laws-of-robotics.html) ⭐️ 8.0/10

Susam Pal proposes three inverse laws of AI: humans must not anthropomorphize AI, must not blindly trust AI outputs, and must not defer responsibility to AI systems. This provocative framing highlights critical ethical issues in human-AI interaction and has sparked substantial community debate about the feasibility and implications of such rules. The article draws an analogy to Asimov's Three Laws of Robotics, but inverts them to focus on human behavior rather than machine constraints. It emphasizes that anthropomorphism distorts judgment and can lead to emotional dependence.

hackernews · blenderob · May 5, 15:27 · [Discussion](https://news.ycombinator.com/item?id=48023861)

**Background**: Asimov's Three Laws of Robotics are fictional rules intended to constrain robot behavior to protect humans. This article proposes inverse laws targeting human conduct when interacting with AI, arguing that current AI systems like LLMs lack true understanding and agency.

**Discussion**: Community comments are divided: some agree with the rules but argue that humans inherently anthropomorphize everything, making the laws unrealistic. Others disagree, stating that humans will inevitably anthropomorphize, trust blindly, and defer responsibility, and that rules should be engineered around this tendency rather than imposed on humans.

**Tags**: `#AI ethics`, `#anthropomorphism`, `#human-AI interaction`, `#AI safety`, `#discussion`

---

<a id="item-7"></a>
## [Chrome Silently Installs 4GB AI Model Without Consent](https://www.thatprivacyguy.com/blog/chrome-silent-nano-install/) ⭐️ 8.0/10

Google Chrome has been silently downloading a 4 GB Gemini Nano AI model onto users' devices without explicit consent, automatically re-downloading it even if manually deleted. This raises serious privacy and resource usage concerns, as users may lose 4 GB of storage and bandwidth without notification, and enterprises face significant disk space and network overhead. The incident also fuels broader debates about consent and control in the age of on-device AI. The model is Gemini Nano's weights, approximately 2.7 GB for CPU and 4.0 GB for GPU versions. Chrome checks hardware eligibility and enables download via flags like 'OnDeviceModelBackgroundDownload' without any user-facing toggle.

hackernews · john-doe · May 5, 07:34 · [Discussion](https://news.ycombinator.com/item?id=48019219)

**Background**: Gemini Nano is Google's lightweight on-device large language model designed for features like the Prompt API in Chrome. Historically, software updates may include background downloads for new features, but a multi-gigabyte model installation without consent is unprecedented. This practice contrasts with typical user expectations of explicit consent for significant storage usage.

<details><summary>References</summary>
<ul>
<li><a href="https://www.thatprivacyguy.com/blog/chrome-silent-nano-install/">Google Chrome silently installs a 4 GB AI model on your device without consent. At a billion-device scale the climate costs are insane. — That Privacy Guy!</a></li>
<li><a href="https://cybernews.com/security/google-chrome-ai-model-device-no-consent/">Guy finds Google Chrome is quietly installing a 4GB AI model on our devices</a></li>
<li><a href="https://tech.yahoo.com/ai/gemini/articles/google-chrome-silently-installs-4-164550734.html">Google Chrome Silently Installs a 4 GB AI Model On Your Device – Without Your Consent</a></li>

</ul>
</details>

**Discussion**: Community reactions are divided: some argue the download is part of Chrome's normal updates and consent is already given by installing the browser, while others strongly object to the lack of transparency and the automatic re-download. Enterprise users highlight the significant impact on shared storage and network resources, calling for system-wide installation options.

**Tags**: `#privacy`, `#google-chrome`, `#ai-model`, `#consent`, `#data-download`

---

<a id="item-8"></a>
## [Author Fears Biological Computing's Ethical and Technical Gaps](https://kuber.studio/blog/Reflections/I%27m-Scared-About-Biological-Computing) ⭐️ 8.0/10

A blog post titled 'I'm scared about biological computing' has sparked a high-engagement discussion, raising ethical and technical concerns about the field. Community comments highlight inaccuracies in the author's interpretation of a Doom-playing neuron demo and debate consciousness in lab-grown neurons. This discussion underscores the urgent need for accurate public understanding and ethical frameworks as biological computing advances. It also reflects growing unease about consciousness and exploitation in hybrid biological-digital systems. The Doom demo referenced by the author actually used a PyTorch wrapper around neural cultures, not purely biological computation. Commenters also cite Julian Baggini's ethical thought experiment on eating meat and Mark Solms' theory that consciousness stems from the brainstem, not cortical neurons alone.

hackernews · kuberwastaken · May 5, 16:03 · [Discussion](https://news.ycombinator.com/item?id=48024358)

**Background**: Biological computing (biocomputing) uses biological materials like DNA, proteins, or living cells to perform computations. Recent advances include 'mini-brains' — 3D cultures of brain tissue that mimic brain functions. The field raises ethical questions about the use of living systems and the potential for consciousness in lab-grown neural networks.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Biological_computing">Biological computing</a></li>
<li><a href="https://www.polytechnique-insights.com/en/columns/science/biocomputing-the-promise-of-biological-computingbrains/">Biocomputing: the promise of biological computing - Polytechnique Insights</a></li>

</ul>
</details>

**Discussion**: The community is skeptical of the article's technical accuracy, especially regarding the Doom demo. Commenters engage deeply with ethical parallels to veganism, consciousness theories, and the inevitability of biological computing. Overall sentiment is critical yet constructive, emphasizing the need for precision and ethical reflection.

**Tags**: `#biological computing`, `#ethics`, `#AI`, `#neuroscience`, `#community discussion`

---

<a id="item-9"></a>
## [Redis Array Playground: Interactive WASM-Based Tool for New Data Type](https://simonwillison.net/2026/May/4/redis-array/#atom-everything) ⭐️ 8.0/10

Simon Willison built an interactive browser-based playground that runs a WASM-compiled subset of Redis to test Salvatore Sanfilippo's new array data type and its 18 new commands. This tool allows Redis users and developers to experiment with the proposed array type without setting up a custom build, potentially accelerating adoption and feedback for the new data structure. The playground includes all new array commands like ARGREP, which leverages the TRE regex library for server-side pattern matching, and is built using Claude Code for web.

rss · Simon Willison · May 4, 15:53

**Background**: Redis traditionally supports data types like strings, lists, sets, and hashes. A new array type would provide ordered, indexable collections with operations similar to arrays in programming languages. The playground uses WebAssembly (WASM) to run a lightweight Redis build directly in the browser, enabling hands-on testing without server dependencies.

<details><summary>References</summary>
<ul>
<li><a href="https://simonwillison.net/2026/May/4/redis-array/">Tool: Redis Array Playground</a></li>
<li><a href="https://redis.io/docs/latest/develop/data-types/">Redis data types | Docs</a></li>

</ul>
</details>

**Tags**: `#Redis`, `#data structures`, `#WASM`, `#interactive tool`, `#open source`

---

<a id="item-10"></a>
## [Image Models Drive 6.5x More AI App Downloads Than Chatbot Updates](https://techcrunch.com/2026/05/04/image-ai-models-now-drive-app-growth-beating-chatbot-upgrades/) ⭐️ 8.0/10

According to an Appfigures report, the release of new image models has driven AI app downloads 6.5 times more than traditional model updates. For instance, Google's Gemini Nano Banana gained over 22 million downloads in 28 days, and ChatGPT's GPT-4o image model gained over 12 million downloads during the same period. This trend signifies that image generation capabilities are becoming a key driver for user acquisition in the AI app market, surpassing the appeal of conversational upgrades. However, the disparity in revenue conversion across platforms highlights the challenge of monetizing these features consistently. During the period studied, only ChatGPT's image model generated approximately $70 million in consumer spending, while Gemini Nano Banana contributed only about $181,000, and Meta AI's Vibes video feature produced no substantial revenue. This shows that download success does not guarantee financial success.

telegram · zaihuapd · May 5, 09:49

**Background**: Image models are AI systems that generate or edit images from text prompts. Google's Nano Banana is a state-of-the-art image generation model built on Gemini, capable of turning photos into custom miniature figurines. Appfigures is a mobile app intelligence platform that tracks downloads and revenue. The comparison between image model and chatbot model releases provides insight into evolving user preferences in the AI app ecosystem.

<details><summary>References</summary>
<ul>
<li><a href="https://deepmind.google/models/gemini-image/">Gemini Image – Nano Banana — Google DeepMind</a></li>
<li><a href="https://gemini.google/overview/image-generation/">Nano Banana 2 - Gemini AI image generator & photo editor</a></li>

</ul>
</details>

**Tags**: `#AI apps`, `#image models`, `#app downloads`, `#revenue`, `#chatbots`

---

<a id="item-11"></a>
## [Google DeepMind UK Staff Vote to Unionize Over Military AI Contracts](https://www.theverge.com/tech/923918/google-deepmind-union-bid-ai-military-israel) ⭐️ 8.0/10

Over 1,000 Google DeepMind employees in the UK have voted to form a union to protest the company's military AI contracts with the US Department of Defense and the Israeli government. This move highlights growing employee activism at a leading AI lab over ethical concerns, potentially setting a precedent for worker-led governance in AI development. Employees are demanding Google commit to not developing weapons or surveillance technology, establish independent ethics oversight, and grant workers the right to refuse projects based on moral grounds. If demands are unmet, they plan a 'research strike' by halting optimization of core products like Gemini.

telegram · zaihuapd · May 5, 12:36

**Background**: Google DeepMind is a leading AI research lab known for breakthroughs like AlphaGo and Gemini. The company has faced previous employee protests over military contracts, including Project Nimbus with Israel, which led to the firing of over 50 participants in 2024. The US Department of Defense recently confirmed agreements with Google, OpenAI, and other AI companies for military use.

**Tags**: `#AI ethics`, `#Google DeepMind`, `#unionization`, `#military AI`, `#corporate governance`

---

<a id="item-12"></a>
## [UK children easily bypass Online Safety Act age checks](https://www.theregister.com/2026/05/04/uk_online_safety_act_age_checks_subvert/) ⭐️ 8.0/10

A survey by Internet Matters found that 46% of UK children consider age verification very easy to bypass, and 32% have successfully done so using simple tricks like drawing fake mustaches or using game avatars. This exposes a critical flaw in the UK Online Safety Act's age verification system, potentially rendering it ineffective in protecting children from harmful content. It also highlights the need for stronger enforcement and proactive safety-by-design approaches. The survey also reported that 49% of children have recently encountered harmful content online, and 17% of parents have actively helped their children bypass age checks. These figures underscore the widespread failure of current verification methods.

telegram · zaihuapd · May 5, 14:16

**Background**: The UK Online Safety Act, passed in 2023, requires platforms to implement age verification to protect minors from harmful content. However, many current systems rely on self-declaration or basic image recognition, which are easily tricked by simple visual alterations or false information.

**Tags**: `#online safety`, `#age verification`, `#UK Online Safety Act`, `#children`, `#technology policy`

---

<a id="item-13"></a>
## [OpenAI Releases GPT-5.3 Instant with Reduced Hallucinations](https://t.me/zaihuapd/41231) ⭐️ 8.0/10

OpenAI has released GPT-5.3 Instant, an update to ChatGPT's daily conversation model, featuring reduced refusal rates, improved web search results, and a hallucination reduction of up to 26.8% in high-risk domains when using web search. This update significantly improves AI safety by reducing hallucinations in critical fields like medicine, law, and finance, making AI more reliable for professional use. It also enhances user experience through better refusal handling and search result quality. Internal evaluations show a 26.8% reduction in hallucination rates with web search enabled and 19.7% without; user-feedback evaluations show 22.5% and 9.6% reductions respectively. GPT-5.3 Instant is rolling out immediately to all ChatGPT users.

telegram · zaihuapd · May 5, 17:06

**Background**: Hallucinations are instances where AI generates false or nonsensical information. GPT-5.3 Instant is a model update focused on reducing such errors, especially in high-stakes scenarios. The model also improves refusal rates and search result quality, building on earlier GPT-5 iterations.

**Tags**: `#OpenAI`, `#GPT-5.3`, `#Hallucination Reduction`, `#AI Safety`, `#ChatGPT`

---

<a id="item-14"></a>
## [Microsoft Edge Exposes All Saved Passwords in Memory](https://cybernews.com/security/microsoft-edge-loads-cleartext-passwords-to-memory/) ⭐️ 8.0/10

Security researcher Tom Jøran Sønstebyseter Rønning discovered that Microsoft Edge decrypts all saved passwords and stores them in cleartext memory for the entire session, even if the user never visits the associated websites. This behavior is not present in other Chromium browsers tested. This vulnerability allows an attacker with administrative access to extract all saved passwords from Edge's process memory, potentially compromising user accounts across services. It highlights a significant privacy risk in one of the most widely used browsers. Microsoft responded that the behavior is by design, meaning it will not be changed. Unlike Chrome, which uses application-bound encryption and only decrypts passwords when needed, Edge keeps passwords in plaintext throughout the session, accessible via tools like Process Hacker.

telegram · zaihuapd · May 5, 23:31

**Background**: Modern browsers offer password managers that store user credentials for convenience. Typically, these passwords are stored encrypted on disk and decrypted only when needed to autofill login forms. Microsoft Edge's approach deviates by decrypting all passwords at startup and keeping them in memory, which is less secure and increases exposure to memory-scanning attacks.

**Tags**: `#security`, `#browser`, `#passwords`, `#Microsoft Edge`, `#vulnerability`

---

<a id="item-15"></a>
## [Meta Plans AI Assistant to Compete with OpenClaw](https://www.ft.com/content/5b48360c-53f2-444a-80a8-f7034750fd62?syn-25a6b1a6=1) ⭐️ 8.0/10

Meta is developing a new AI assistant powered by the Muse Spark model, targeting its over 3 billion users, and plans to compete with the OpenClaw project. The assistant is currently in internal testing and can automate web browsing, email, and calendar tasks. This move positions Meta as a major player in the AI assistant market, potentially transforming user experience across its platforms. It comes amid investor pressure over Meta's high AI capital expenditure, which was raised by $10 billion to up to $145 billion for this year. Users can choose whether to share sensitive information like health and financial data with the assistant. The project aims to make agent-like experiences for tasks such as shopping, web browsing, email, and calendar management more accessible.

telegram · zaihuapd · May 6, 03:00

**Background**: AI assistants are software agents that perform tasks or services for users based on commands or questions. Meta has been investing heavily in AI, with its capital expenditure rising significantly, causing investor concern. The referenced OpenClaw project appears to be unrelated; web search results point to Open Law, a legal project at Harvard, not an AI assistant. This discrepancy suggests the news may contain a naming error.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Open_Law_project">Open Law project</a></li>

</ul>
</details>

**Tags**: `#Meta`, `#AI Assistant`, `#OpenClaw`, `#Muse Spark`, `#Capital Expenditure`

---

<a id="item-16"></a>
## [Anthropic Commits $200 Billion to Google Cloud](https://www.theinformation.com/articles/anthropic-commits-spending-200-billion-googles-cloud-chips?utm_source=chatgpt.com) ⭐️ 8.0/10

Anthropic has committed to spending $200 billion on Google Cloud over five years for AI compute. Additionally, Alphabet plans to invest up to $40 billion in Anthropic at a $350 billion valuation. This massive deal underscores the enormous capital requirements for training and deploying advanced AI models, and solidifies the deep partnership between Anthropic and Google, potentially reshaping the cloud AI landscape. The $200 billion commitment represents over 40% of Google Cloud's reported backlog. Additionally, Anthropic and Google signed a deal with Broadcom to secure gigawatts of TPU compute capacity starting in 2027.

telegram · zaihuapd · May 6, 03:53

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Google_Translate">Google Translate</a></li>

</ul>
</details>

**Tags**: `#Anthropic`, `#Google Cloud`, `#AI infrastructure`, `#business deal`

---

<a id="item-17"></a>
## [Apple Plans to Open Third-Party AI Model Selection](https://www.bloomberg.com/news/articles/2026-05-05/ios-27-features-apple-plans-to-let-users-swap-models-across-apple-intelligence) ⭐️ 8.0/10

Apple plans to allow users to select third-party AI models, such as those from Google and Anthropic, in iOS 27, iPadOS 27, and macOS 27, ending ChatGPT's exclusive integration in Apple Intelligence. This marks a major strategic shift for Apple, turning its devices into an AI platform where users can choose their preferred models, potentially reshaping the AI ecosystem and increasing competition. The feature, internally called 'Extensions', lets users select AI services in Settings for use with Siri, Writing Tools, and Image Playground, while Apple continues to offer its own models.

telegram · zaihuapd · May 6, 05:38

**Background**: Apple Intelligence is Apple's generative AI system announced at WWDC 2024, integrated into iOS 18, iPadOS 18, and macOS Sequoia. It initially featured exclusive ChatGPT integration and relies on on-device and server processing. Currently, Apple Intelligence is not available in mainland China.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Apple_Intelligence">Apple Intelligence</a></li>

</ul>
</details>

**Tags**: `#苹果`, `#AI模型`, `#第三方集成`, `#iOS`, `#战略更新`

---

<a id="item-18"></a>
## [DeepSeek reportedly valued at $45B in funding round](https://www.bloomberg.com/news/articles/2026-05-06/china-chip-fund-in-talks-to-lead-mega-deepseek-funding-ft-says) ⭐️ 8.0/10

China's National Integrated Circuit Industry Investment Fund is reportedly in talks to lead DeepSeek's first external funding round, which could value the AI company at around $45 billion. This would mark a major milestone for DeepSeek as its first large-scale external funding, signaling deeper state-backed investment in China's core AI sector and potentially reshaping the competitive landscape against global players like OpenAI. The funding is led by the Big Fund (China's national semiconductor fund), and the valuation of ~$45 billion is substantial for a company that has previously been funded solely by its founder's hedge fund, High-Flyer.

telegram · zaihuapd · May 6, 06:28

**Background**: DeepSeek, founded in 2023 by Liang Wenfeng, is a Chinese AI company known for developing cost-effective large language models like DeepSeek-R1 and V3. The company gained global attention in January 2025 when its R1 model rivaled OpenAI's GPT-4 at a fraction of the training cost, using weaker chips due to US export restrictions. DeepSeek's open-weight models have been praised for their efficiency and have caused market disruptions, notably a $600 billion drop in Nvidia's market cap.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/DeepSeek_(Company)">DeepSeek (Company)</a></li>

</ul>
</details>

**Tags**: `#DeepSeek`, `#funding`, `#AI`, `#China`, `#semiconductor`

---