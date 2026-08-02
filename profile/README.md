# AIWave API

**One API Key for 48 Chinese AI Models — OpenAI Compatible**

[![Website](https://img.shields.io/badge/website-aiwave.live-blue)](https://aiwave.live)
[![Models](https://img.shields.io/badge/models-48-brightgreen)](https://aiwave.live/pricing)

## Live model catalog

AIWave provides one OpenAI-compatible endpoint for 48 Chinese AI models. The live model names and USD prices are maintained on the [pricing page](https://aiwave.live/pricing); do not rely on a static README list.

## Quick Start

```python
from openai import OpenAI
client = OpenAI(
    api_key="YOUR_API_KEY_HERE",
    base_url="https://aiwave.live/v1"
)
response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[{"role": "user", "content": "Hello!"}]
)
```

Use a key from [aiwave.live](https://aiwave.live), and never commit a real key.

## Why AIWave?

- **One API key** for 48 Chinese AI models
- **OpenAI compatible** with existing SDKs and tools
- **Pay-as-you-go** USD billing
- **$1 free credit** on signup for testing

## Resources

- [Pricing and live model catalog](https://aiwave.live/pricing)
- [Developer blog](https://aiwave.live/blog/)

### SDKs

| Language | Repository |
|----------|------------|
| Python | [aiwave-sdk-python](https://github.com/AIWaveAPI/aiwave-sdk-python) |
| Node.js | [aiwave-sdk-node](https://github.com/AIWaveAPI/aiwave-sdk-node) |