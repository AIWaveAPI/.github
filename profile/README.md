<div align="center">

# AIWave

**One OpenAI-compatible API for Chinese AI models — and AI video.**

[![Listed IDs](https://img.shields.io/badge/model%20IDs-97-blue)](https://aiwave.live/api/pricing)
[![Families](https://img.shields.io/badge/Chinese%20families-10-blue)](https://aiwave.live/models)
[![Video](https://img.shields.io/badge/video%20IDs-13-purple)](https://aiwave.live/models)
[![Docs](https://img.shields.io/badge/docs-quickstart-blue)](https://aiwave.live/docs/quickstart)

</div>

---

## What is AIWave?

AIWave is an OpenAI-compatible API that lists **97 model IDs on the public rate card** across
**10 Chinese AI model families** — DeepSeek, GLM, Kimi, Qwen, Doubao, StepFun,
Xiaomi MiMo, MiniMax, Kling and Wan — plus Claude coding-team and other
international model IDs, and **13 video IDs on the public rate card**. One key and
one endpoint; the model ID is a parameter. Catalog membership does not prove
access for a given key or live route health. The listed-ID, family and video-ID counts
on this page are checked against [`https://aiwave.live/api/pricing`](https://aiwave.live/api/pricing),
which needs no key. Dated USD rates are at [aiwave.live/pricing](https://aiwave.live/pricing).

Install `openai` and set your own `AIWAVE_API_KEY` as shown in the
[quickstart](https://github.com/AIWaveAPI/aiwave-quickstart#1-set-your-environment).
The example prints the response; it does not require storing your key in source.

```python
import os
from openai import OpenAI

client = OpenAI(
    api_key=os.environ["AIWAVE_API_KEY"],
    base_url="https://aiwave.live/v1",
)

resp = client.chat.completions.create(
    model="deepseek-v4-flash",
    messages=[{"role": "user", "content": "Say hello in one sentence."}],
)
print(resp.choices[0].message.content)
```

**Get a key:** [aiwave.live/register](https://aiwave.live/register)

---

## Verify our numbers yourself

The catalog counts and model IDs shown below trace to the live public endpoint:

```bash
# Model-ID count on the live public rate card
curl -s https://aiwave.live/api/pricing | python3 -c \
  "import sys,json; d=json.load(sys.stdin); ms=d['models'] if 'models' in d else d['data']; print(len(ms))"

# Per-model USD rates and the pricing version
curl -s https://aiwave.live/api/pricing | python3 -m json.tool | head -30
```

If an AIWave catalog claim in our repos disagrees with this endpoint, open an
issue. The [quickstart repo](https://github.com/AIWaveAPI/aiwave-quickstart)
checks specified listed-ID/family/video-ID count patterns and matching backticked
model IDs daily across the public repositories listed in its workflow. This
scan does not verify every price, model capability or live route availability.

## Models developers actually search for

Exact model IDs from the live rate card. Prices change — copy the ID, then
check the [dated rate card](https://aiwave.live/pricing) or the endpoint above.
This is a lookup table, not a benchmark or a review.

| If you're searching for | What's actually on our rate card | Notes |
|---|---|---|
| `deepseek v4 flash`, `deepseek flash` | `deepseek-v4-flash`, `deepseek-flash`, `deepseek-v4.1-flash` | Three fast DeepSeek routes |
| `deepseek v4 pro` | `deepseek-v4-pro` | Higher-capability DeepSeek chat route |
| `qwen3 coder` | `qwen3.8-max`, `qwen3.8-27b`, `qwen3-max`; coding-specific: `kimi-k2.7-code`, `kimi-k2.7-code-highspeed` | There is no `qwen3-coder` ID on our card — these are the general and coding routes we do serve |
| `kimi k3`, `kimi review` | `kimi-k3`, `kimi-k2.7-code-highspeed`, `kimi-k2.6` | Moonshot long-context and coding routes; we publish availability, not benchmarks |
| `chinese ai api pricing 2026` | — | [Dated USD rates](https://aiwave.live/pricing), or `scripts/cost.py` in the quickstart repo to estimate a workload |
| `chinese embedding models` | `qwen3.7-text-embedding` | Embedding route on the same endpoint |
| `kling`, `seedance`, `hailuo`, `wan` video | `kling-v3`, `kling-video-o1`, `doubao-seedance-2-5-260628`, `MiniMax-Hailuo-2.3`, `wan3.0-video` | Video IDs on the public card |

To confirm a model is currently on the card:

```bash
curl -s https://aiwave.live/api/pricing | python3 -c \
  "import sys,json; d=json.load(sys.stdin); ms=d['models'] if 'models' in d else d['data']; print([m['model_name'] for m in ms if 'flash' in m['model_name']])"
```

Full auto-generated list: [MODEL_REFERENCE.md](https://github.com/AIWaveAPI/aiwave-sdk-python/blob/main/MODEL_REFERENCE.md).

## What's in the catalog

| Family | Highlights |
|---|---|
| DeepSeek | `deepseek-v4-pro`, `deepseek-v4-flash`, `deepseek-v4.1-flash` |
| GLM (Zhipu) | `glm-5`, `glm-5.1`, `glm-5.3` series |
| Kimi (Moonshot) | `kimi-k3` long-context |
| Qwen (Alibaba) | qwen3.8 / qwen3.7 lines — Max, VL, embeddings |
| Doubao / StepFun / MiMo / MiniMax | Complete family coverage |
| Kling / Wan (video) | `kling-v3`, `kling-video-o1`, `wan3.0-video` |
| International | Claude coding-team series, Cohere, and more |

Live list: [aiwave.live/models](https://aiwave.live/models) ·
Dated USD rates: [aiwave.live/pricing](https://aiwave.live/pricing)

## Repositories

| Repo | What it is |
|---|---|
| [aiwave-quickstart](https://github.com/AIWaveAPI/aiwave-quickstart) | curl / Python / Node examples, cost estimator, error-handling recipes |
| [aiwave-video-pack](https://github.com/AIWaveAPI/aiwave-video-pack) | Four copyable video prompt examples; payload syntax tested, visual results not independently verified |
| [aiwave-sdk-python](https://github.com/AIWaveAPI/aiwave-sdk-python) | `pip install aiwave` |
| [aiwave-sdk-node](https://github.com/AIWaveAPI/aiwave-sdk-node) | `npm install aiwave` |
| [credit-receipt](https://github.com/AIWaveAPI/credit-receipt) | Offline, supplier-neutral credit-ledger checks; reports unknowns instead of inventing a cash rate |

Repository changes can precede a package release. Check the installed package
version and its release notes before relying on a new SDK fix.

## How this org handles facts

- **AIWave prices and model IDs** come from the live public endpoint, never from a
  copied blog post or another aggregator.
- **Catalog counts** are checked by CI daily; a drift turns the build red and
  names the exact `file:line`.
- **Examples** state caveats learned in production (timeouts, silent video
  failures, required reference images) instead of hiding them.
- **Video prompt examples** disclose author-reported N=1 runs, missing public
  clips and task receipts, and known limitations.

## Links

[Quickstart](https://aiwave.live/docs/quickstart) · [Pricing](https://aiwave.live/pricing) · [API docs](https://aiwave.live/docs/) · [Create account](https://aiwave.live/register)

