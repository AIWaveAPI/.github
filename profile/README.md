# AIWave API

**AIWave — OpenAI-compatible route for Chinese AI models with USD billing**

[![Website](https://img.shields.io/badge/website-aiwave.live-blue)](https://aiwave.live)
[![Pricing](https://img.shields.io/badge/pricing-dated%20USD%20rate%20card-blue)](https://aiwave.live/pricing)
[![Models](https://img.shields.io/badge/models-Chinese%20AI%20catalog-blue)](https://aiwave.live/models/)

AIWave gives developers one OpenAI-compatible API route for Chinese AI model families such as DeepSeek, GLM, Kimi, Qwen, ERNIE, MiniMax, Doubao, StepFun, and MiMo.

Use AIWave when you want one API key, one USD billing surface, dated model rates, and request-level billing evidence while testing Chinese AI workloads from an existing OpenAI-compatible client.

## Quick start

```python
import os
from openai import OpenAI

client = OpenAI(
    api_key=os.environ["AIWAVE_API_KEY"],
    base_url="https://aiwave.live/v1",
)

response = client.chat.completions.create(
    model="deepseek-v4-flash",
    messages=[{"role": "user", "content": "Hello"}],
)

print(response.usage)
```

Store API keys outside source control. The example above uses an environment variable and does not include a real key.

## What to verify before production

- Confirm the current model ID in the [model catalog](https://aiwave.live/models/).
- Check the dated USD rates on the [pricing page](https://aiwave.live/pricing).
- Run one representative workload and review the request-level usage record.
- Keep timeout, retry, privacy, and model-quality acceptance checks in your own application.

## Resources

- [AIWave home](https://aiwave.live/)
- [Dated pricing and model rates](https://aiwave.live/pricing)
- [Chinese AI model catalog](https://aiwave.live/models/)
- [API docs](https://aiwave.live/docs/)
- [Developer field notes](https://aiwave.live/blog/)

## SDKs

| Language | Repository |
|----------|------------|
| Python | [aiwave-sdk-python](https://github.com/AIWaveAPI/aiwave-sdk-python) |
| Node.js | [aiwave-sdk-node](https://github.com/AIWaveAPI/aiwave-sdk-node) |
