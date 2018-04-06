# Chaos Toolkit - An Open API for Chaos Engineering

[![Build Status](https://travis-ci.org/chaostoolkit/chaostoolkit.svg?branch=master)](https://travis-ci.org/chaostoolkit/chaostoolkit)
[![Docker Pulls](https://img.shields.io/docker/pulls/chaostoolkit/chaostoolkit.svg)](https://hub.docker.com/r/chaostoolkit/chaostoolkit/)
[![Python versions](https://img.shields.io/pypi/pyversions/chaostoolkit.svg)](https://www.python.org/)
[![Requirements Status](https://requires.io/github/chaostoolkit/chaostoolkit/requirements.svg?branch=master)](https://requires.io/github/chaostoolkit/chaostoolkit/requirements/?branch=master)
[![Has wheel](https://img.shields.io/pypi/wheel/chaostoolkit.svg)](http://pythonwheels.com/)

Chaos Toolkit is a project whose mission is to provide a free, open and community-driven toolkit and API to all the various forms of chaos engineering tools that the community needs.

## Why the Chaos Toolkit?

The Chaos Toolkit has two main purposes:

* To provide a full chaos engineering implementation that simplifies the adoption of chaos engineering by providing an easy starting point for applying the discipline.
* To define an open API with the community so that any chaos experiment can be executed consistently using integrations with the many commercial, private and open source chaos implementations that are emerging.

![Chaos Toolkit](http://chaostoolkit.org/static/images/schema-1920.svg)

### Simplifying Adoption of Chaos Engineering

Firstly the Chaos Toolkit aims to make it simple and straightforward to run
experiments against your live system to build confidence in its behavior and learn about
potential weaknesses.

Following the 
[principles of chaos engineering][principles], the Chaos Toolkit aims to be the easiest way to apply these principles to your own complex, and even sometimes chaotic, systems.

[principles]: http://principlesofchaos.org/

### An Open API to Chaos Engineering

Secondly the Chaos Toolkit defines an [Open API][api] to Chaos Engineering through it's JSON-format experiment definition. The toolkit can be extended to integrate with any number of commercial, private and open source chaos implementations through probes (to measure steady-state before and after an experiment) and actions (to vary real-world events during an experiment).

[api]: http://chaostoolkit.org/reference/api/experiment/

## Install or Upgrade

Before installing the Chaos Toolkit it is recommended that you create a Python virtual environment for running your chaos experiments. Full instructions for installing chaostoolkit and its requirements are available in the [installation documentation][install].

[install]: http://chaostoolkit.org/reference/usage/install/

## Getting Started

Once you have installed the Chaos Toolkit you can use it through its simple command line tool. The tool's main job is to run your experiment and then 
generate a report of the findings from the experiment to then share with your team for discussion.

Running an experiment is as simple as:

```
$ chaos run experiment.json
```

The Chaos Toolkit takes experiments defined in a [JSON format][json] description file, encoded in JSON, and runs its steps sequentially. A full specifiction of this JSON experiment description file can be found in the [main project documentation][api].

[json]: https://www.json.org/

## Extending the Chaos Toolkit

The Chaos Toolkit plays the experiment JSON description that you provide to it. 
Experiments are made up of probes and actions (to vary real-world events during an experiment). We are always looking for community contribution and ideas around
what probes and actions you might need as you integrate chaos experiments through the Chaos Toolkit, into your own unique context and evironment.

If you have an idea for a new set of probes and actions that you'd like to share, please first consider raising a ticket or even joining our community slack to suggest your idea.

In terms of implementation, the [Chaos Toolkit currently supports][extend] probes and actions implemented as Python functions, separate processes or even remote HTTP calls. As long as your extensions conform to the [Chaos Toolkit API][api] you can then specify your own unique extensions in your experiment JSON definitions. 

The core implementation of the Chaos Toolkit API can be found in the [chaostoolkit-lib][chaoslib] project.

[extend]: http://chaostoolkit.org/reference/extending/approaches/
[chaoslib]: https://github.com/chaostoolkit/chaostoolkit-lib

### Current Known Extensions

The following free and open source extensions are available for your probes
and/or actions:

* [chaostoolkit-kubernetes][chaoskube]: Kubernetes activities
* [chaostoolkit-gremlin][chaosgremlin]: Gremlin, Inc activities
* [chaostoolkit-aws][chaosaws]: AWS activities
* [chaostoolkit-cloud-foundry][chaoscf]: Cloud Foundry activities
* [chaostoolkit-prometheus][chaosprom]: Prometheus probes
* [chaostoolkit-slack][chaosslack]: Slack notifications
* [chaostoolkit-humio][chaoshumio]: Humio logging

[chaoskube]: https://github.com/chaostoolkit/chaostoolkit-kubernetes-support
[chaosgremlin]: https://github.com/chaostoolkit-incubator/chaostoolkit-gremlin
[chaosaws]: https://github.com/chaostoolkit-incubator/chaostoolkit-aws
[chaosprom]: https://github.com/chaostoolkit-incubator/chaostoolkit-prometheus
[chaoscf]: https://github.com/chaostoolkit-incubator/chaostoolkit-cloud-foundry
[chaosslack]: https://github.com/chaostoolkit-incubator/chaostoolkit-slack
[chaoshumio]: https://github.com/chaostoolkit-incubator/chaostoolkit-humio

## Get involved!

Chaos Toolkit's mission is to provide an open API to chaos engineering in all its forms. As such, we encourage and welcome you  to [join][join] our open community Slack team to discuss and share your experiments and needs with the community.

[join]: https://join.chaostoolkit.org/

If you'd prefer not to use Slack then we welcome the raising of GitHub issues on this repo for any questions, requests, or discussions around the Chaos Toolkit.

Finally you can always email `contact@chaostoolkit.org` with any questions as well.
