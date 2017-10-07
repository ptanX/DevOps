## Kubernetes v1.8.0

### Software Versions

* Kubernetes v1.8.0
* Etcd v3.0.17

### Required Open Ports on hosts

 The following TCP ports are required to be open for `kubectl`: `10250` and `10255`. To access any exposed services, the ports used for the NodePort will also need to be opened. The default ports used by NodePort are TCP ports `30000` - `32767`.

### Plane Isolation

If you want to separate the planes for resiliency by labeling your hosts to separate out the data, orchestration and compute planes, you **must** change the plane isolation option to `required`. The host labels, `compute=true`, `orchestration=true` and `etcd=true`, are required on your hosts in order for Kubernetes to successfully launch. By default, `none` is selected and there will be no attempt for plane isolation.

### KubeDNS

KubeDNS is enabled for name resolution as described in the [Kubernetes DNS docs](http://kubernetes.io/docs/admin/dns/). The DNS service IP address is `10.43.0.10`.

### Audit Logs

Audit logs can be enabled through a simple option when deploying kubernetes, it will redirect all the Audit logs to the standard output for the kubernetes api container.

### Using in a proxy environment

By setting the HTTP_PROXY parameter, the `HTTP_PROXY`, `HTTPS_PROXY` and `NO_PROXY` environment variables will be added to the kubernetes containers.
