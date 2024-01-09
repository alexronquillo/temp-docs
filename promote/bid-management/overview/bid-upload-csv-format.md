# Bid upload CSV format

When you upload a CSV to manage bids in bulk, your CSV must have the following format:

| Column Name    | Required | Description                                                                                                                                                                                                |
| -------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AdSetId        |          | <p>The adset Id from justtrack.<br><br><strong>Note:</strong> not all partners support bidding at the adset level.</p>                                                                                     |
| Country        | ✅        | The two-digit [ISO 3166 code](https://www.iso.org/obp/ui/#search) for the bid's target country. For example: `DE` or `FR`                                                                                  |
| CampaignId     | ✅        | The campaign id from justtrack.                                                                                                                                                                            |
| CampaignName   |          | <p>The name of the campaign.<br><br><strong>Note:</strong> This is to help you keep track of the data in your CSV. We ignore this value. Instead, we use the campaign Id to look up the campaign name.</p> |
| SourceId       |          | The identifier for the source in which the ad is shown.                                                                                                                                                    |
| SourceBundleId |          | The bundle Id or package name of the app in which the ad is shown.                                                                                                                                         |
| OptimalBidUsd  | ✅        | <p>The USD ($) target bid value. For example <code>0.20</code>.<br><br><strong>Note:</strong> The number of supported digits depends on the partner.</p>                                                   |
| Delete         | ✅        | An indication of whether we should delete the bid. `true` means delete. `false` means do not delete.                                                                                                       |

{% hint style="info" %}
Instead of creating this format yourself, you can [download our sample CSV ](../configure-bids-with-a-csv.md#download-the-sample-csv)from the **Bid Uploads** page and fill in your bid configurations. If you use this method, don't delete any unused columns. Otherwise, the format will no longer be valid.
{% endhint %}
