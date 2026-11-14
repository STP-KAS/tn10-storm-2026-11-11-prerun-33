MET

Scored on submit-OK, not on inclusion. Inclusion, reported and not scored: in 5 of 10 minutes our payments included (desk counter) were within 10 percent of submit-OK.

# RETURN, desk, pre-run 33

> Our own TN10 testing: what we observed in this run, on our own desk node. Counts only. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

RETURN offers 1,013 payments a second again, one third of 3,040, with the families, the mint line and the guest still up. It asks whether the lines come back after the overload minute.

Payment offer 1,013 tx/s at 150 sompi/gram, from 9 payment senders, 3 per kept public node (3 unique kaspads), each its own process and connection. Families offer 1.2 hop/s, 13 families live, one family-sender process and one builder: floor (families 1–12) 100 sompi/gram on the desk's private node, kcc (families 13–13) 100 sompi/gram on the desk's private node (public map ).

Payment pile: 5,408 coins on the payment key at the preflight, dealt evenly over the 9 senders before the first payment (last deal, repair: 5,408 coins in all, 601 / 601 / 601 / 601 / 601 / 601 / 601 / 601 / 600, even). A deal never holds more coins than the preflight pile. A coin is re-used about once a second, so one sender's ceiling is about its pool per second.

## Submit-OK and included, per minute

| Minute (UTC) | Pay submit-OK | Our payments included | Included, all non-coinbase | Counter |
|---|---:|---:|---:|---|
| 2026-11-14T12:56 | 12,279 | 139,387 | 139,239 | kept pace |
| 2026-11-14T12:57 | 0 | 145,382 | 145,243 | kept pace |
| 2026-11-14T12:58 | 0 | 141,148 | 141,023 | kept pace |
| 2026-11-14T12:59 | 0 | 132,803 | 135,302 | kept pace |
| 2026-11-14T13:00 | 0 | 82,652 | 86,223 | kept pace |
| 2026-11-14T13:01 | 0 | 0 | 4,087 | kept pace |
| 2026-11-14T13:03 | 60,869 | 60,696 | 64,459 | kept pace |
| 2026-11-14T13:04 | 60,960 | 61,136 | 64,752 | kept pace |
| 2026-11-14T13:05 | 60,613 | 60,876 | 64,554 | kept pace |
| 2026-11-14T13:06 | 60,463 | 60,436 | 64,170 | kept pace |

Submit-OK counts in the minute a submit was answered. Included counts in the minute of the chain block that accepted it, so a payment submitted late in one minute can be included in the next. "Kept pace" means the desk node's DAA stayed within 100 of the kept public kaspad and its sink was under 30 s old in every sample of that minute; "LAGGING" means it did not, and the count is what the node had accepted, not a network figure.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | Kcc hops (100) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-14T12:56 | 139,239 | 139,387 | 93 | 0 | 14 | 298 | 2 | 542 | 20 | kept pace |
| 2026-11-14T12:57 | 145,243 | 145,382 | 90 | 0 | 11 | 313 | 1 | 453 | 21 | kept pace |
| 2026-11-14T12:58 | 141,023 | 141,148 | 99 | 0 | 20 | 290 | 1 | 545 | 20 | kept pace |
| 2026-11-14T12:59 | 135,302 | 132,803 | 165 | 0 | 2,383 | 287 | 2 | 548 | 20 | kept pace |
| 2026-11-14T13:00 | 86,223 | 82,652 | 540 | 0 | 3,073 | 315 | 0 | 424 | 19 | kept pace |
| 2026-11-14T13:01 | 4,087 | 0 | 939 | 0 | 3,184 | 406 | 1 | 346 | 20 | kept pace |
| 2026-11-14T13:03 | 64,459 | 60,696 | 639 | 0 | 3,171 | 326 | 0 | 386 | 20 | kept pace |
| 2026-11-14T13:04 | 64,752 | 61,136 | 625 | 0 | 3,043 | 311 | 0 | 529 | 20 | kept pace |
| 2026-11-14T13:05 | 64,554 | 60,876 | 667 | 0 | 3,095 | 331 | 0 | 351 | 19 | kept pace |
| 2026-11-14T13:06 | 64,170 | 60,436 | 719 | 0 | 3,078 | 350 | 0 | 505 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–12, desk private node): 100 sompi/gram per hop. Kcc (families 13–13, desk private node): no rows sompi/gram per hop. In pre-run 33 that rate is on the hop's node-side mass (kit21): the builder is asked for a bill rate on its own mass so that fee / node mass is the tier's rate.

| Tier | Node rate as built, median (min–max) | Bill rate, median | Node mass, median (min–max) | Node rate in the desk mempool, lowest–highest (probe) |
|---|---|---:|---|---|
| floor (100) | 100.12 (100–100.32) | 314 | 40,953 (40,377–43,899) | 100.01–100.3 |
| kcc (100) | - | - | - | - |

Node rate as built is kit21's fee / node mass (rusty-kaspa v2.1.0 storage mass with UTXO plurality, or compute or transient/2 if larger). In the desk mempool the probe divides the node's fee by the larger of the storage and compute mass the node reports.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 4 (330), 11 (213), 10 (197), 9 (189), 13 (174), 14 (171), 8 (163), 7 (153), 15 (145), 16 (135), 6 (122), 5 (109), and 52 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Kcc OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---:|---:|---|
| 2026-11-14T12:56 | 12,279 | 12,279 | 0 | 0 | 0 | 93 / 892 / 0 / 0 / 13 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | no: ok-off;pay_stop;pay_exit;proc_exit |
| 2026-11-14T12:57 | 0 | 0 | 0 | 0 | 0 | 90 / 884 / 0 / 0 / 13 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | no: ok-off;proc-row-missing |
| 2026-11-14T12:58 | 0 | 0 | 0 | 0 | 0 | 98 / 889 / 0 / 0 / 12 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | no: ok-off;proc-row-missing |
| 2026-11-14T12:59 | 0 | 0 | 0 | 0 | 0 | 165 / 927 / 0 / 0 / 12 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | no: ok-off;proc-row-missing |
| 2026-11-14T13:00 | 0 | 0 | 0 | 0 | 0 | 541 / 1051 / 0 / 0 / 13 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | no: ok-off;proc-row-missing |
| 2026-11-14T13:01 | 0 | 0 | 0 | 0 | 0 | 939 / 1202 / 0 / 0 / 13 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | no: ok-off;proc-row-missing |
| 2026-11-14T13:03 | 60,869 | 60,869 | 0 | 0 | 0 | 639 / 1068 / 0 / 0 / 13 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-14T13:04 | 60,960 | 60,960 | 0 | 0 | 0 | 636 / 1073 / 0 / 0 / 12 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-14T13:05 | 60,613 | 60,614 | 0 | 0 | 1 | 655 / 1063 / 0 / 0 / 12 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-14T13:06 | 60,463 | 60,463 | 0 | 0 | 0 | 717 / 1080 / 0 / 0 / 10 | 0 / 0 / 0 / 0 / 0 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 33 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 54,702 to 66,858 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 3, 7. The family sender reads and submits every tier on the desk's private node, which the desk counter reads. The kept public kaspads are read for sync and DAA only.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 7 candidate endpoints passed the check and were 3 kaspads (node 2 is node 1, node 4 is node 1, node 5 is node 1, node 6 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 623252651 | 85,398 | 0 | 0 | 33 |
| 3 | yes | 623252651 | 85,150 | 1 | 0 | 35 |
| 7 | yes | 623252651 | 84,636 | 0 | 0 | 72 |

## Payment senders

| Sender | Node | Pay submit-OK | Rejects | Minutes with a row |
|---|---:|---:|---:|---:|
| 1.1 | 1 | 28,464 | 0 | 5 of 10 |
| 1.2 | 1 | 28,469 | 0 | 5 of 10 |
| 1.3 | 1 | 28,465 | 0 | 5 of 10 |
| 3.1 | 3 | 28,469 | 1 | 5 of 10 |
| 3.2 | 3 | 28,469 | 0 | 5 of 10 |
| 3.3 | 3 | 28,212 | 0 | 5 of 10 |
| 7.1 | 7 | 28,222 | 0 | 5 of 10 |
| 7.2 | 7 | 28,210 | 0 | 5 of 10 |
| 7.3 | 7 | 28,204 | 0 | 5 of 10 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 5221 of 5221 | 806 | 3097 |
| kcc | 0 of 0 | - | - |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Every tier has the same hop shape and the same node; only the rate differs.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | Kcc in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: kcc | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 3 mempool | Public 7 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|---:|
| 2026-11-14T12:56 | 3 (entries skipped: over the read cap) | 542,827 | 5,350 | 25.73 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 391.1 / 181.5 / 114.2 | 545,881 | 545,881 | 545,881 |
| 2026-11-14T12:57 | 3 (entries skipped: over the read cap) | 400,435 | 5,352 | 26.54 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 390.8 / 181.4 / 114.2 | 400,142 | 399,848 | 400,421 |
| 2026-11-14T12:58 | 3 (entries skipped: over the read cap) | 260,752 | 5,282 | 26.80 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 389.3 / 181.3 / 114.2 | 259,273 | 259,272 | 259,273 |
| 2026-11-14T12:59 | 3 (entries skipped: over the read cap) | 127,226 | 3,921 | 22.47 | - | - | - | - | - | - / - | - / - | - / - | 306 | 40,839 | 0 | 0 | 0 | 0 | 0 | 0 | 350.6 / 178.0 / 113.9 | 120,312 | 120,312 | 120,601 |
| 2026-11-14T13:00 | 2 (entries skipped: over the read cap) | 44,356 | 1,970 | 7.59 | 15 | 15 | 4 | 40,990 | 8,362 | 0 / 0 | 7 / 7 | 0 / 0 | 307 | 97,566 | 0 | 306 | 0 | 0 | 0 | 1 | 284.3 / 169.7 / 113.2 | 42,829 | 42,826 | 42,826 |
| 2026-11-14T13:01 | 3 | 12 | 12 | 0.98 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 489,942 | 0 | 0 | 0 | 12 | 0 | 0 | 100.0 / 100.0 / 100.0 | 1 | 1 | 2 |
| 2026-11-14T13:03 | 3 | 309 | 309 | 2.28 | 8 | 8 | - | - | 282 | 0 / 0 | 12 / 12 | 0 / 0 | 209 | 163,485 | 0 | 200 | 0 | 4 | 0 | 5 | 123.8 / 116.2 / 104.7 | 596 | 758 | 757 |
| 2026-11-14T13:04 | 3 | 223 | 223 | 1.59 | 6 | 6 | - | - | 212 | 0 / 0 | 11 / 11 | 0 / 0 | 215 | 123,718 | 0 | 212 | 0 | 3 | 0 | 6 | 100.0 / 100.0 / 100.0 | 741 | 674 | 674 |
| 2026-11-14T13:05 | 3 | 246 | 246 | 1.48 | 1 | 1 | - | - | 235 | 0 / 0 | 9 / 9 | 0 / 0 | 235 | 123,028 | 0 | 232 | 0 | 3 | 0 | 1 | 100.0 / 100.0 / 100.0 | 555 | 422 | 763 |
| 2026-11-14T13:06 | 3 | 18 | 340 | 2.05 | 0 | 0 | - | - | 328 | 0 / 0 | 12 / 12 | 0 / 0 | 283 | 41,054 | 0 | 282 | 0 | 1 | 0 | 0 | 172.5 / 140.7 / 109.5 | 453 | 339 | 339 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
