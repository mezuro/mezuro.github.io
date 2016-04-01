---
layout: post
title:  "Analyzing a repository"
date:   2016-04-01 16:45:20 -0200
categories: tutorial
highlight: true

---

This tutorial shows how to analyze a repository's source code. It will guide you through the creation of a "project" - optional - and a repository. In the end, you'll be able to
understand the results of the analysis.

## Requisites
In order to execute all the steps of this tutorial, you must:

 - Have signed up to the platform
 - Be signed in
 - Have a repository URL which you wish to analyze

## Steps

### Project creation (Optional)

 1. Click on "Project" on the upper menu
 2. Click on "Create Project"
 3. Choose a name that must be unique
 4. Write a description - not required
 5. Choose an image for the repository - not required
 5. Click on "Save" and you should be at the project page now, congratulations!

### Repository creation

 1. From the project page, click on "New Repository"
 2. Fill in the form, making sure that:
  - The name is unique
  - You choose one of the Open Source licenses in the platform according to your code
  - The _Type_ field stands for the Repository source code management tool (Git or Subversion)
  - You fill in the _Address_ with the URL from which we can download your code
  - You choose a branch for analysis. The branches are automatically fetched, and the default is the _master_
  - You set the analysis' periodicity. For example, you can schedule a new analysis for every two days. Notice that you can always run it from the interface whenever you want, as well
  - The _Configuration_ chosen matches the set of metrics and interpretation that you want to use to analyze your project
 3. Click on _Save_ and you'll be redirected to the repository page, and wait for analysis

### Repository page details
The repository page is divided into five different sections:

#### Details

 - Information that you provided during the creation steps
 - Select box so it is possible to visualize previous analysis of your repository

#### Processing information

 - Information about the time it has taken to finish each step of the processing
   * PREPARING: the system reserves a folder for your repository and retrieves the configuration
   * DOWNLOADING: retrieves the source code
   * COLLECTING: calculates the metrics for your repository
   * CHECKING: sets default values for metrics on modules where they don't apply
   * BUILDING: organizes the results into a source tree structure
   * AGGREGATING: calculates the aggregated value for parent modules in the source tree
   * CALCULATING: if the chosen configuration has compound metrics, calculates them
   * INTERPRETING: interprets the results using reading groups (labels and colors)

#### Modules Tree

 - Source tree structure where you can navigate by clicking on the names
 - Information about the granularity of the module
   * METHOD
   * FUNCTION
   * CLASS
   * PACKAGE
   * SOFTWARE
 - Grade of the given module according to the weights of the metrics on the configuration

#### Metric Results

The metric results are of two basic types: _hotspot_ and _tree_. Hotspot metrics will show you specific locations on the code where problems may arise, like duplicated code. Tree metric results will assign numbers to specific aspects of the code, like cyclomatic complexity.

##### Hotspot Metric Results

If there are any _hotspot metrics_ on the configuration you chose, they'll appear on this section. On the root directory, all results will be shown. As you navigate through the source tree, the results will be filtered accordingly.

 - _Name_ refers to the module where an possible issue is
 - _Line_ is the specific line on the source code
 - _Message_ is the warning yielded by the metric collector

##### Tree Metric Results

If there are any _tree metrics_ on the chosen configuration, you'll see their results on this section.

 - _Value_ is the result calculated by the corresponding _metric_
 - The _grade_ for the module is the result of the mean of the values with their _weights_
 - _Threshold_ displays the interpretation of the _value_ given by the configuration you chose

Also, if you click on the metric name, you can see a graph with the evolution of the metric values over each processing.
