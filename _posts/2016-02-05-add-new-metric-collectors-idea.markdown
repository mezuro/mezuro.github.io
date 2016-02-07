---
layout: post
title:  "Add new Metric Collectors"
date:   2016-02-05 15:50:00 -0200
categories: idea
image: /img/bulb.svg
---
A Metric Collector is responsible for parsing the Repositories' code and returning results that can be
parsed and aggregated according to modules, functions or the entire software.

Currently, Mezuro has three Metric Collectors: Analizo (for C, C++ and Java), Radon (for python) and
MetricFu (for Ruby). We are looking to add more collectors to cover more languages and to provide different
metrics for the already covered ones.

The Metric Collectors are supposed to be separated into gems that can be easily included into Kalibro Processor using
[Kolekti](https://github.com/mezuro/kolekti). The Analizo collector has already been extracted from Processor into a [proper gem](https://github.com/mezuro/kolekti_analizo/).

More context:

* <https://github.com/mezuro/kalibro_processor/issues/145>
* <https://github.com/mezuro/kalibro_processor/issues/144>

**Mentor**: [Rafael Manzo](https://github.com/rafamanzo/)

**Skills**: Ruby, RoR, [KalibroProcessor](https://github.com/mezuro/kalibro_processor),
[Kolekti](https://github.com/mezuro/kolekti)
