---
layout: page
title: Components
permalink: /components/
---
Mezuro is composed of different software that communicate through RESTful APIs and together are capable of providing a unique, friendly and extensible gateway for several languages code metrics. Those are:

* [Prezento](https://github.com/mezuro/prezento): front-end application accumulating also user and resource ownership management
* [KalibroConfigurations](https://github.com/mezuro/kalibro_configurations): API responsible for analysis configurations management
* [KalibroProcessor](https://github.com/mezuro/kalibro_processor): API responsible for repository downloading, metric collectors execution and parsing
* [KalibroClient](https://github.com/mezuro/kalibro_client): Rubygem in charge of abstracting both Kalibros APIs as classes (see also its [Python](https://github.com/mezuro/kalibro_client_py) version)

The three main services (Prezento + Configurations + Processor) have both CentOS 7 and Debian 8 compatible packages built with [Mezuro Packaging](https://github.com/mezuro/packaging) scripts.

**Coming soon**

* [Kolekti](https://github.com/mezuro/kolekti): Rubygem that extracts and abstracts collector execution and result parse from KalibroProcessor making easier to add new collectors to Mezuro
  * [KolektiAnalizo](https://github.com/mezuro/kolekti_analizo): Unpublished Rubygem with the first collector getting migrated from KalibroProcessorto the new structure
* [Likeno](https://github.com/mezuro/likeno): Mezuro team's take on RESTful APIs representation as ActiveRecord-like models (similar to [ActiveResource](https://github.com/rails/activeresource) and [her](https://github.com/remiprev/her)). It is actually code extracted from KalibroClient in order to simplify it and make it easier to reuse in non-Mezuro projects of our own