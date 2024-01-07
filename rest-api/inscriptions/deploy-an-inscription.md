---
description: Deploy an Inscription with a name, ticker, max, limit, metadata, and memo.
---

# Deploy an Inscription

### Deployment HCS-20 Structure

This is the stucture that is used to send to the topic, this payload has been humanised to be more understandable.

```
{
  "p": "hcs-20",
  "op": "deploy",
  "name": "point_name",
  "tick": "unique_point_identifier",
  "max": "max_supply",
  "lim": "optional_limit_of_mint_per_transaction",
  "metadata": "optional_metadata",
  "m": "optional_memo"
}
```

### Overview

There are 3 required fields needed to deploy an inscription:

* name
* ticker
* max (supply)

These are the optional fields you can use:

* topic\_id (your private application for controlling all points or inscriptions)
* limit (the amount of points or inscription amount that can be sent in one tx)
* metadata (any HIP412 compliant data, can be used for NFT/Art)
* memo (an additional memo at the deployment level)

{% swagger method="post" path="/api/inscription/deploy" baseUrl="https://hedera-serverless-consensus.vercel.app" summary="" %}
{% swagger-description %}
Deploy an Inscription
{% endswagger-description %}

{% swagger-parameter in="body" name="ticker" required="true" type="" %}
Unique ticker of the inscription
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" required="true" %}
Name of the inscription
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-api-key" required="true" %}
The **API\_SECRET\_KEY** from the client's environment variables.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="max" type="Int" required="true" %}
Supply of the inscription
{% endswagger-parameter %}

{% swagger-parameter in="body" name="topic_id" type="String" %}
your private topic for limiting access&#x20;
{% endswagger-parameter %}

{% swagger-parameter in="body" name="limit" type="Int" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="metadata" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="memo" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="" type="" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Inscription Deployed" %}
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

