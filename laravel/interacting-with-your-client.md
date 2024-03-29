---
description: How to get started with the laravel package.
---

# Interacting with your client

## Recording a trust event

Events can only be recorded using a single private key, this is the default behaviour. This means that you and your users can Trust that the messages will only come from you, the owner of the hedera private key.&#x20;

If a **Topic** doesn't exist in your database one will be created before the consensus message is dispatched.

### Imports

```
use Trustenterprises\LaravelHashgraph\LaravelHashgraph;
use Trustenterprises\LaravelHashgraph\Models\ConsensusMessage;
```

### Code

The Consensus Message takes a **String** if you wish to use an object convert it first using **json\_encode.** We suggest that this code should be run in a Job as it uses the synchronous&#x20;

```
$message = new ConsensusMessage('This is an event you wish to store');
$message->setReference('an-internal-model-id'); // optional

LaravelHashgraph::withTopic('Trust Enterprises')->sendMessage($message);
```

## Extending behaviour with event listenters

There are 2 events that can be listened to:

* ConsensusMessageWasReceived&#x20;
* TopicWasCreated

Have a look at the [Laravel offical docs for events](https://laravel.com/docs/8.x/events) for creating your own listenters for events.





 
