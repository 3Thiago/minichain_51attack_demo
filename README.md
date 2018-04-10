# minichain_51attack_demo

an implementation of bad node that denies every blocks generated by pure nodes.


How it works
----
```cs
protected override void OnNewBlock(Peer sender, PktBroadcastNewBlock pkt)
{
  // Check this block is mined by alias
  if (badNodeAddrs.Contains(pkt.block.minerAddr) == false) return;

  base.OnNewBlock(sender, pkt);
}
```
