# Contributing to AIWave

Thanks for helping. These are organization-wide defaults; some repositories
(like [aiwave-quickstart](https://github.com/AIWaveAPI/aiwave-quickstart))
have their own, more specific CONTRIBUTING file — those take precedence.

## The most valuable contribution: report a wrong number

Our model catalog and prices come from a live public endpoint:

    https://aiwave.live/api/pricing

Vendors change prices and retire models without notice. If any number on a
website page, README, or in `MODEL_REFERENCE.md` disagrees with that endpoint,
open an issue with:

1. Where the wrong number appears (URL or `file:line`)
2. The exact model ID
3. The endpoint response and the date you fetched it

We treat these as bugs. **Do not "correct" numbers by copying from another
aggregator or an old blog post** — the live endpoint is the only source of
truth. See the quickstart repo for `verify_claims.py` / `sync_claims.py`.

## Reporting bugs

Use the issue template. Include a minimal reproduction and redact all keys:

    Authorization: Bearer sk-REDACTED

Never paste real API keys, tokens, or customer data into a public issue.

## Proposing changes

- One idea per issue or PR
- Runnable examples belong in `examples/` and use `AIWAVE_API_KEY`
- State caveats you learned the hard way (timeouts, silent failures,
  required parameters) — those notes are worth more than the code
- Claims about prices or model counts must carry a source and a date

## Code of conduct

See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). Report unacceptable behavior
to security@aiwave.live.

## Disclosure

If you work on AIWave, please say so in your issue or PR so reviewers can
weigh it accordingly.
