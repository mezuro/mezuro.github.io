---
layout: post
title:  "KalibroConfiguration Cloning"
date:   2016-02-03 11:34:20 -0200
categories: idea
image: /img/bulb.svg
---
KalibroConfiguration is the main object that holds and give scope to all the configuration components. As it is hard and requires several steps to create such structure, enable cloning of KalibroConfiguraions and its substructures will provide better usability for advanced users that are interested in configuring.

As mentioned the KalibroConfigurations is just the entry point for the cloning process. It is actually related to ReadingGroup and has many MetricConfiguration (which can be of three different types: Tree, Hotspot or Compound) which can have many KalibroRanges. So the cloning process has to work in a way that avoids dependence dead-locks during the substructures creation and has to make some decision like just referencing the ReadingGroup or creating clones of it and its Readings.

More context:

* <https://github.com/mezuro/kalibro_configurations/issues/40>
* <https://github.com/mezuro/prezento/issues/48#issuecomment-48563334>
* <https://github.com/mezuro/prezento/wiki/Reading-and-ReadingGroup-clone-behaviour>

**Mentor**: [Rafael Manzo](https://github.com/rafamanzo/)

**Skills**: Ruby, RoR, [KalibroConfigurations](https://github.com/mezuro/kalibro_configurations)
