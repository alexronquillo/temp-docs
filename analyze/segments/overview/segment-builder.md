# Segment Builder

With the _Segment Builder_ you can add and edit segments:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-18 at 16.29.03.png" alt="" width="294"><figcaption><p>Segment Builder</p></figcaption></figure>

In this document, you'll learn the important details of how the Segment Builder works.

{% hint style="info" %}
Read [Manage your segments](../manage-your-segments.md) to learn how to use the _Segment Builder_ to add or edit segments.
{% endhint %}

## Default filters

There are three default dimension filters for segments:

* App
* Network
* Country

If you do not change the values for these dimensions, then all apps, networks, and countries are selected. This means an un-configured segment contains all users.

## Additional filters

You can add filters on additional dimensions by clicking **Add Filter**:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-18 at 16.29.03 (1).png" alt="" width="294"><figcaption><p>Add Filter</p></figcaption></figure>

Like with the default filters, all values for the new dimension filter are selected by default.

## Confirming filters

If you change a filter, you need to confirm the change. Otherwise, we ignore it when you click away or cancel:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-18 at 16.20.40.png" alt="" width="294"><figcaption><p>Confirm</p></figcaption></figure>

When you confirm a change, you'll see:&#x20;

* A blue dot that indicates you modified the filter.
* The number of values you selected.
* The values, themselves.

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-18 at 16.32.33.png" alt="" width="294"><figcaption><p>Confirmed Changes</p></figcaption></figure>

## Applying your segment

When you want to apply all the changes you've made to your segment, you must click **Apply**:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-18 at 16.50.05.png" alt="" width="294"><figcaption></figcaption></figure>

You will lose any unapplied changes if you navigate to another page or discard the changes.

## Removing filters

To remove a filter, click the menu icon then **Remove Filter**:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-18 at 16.54.02.png" alt="" width="294"><figcaption><p>Remove Filter</p></figcaption></figure>

This will remove any specific values you've selected for the dimension, essentially including all users for all values of that dimension.

## Setting values for all segments

To copy values you've selected for a particular dimension and share them across all other segments, click the menu icon then **Set For All Segments**:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-18 at 16.57.53.png" alt="" width="294"><figcaption><p>Set For All Segments</p></figcaption></figure>

For example, if you select one app for a segment and you want to filter all other segments based on that same app, you can use **Set For All Segments**. Other filters are not affected.

## Segment Limitations

There are a couple of limitations for segments in justtrack:

* You can only create 4 segments.
* Segments persist only during your session.

## Learn more

Read [Manage your segments](../manage-your-segments.md) to learn how to use the _Segment Builder_ to add or edit segments.

