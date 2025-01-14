# Typhoon

Notable changes between versions.

## Latest

* Kubernetes [v1.8.6](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG-1.8.md#v186)

## v1.8.5

* Kubernetes [v1.8.5](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG-1.8.md#v185)
* Recommend Container Linux [images](https://coreos.com/releases/) with Docker 17.09
  * Container Linux stable, beta, and alpha now provide Docker 17.09 (instead
  of 1.12)
  * Older clusters (with CLUO addon) auto-update Container Linux version to begin using Docker 17.09
* Fix race where `etcd-member.service` could fail to resolve peers ([#69](https://github.com/poseidon/typhoon/pull/69)) 
* Add optional `cluster_domain_suffix` variable (#74)
* Use kubernetes-incubator/bootkube v0.9.1

#### Bare-Metal

* Add kubelet `--volume-plugin-dir` flag to allow flexvolume providers ([#61](https://github.com/poseidon/typhoon/pull/61))

#### Addons

* Discourage deploying the Kubernetes Dashboard (security)

## v1.8.4

* Kubernetes v1.8.4
* Calico related bug fixes
* Update Calico from v2.6.1 to v2.6.3
* Update flannel from v0.9.0 to v0.9.1
* Service accounts for kube-proxy and pod-checkpointer
* Use kubernetes-incubator/bootkube v0.9.0

## v1.8.3

* Kubernetes v1.8.3
* Run etcd on-host, across controllers
* Promote AWS platform to beta
* Use kubernetes-incubator/bootkube v0.8.2

#### Google Cloud

* Add required variable `region` (e.g. "us-central1")
* Reduce time to bootstrap a cluster
* Change etcd to run on-host, across controllers (etcd-member.service)
* Change controller instances to automatically span zones in the region
* Change worker managed instance group to automatically span zones in the region
* Improve internal firewall rules and use tag-based firewall policies
* Remove support for self-hosted etcd
* Remove the `zone` required variable
* Remove the `controller_preemptible` optional variable

#### AWS

* Promote AWS platform to beta
* Reduce time to bootstrap a cluster
* Change etcd to run on-host, across controllers (etcd-member.service)
* Fix firewall rules for multi-controller kubelet scraping and node-exporter
* Remove support for self-hosted etcd

#### Addons

* Add Prometheus 2.0 addon with alerting rules
* Add Grafana dashboard for observing metrics

## v1.8.2

* Kubernetes v1.8.2
  * Fixes a memory leak in the v1.8.1 apiserver ([kubernetes#53485](https://github.com/kubernetes/kubernetes/issues/53485))
* Switch to using the `gcr.io/google_containers/hyperkube`
* Update flannel from v0.8.0 to v0.9.0
* Add `hairpinMode` to flannel CNI config
* Add `--no-negcache` to kube-dns dnsmasq
* Use kubernetes-incubator/bootkube v0.8.1

## v1.8.1

* Kubernetes v1.8.1
* Use kubernetes-incubator/bootkube v0.8.0

#### Digital Ocean

* Run etcd cluster across controller nodes (etcd-member.service)
* Remove support for self-hosted etcd
* Reduce time to bootstrap a cluster

## v1.7.7

* Kubernetes v1.7.7
* Use kubernetes-incubator/bootkube v0.7.0
* Update kube-dns to 1.14.5 to fix dnsmasq [vulnerability](https://security.googleblog.com/2017/10/behind-masq-yet-more-dns-and-dhcp.html)
* Calico v2.6.1
* flannel-cni v0.3.0
  * Update flannel CNI config to fix hostPort

## v1.7.5

* Kubernetes v1.7.5
* Use kubernetes-incubator/bootkube v0.6.2
* Add AWS Terraform module (alpha)
* Add support for Calico networking (bare-metal, Google Cloud, AWS)
* Change networking default from "flannel" to "calico"

#### AWS

* Add `network_mtu` to allow CNI interface MTU customization

#### Bare-Metal

* Add `network_mtu` to allow CNI interface MTU customization
* Remove support for `experimental_self_hosted_etcd`

## v1.7.3

* Kubernetes v1.7.3
* Use kubernetes-incubator/bootkube v0.6.1

#### Digital Ocean

* Add cloud firewall rules (requires Terraform v0.10)
* Change nodes tags from strings to DO tags

## v1.7.1

* Kubernetes v1.7.1
* Use kubernetes-incubator/bootkube v0.6.0
* Add Bare-Metal Terraform module (stable)
* Add Digital Ocean Terraform module (beta)

#### Google Cloud

* Remove `k8s_domain_name` variable, `cluster_name` + `dns_zone` resolves to controllers
* Rename `dns_base_zone` to `dns_zone`
* Rename `dns_base_zone_name` to `dns_zone_name`

## v1.6.7

* Kubernetes v1.6.7
* Use kubernetes-incubator/bootkube v0.5.1

## v1.6.6

* Kubernetes v1.6.6
* Use kubernetes-incubator/bootkube v0.4.5
* Disable locksmithd on hosts, in favor of [CLUO](https://github.com/coreos/container-linux-update-operator).

## v1.6.4

* Kubernetes v1.6.4
* Add Google Cloud Terraform module (stable)

## Earlier

Earlier versions, back to v1.3.0, used different designs and mechanisms.
