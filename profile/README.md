# AIWave API

**AIWave — OpenAI-compatible route for Chinese AI models with USD billing**

[![Website](https://img.shields.io/badge/website-aiwave.live-blue)](https://aiwave.live)
[![Pricing](https://img.shields.io/badge/pricing-dated%20USD%20rate%20card-blue)](https://aiwave.live/pricing)
[![Quickstart](https://img.shields.io/badge/docs-30%20second%20quickstart-blue)](https://aiwave.live/docs/quickstart)

AIWave gives developers one OpenAI-compatible API route for Chinese AI model families such as DeepSeek, GLM, Kimi, Qwen, ERNIE, MiniMax, Doubao, StepFun, and MiMo.

Use one API key, one USD billing surface, dated model rates, and request-level usage evidence while testing Chinese AI workloads from an existing OpenAI-compatible client.

## Quick start

```bash
curl https://aiwave.live/v1/chat/completions \
  -H "Authorization: Bearer $AIWAVE_API_KEY" -H "Content-Type: application/json" \
  -d '{"model":"deepseek-flash","messages":[{"role":"user","content":"Reply with OK"}]}'
```

Store API keys outside source control. This example reads the key from an environment variable and does not include a real credential.

## What to verify before production

- Confirm the exact model ID in the [model catalog](https://aiwave.live/models/).
- Check the dated USD rates in the [pricing JSON](https://aiwave.live/api/v1/pricing).
- Run one representative workload and review the request-level usage record.
- Keep timeout, retry, privacy, and model-quality acceptance checks in your own application.

## Resources

- [30-second quickstart](https://aiwave.live/docs/quickstart)
- [Dated pricing page](https://aiwave.live/pricing)
- [Filterable model comparison](https://aiwave.live/compare/chinese-ai-models)
- [API documentation](https://aiwave.live/docs/)
- [Developer field notes](https://aiwave.live/blog/)

## SDKs

| Language | Repository |
|----------|------------|
| Python | [aiwave-sdk-python](https://github.com/AIWaveAPI/aiwave-sdk-python) |
| Node.js | [aiwave-sdk-node](https://github.com/AIWaveAPI/aiwave-sdk-node) |
