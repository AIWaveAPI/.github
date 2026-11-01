<div align="center">

# AIWave

**One OpenAI-compatible API for Chinese AI models — and AI video.**

[![Routes](https://img.shields.io/badge/public%20rate%20card-97%20routes-blue)](https://aiwave.live/api/pricing)
[![Families](https://img.shields.io/badge/Chinese%20families-10-blue)](https://aiwave.live/models)
[![Video](https://img.shields.io/badge/public%20video%20routes-10-purple)](https://aiwave.live/models)
[![Docs](https://img.shields.io/badge/docs-quickstart-blue)](https://aiwave.live/docs/quickstart)

</div>

---

One key. One endpoint. **97 routes on the public rate card** across **10
Chinese AI families** — DeepSeek, GLM, Kimi, Qwen, Doubao, StepFun,
Xiaomi MiMo, MiniMax, Kling, Wan — plus Claude coding-team and other
international routes, and **10 public video-generation routes** (more on
paid tiers).

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

## Verify our numbers yourself

Every claim in this org traces to a public endpoint. No marketing math:

```bash
# Route count on the public rate card (as of 2026-11-01, pricing_version 5a90f2b8…)
curl -s https://aiwave.live/api/pricing | python3 -c \
  "import sys,json; d=json.load(sys.stdin); ms=d['models'] if 'models' in d else d['data']; print(len(ms))"

# Dated USD rates (per model, with effective date)
curl -s https://aiwave.live/api/v1/pricing | python3 -m json.tool | head -20
```

If any number in our repos disagrees with these endpoints, that's a bug —
open an issue.

## What's in the catalog

| Family | Highlights |
|---|---|
| DeepSeek | `deepseek-v4-pro`, `deepseek-v4-flash` |
| GLM (Zhipu) | `glm-5`, `glm-5.1`, `glm-5.3` series |
| Kimi (Moonshot) | `kimi-k3` long-context |
| Qwen (Alibaba) | qwen3.8 full line — Max, Coder, embeddings |
| Doubao / StepFun / MiMo / MiniMax | Complete family coverage |
| Kling / Wan (video) | `kling-v3`, `kling-video-o1`, `wan3.0-video` |
| International | Claude coding-team series, Cohere, and more |

Live list: [aiwave.live/models](https://aiwave.live/models) ·
Dated USD rates: [aiwave.live/pricing](https://aiwave.live/pricing)

## Repositories

| Repo | What it is |
|---|---|
| [aiwave-quickstart](https://github.com/AIWaveAPI/aiwave-quickstart) | curl / Python / Node examples — first call in under a minute |
| [aiwave-video-pack](https://github.com/AIWaveAPI/aiwave-video-pack) | Free validated cinematic prompt modules (with evidence) |
| [aiwave-sdk-python](https://github.com/AIWaveAPI/aiwave-sdk-python) | `pip install aiwave` |
| [aiwave-sdk-node](https://github.com/AIWaveAPI/aiwave-sdk-node) | `npm install aiwave` |

## Why developers pick AIWave

- **One key, ten Chinese families + international routes** — no ten vendor accounts, no ten invoices
- **Video included** — the same key renders Kling and Seedance clips; most aggregators don't offer video at all
- **Prices synced to vendor list prices** — dated rate card, no stale numbers
- **OpenAI-compatible** — your existing SDK works; swap `base_url` and go

## Links

[Quickstart](https://aiwave.live/docs/quickstart) · [Pricing](https://aiwave.live/pricing) · [API docs](https://aiwave.live/docs/) · [Create account](https://aiwave.live/register)
