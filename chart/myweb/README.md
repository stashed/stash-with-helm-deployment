# myweb
[myweb by AppsCode](https://github.com/appscode/myweb) - Ajax friendly Helm Tiller Proxy
## TL;DR;

```console
$ helm install stable/myweb
```

## Introduction

This chart bootstraps a [Helm Tiller Proxy](https://github.com/appscode/myweb) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

## Prerequisites

- Kubernetes 1.6+

## Installing the Chart
To install the chart with the release name `my-release`:
```console
$ helm install stable/myweb --name my-release
```
The command deploys Swift proxy on the Kubernetes cluster in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `my-release`:

```console
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The following tables lists the configurable parameters of the myweb chart and their default values.


| Parameter                 | Description                                                   | Default          |
| --------------------------| --------------------------------------------------------------| -----------------|
| `replicaCount`            | Number of myweb replicas to create (only 1 is supported)      | `1`              |
| `myweb.image`             | myweb container image                                         | `appscode/myweb` |
| `myweb.tag`               | myweb container image tag                                     | `0.7.2`          |
| `imagePullSecrets`        | Specify image pull secrets                                    | `nil` (does not add image pull secrets to deployed pods) |
| `serviceAccount.create`   | If `true`, create a new service account                       | `true`           |
| `serviceAccount.name`     | Service account to be used. If not set and `serviceAccount.create` is `true`, a name is generated using the fullname template | `` |


Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example:

```console
$ helm install --name my-release --set image.tag=v0.2.1 stable/myweb
```

Alternatively, a YAML file that specifies the values for the parameters can be provided while
installing the chart. For example:

```console
$ helm install --name my-release --values values.yaml stable/myweb
```
