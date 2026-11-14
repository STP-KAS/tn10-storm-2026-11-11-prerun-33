> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · This page does not start a machine. Pre-run 33. Not Wednesday. Not Tuesday. Not pre-runs 1 to 32.

# Targets

**Question.** Open question 10 in tn-master asks whether covenant families still land when simple payments are offered at one third, two thirds, three thirds and one minute at four thirds of 3,040 payments a second. Pre-run 32 ran the three lines (12 covenant families, one KCC-20 mint line, one tic-tac-toe match) with no payment of ours, and the ready mass sat near one block. That is not this question. This run keeps those three lines up and adds the payment ladder.

**Target.** Between `PRE-RUN-OPEN` and the end of RETURN, at least one covenant hop, one KCC-20 mint and one tic-tac-toe carrier are accepted on our desk node. Each scored payment step is three clean minutes of submit-OK within 10 percent, or `NOT MET` after one repair. The 4,053 minute is an observation. The run names the first component that falls behind. Retry count 0.

## The one knob, written before the arm

**The payment offer.** 1,013, then 2,027, then 3,040, then one minute at 4,053, then 1,013 again. Payments pay 150 sompi per gram. They go to the kept public TN10 nodes, the same shape as the earlier payment pre-runs. The families, the mint line and the guest stay on the desk node.

What stays put, so it is not a second knob:

- Twelve covenant families at 100 sompi per gram of node mass, 1.2 hops a second, one sender, one builder.
- The KCC-20 mint line, one mint at a time, 15 s after each accept. The cap is 120 so the line is still minting at the overload minute. Pre-run 32's cap of 30 would have finished before this ladder.
- Tic-tac-toe matches, one carrier at a time, repeating until RETURN. A carrier counts only when its id is among the desk node's accepted ids.
- No heavy lane. The desk node is not restarted. We do not stop it for this send. The Wednesday page describes a send with that process stopped. This pre-run cannot do that: the three lines and the counter read that node.

Two recorded facts that are not a second knob:

- The Mini is not reachable from this desk. This run has one counter, the desk node. [logs/MINI-NOT-REACHABLE.md](../logs/MINI-NOT-REACHABLE.md) is on origin before the arm. We do not write a Mini-armed file.
- Keys 1 and 2 are not used. One distinct key per family. The payment pile is a different key. The tool counts a pile coin only when it is over 10 tKAS (and under 100,000). A coin is reused about once a second, so the 4,053 minute needs at least that many coins. The payment key holds about 69,000 tKAS, which funds on the order of 5,500 coins at 12 tKAS, not 6,000. 5,500 still covers 4,053, with less spare than the old 6,000 line. We wait until those coins' block DAA is behind the tip before the open, because a fresh coin with sequence 0 is rejected until then. If a family key has no coin of at least 15 tKAS after pre-run 32, it receives 20 tKAS from the sender key before the hashes. That top-up is logged.

## A correction on this page, before any submit

The first commit of this plan said the pile coins had to be above 1 tKAS, and that we would cut at least 6,000 of them. That was our misreading. The preflight counts a coin only above 10 tKAS. This paragraph is the correction. The prediction page is not touched.

## What we are checking in our own earlier pages

- Pre-run 32's count files say the family count was "raised from 4". The lock for that run says 8 → 12. The "4" is leftover text in the runner. We do not treat it as the knob, and we do not edit that prediction page.
- Pre-run 32's early minutes landed about 870–930 floor hops a minute with ready mass about one block, while other traffic on our node stayed near 3,100 a minute. That is a quiet combined load next to 3,040 payments a second. It does not answer the ladder.
- A guest tool that reads an older abort line in the same log will record zero carriers. This run's guest tool reads only the log written after the match starts.

## Order

1. Disk floor written. Desk free space at 2026-11-14T11:59:23Z: 340.05 GB. Abort under 150 GB. The desk node is not restarted.
2. Free check, read-only, committed before any submit. Names that do not answer are logged and dropped. A raw address found by a scan is not a send target.
3. Payment-pile split, logged, before the hashes. Coins over 10 tKAS, about 12 tKAS each, as many as the payment key can fund (about 5,500, not 6,000). Family top-up only if a key is short. The new coins are left until their block DAA is behind the tip.
4. Hashes first. Thirteen rows in [hashes/SIXTEEN.md](../hashes/README.md) (the file keeps that name). The offline check builds them and does not submit.
5. `PRE-RUN-OPEN`, then genesis of the thirteen covenants, then the lines, then the ladder.

| Order | File | Payments | What else runs |
|---:|---|---|---|
| 1 | BASE | none | families, mint line, guest. 2 whole minutes. Not scored |
| 2 | HOLD-1 | 1,013 tx/s | the three lines stay up |
| 3 | HOLD-2 | 2,027 tx/s | the same |
| 4 | HOLD-3 | 3,040 tx/s | the same |
| 5 | HOLD-4 | 4,053 tx/s | one pinned minute. Not scored |
| 6 | RETURN | 1,013 tx/s | the same, to see whether the lines come back |
| 7 | tail | stopped | the counter reads on for 5 minutes |

The knob is the offer. It changes on the schedule above and not otherwise. One repair per scored step, the same handoff the earlier payment runs used, and then the step stands.

## Cohorts

| Cohort | Families | Rate, sompi/gram of node mass | Where |
|---|---|---:|---|
| floor | 1–12 | 100 | desk node |
| kcc | 13 | 100 | desk node, the mint line |
| payments | — | 150 sompi/gram, on the payment's own mass | kept public TN10 nodes |

Finding 1 is the capacity line we are using: about 304–308 simple payments in a full block, about 3,040–3,080 a second at 10 blocks a second. 1,013, 2,027, 3,040 and 4,053 are one third, two thirds, three thirds and four thirds of the low edge. We may be dividing it wrong. The count files will say what the node did.
