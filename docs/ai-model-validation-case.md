# Testing AI before trusting it with money

*A case study in validating AI agents where mistakes are expensive.*

<p align="center">
  <img src="img/random-control-chimp.jpg" alt="A chimpanzee, a nod to the random control" width="560">
</p>

**The short version.** I used AI and my own validation lab to test several AI trading agents under one frozen protocol, against a random baseline and a simple rule. The AI agents did not beat the simple rule, and they finished close to random. A result like that is cheap to get in a simulation and expensive to learn with real capital. I recommend running this kind of test before any AI is given a role where errors cost money.

This is one of the ways I work on the question behind my profile: how people and businesses work with AI where mistakes are expensive. My background is 20+ years as a crisis manager and systems troubleshooter in manufacturing, ERP/MRP, logistics and finance.

---

## The question

AI agents often look convincing. They explain their decisions fluently, and a good-looking story is easy to mistake for good performance. So I asked a plain question: **if you let an AI act in a setting where errors are costly, does it do better than something simple and better than chance?**

Simulated trading is a convenient test bed: the cost of being wrong shows up directly as money, and luck is easy to mistake for skill.

## The setup

All participants were tested on the same market data under the same rules, in a simulation (no real money, no live trading).

| Participant | What it is |
|---|---|
| **H** | An AI agent in its own isolated conversation, with a calm, analytical profile |
| **HC** | The same AI agent, plus one independent AI adviser consultation per session |
| **M** | A separate AI agent with a deliberately emotional profile: fearful, greedy, impatient |
| **SMA20** | A simple mechanical moving-average rule, used as the benchmark |
| **Random control** | 1,000 independent random runs under the same protections |

Every participant had the same risk limits and the same trading costs. Each AI agent made its own decisions, one step at a time, and could not see the future.

## How I kept the test honest

The important part is not the trading, it is the method. These are the safeguards I built in so the result could not be flattered after the fact:

- **Frozen protocol.** The rules were written down and fingerprinted before the run. They were not edited afterwards.
- **Random control as the bar.** An AI agent has to beat what pure chance produces under the same rules, not just "make money" or "lose less than the market".
- **A simple benchmark.** A plain rule runs alongside the AI agents. If the AI cannot beat it, the extra complexity has not earned its place.
- **Causality checks.** Tests confirm that a decision could not have used data from the future.
- **Hashes.** The protocol, configuration, prompts, runner and data are fingerprinted so that anyone with access can verify that nothing changed.
- **Original AI answers kept in full.** Nothing was rewritten or tidied up after the fact.
- **Identical constraints for everyone**, including the random control.
- **Exactly 1,000 random runs**, with seeds fixed in advance.
- **No open positions at the end**, so the final numbers contain no unrealised surprises.

Fingerprints (SHA-256) of the frozen protocol and of the saved AI answers:

| Item | SHA-256 |
|---|---|
| Frozen protocol | `588fd2da5d0fefdce000f25cc51a005493c4743bc1876af77fd85828d1460f4b` |
| Saved answers, H | `049b26f56bc3397a0837433f980dfe7779ec2bd2cfa6d0c5407d11d5f02ad48c` |
| Saved answers, HC | `6582682844aa3f270a503bc9a67c4e274368164da604e7f0d11680c374102251` |
| Saved answers, M | `10a2bafbe7f77e13b99877cabec36f711ed5fcf3d8ebb2df432a26b4554c7954` |

## The result

Hourly GBP/USD, July to August 2018: 45 full trading sessions and 360 decision slots per participant. The study was run in November 2026 on historical data.

| Participant | Return | Max drawdown | Trades | Finished ahead of this share of the 1,000 random runs |
|---|---:|---:|---:|---:|
| SMA20 (simple rule) | **+0.75%** | 3.41% | 47 | 88.2% |
| H (AI agent) | −3.75% | 3.77% | 58 | 46.8% |
| HC (AI agent + adviser) | −3.99% | 4.27% | 51 | 42.9% |
| M (emotional AI persona) | −5.53% | 6.31% | 79 | 19.1% |

The random control had a median return of **−3.47%**. Its 5th to 95th percentile range ran from −6.05% to +2.79%, and 168 of the 1,000 random runs ended in profit.

**In plain terms:**

- The AI agents did **not** beat the simple rule. Only SMA20 ended in profit.
- H and HC ended close to the middle of the random distribution. They beat 46.8% and 42.9% of random runs.
- The emotional persona (M) did worse than most random runs. It traded the most, then hit the protocol's irreversible loss halt in early August and was stopped. The halt is by design and was not reset to let it trade more.
- The adviser did not help: HC finished 0.25 percentage points behind H. Part of that gap is ordinary run-to-run variation in AI answers, so it is not a clean measure of the adviser.

## What this does not show

A test is only as useful as it is honest about its limits:

- **One instrument and one period.** Two known historical months of one currency pair. This says nothing about other markets or other regimes.
- **Single runs.** Each AI agent ran once. A different run could land elsewhere.
- **A shortened study.** The plan was longer. I ended it early, and the window was cut after the run had started. The shortened result is a descriptive comparison, not a statistical proof.
- **Interrupted dialogues.** After a usage limit, the AI conversations were resumed from saved memory. The saved answers were kept byte for byte and nothing lost was reconstructed.
- **Imperfect adviser context.** In five consultations the adviser did not receive the full account context, and in three it did not receive complete price bars. The original answers are kept as they were.
- **Simplified market model.** Bid prices with a fixed spread. There is no historical ask or tick-level reconstruction.
- **A simulation.** It is not a live track record and it is not a forecast.

Nothing here claims that AI cannot trade, or that the simple rule is a good strategy. The finding is narrower: **these AI agents, in this test, gave no evidence of an edge**, and that is what the test was built to find out.

## Why it matters beyond trading

The point is the pattern, not the market. The same questions apply to any AI that is allowed to act where errors are expensive, for example planning and scheduling on top of ERP/MES:

1. **Agree the acceptance criteria before the run**, and freeze them.
2. **Compare against chance and against a simple baseline.** Plausible explanations do not count as evidence.
3. **Keep every original output**, so the result can be audited later.
4. **State the limits next to the result**, not in a footnote nobody reads.
5. **Keep a human go/no-go** on any costly decision.

An AI that sounds smart and has not been tested is a risk. A short, honest test is usually the cheapest protection you can buy.

## Work with me

If you are about to give an AI agent a costly job, or you already have and want to know whether it can be trusted, I can design and run this kind of test for you, or review one you have already done.

Send a short description of the decision or system at stake, and I will tell you honestly whether I can help.

- Email: [igor@telelyukhin.com](mailto:igor@telelyukhin.com)
- LinkedIn: [Igor Telelyukhin](https://www.linkedin.com/in/igor-telelyukhin/)

---

*The laboratory code, AI prompts, strategy settings and decision logs are private and are not published. The figures above come from the study's result file. This page is research documentation, not investment advice.*

[← Back to profile](../README.md)
