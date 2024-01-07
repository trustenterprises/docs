---
description: Burn an Inscription with an amount, ticker, and from address.
---

# Burn an Inscription

### Burn HCS-20 Structure

This is the stucture that is used to send to the topic, this payload has been humanised to be more understandable.

```
{
  "p": "hcs-20",
  "op": "burn",
  "tick": "unique_point_identifier",
  "amt": "number_of_points",
  "from": "recipient_hedera_address",
  "m": "optional_memo"
}
```

### Overview

There are 2 required fields needed to burn an inscription:

* from
* amount

These are the optional fields you can use:

* topic\_id (your private application for controlling all points or inscriptions)
* memo (an additional memo at the deployment level)

{% swagger method="post" path="/api/inscription/{ticker}/burn" baseUrl="https://hedera-serverless-consensus.vercel.app" summary="" %}
{% swagger-description %}
Mint an Inscription
{% endswagger-description %}

{% swagger-parameter in="body" name="from" %}
from address to burn
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-api-key" required="true" %}
The **API\_SECRET\_KEY** from the client's environment variables.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Int" required="true" %}
amount to mint in one transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="topic_id" type="String" %}
your private topic for limiting access&#x20;
{% endswagger-parameter %}

{% swagger-parameter in="body" name="memo" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="query" name="ticker" required="true" %}
Unique ticker of the inscription
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Inscription Minted" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Header Auth Missing/invalid" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="422: Unprocessable Entity" description="Missing params in body" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

