# Redaction report

Related: [Project overview](https://akzar1el.github.io/walk-forward-crypto/) · [Numbers ledger](https://akzar1el.github.io/walk-forward-crypto/NUMBERS_LEDGER.html) · [OOS dashboard](https://akzar1el.github.io/walk-forward-crypto/interactive/dashboard.html)

What the case study abstracts, what it keeps, and how this public
repository enforces the redaction.

## Abstracted in the case study

| Detail | How it appears publicly | Why |
|---|---|---|
| Exact indicator parameters (MA spans, channel lengths, oscillator levels/thresholds) | "moving-average crosses", "channel breakouts", "oscillator and band signals" — family level only | Parameter sets are the replicable part of the work product |
| The full 24-config zoo listing | "a fixed zoo of 24 simple configurations, four families" | Same |
| Weekly winner identities | Family-level ribbon only (trend / breakout / mean-reversion / cash / mixed); no config names in any chart label | Same |
| Current live stance (which configs, what size, what direction) | Not in the case study at all | Operational |
| Tie-breaking rule details in selection | Described as "how exact score ties break", no implementation detail | Minor, but parameter-adjacent |
| Live dashboard URL / port / machine details | Not mentioned | Operational security |

## Deliberately kept (not redacted)

| Detail | Rationale |
|---|---|
| Structural choices: weekly cadence, 30-day training window, 4h bars, top-3 averaging, 24-candidate pool size | These are the case study's subject matter; without them the graveyard is meaningless. They are method, not parameters. |
| Sizing: 50% vol target, 1.5× cap (and the 35%/1× reference variant) | The risk-dial discussion is a core honesty point; constants are not the secret sauce (the operator brief allowed naming the vol target). |
| Cost model (0.15%/side) and funding methodology | Required for any reader to assess realism. |
| All aggregate results, drawdowns, Sharpe estimates and their errors | The point of the document. |

## Account identifiers, keys, personal data

None exist in the repo: the system uses only public, keyless APIs. The
secret scan covers api-key patterns, private keys, wallet addresses and
.env content across all published files. Scan result: **no findings** in
README.md or docs/. The live trade record and the fit-watchdog status file
live only in the private repository and are absent from this mirror.

## How this repository resolves the redaction

The full strategy source — which defines the 24-config zoo and every
indicator parameter the case study abstracts — lives in a **separate,
private research repository**. The redaction is therefore enforced
structurally: this public repository contains only the case study
(README.md, docs/assets, docs/interactive, and these two docs). None of the
strategy source, parameters, or config listings are present here to leak.

This is the **mirror model**: a standalone public case study, with the code
repository kept private. Casual and determined readers alike see the same
family-level abstraction, because the parameters simply are not in this
repo. The case study text stays honest either way.
