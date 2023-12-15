# Cohort analysis table

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-14 at 15.14.43 (1).png" alt="" width="563"><figcaption><p>Cohorts</p></figcaption></figure>

The _Cohort Analysis_ table is the primary way to analyze cohort data in justtrack. In this article, you'll learn:&#x20;

* Specific implementation details of this table.
* How to configure your cohorts.

{% hint style="warning" %}
Any changes you make to the _Cohort Analysis_ table are stored for the current session only, not across sessions, users, or browser tabs.
{% endhint %}

## Average row

The _average_ row calculates the average of the data for each column header in the table. However, these averages account for _all_ cohorts, not only for the cohorts present in the table.&#x20;

So, for example, if you are looking at cohorts for three install days, the average row will not only include those days, but also all other cohorts that have data.

## Cohort rows

Each of the other rows shows data for a specific cohort, with the leftmost column being the install date that defines the cohort. These install dates are based on the date picker.&#x20;

So, to see different cohorts, adjust the date picker:

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-14 at 15.31.00.png" alt="" width="563"><figcaption><p>Date Picker</p></figcaption></figure>

## Visualizing days

You can visualize some of the rows from your table in a line chart. To do so, check the box in the column header for the day you want to visualize:

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-14 at 15.45.21.png" alt=""><figcaption><p>Visualizing Cohort Data</p></figcaption></figure>

{% hint style="info" %}
You can visualize a maximum of **three** days at a time.
{% endhint %}

