# Qwen &mdash; Presentation Series

A comprehensive, high-quality, twelve-part visual exploration of **Qwen**, Alibaba's open-weight model family &mdash; from the 7B research release of August 2023 to the 2.4-trillion-parameter Qwen3.8-Max three years later. Every generation is covered, and every model within each generation. Presented for engineers: each deck answers *what the model is*, *how the mechanism works*, *what it is good and bad at*, *which options and flags matter*, and *how well it is served by vLLM* &mdash; with hand-drawn SVG diagrams throughout.

**Live index:** https://brendanjameslynskey.github.io/Qwen/

## Presentations in this series

### A &middot; Orientation

| # | Title | Status | What it covers |
|---|-------|--------|----------------|
| 01 | [The Qwen Story](https://brendanjameslynskey.github.io/Qwen/part1.html) | live | Six generations in three years. The release timeline as swimlanes, how to parse a Qwen model name, the open / `-Plus` / `-Max` tier ladder, the licence history from a bespoke source-available licence to blanket Apache 2.0, and the architectural through-line from dense to sparse to hybrid linear attention. |

### B &middot; Foundations &mdash; 2023 to early 2025

| # | Title | Status | What it covers |
|---|-------|--------|----------------|
| 02 | [Qwen 1.0 &amp; Qwen1.5](https://brendanjameslynskey.github.io/Qwen/part2.html) | live | The first open Chinese frontier models. What was in Qwen-7B; why the 151,936-entry tokenizer mattered more than the architecture; NTK-aware interpolation, LogN scaling and window attention; Qwen-VL and Qwen-Audio; the Qwen1.5 compatibility release; the 14.3B mixture-of-experts that proved sparsity; and CodeQwen1.5. |
| 03 | [Qwen2 &amp; Qwen2.5 &mdash; the workhorse generation](https://brendanjameslynskey.github.io/Qwen/part3.html) | live | Grouped-query attention everywhere, with the KV-cache arithmetic that justifies it; 18 trillion pre-training tokens; long context done properly with YaRN and dual chunk attention; Qwen2.5-Coder and fill-in-the-middle; Qwen2.5-Math and tool-integrated reasoning; Qwen2.5-VL's dynamic resolution; and the Thinker&ndash;Talker split in Qwen2.5-Omni. |
| 04 | [QwQ &amp; QVQ &mdash; the reasoning detour](https://brendanjameslynskey.github.io/Qwen/part4.html) | live | Sixteen weeks in which a 32B matched a 671B on reasoning. What a `<think>` block actually is; reinforcement learning with verifiable rewards; the test-time compute curve and its knee; QVQ's visual reasoning; why serving a reasoning model breaks your assumptions; and why the line was absorbed into Qwen3. |

### C &middot; The Qwen3 generation &mdash; April 2025 to February 2026

| # | Title | Status | What it covers |
|---|-------|--------|----------------|
| 05 | [Qwen3 &mdash; architecture &amp; the hybrid-thinking experiment](https://brendanjameslynskey.github.io/Qwen/part5.html) | live | Eight open models from 0.6B to 235B-A22B with the full spec table; QK-Norm and the removal of QKV bias; inside the 128-expert MoE block; three pre-training stages over 36 trillion tokens; hybrid thinking and its three controls; four-stage post-training and strong-to-weak distillation; agentic capability and MCP; and the 2507 split that admitted the experiment had failed. |
| 06 | [Qwen3-Coder &mdash; agentic coding deep dive](https://brendanjameslynskey.github.io/Qwen/part6.html) | live | The 480B-A35B specified in full; the 20,000-parallel-environment RL system that taught it to recover from its own mistakes; benchmarks with the harness caveat most comparisons ignore; every ability and every option worth setting; an honest list of strengths and weaknesses; a capability-by-capability vLLM assessment; and the Coder-Next rewrite that matched it at a twelfth of the cost. |
| 07 | [Qwen3-Next &mdash; the architecture pivot](https://brendanjameslynskey.github.io/Qwen/part7.html) | live | Gated DeltaNet from the state-update equation up &mdash; gating for forgetting, the delta rule for retrieval. The 3:1 hybrid stack and what it does to the KV cache; 512 experts at a 1:50 activation ratio; the stability toolkit that also makes it quantise well; multi-token prediction; and the hybrid KV-cache manager and Triton kernels vLLM had to build to serve it. |
| 08 | [Multimodal &amp; specialists](https://brendanjameslynskey.github.io/Qwen/part8.html) | live | Qwen3-VL's DeepStack, interleaved M-RoPE and text-timestamp alignment, plus how to serve a VLM without running out of memory; Qwen3-Omni; the Embedding and Reranker pair as a retrieval cascade; Qwen3Guard's three-tier streaming safety; Qwen-Image's text rendering and the speech stack &mdash; then all of it composed into one working system. |

### D &middot; The 2026 line &mdash; February to August 2026

| # | Title | Status | What it covers |
|---|-------|--------|----------------|
| 09 | [Qwen3.5 &mdash; hybrid attention goes mainline](https://brendanjameslynskey.github.io/Qwen/part9.html) | live | Eight models from 0.8B to 397B-A17B, every one hybrid-attention and natively multimodal. The flagship specified; early fusion versus late fusion; 201 languages and the tokenizer break that ends three years of continuity; thinking and non-thinking finally reconciled; a general model beating the dedicated coder on SWE-bench; where it is still weak; and the vLLM recipe. |
| 10 | [Qwen3.6 to Qwen3.8 &mdash; dense returns, Max goes frontier](https://brendanjameslynskey.github.io/Qwen/part10.html) | live | A 27B dense model beating the 397B on agentic coding, and why dense wins that workload; thinking preservation across turns; the closed Max tier from Qwen3-Max to the 2.4-trillion-parameter Qwen3.8-Max; the open-weights release that is announced but not yet shipped; and what the trajectory implies for a decision made today. |

### E &middot; Running it

| # | Title | Status | What it covers |
|---|-------|--------|----------------|
| 11 | [Serving Qwen with vLLM](https://brendanjameslynskey.github.io/Qwen/part11.html) | live | The architecture support matrix; the reasoning/tool-call parser pairing table and the silent failures a mismatch causes; tensor, pipeline, expert and data parallelism and when each is right; the KV-cache formula and where the memory actually goes; long context, prefix caching and prompt ordering; quantisation and the MoE router caveat; MTP speculative decoding; multimodal and pooling endpoints; and a symptom-to-fix diagnostic table. |
| 12 | [Choosing, sizing &amp; deploying](https://brendanjameslynskey.github.io/Qwen/part12.html) | live | A decision tree and a selection matrix by workload; weight and KV-cache sizing for every model in the family; a dense-versus-sparse rule that works; the self-host versus API break-even done honestly; when to fine-tune and when not to; a migration procedure for generation upgrades; a production checklist; and how to verify any claim in the series for yourself. |

## How to read this series

Read **Part 01** first for the map. **Parts 02&ndash;04** build the vocabulary &mdash; tokenizers, grouped-query attention, mixtures of experts, reasoning traces &mdash; that the later decks assume. **Part 05** is the pivot: Qwen3 is the generation everything since is defined against. **Part 07** is the most important architectural deck; understand the 3:1 hybrid stack and you understand every current Qwen. **Parts 11 and 12** are reference material rather than narrative, and are worth returning to.

If you are here for one thing: **Qwen3-Coder is Part 06**, **vLLM serving is Part 11**, and *which model should I use* is **Part 12**.

## As of 10 August 2026

The Qwen line moves faster than any document about it. Architecture and flag claims come from Hugging Face model cards and technical reports; benchmark figures come from model cards and official release blogs; figures for the closed `-Max` tier are vendor-reported and flagged as such throughout. The announced Qwen3.8 open-weights release had **not yet appeared** when this was written &mdash; Part 12 explains how to verify every class of claim here for yourself.

## Where this fits

Part of the [LLMs hub](https://github.com/BrendanJamesLynskey/LLMs) &mdash; an index of presentation series for AI / LLM engineers &mdash; under **Foundations &amp; Internals**. Complements [Local LLM Hosting](https://github.com/BrendanJamesLynskey/LLM_Hub_Local_LLM_Hosting) (the serving stacks themselves), [Modern Architectures](https://github.com/BrendanJamesLynskey/LLM_Hub_Modern_Architectures) (MoE, state-space models and long context in general), [Vision-Language Models](https://github.com/BrendanJamesLynskey/LLM_Hub_Vision_Language) and [Coding Agents Internals](https://github.com/BrendanJamesLynskey/LLM_Hub_Coding_Agents).

Primary sources throughout: the [Qwen blog](https://qwenlm.github.io/blog/), [Qwen on Hugging Face](https://huggingface.co/Qwen), [github.com/QwenLM](https://github.com/QwenLM), the [vLLM documentation](https://docs.vllm.ai/) and [qwen.readthedocs.io](https://qwen.readthedocs.io/).

---

*Interactive HTML decks rendered on GitHub Pages. No build step &mdash; each part is a single self-contained `.html` file.*
