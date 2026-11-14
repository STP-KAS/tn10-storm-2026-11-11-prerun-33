> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> **This is a pre-run. Pre-run 33.** It is not the Wednesday run. It is not the Tuesday run. It is not pre-run 1 to 32, and it does not edit their repos. A read does not start a runner.

# tn10-storm-2026-11-11-prerun-33

**Pre-run 33: covenants, KCC-20 and tic-tac-toe, held up under a payment ladder at one third, two thirds, three thirds and four thirds of 3,040 tx/s.** The neuron stays [tn10-storm-2026-11-11](https://github.com/STP-KAS/tn10-storm-2026-11-11). This repo does not edit that repo.

> **Our own testing.** This is our own Kaspa Testnet-10 testing, run on our own machines and nodes. What these pages report is what we observed in this run; it is not a claim of how TN10 or Kaspa behave in general.

| Field | Value |
|---|---|
| Target | The three lines from pre-run 32 stay up while simple payments are offered at 1,013, then 2,027, then 3,040, then one minute at 4,053, then 1,013 again. At least one hop, one mint and one guest carrier land in the open window. The run names the first line that falls behind |
| The change | One knob: the payment offer, on finding 1's line of 3,040 payments a second. Families stay at 12. No heavy lane |
| Met or not met | **met** on the three-part target: 13,620 covenant hops, 30 of 30 mints, 8 of 8 guest carriers, in one window (2026-11-14T12:30:15Z to 2026-11-14T13:13:03Z). The capacity reading is in the timeline: floor hops left their quiet pace at the 1,013 step; payment submit-OK stayed near the offer through 3,040 and the one minute near 4,053, while same-minute inclusion of our payments stayed near 123,000–133,000 a minute at those two steps |
| Retry count | 0. Does not retry a run. Follows pre-run 32 (12 families, mint cap 30, one guest match, no payment of ours) |
| Core tags | 1 (0 of 1,440 accepted ids still listed) |
| Status | done. Desk counter. Not Pulse's count |

Plan, lock, and the prediction are in [plan/PLAN.md](plan/PLAN.md), [locks/LOCKED.md](locks/LOCKED.md), and [plan/PREDICTIONS.md](plan/PREDICTIONS.md). Written before any submit. The prediction page is unchanged.

Counts: [counts/desk/TARGET.md](counts/desk/TARGET.md), [counts/chain/TIMELINE.md](counts/chain/TIMELINE.md), [counts/chain/FIRST-BEHIND.md](counts/chain/FIRST-BEHIND.md), [logs/LESSONS.md](logs/LESSONS.md).
