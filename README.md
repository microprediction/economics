# economics (view as [web page](https://economics.microprediction.org))

Working papers on the economics of AI production: who executes the work when
computation is subdivided, subcontracted, and free to move.

**Paper:** [Division of Labor and the Survival Value of PnL per Token](https://economics.microprediction.org/pnl_per_token.pdf)
**Short version (Economics Letters draft):** [Winning the Large Language Capability Battle and Losing the Production Economy](https://economics.microprediction.org/pnl_per_token_letter.pdf)
**Sources:** [`papers/`](papers/)

A competitive economy of prediction tasks supplied by itinerant compute.
Mobility equalizes marginal PnL per token at the shadow price; within any
subcontractible task, the technology with the highest per-token value displaces
every other completely. As the task partition refines, a generalist that wins
on capability everywhere can have equilibrium compute share tending to zero.
The valid empirical statistic is incremental PnL per unit of compute cost on
comparable tasks at a common congestion state, not aggregate PnL over aggregate
tokens.

## Data

The theory above names an empirical statistic — incremental PnL per unit of
compute cost, on comparable tasks, at a common congestion state — and the
hard part of measuring it is the last clause. Two of the three ingredients
are now public.

[data.agentic-system.org](https://data.agentic-system.org/) (Harvard MadSys
Lab) publishes traces from LLM serving:

- **One Year in LLM Serving** — 6.12 billion requests across 9,174 models,
  with token counts, cache behaviour and timing. Task composition and the
  arrival process, measured rather than assumed.
- **GPU and serving telemetry** — live time series from the FreeInference
  fleet: utilization, memory, inference performance. This is the
  *congestion state* the comparison has to be conditioned on, and it is the
  ingredient that usually has to be waved at.

What it does not carry is the numerator. There is no revenue or task value
in these traces, so PnL per token cannot be read off them directly; they
give the denominator and the conditioning variable, and the value side
still has to come from somewhere else. Their agent-workload datasets
(KV-cache traces, sanitized prompts) are announced but unreleased, and the
telemetry is one fleet's, so its model mix and cache policy are its own.

## Layout

```
papers/            LaTeX sources, one subfolder per paper (PDFs gitignored)
docs/              the site, served by GitHub Pages at economics.microprediction.org
                   (PDFs are committed here; the site hosts them)
```

## Cite

```bibtex
@unpublished{cotton2026pnl,
  author = {Cotton, Peter},
  title  = {Division of Labor and the Survival Value of PnL per Token},
  note   = {Working paper},
  year   = {2026},
  url    = {https://economics.microprediction.org/pnl_per_token.pdf}
}
```
