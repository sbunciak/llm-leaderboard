# LLM Leaderboard — June 2026

> Data sourced from Arena.ai, LLM Stats, BenchLM, Artificial Analysis, and OpenRouter. Updated June 7, 2026.

---

## 🏆 Frontier Models (Top 10)

Ranked by Arena Elo (best available variant). Thinking/extended variants noted in architecture column.

| Rank | Model | Provider | Arch | Released | Context | In $/M | Out $/M | GPQA ◆ | SWE-Bench | Arena Elo |
|------|-------|----------|------|----------|---------|--------|---------|--------|-----------|-----------|
| 1 | Claude Opus 4.6 | Anthropic | Dense · Thinking | Mar 2026 | 1M | $5.00 | $25.00 | — | 80.8% | 1504 |
| 2 | Claude Opus 4.7 | Anthropic | Dense · Thinking | Apr 2026 | 1M | $5.00 | $25.00 | 94.2% | — | 1501 |
| 3 | Meta Muse Spark ⚠ | Meta | Dense · Multimodal | Apr 2026 | 1M | N/A | N/A | 89.5% | 77.4% | 1489 |
| 4 | Gemini 3.1 Pro | Google | Dense · Thinking | Feb 2026 | 1M | $2.00 | $12.00 | 94.3% | 80.6% | 1488 |
| 5 | Gemini 3 Pro | Google | Dense | Jan 2026 | 1M | $2.00 | $12.00 | — | 76.2% | 1486 |
| 6 | Claude Opus 4.8 ⚠ | Anthropic | Dense · Thinking | May 2026 | 1M | $5.00 | $25.00 | 93.6% | 88.6% | 1482 |
| 7 | GPT-5.5 | OpenAI | Dense | Apr 2026 | 1.1M | $5.00 | $30.00 | 93.6% | 88.7% | 1482 |
| 8 | GPT-5.4 | OpenAI | Dense | Mar 2026 | 1.1M | $2.50 | $15.00 | 94.4% | — | 1479 |
| 9 | Gemini 3.5 Flash ⚠ | Google | Dense | May 2026 | 1M | $1.50 | $9.00 | — | — | 1477 |
| 10 | Grok 4 | xAI | Dense · Thinking | Mar 2026 | 2M | $2.00 | $6.00 | 88.9% | 74.9% | 1474 |

> ⚠ Preliminary Arena Elo — fewer than 20K votes; confidence interval wider than established models.

---

## 🔓 Open-Weight / Open-Source Models (Top 10)

Ranked by BenchLM composite score (primary) and GPQA Diamond (tiebreaker). API pricing is the cheapest hosted rate (OpenRouter, Together.ai, etc.).

| Rank | Model | Provider | License | Released | Size (Total / Active) | Context | API $/M in | Self-host | GPQA ◆ | SWE-Bench | Arena Elo |
|------|-------|----------|---------|----------|-----------------------|---------|-----------|-----------|--------|-----------|-----------|
| 1 | DeepSeek V4 Pro | DeepSeek | MIT | Apr 2026 | 1.6T / 49B | 1M | $1.74 | 8× H200 | 90.1% | 80.6% | — |
| 2 | Kimi K2.6 | Moonshot AI | MIT | Apr 2026 | 1T / 32B | 256K | $0.95 | 8× H100 | 90.5% | — | — |
| 3 | GLM-5.1 | Z.AI (Zhipu) | Open | Apr 2026 | — | 203K | $1.40 | — | 86.2% | — | 1475 |
| 4 | GLM-5 Reasoning | Z.AI (Zhipu) | Open | Feb 2026 | — | 200K | $1.00 | — | 94.0% | — | — |
| 5 | Qwen3.5 397B | Alibaba / Qwen | Apache 2.0 | Mar 2026 | 397B / 17B | 128K | $0.60 | 4× H100 | 88.4% | 73.4% | — |
| 6 | MiniMax M3 | MiniMax | MIT | Jun 2026 | — | 1M | — | — | — | — | — |
| 7 | Qwen3.6 Max | Alibaba / Qwen | Apache 2.0 | Apr 2026 | — | 1M | $0.80 | — | — | — | — |
| 8 | Qwen 3 235B | Alibaba / Qwen | Apache 2.0 | Feb 2026 | 235B / 22B | 128K | $0.40 | 2× H100 | — | — | — |
| 9 | Llama 4 Scout | Meta | Llama Community | Feb 2026 | — | 10M | $0.17 | — | — | — | — |
| 10 | DeepSeek V4 Flash | DeepSeek | MIT | Apr 2026 | 284B / 13B | 1M | $0.27 | 2× H100 | — | — | — |

**Notes:**
- MiniMax M3 (Jun 2026): SWE-Bench Pro 59%; first open-weight model combining 1M context + frontier coding + native multimodality
- GLM-5.1: SWE-Bench Pro 58.4% (agentic coding); GLM-5 Reasoning leads GPQA at 94.0% among open-weight models
- Qwen3.5 397B: AIME 2026 91.3%; strong math reasoning
- Llama 4 Scout: 10M token context window, designed for speed-critical agentic pipelines
- Self-host tiers are based on **total** params at Q4 quantization (~0.5 bytes/param). MoE models require all expert weights resident in VRAM simultaneously — the router can call any expert at any token, so active-param count is not the right basis for VRAM estimation. H100 = 80 GB, H200 = 141 GB.

---

## Benchmark Key

| Benchmark | What it measures | Notes |
|-----------|-----------------|-------|
| **GPQA ◆** | Graduate-level science reasoning (Diamond set) | Most discriminating frontier benchmark in 2026; not yet saturated |
| **SWE-Bench** | Real GitHub issue resolution (Verified subset, 500 tasks) | Primary coding signal; HumanEval deprecated |
| **Arena Elo** | Human-preference ranking from arena.ai (~6.7M votes) | Higher = better; primary sort for frontier |
| **MMLU-Pro** | General knowledge (57 subjects) | Approaching saturation at frontier — not shown |
| **AIME 2026** | Math olympiad reasoning | Noted where available; GPT-5 series scored 98–100% |

---

## Tier Definitions

- **S Tier** (Ranks 1–3): State-of-the-art, leading benchmark performance
- **A Tier** (Ranks 4–7): Highly capable, competitive on most evals
- **B Tier** (Ranks 8–10): Solid performers, often better value per dollar

---

## Sources

- [Arena.ai Leaderboard](https://arena.ai/leaderboard/text)
- [LLM Stats](https://llm-stats.com/)
- [BenchLM](https://benchlm.ai/)
- [Artificial Analysis](https://artificialanalysis.ai/)
- [OpenRouter Rankings](https://openrouter.ai/rankings)

---

*Benchmarks change rapidly. Scores reflect publicly reported values at time of publication. "—" indicates data not publicly available. Cross-reference multiple sources before making infrastructure decisions.*
