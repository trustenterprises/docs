---
description: >-
  This functionality implements the HCS-20 standard, and evolves with it over
  time. It provides all the alpha features expected including deploying,
  minting, burning, and transfer.
---

# Inscriptions

> It is inspired by the BRC-20 protocol on Ordinals and has extended the functionality to auditable points in addition to introducing inscriptions on Hedera / Hashinals.

{% hint style="warning" %}
This feature is considered to be in an **Alpha** state, and that any code may change at anytime. We may additionally update this documentation to reflect the updated standards for dealing with this meta-protocol.

But due to the low-cost nature of HCS there is lower overhead to rectify issues.

Use at your own risk but have fun.
{% endhint %}

On **mainnet e**very inscription call may provide a custom topic for private usage but it will always default to the public topic of [0.0.4350190](https://hashscan.io/mainnet/topic/0.0.4350190).

These are the calls as follows:

### Deploy an Inscription

{% content-ref url="deploy-an-inscription.md" %}
[deploy-an-inscription.md](deploy-an-inscription.md)
{% endcontent-ref %}

### Mint an Inscription

{% content-ref url="mint-an-inscription.md" %}
[mint-an-inscription.md](mint-an-inscription.md)
{% endcontent-ref %}

### Burn an Inscription

{% content-ref url="burn-an-inscription.md" %}
[burn-an-inscription.md](burn-an-inscription.md)
{% endcontent-ref %}

### Transfer an Inscription

{% content-ref url="transfer-an-inscription.md" %}
[transfer-an-inscription.md](transfer-an-inscription.md)
{% endcontent-ref %}
