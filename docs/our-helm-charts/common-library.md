# Common library

Most of our application Helm charts consume our Common library Helm chart.

!!! note
    The Common library chart is not meant to be installed directly, application
    charts use the Common library as a dependency.

## Background

In Helm 3, their team introduced the concept of a
[Library chart](https://helm.sh/docs/topics/library_charts/).

> A library chart is a type of Helm chart that defines chart primitives or
  definitions which can be shared by Helm templates in other charts. This
  allows users to share snippets of code that can be re-used across charts,
  avoiding repetition and keeping charts DRY.

The common library was created because we saw many charts requiring only a
few select configuration options in their Helm charts.

!!! note
    Take one of the many charts like `sonarr` or `nzbget`. Each of these
    charts only require setting `service`, `port`, `persistence`, `ingress`
    and `image` since state and app configuration is handled by the application
    itself.

In order to stay somewhat DRY (Don't Repeat Yourself) and keeping with Helm 3
usage for a Library chart, we saw this pattern and decided it was worth it for
us to create a library. This means each one of these app charts has a
dependency on what we call the `common` library.

## Changelog

To view the changelog for the common library see
[here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common#changelog).

## Source code

The source code for our library chart can be found
[here](https://github.com/k8s-at-home/library-charts).
