<div align="center">

# AIWave

**One OpenAI-compatible API for Chinese AI models — and AI video.**

[![Models](https://img.shields.io/badge/models-128%20live%20routes-blue)](https://aiwave.live/models)
[![Video](https://img.shields.io/badge/video-13%20generation%20routes-purple)](https://aiwave.live/models)
[![Families](https://img.shields.io/badge/families-9%20Chinese%20AI%20vendors-blue)](https://aiwave.live/models)
[![Pricing](https://img.shields.io/badge/pricing-dated%20USD%20rate%20card-blue)](https://aiwave.live/pricing)
[![Docs](https://img.shields.io/badge/docs-30%20second%20quickstart-blue)](https://aiwave.live/docs/quickstart)

</div>

---

One key. One endpoint. **128 live model routes** across nine Chinese AI families — DeepSeek, GLM, Kimi, Qwen, ERNIE, MiniMax, Doubao, StepFun, and Xiaomi MiMo — plus **13 AI video generation routes** (Kling, Seedance, Hailuo, Wan, Vidu).

Keep your OpenAI SDK. Change one string. Ship.

```python
from openai import OpenAI

client = OpenAI(
    api_key="your-aiwave-key",
    base_url="https://aiwave.live/v1",
)

resp = client.chat.completions.create(
    model="deepseek-v4-flash",
    messages=[{"role": "user", "content": "Say hello in one sentence."}],
)
```

**Get a key:** [aiwave.live/register](https://aiwave.live/register) — free tier included.

---

## What's in the catalog

| Family | Highlights |
|---|---|
| DeepSeek | `deepseek-v4-pro`, `deepseek-v4-flash` — flagship & budget reasoning |
| GLM (Zhipu) | `glm-5`, `glm-5.1`, `glm-5.3` series |
| Kimi (Moonshot) | `kimi-k3` long-context |
| Qwen (Alibaba) | qwen3.8 full line — Max, Coder, audio, embeddings |
| ERNIE / MiniMax / Doubao / StepFun / MiMo | Complete family coverage |
| **AI Video** | **Kling v3 / video-o1, Seedance 2.5, Hailuo 2.3, Wan 3.0, Vidu Q3** |

Full list with live availability: [aiwave.live/models](https://aiwave.live/models)
Dated USD rates: [aiwave.live/pricing](https://aiwave.live/pricing)

## Repositories

| Repo | What it is |
|---|---|
| [aiwave-quickstart](https://github.com/AIWaveAPI/aiwave-quickstart) | curl / Python / Node examples — first call in under a minute |
| [aiwave-sdk-python](https://github.com/AIWaveAPI/aiwave-sdk-python) | `pip install aiwave` |
| [aiwave-sdk-node](https://github.com/AIWaveAPI/aiwave-sdk-node) | `npm install aiwave` |

## Why developers pick AIWave

- **One key, nine families** — no nine vendor accounts, no nine invoices
- **Video included** — the same key renders Kling and Seedance clips; most aggregators don't offer video at all
- **Prices synced to vendor list prices** — dated rate card, no stale numbers
- **OpenAI-compatible** — your existing SDK works; swap `base_url` and go

## Verify before you build

- Exact model IDs: [model catalog](https://aiwave.live/models/)
- Dated USD rates: [pricing JSON](https://aiwave.live/api/v1/pricing)
- Run one representative workload and check the usage record in the console

## Links

[Quickstart](https://aiwave.live/docs/quickstart) · [Pricing](https://aiwave.live/pricing) · [Model comparison](https://aiwave.live/compare/chinese-ai-models) · [API docs](https://aiwave.live/docs/) · [Field notes](https://aiwave.live/blog/) · [Create account](https://aiwave.live/register)
