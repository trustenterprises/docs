---
description: >-
  The Laravel client provides the programmatic ability to manage the entire
  lifecycle of inscriptions, for deployments, minting, burning, and
  transferring.
---

# Manage your Inscription Flow

This provides inscription capibility for PHP, you can view the tests where appropriate but the features mirror the inscription API for:

* deploying
* minting
* burning
* transferring

Every response through the Inscription methods will return a **InscriptionResponse** object that includes the raw inscription data and related consensus message ids for storage.

{% hint style="warning" %}
This feature is considered to be in an **Alpha** state, and that any code may change at anytime. We may additionally update this documentation to reflect the updated standards for dealing with this meta-protocol.

Have fun!
{% endhint %}

These examples consider a **private topic as a points system on testnet.** If you don't set the private topic on mainnet it will default to the default HCS-20 topic

## Deploying an Inscription

### Imports

```
use Trustenterprises\LaravelHashgraph\LaravelHashgraph;
use Trustenterprises\LaravelHashgraph\Models\Inscriptions\BurnInscription;
use Trustenterprises\LaravelHashgraph\Models\Inscriptions\DeployInscription;
use Trustenterprises\LaravelHashgraph\Models\Inscriptions\MintInscription;
use Trustenterprises\LaravelHashgraph\Models\Inscriptions\TransferInscription;
```

### Code

```
$deploy = new DeployInscription('TICK1', 'Ticker', 300);
$deploy->setPrivateTopic("7459744");

$minted = LaravelHashgraph::deployInscription($deploy);

```

## Mint an Inscription

### Code

```
$mint = new MintInscription('TICK1', '0.0.1', 1);
$mint->setPrivateTopic("7459744");

$minted = LaravelHashgraph::mintInscription($mint);
```

## Burn an Inscription

### Code

```
$burn = new BurnInscription('TICK1', '0.0.1', 1);
$burn->setPrivateTopic("7459744");

$minted = LaravelHashgraph::burnInscription($burn);
```

## Transfer an Inscription

### Code

```
$transfer = new TransferInscription('TICK1', '0.0.1', '0.0.2', 1);
$transfer->setPrivateTopic("7459744");

$minted = LaravelHashgraph::transferInscription($transfer);
```
