> **Experimental. We are just trying this.** [Disclaimer](../../DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value. Counts only.

> **Our own testing.** What this page shows is what our probe read on our own desk node in this run; it is not a claim of how TN10 behaves in general.

# Mempool and template timeline, pre-run 33

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.

## The run

Step is the runner's step at the minute's start (see TIMELINE.md).

| Minute (UTC) | Step | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | Kcc in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: kcc | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 3 mempool | Public 7 mempool |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|---:|
| 2026-11-14T12:31 | BASE | 3 | 12 | 12 | 0.99 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 495,133 | 0 | 0 | 0 | 12 | 0 | 0 | 100.0 / 100.0 / 100.0 | 1 | 1 | 1 |
| 2026-11-14T12:32 | BASE | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 1 | 1 | 1 |
| 2026-11-14T12:33 | BASE | 3 | 2 | 2 | 0.44 | 0 | 0 | - | - | 0 | 0 / 0 | 1 / 1 | 0 / 0 | 2 | 221,225 | 0 | 0 | 0 | 1 | 0 | 0 | 100.0 / 100.0 / 100.0 | 3 | 0 | 4 |
| 2026-11-14T12:34 | HOLD-1 | 3 | 13 | 13 | 1.07 | 0 | 0 | - | - | 0 | 0 / 0 | 11 / 11 | 0 / 0 | 12 | 450,292 | 0 | 0 | 0 | 11 | 0 | 0 | 100.0 / 100.0 / 100.0 | 3 | 1 | 1 |
| 2026-11-14T12:35 | HOLD-1 | 3 | 360 | 325 | 2.24 | 2 | 2 | 2 | 41,110 | 312 | 0 / 0 | 10 / 10 | 0 / 0 | 209 | 164,418 | 0 | 205 | 0 | 4 | 0 | 0 | 261.5 / 165.8 / 112.8 | 456 | 384 | 372 |
| 2026-11-14T12:36 | HOLD-1 | 3 | 368 | 239 | 1.57 | 6 | 6 | - | - | 223 | 0 / 0 | 10 / 10 | 0 / 0 | 209 | 164,694 | 0 | 203 | 0 | 4 | 0 | 2 | 232.5 / 159.5 / 112.1 | 797 | 831 | 772 |
| 2026-11-14T12:37 | HOLD-1 | 3 | 12 | 466 | 2.42 | 1 | 1 | - | - | 453 | 0 / 0 | 12 / 12 | 0 / 0 | 283 | 40,874 | 0 | 280 | 0 | 1 | 0 | 0 | 238.0 / 160.8 / 112.2 | 449 | 340 | 406 |
| 2026-11-14T12:38 | HOLD-1 | 3 | 240 | 363 | 2.15 | 6 | 6 | 6 | 41,579 | 344 | 0 / 0 | 12 / 12 | 0 / 0 | 235 | 121,729 | 0 | 232 | 0 | 3 | 0 | 0 | 200.0 / 150.6 / 110.9 | 582 | 921 | 916 |
| 2026-11-14T12:39 | HOLD-1 | 3 | 289 | 432 | 2.30 | 6 | 6 | 1 | 40,873 | 384 | 0 / 0 | 10 / 10 | 0 / 0 | 231 | 123,860 | 0 | 216 | 0 | 3 | 0 | 5 | 239.4 / 161.2 / 112.3 | 657 | 612 | 661 |
| 2026-11-14T12:40 | HOLD-2 | 3 | 458 | 468 | 2.50 | 1 | 1 | - | - | 455 | 0 / 0 | 12 / 12 | 0 / 0 | 259 | 82,035 | 0 | 257 | 0 | 2 | 0 | 1 | 202.4 / 151.3 / 111.0 | 1,821 | 1,820 | 1,822 |
| 2026-11-14T12:41 | HOLD-2 | 3 | 4,063 | 3,230 | 13.63 | 136 | 136 | - | - | 4,296 | 0 / 0 | 12 / 12 | 0 / 0 | 282 | 40,958 | 0 | 278 | 0 | 1 | 0 | 7 | 341.0 / 177.0 / 113.8 | 5,364 | 5,208 | 5,663 |
| 2026-11-14T12:42 | HOLD-2 | 3 | 2,420 | 2,372 | 12.47 | 91 | 91 | 1 | 40,465 | 2,318 | 0 / 0 | 11 / 11 | 0 / 0 | 282 | 40,659 | 0 | 275 | 0 | 1 | 0 | 5 | 301.8 / 172.3 / 113.4 | 2,798 | 2,570 | 2,571 |
| 2026-11-14T12:43 | HOLD-2 | 3 | 4,676 | 4,040 | 18.06 | 206 | 195 | - | - | 4,805 | 0 / 0 | 12 / 12 | 0 / 0 | 305 | 104 | 0 | 294 | 0 | 0 | 0 | 6 | 354.2 / 178.3 / 114.0 | 5,071 | 5,014 | 5,004 |
| 2026-11-14T12:44 | HOLD-2 | 3 | 4,823 | 3,873 | 18.17 | 210 | 210 | - | - | 5,156 | 0 / 0 | 12 / 12 | 0 / 0 | 283 | 40,426 | 0 | 281 | 0 | 1 | 0 | 4 | 331.9 / 176.1 / 113.8 | 6,257 | 6,052 | 6,049 |
| 2026-11-14T12:45 | HOLD-3 | 3 (entries skipped: over the read cap) | 8,096 | 5,254 | 23.39 | 288 | 252 | - | - | 10,086 | 0 / 0 | 12 / 12 | 0 / 0 | 282 | 41,171 | 0 | 276 | 0 | 0 | 0 | 5 | 381.8 / 180.7 / 114.2 | 10,343 | 11,940 | 11,751 |
| 2026-11-14T12:46 | HOLD-3 | 3 (entries skipped: over the read cap) | 74,723 | 5,761 | 25.02 | - | - | - | - | - | - / - | - / - | - / - | 306 | 98 | 0 | 0 | 0 | 0 | 0 | 0 | 397.3 / 181.9 / 114.3 | 81,104 | 80,843 | 81,742 |
| 2026-11-14T12:47 | HOLD-3 | 3 (entries skipped: over the read cap) | 133,400 | 5,698 | 25.03 | - | - | - | - | - | - / - | - / - | - / - | 305 | 110 | 0 | 0 | 0 | 0 | 0 | 0 | 396.3 / 181.8 / 114.3 | 139,353 | 139,358 | 139,855 |
| 2026-11-14T12:48 | HOLD-3 | 3 (entries skipped: over the read cap) | 181,824 | 5,642 | 25.07 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 395.4 / 181.8 / 114.3 | 185,516 | 185,870 | 185,493 |
| 2026-11-14T12:49 | HOLD-3 | 3 (entries skipped: over the read cap) | 237,136 | 5,457 | 24.62 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 393.1 / 181.6 / 114.2 | 242,012 | 242,270 | 241,492 |
| 2026-11-14T12:50 | HOLD-3 | 3 (entries skipped: over the read cap) | 287,125 | 5,357 | 24.32 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 390.9 / 181.4 / 114.2 | 294,702 | 293,711 | 294,807 |
| 2026-11-14T12:51 | HOLD-3 | 3 (entries skipped: over the read cap) | 336,078 | 5,355 | 24.92 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 390.4 / 181.4 / 114.2 | 344,953 | 344,927 | 345,036 |
| 2026-11-14T12:52 | HOLD-3 | 3 (entries skipped: over the read cap) | 389,141 | 5,359 | 25.71 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 390.4 / 181.4 / 114.2 | 398,151 | 398,476 | 397,945 |
| 2026-11-14T12:53 | HOLD-4 | 3 (entries skipped: over the read cap) | 459,774 | 5,361 | 26.75 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 390.3 / 181.4 / 114.2 | 477,242 | 476,896 | 476,510 |
| 2026-11-14T12:54 | HOLD-4 | 3 (entries skipped: over the read cap) | 562,501 | 5,360 | 27.00 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 390.4 / 181.4 / 114.2 | 586,821 | 586,584 | 587,462 |
| 2026-11-14T12:55 | RETURN | 3 (entries skipped: over the read cap) | 645,343 | 5,357 | 26.94 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 390.5 / 181.4 / 114.2 | 653,508 | 653,201 | 653,731 |
| 2026-11-14T12:56 | RETURN | 3 (entries skipped: over the read cap) | 542,827 | 5,350 | 25.73 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 391.1 / 181.5 / 114.2 | 545,881 | 545,881 | 545,881 |
| 2026-11-14T12:57 | RETURN | 3 (entries skipped: over the read cap) | 400,435 | 5,352 | 26.54 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 390.8 / 181.4 / 114.2 | 400,142 | 399,848 | 400,421 |
| 2026-11-14T12:58 | RETURN | 3 (entries skipped: over the read cap) | 260,752 | 5,282 | 26.80 | - | - | - | - | - | - / - | - / - | - / - | - | - | - | - | - | - | - | - | 389.3 / 181.3 / 114.2 | 259,273 | 259,272 | 259,273 |
| 2026-11-14T12:59 | RETURN | 3 (entries skipped: over the read cap) | 127,226 | 3,921 | 22.47 | - | - | - | - | - | - / - | - / - | - / - | 306 | 40,839 | 0 | 0 | 0 | 0 | 0 | 0 | 350.6 / 178.0 / 113.9 | 120,312 | 120,312 | 120,601 |
| 2026-11-14T13:00 | RETURN | 2 (entries skipped: over the read cap) | 44,356 | 1,970 | 7.59 | 15 | 15 | 4 | 40,990 | 8,362 | 0 / 0 | 7 / 7 | 0 / 0 | 307 | 97,566 | 0 | 306 | 0 | 0 | 0 | 1 | 284.3 / 169.7 / 113.2 | 42,829 | 42,826 | 42,826 |
| 2026-11-14T13:01 | RETURN | 3 | 12 | 12 | 0.98 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 489,942 | 0 | 0 | 0 | 12 | 0 | 0 | 100.0 / 100.0 / 100.0 | 1 | 1 | 2 |
| 2026-11-14T13:02 | RETURN | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 1 | 1 | 1 |
| 2026-11-14T13:03 | RETURN | 3 | 309 | 309 | 2.28 | 8 | 8 | - | - | 282 | 0 / 0 | 12 / 12 | 0 / 0 | 209 | 163,485 | 0 | 200 | 0 | 4 | 0 | 5 | 123.8 / 116.2 / 104.7 | 596 | 758 | 757 |
| 2026-11-14T13:04 | RETURN | 3 | 223 | 223 | 1.59 | 6 | 6 | - | - | 212 | 0 / 0 | 11 / 11 | 0 / 0 | 215 | 123,718 | 0 | 212 | 0 | 3 | 0 | 6 | 100.0 / 100.0 / 100.0 | 741 | 674 | 674 |
| 2026-11-14T13:05 | RETURN | 3 | 246 | 246 | 1.48 | 1 | 1 | - | - | 235 | 0 / 0 | 9 / 9 | 0 / 0 | 235 | 123,028 | 0 | 232 | 0 | 3 | 0 | 1 | 100.0 / 100.0 / 100.0 | 555 | 422 | 763 |
| 2026-11-14T13:06 | RETURN | 3 | 18 | 340 | 2.05 | 0 | 0 | - | - | 328 | 0 / 0 | 12 / 12 | 0 / 0 | 283 | 41,054 | 0 | 282 | 0 | 1 | 0 | 0 | 172.5 / 140.7 / 109.5 | 453 | 339 | 339 |
| 2026-11-14T13:07 | tail | 3 | 5 | 110 | 1.14 | 0 | 0 | - | - | 100 | 0 / 0 | 10 / 10 | 0 / 0 | 108 | 122,821 | 0 | 100 | 0 | 3 | 0 | 0 | 100.0 / 100.0 / 100.0 | 451 | 343 | 372 |
| 2026-11-14T13:08 | tail | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 | 1 |
| 2026-11-14T13:09 | tail | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 | 1 |
| 2026-11-14T13:10 | tail | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 | 0 |
| 2026-11-14T13:11 | tail | 3 | 0 | 0 | 0.00 | 0 | 0 | 1 | 3,362 | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 | 1 |
| 2026-11-14T13:12 | tail | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 1 | 0 | 1 |
