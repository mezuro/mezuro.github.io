---
layout: post
title:  "Setting up a new configuration"
date:   2016-04-04 13:45:20 -0200
categories: tutorial
highlight: true
image: /img/configuration.png

---

This tutorial shows how create and customize a configuration. That process includes the creation of what we call __Metric Configurations__ and their interpretations. In the end, you'll be able to configure your own set of metrics and use them to process repositories.

## Requisites
In order to execute all the steps of this tutorial, you must:

  - Have signed up to the platform
  - Be signed in
  - Have already created at least one Reading Group

## Introduction
To process a repository, Mezuro uses configurations which you specify on the [Repository Creation](/tutorial/2016/04/01/tutorial-analysis.html).

### Configuration components

Here you will be briefly introduced to all the components of a configuration and then guided through the steps to create one.

#### Configuration
Just a high level container for metrics and their customization and interpretations.

#### Metrics
Specification of which metric will be calculated during the processing and how to interpret its results:

  - __Weight__. For each module a grade is calculated. It is a weighted average of all the metrics calculated for it. This field is the weight of the metric on the final grade
  - __Aggregation Form__. Not all the metrics can be calculated for every module. For that type of metric, we calculate the aggregation of the children values according to what this field specifies. Aggregation forms include: _mean_, _median_, _maximum_, _minimum_, _standard deviation_ and _count_
  - __Reading Group__. Specifies which set of interpretations (called readings) will be available for the metric

#### Reading Group
Just a high level container for the readings (interpretations).

#### Reading
Interpretation for a given value. Each reading defines a label, a grade (this is the grade used for the weighted average mentioned above) and a color.

#### Range
Associates numeric intervals to the readings of a given metric.

## Steps

### Reading Group creation
  1. Click on "Reading Group" on the upper menu
  2. Click on "New Reading Group"
  3. Choose a name that must be unique
  4. Write a description - not required
  5. Click on "Save" and you should be at the reading group page now

### Add Readings to your Reading Group
From the reading group page:

  1. Click on "New Reading"
  2. Define a _Label_ that must be unique on your reading group scope
  3. Choose a _Color_, a hexadecimal value, that must be unique on your reading group
  4. Specify a _Grade_, also unique on your reading group scope

You can add as many readings as you feel necessary to better interpret metric values.

### Configuration creation
  1. Click on "Configuration" on the upper menu
  2. Click on "New Configuration"
  3. Choose a name that must be unique
  4. Write a description - not required
  5. Click on "Save" and you should be at the configuration page now

### Metric addition
From the configuration page:

  1. Click on "Add Metric Configuration"
  2. Select one collector from the options, and click on the metric that you want to add
     - If you chose a hotspot metric, you'll be redirected to the configuration page and the metric will be listed on the _Hotspot Metric_ section
     - If you chose a tree metric you'll need a bit more configuration:
       - Define a _Weight_, used to calculate the final grade
       - Select the _Aggregation Form_ that will be used for this metric
       - Select the _Reading Group_ which will provide the interpretations for this metric. You can use your newly created one!
       - Click on "Save" and you'll be redirected to the configuration page with the new metric added on the _Tree Metrics_ section

You can add as many metrics as you feel necessary to better measure the quality of your code, but know that he processing time increases with the number of metrics to calculate.

### Compound metrics
If you think the set of metrics provided by the collectors are not enough, you can arrange tree metrics to create compound metrics. You do that by implementing your own Javascript code where any tree metric on your configuration can referenced.

From the configuration page:

  1. Click on "Add Metric Configuration"
  2. Click on "Compound Metric"
  3. Define a _Name_ for your compound metric
  4. Write a description of what it is supposed to calculate - not required
  5. Implement a Javascript _Script_ for your metric. This will be a mathematical expression that can reference tree metrics by their code (listed on the top of the creation page) and it __must__ have a return statement
  6. Select a _Scope_ for your metric. Current values include: _method_, _function_, _class_, _package_ and _software_
  7. Define a _Code_. It must be a valid Javascript identifier
  8. Define a _Weight_, used to calculate the final grade
  9. Select the _Reading Group_ which will provide the interpretations for this metric. You can use your newly created one!

__Observation__: You can only create a _Compound Metric_ after adding at least one _Tree Metric_.

### Ranges creation
From the configuration page:

  1. Click on "Show" for the metric which you want to create ranges for. Notice that you can only do that for tree metrics
  2. Click on "Add Range"
  3. Select the _Reading_ which will be associated with this range
  4. Choose a _Beginning_ and an _End_ values for the interval
  5. Write _Comments_ explaining why you chose that particular _Reading_ for this interval
  6. Click on "Save" and you should be at the metric page with the new range added, congratulations!

__Caveat__: The number of ranges you can add is equal to the number of readings the reading group for the metric because the _Label_ must be unique on the range scope.
