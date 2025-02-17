---
title: "Addons"
date: 2019-07-31
weight: 4
description: >
  Using addons
---

minikube has a set of built-in addons that, when enabled, can be used within Kubernetes.

## Available addons

* [Kubernetes Dashboard](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/dashboard)
* [Heapster](https://github.com/kubernetes/heapster): [Troubleshooting Guide](https://github.com/kubernetes/heapster/blob/master/docs/influxdb.md) Note:You will need to login to Grafana as admin/admin in order to access the console
* [EFK](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/fluentd-elasticsearch)
* [Registry](https://github.com/kubernetes/minikube/tree/master/deploy/addons/registry)
* [Registry Credentials](https://github.com/upmc-enterprises/registry-creds)
* [Ingress](https://github.com/kubernetes/ingress-nginx)
* [Freshpod](https://github.com/GoogleCloudPlatform/freshpod)
* [nvidia-driver-installer](https://github.com/GoogleCloudPlatform/container-engine-accelerators/tree/master/nvidia-driver-installer/minikube)
* [nvidia-gpu-device-plugin](https://github.com/GoogleCloudPlatform/container-engine-accelerators/tree/master/cmd/nvidia_gpu)
* [logviewer](https://github.com/ivans3/minikube-log-viewer)
* [gvisor](../deploy/addons/gvisor/README.md)
* [storage-provisioner-gluster](../deploy/addons/storage-provisioner-gluster/README.md)
* [helm-tiller](../deploy/addons/helm-tiller/README.md)
* [ingress-dns](../deploy/addons/ingress-dns/README.md)

## Listing available addons

```shell
minikube addons list
```

Example output:

```
- registry: disabled
- registry-creds: disabled
- freshpod: disabled
- addon-manager: enabled
- dashboard: enabled
- heapster: disabled
- efk: disabled
- ingress: disabled
- default-storageclass: enabled
- storage-provisioner: enabled
- storage-provisioner-gluster: disabled
- nvidia-driver-installer: disabled
- nvidia-gpu-device-plugin: disabled
```

## Enabling an addon

```shell
minikube addons enable <name>
```

## Interacting with an addon

For addons that expose a browser endpoint, use:

```shell
minikube addons open <name>
```

## Disabling an addon

```shell
minikube addons disable <name>
```

## Custom Addons

If you would like to have minikube properly start/restart custom addons, place the addon(s) _.yaml_ you wish to be launched with minikube in the `.minikube/addons` directory. Addons in this folder will be moved to the minikube VM and launched each time minikube is started/restarted. Learn [how to develop minikube addons]({{< ref "/docs/contributing/addons.en.md" >}}).
