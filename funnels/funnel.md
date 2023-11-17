---
description: An overview of using funnels in justtrack
---

# Overview

## Funnel

For analyzing your users in-game behavior justtrack offers two funnel views:

* Basic Funnel which allows you to add every event you want
* Game Progression Funnel which is automatically generated based on level progression

## Basic Funnel

### Concept

Justtrack’s Basic Funnel is the perfect way to track users progress inside your apps or games. You can conveniently check which steps users pass and find weak spots, where users decide to leave. The Basic Funnel provides information about users’ churn and is equipped with different visualizations, so you can use the most convenient and meaningful for you. Let’s dig in deeper.

By default we feed your funnel with the most meaningful events, for example `session_app_open` and `registration_process_start`. This gives you an opportunity to touch some data without any additional setup.

When you are ready to build something custom, you can easily add, delete or edit steps. Every time you update your funnel structure, it will be recalculated and you will receive updated data. Moreover, you don’t have to care about ordering the funnel steps. Justtrack automatically orders all requested events by unique count per user. Also it takes into account only events from users that completed the very first step. Finally, the funnel will help you to find anomalies by unobtrusive color coding.

### Adding and Editing Steps

Both can be done via single form. All you have to do is: Select an event you want to add. If you want to edit an event, this field will be already filled in for you.

Select a mode of adding steps:

* All events - you will get back one entry for the selected event with all unique occurrences. Fast and easy
* All events split by an event dimension - handy if you need to add several mutations of the same event
* Some events - filter for specific values in all available dimensions - use 100% of basic funnel flexibility

### Understanding Funnel Table Data

* Users - unique count per user (only one occurrence of an event per user is taken into account). All further steps only contain events from users who completed the first step.
* Users of Step 1 - users of the current step / users of the Step 1 \* 100
* Completion Rate - users of the next step / users of the current step \* 100
* Churn - users of the next step - users of the current step
* Churn Rate - (users of the next step / users of the current step) \* 100

### Understanding Funnel Graph Data

For visualization of your users in-app life we use 2 types of graphs:

* Default graph - direct visualisation of the table data with possibility to select metrics you want to see Time graph (for absolute and relative churn ) - see users churn aggregated by selected time period (date, week, month). We recommend you to use
* Time graphs when you want to check for some dramatic changes in events churn - for example after app update roll out.

## Game Progression Funnel

The Game Progression Funnel is the best option to analyze quality, difficulty, and attractiveness of levels in your games. Available are all metrics introduced in Basic Funnel as well as additional metrics specific to the level progression. Thus, the Game Progression funnel enables an extended understanding of users' in-game behaviors.

To start working with the Game Progression Funnel you need to set up the justtrack SDK to send at least the [JtLevelStart](http://127.0.0.1:5000/s/CSwomFswqKEitapGh0xs/readme/predefined-events#jtlevelstart) event. This will provide you with the standard funnel metrics you are familiar with from the Basic Funnel.

For getting info about average playtime you also have to set up the [JtLevelFinish](http://127.0.0.1:5000/s/CSwomFswqKEitapGh0xs/readme/predefined-events#jtlevelfinish) event.

The last step for getting the full Game Progression Funnel power is to add [JtLevelFail](http://127.0.0.1:5000/s/CSwomFswqKEitapGh0xs/readme/predefined-events#jtlevelfail) event. Together with Average Playtime and Average Fails per user you will get a possibility to analyze the difficulty of your levels.

The Game Progression Funnel uses the same logic of ordering events as the Basic Funnel. This is a great way for you to notice anomalies.

### Events in detail

* Send JtLevelStart when the level is started/restarted.
* Send JtLevelFinish when the user successfully ends a level.
* Send JtLevelFail when the user unsuccessfully ends a level.
* To make things work all together it is required that the value for the  `jt_level_name` dimension is identical for the start, fail, and finish events that belong to the same level.
