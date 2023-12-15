# Analyze user retention

One of the most common use cases for _Cohort Analysis_ is analyzing user retention. In this case, you want to understand how often users come back to your app after they first install it.

In this guide, you'll learn how to:

* Configure the _Cohort Analysis_ table to display user retention for specific apps.
* Visualize some important retention data.

## Navigate to Cohort Analysis

In the _Main Menu_, click [**App Analytics -> Cohort Analysis**](https://dashboard.justtrack.io/app-analytics/cohort-analysis)**:**

<figure><img src="../.gitbook/assets/Screenshot 2023-12-15 at 10.51.19.png" alt=""><figcaption><p>Cohort Analysis</p></figcaption></figure>

## Narrow your user segment

Before you configure your cohort and metrics, you need to narrow the user segment. In this guide, you'll narrow the segment by application so you can analyze the retention for a specific subset of apps:

1. Click the default **All Users** segment.
2. Choose the app or apps you want to analyze.
3. Click **Apply**.

<figure><img src="../.gitbook/assets/segments (3).png" alt="" width="563"><figcaption><p>Narrow Your User Segment</p></figcaption></figure>

{% hint style="info" %}
There are also other ways to segment your users. Read [Manage your segments](../segments/manage-your-segments.md) to learn more.
{% endhint %}

Now, your cohorts are limited to only the apps you selected.

## Configure your metrics

Next, you need to configure the metrics in the cohorts table. In this guide, you'll look at the retention metric for the first two weeks after users install your app.

1. Select days 0-14 from the [days since install](overview/cohort-analysis-table.md#days-since-install) dropdown.
2. Click **Confirm**.
3. Choose **Retention Rate** from the [metric dropdown](overview/cohort-analysis-table.md#metric).

<figure><img src="../.gitbook/assets/Screenshot 2023-12-15 at 11.18.16.png" alt="" width="563"><figcaption><p>Configure Your Metrics</p></figcaption></figure>

## Change the timeframe

This configuration isn't very helpful yet because your table only shows cohorts for the [last seven days](overview/cohort-analysis-table.md#cohort-rows). In this case, you won't have enough data to see two-week retention. Now, you'll update your table to show the last month's worth of cohorts.

1. Click the date picker.
2. Select **Last 30 Days**.
3. Click **Apply**.

<figure><img src="../.gitbook/assets/Screenshot 2023-12-15 at 12.08.20 (1).png" alt="" width="563"><figcaption><p>Change the Timeframe</p></figcaption></figure>

Now, you can see your two-week user retention, given a month's worth of cohorts.

## Visualize retention

While you can see your data in the table, visualizing certain aspects of that same data in a chart can be helpful. To do so, check the box next to the days you want to visualize.

For example, if you want to visualize your day-1, day-3, and day-7 retention, check the boxes for those three days:

<figure><img src="../.gitbook/assets/Screenshot 2023-12-15 at 12.11.18.png" alt="" width="563"><figcaption><p>Visualize Retention</p></figcaption></figure>

## Conclusion

Great work! With this guide, you learned how to configure cohorts and present them in both table and chart formats.

To learn more about cohorts and _Cohort Analysis_, check out this documentation:

* Cohorts
* [Configuring your metrics](overview/configuring-your-metrics.md)
* [Comparing segmented cohorts](overview/comparing-segmented-cohorts.md)

