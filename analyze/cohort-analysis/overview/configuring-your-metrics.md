# Configuring your metrics

There are several options to consider when configuring your cohort metrics on the _Cohort Analysis_ page:

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-15 at 08.27.45.png" alt=""><figcaption><p>Configure Metrics</p></figcaption></figure>

### Days since install

You can choose the **days since install** that you want to show in your table. By default, days zero (d0) through seven (d7), inclusive, are selected. But you can select any and all days from d0 to d90.

When you change the days you want to display, click **Confirm** to apply the changes.

### Metric

You can choose the metric to display in the chart.

### Advanced options

With _Advanced options_, you can fine-tune your cohort data. These options are dependent on the metric you've selected and, therefore, may not be present for every metric:

| Option                  | Description                                                                                                                  |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Sum, Count, or Average  | An indication of how the metric value is calculated.                                                                         |
| Divide by active users  | A toggle that determines if the metric should be calculated by dividing the value by the number of active users for the day. |
| Monetization dimensions | A series of dropdowns with which you can specify the monetization events to be included in the metric calculation.           |

When you change these advanced options, click **Apply** to apply the changes. These changes will be discarded if you change to a different metric.

### Cumulative

With the **Cumulative** toggle, you can choose whether your metric calculations should be restricted to each day or whether they should be accumulated over time. The state of this toggle remains, even if you change metrics.

{% hint style="success" %}
**Example:** Imagine you're looking at revenue on the third day since install (d3). With **Cumulative**, you choose whether to show:

* Only the revenue for that day (**non-cumulative**)
* The sum of all revenue from d0 to d3 (**cumulative**).
{% endhint %}

When **Cumulative** is toggled on, you will also see delta values in the table cells. These indicate the rate of change from the previous day.
