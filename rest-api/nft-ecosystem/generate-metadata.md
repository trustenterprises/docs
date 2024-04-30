---
description: >-
  Helping you to generate and pin HIP412 compliant metadata for your minted NFTs
  in your collection inside of IPFS through NFT storage.
---

# Generate Metadata

### Overview&#x20;

Metadata is what we refer to as a structure [that conforms to HIP412](https://hips.hedera.com/hip/hip-412), to ensure that it is processable for down-stream clients such as wallets like [Hashpack](https://www.hashpack.app/). Upon successful validation, you will be provided a **CID** as a unique reference to an IPFS pin for minting NFTs.

You should handle the media uploads by default, this is handled through the[ tools provided by filebase](https://filebase.com/), or [using NFTup](https://nft.storage/docs/quickstart/#uploading-files--directories-via-the-nftup-application) for directories.&#x20;

Below is an example of valid metadata, but the validation has been handcrafted in the API to strictly handle many variations of HIP412, based on spec and examples.

If your JSON structure does **not comply with the rules of the aforementioned HIP a status of 422** will be returned with a detailed error response on the issue.

![Basic metadata to generate CID](<../../.gitbook/assets/Screenshot 2022-08-15 at 08.11.34.png>)

### Environment Variables

Remember, for complete management of NFT over an API for the creation, minting, metadata generation, and advanced transfer feature you need both the **NFT\_STORAGE\_TOKEN** and **MIRROR\_NODE\_URL** set.

{% content-ref url="../../deployment/environment-variables.md" %}
[environment-variables.md](../../deployment/environment-variables.md)
{% endcontent-ref %}

<mark style="color:green;">`POST`</mark> `https://hedera-serverless-consensus.vercel.app/api/nft/metadata`

Generate the metadata based on a valid structure

#### Headers

| Name                                        | Type   | Description                                                       |
| ------------------------------------------- | ------ | ----------------------------------------------------------------- |
| x-api-key<mark style="color:red;">\*</mark> | String | The **API\_SECRET\_KEY** from the client's environment variables. |

#### Request Body

| Name                                 | Type | Description                     |
| ------------------------------------ | ---- | ------------------------------- |
| {}<mark style="color:red;">\*</mark> | json | Compliant HIP412 JSON structure |

{% tabs %}
{% tab title="200: OK Returns a CID" %}
```javascript
{
    // Response
}
```
{% endtab %}

{% tab title="401: Unauthorized Header Auth Missing/invalid" %}
```javascript
{
    // Response
}
```
{% endtab %}

{% tab title="422: Unprocessable Entity JSON structure does not comply with HIP412" %}
```javascript
{
    // Response
}
```
{% endtab %}
{% endtabs %}
