> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · Kaspa Testnet-10 only. tKAS has no value.

# Lock (pre-run 33)

Locked before the first submit.

- Network: Testnet-10. The desk node is not restarted and it is not stopped.
- One knob: the payment offer. 1,013, then 2,027, then 3,040, then one minute at 4,053, then 1,013. Fee 150 sompi per gram. Those payments go to the kept public TN10 nodes.
- Families stay at 12, floor 100 on node mass, 1.2 hops a second, on the desk node. The mint line stays one at a time, cap 120, on the desk node. Guest matches repeat until RETURN, on the desk node.
- No heavy lane.
- One counter: the desk node. The Mini is not reachable. No Mini-armed file.
- Keys 1 and 2 are not used. One distinct key per family. The payment pile is split, before the hashes, into coins over 10 tKAS. The payment key can fund about 5,500 coins at 12 tKAS. That is the pile. It is not spent until those coins' block DAA is behind the tip.
- Disk line: abort if the desk is under 150 GB free. It was 340.05 GB at 2026-11-14T11:59:23Z.
- A miss is a retry with the fix written first. This page is not rewritten to match the result.
