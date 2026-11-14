MET

Scored on submit-OK, not on inclusion. Inclusion, reported and not scored: in 4 of 4 minutes our payments included (desk counter) were within 10 percent of submit-OK.

# HOLD-2, desk, pre-run 33

> Our own TN10 testing: what we observed in this run, on our own desk node. Counts only. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

HOLD-2 offers 2027 simple payments a second at 150 sompi/gram (two thirds of 3,040 payments a second) on the kept public TN10 nodes. The covenant families, the KCC-20 mint line and the tic-tac-toe guest keep running on the desk node. No heavy lane. The desk node is not restarted.

Payment offer 2,027 tx/s at 150 sompi/gram, from 9 payment senders, 3 per kept public node (3 unique kaspads), each its own process and connection. Families offer 1.2 hop/s, 13 families live, one family-sender process and one builder: floor (families 1–12) 100 sompi/gram on the desk's private node, kcc (families 13–13) 100 sompi/gram on the desk's private node (public map ).

Payment pile: 5,408 coins on the payment key at the preflight, dealt evenly over the 9 senders before the first payment. A deal never holds more coins than the preflight pile. A coin is re-used about once a second, so one sender's ceiling is about its pool per second.

## Submit-OK and included, per minute

| Minute (UTC) | Pay submit-OK | Our payments included | Included, all non-coinbase | Counter |
|---|---:|---:|---:|---|
| 2026-11-14T12:41 | 121,689 | 122,952 | 126,050 | kept pace |
| 2026-11-14T12:42 | 121,673 | 123,717 | 126,944 | kept pace |
| 2026-11-14T12:43 | 121,672 | 121,004 | 124,095 | kept pace |
| 2026-11-14T12:44 | 121,077 | 122,134 | 125,222 | kept pace |

Submit-OK counts in the minute a submit was answered. Included counts in the minute of the chain block that accepted it, so a payment submitted late in one minute can be included in the next. "Kept pace" means the desk node's DAA stayed within 100 of the kept public kaspad and its sink was under 30 s old in every sample of that minute; "LAGGING" means it did not, and the count is what the node had accepted, not a network figure.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | Kcc hops (100) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-14T12:41 | 126,050 | 122,952 | 115 | 0 | 2,983 | 266 | 0 | 341 | 20 | kept pace |
| 2026-11-14T12:42 | 126,944 | 123,717 | 162 | 0 | 3,066 | 299 | 0 | 600 | 20 | kept pace |
| 2026-11-14T12:43 | 124,095 | 121,004 | 134 | 0 | 2,959 | 283 | 0 | 429 | 19 | kept pace |
| 2026-11-14T12:44 | 125,222 | 122,134 | 103 | 0 | 2,985 | 268 | 0 | 427 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–12, desk private node): 100 sompi/gram per hop. Kcc (families 13–13, desk private node): no rows sompi/gram per hop. In pre-run 33 that rate is on the hop's node-side mass (kit21): the builder is asked for a bill rate on its own mass so that fee / node mass is the tier's rate.

| Tier | Node rate as built, median (min–max) | Bill rate, median | Node mass, median (min–max) | Node rate in the desk mempool, lowest–highest (probe) |
|---|---|---:|---|---|
| floor (100) | 100.12 (100.01–100.32) | 314 | 40,953 (40,379–43,891) | 100.01–100.3 |
| kcc (100) | - | - | - | - |

Node rate as built is kit21's fee / node mass (rusty-kaspa v2.1.0 storage mass with UTXO plurality, or compute or transient/2 if larger). In the desk mempool the probe divides the node's fee by the larger of the storage and compute mass the node reports.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 4 (272), 14 (210), 11 (207), 15 (206), 16 (187), 13 (184), 10 (166), 17 (161), 9 (137), 18 (131), 8 (120), 7 (111), and 50 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Kcc OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---:|---:|---|
| 2026-11-14T12:41 | 121,689 | 121,690 | 0 | 0 | 1 | 115 / 902 / 0 / 0 / 11 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-14T12:42 | 121,673 | 121,675 | 0 | 0 | 2 | 161 / 924 / 0 / 0 / 10 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-14T12:43 | 121,672 | 121,675 | 0 | 0 | 3 | 136 / 918 / 0 / 0 / 12 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-14T12:44 | 121,077 | 121,078 | 0 | 0 | 1 | 103 / 898 / 0 / 0 / 12 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 33 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 109,458 to 133,782 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 3, 7. The family sender reads and submits every tier on the desk's private node, which the desk counter reads. The kept public kaspads are read for sync and DAA only.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 7 candidate endpoints passed the check and were 3 kaspads (node 2 is node 1, node 4 is node 1, node 5 is node 1, node 6 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 623240382 | 162,350 | 4 | 0 | 35 |
| 3 | yes | 623240382 | 161,882 | 1 | 0 | 35 |
| 7 | yes | 623240383 | 161,879 | 2 | 0 | 72 |

## Payment senders

| Sender | Node | Pay submit-OK | Rejects | Minutes with a row |
|---|---:|---:|---:|---:|
| 1.1 | 1 | 54,175 | 2 | 4 of 4 |
| 1.2 | 1 | 54,218 | 1 | 4 of 4 |
| 1.3 | 1 | 53,957 | 1 | 4 of 4 |
| 3.1 | 3 | 53,969 | 1 | 4 of 4 |
| 3.2 | 3 | 53,960 | 0 | 4 of 4 |
| 3.3 | 3 | 53,953 | 0 | 4 of 4 |
| 7.1 | 7 | 53,958 | 1 | 4 of 4 |
| 7.2 | 7 | 53,948 | 1 | 4 of 4 |
| 7.3 | 7 | 53,973 | 0 | 4 of 4 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 515 of 515 | 3777 | 15657 |
| kcc | 0 of 0 | - | - |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Every tier has the same hop shape and the same node; only the rate differs.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | Kcc in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: kcc | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 3 mempool | Public 7 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|---:|
| 2026-11-14T12:41 | 3 | 4,063 | 3,230 | 13.63 | 136 | 136 | - | - | 4,296 | 0 / 0 | 12 / 12 | 0 / 0 | 282 | 40,958 | 0 | 278 | 0 | 1 | 0 | 7 | 341.0 / 177.0 / 113.8 | 5,364 | 5,208 | 5,663 |
| 2026-11-14T12:42 | 3 | 2,420 | 2,372 | 12.47 | 91 | 91 | 1 | 40,465 | 2,318 | 0 / 0 | 11 / 11 | 0 / 0 | 282 | 40,659 | 0 | 275 | 0 | 1 | 0 | 5 | 301.8 / 172.3 / 113.4 | 2,798 | 2,570 | 2,571 |
| 2026-11-14T12:43 | 3 | 4,676 | 4,040 | 18.06 | 206 | 195 | - | - | 4,805 | 0 / 0 | 12 / 12 | 0 / 0 | 305 | 104 | 0 | 294 | 0 | 0 | 0 | 6 | 354.2 / 178.3 / 114.0 | 5,071 | 5,014 | 5,004 |
| 2026-11-14T12:44 | 3 | 4,823 | 3,873 | 18.17 | 210 | 210 | - | - | 5,156 | 0 / 0 | 12 / 12 | 0 / 0 | 283 | 40,426 | 0 | 281 | 0 | 1 | 0 | 4 | 331.9 / 176.1 / 113.8 | 6,257 | 6,052 | 6,049 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
