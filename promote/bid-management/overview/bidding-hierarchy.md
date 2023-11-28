# Bidding hierarchy

You can configure bids for different levels of granularity:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-03 at 15.43.46.png" alt="" width="375"><figcaption></figcaption></figure>

## **Campaign-level bids**

These bids apply to all ads for the campaign that don't match any more specific bidding criteria.

## **Country-level bids**

These bids apply to ads in your campaign that target a specific country. All other ads will fall back to the campaign-level bid.

## **AdSet-level bids**

These bids apply to ads in your campaign that are part of a specific AdSet. All other ads will fall back to the appropriate country or campaign-level bid.

## **Source-level bids**

These bids apply to ads in your campaign that are shown in some specific source content, such as in another app or a website. All ads shown in other content sources will fall back to the appropriate AdSet, country, or campaign-level bid.

## **Example**

Here is an example of how bid configurations are applied to different cases. These are ordered from the most general to the most specific:

<table><thead><tr><th width="153">AdSetId</th><th width="146">Country</th><th width="169">CampaignId</th><th width="172">SourceId</th><th>Bid</th></tr></thead><tbody><tr><td></td><td></td><td>123</td><td></td><td>0.5</td></tr><tr><td></td><td>DE</td><td>123</td><td></td><td>0.1</td></tr><tr><td>456</td><td>DE</td><td>123</td><td></td><td>0.05</td></tr><tr><td>456</td><td>DE</td><td>123</td><td>789</td><td>0.03</td></tr></tbody></table>

{% hint style="warning" %}
This example provides a simplified version of the bid upload data. This would not be valid for a CSV upload. Refer to our [Bid upload CSV format](bid-upload-csv-format.md) for the correct columns.
{% endhint %}
