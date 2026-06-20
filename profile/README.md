# AIWave API

**One API Key for 50+ Chinese AI Models — OpenAI Compatible**

[![Website](https://img.shields.io/badge/website-aiwave.live-blue)](https://aiwave.live)
[![Models](https://img.shields.io/badge/models-50+-brightgreen)](https://aiwave.live/pricing)

## Supported Models

| Provider | Models |
|----------|--------|
| **DeepSeek** | V4 Pro, V3, R1 (Reasoning) |
| **GLM** | GLM-5.1, GLM-5, GLM-4-Flash |
| **Kimi** | Kimi VL (Vision), Kimi Thinking |
| **ERNIE** | ERNIE 4.5, ERNIE Speed |
| **Qwen** | Qwen 3, Qwen 3 VL |
| **+ more** | 50+ Chinese AI models |

## Quick Start

```python
from openai import OpenAI
client = OpenAI(
    api_key="***",
    base_url="https://aiwave.live/v1"
)
response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[{"role": "user", "content": "Hello!"}]
)
```

## Why AIWave?

- **One API key** — all 50+ models
- **Pay-as-you-go** — no minimum deposit
- **Start free** — free credits on signup
- **OpenAI compatible** — works with existing tools

**[Get started →](https://aiwave.live)**

### SDKs
| Language | |
|----------|-----|
| Python | [aiwave-sdk-python](https://github.com/AIWaveAPI/aiwave-sdk-python) |
| Node.js | [aiwave-sdk-node](https://github.com/AIWaveAPI/aiwave-sdk-node) |
