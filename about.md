---
layout: page
title: About
permalink: /about/
---
The Mezuro project attempts to provide a platform to compare projects and metric techniques, teaching how to use metrics through configurations and code analysis, avoid technical debts and disseminate code metrics usage and understanding.

It has been under development by the [FLOSS Competence Center](http://ccsl.ime.usp.br/en) at the [Institute of Mathematics and Statistics of the University of São Paulo](http://www.ime.usp.br/en) (IME - USP) since 2010 going through many versions. Currently it has also got integrated into the [New Brazilian Public Software Portal](https://softwarepublico.gov.br/social/) (link in Portuguese) with support of [University of Brasília](https://www.fga.unb.br/) (UnB - link in Portuguese) with its release coming soon.

The current project is divided into it's front-end, called [prezento](https://github.com/mezuro/prezento), it's services
related to the configuration necessary for each analysis
([Kalibro Configurations](https://github.com/mezuro/kalibro_configurations)) and to their actual execution
([Kalibro Processor](https://github.com/mezuro/kalibro_processor)), which uses metric collectors such as
[Analizo](http://www.analizo.org/), [Radon](https://pypi.python.org/pypi/radon) and
[MetricFu](https://github.com/metricfu/metric_fu) to obtain the relevant measurements associated with a
given code base.

Check it under production at [mezuro.org](mezuro.org).
