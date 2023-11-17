# Bid upload validation

When you upload bids in bulk, whether with a [CSV](../configure-bids-with-a-csv.md) or our [API](http://127.0.0.1:5000/s/hrcsPPQosGhAkTL0m2NJ/management-api/bid-upload), we validate your data. If there are issues with the data, we reject the full bid upload request so you can address those issues and try again. If we find no issues, we'll update your bids.

## CSV upload validation

<figure><img src="../../.gitbook/assets/csv-validation (3).png" alt="" width="563"><figcaption><p>CSV Validation Modal</p></figcaption></figure>

When you upload a CSV for bids, we display a modal where you can see the validation results.

{% hint style="info" %}
You can read more about upload errors in our API documentation.
{% endhint %}

## API upload validation

If you're using the bid upload API, review our API documentation to learn more about the possible responses you may receive after we validate your data.

####
