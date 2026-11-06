<p align="center">
  <img src="https://raw.githubusercontent.com/liquidmetal-dev/getting-started/main/media/logos/SVG/LM%20LOGO-HORIZONTAL%20LIGHTBACK-02_trimmed.svg" alt="lm" width="400x"/>
</p>

## Hi there 👋

Thanks for visiting, this organization contains all the projects related to **Liquid Metal**.

> :tada: **This project was originally developed by Weaveworks but is now owned & run by the community. If you are interested in helping out please reach out.**

### :raising_hand: What is Liquid Metal?

Liquid Metal is a set of open source projects for running **lightweight virtual machines (microVMs)** on your own hardware and managing them **declaratively**.

* **Hard isolation, light footprint**: every workload gets its own kernel and a real KVM boundary, without the overhead of a full VM
* **Fast to boot, fast to throw away**: microVMs start in close to container time
* **More from your hardware**: pack more workloads onto each bare-metal host, from datacenter servers to the edge
* **Standard building blocks**: [Firecracker](https://firecracker-microvm.github.io/), [Cloud Hypervisor](https://www.cloudhypervisor.org/), containerd, KVM and Kubernetes

Use it for:

* [Kubernetes clusters](https://liquidmetal.dev/docs/use-cases/kubernetes/) with microVMs as nodes
* [CI runners](https://liquidmetal.dev/docs/use-cases/ci-runners/) with a fresh microVM per job
* [Ephemeral environments](https://liquidmetal.dev/docs/use-cases/ephemeral-environments/) for previews, tests and development
* [AI agent sandboxes](https://liquidmetal.dev/docs/use-cases/agent-sandboxes/) to run untrusted code in

> Hang on, what is this **microVM** thing you mention!?! A microVM is a very lightweight virtual machine that optimizes for speed and less resource consumption over supporting a wide array of devices. It gives you the isolation of a VM with close to the speed of a container.

### :mag_right: How do I get started?

Head over to [liquidmetal.dev](https://liquidmetal.dev/). The [30 minute tutorial](https://liquidmetal.dev/docs/tutorial-basics/) builds a Liquid Metal platform on your own Linux machine.

### :sparkles: What are the main projects?

* [flintlock](https://github.com/liquidmetal-dev/flintlock) - an agent on each host machine that creates and manages microVMs via API calls. It does not know about Kubernetes, so you can use it to start a microVM for any task. It uses containerd so that container images can be the kernel and volumes for a microVM.
* [Cluster API Provider Microvm (CAPMVM)](https://github.com/liquidmetal-dev/cluster-api-provider-microvm) - a [Cluster API](https://cluster-api.sigs.k8s.io/) infrastructure provider. It creates microVMs on Flintlock hosts and bootstraps Kubernetes on them, so a microVM becomes a whole Kubernetes node.
* [microvm-operator](https://github.com/liquidmetal-dev/microvm-operator) (experimental) - manage microVMs as Kubernetes resources: `Microvm`, `MicrovmReplicaSet` and `MicrovmDeployment`.
* [brigade](https://github.com/liquidmetal-dev/brigade) (experimental) - a distributed orchestrator that speaks the Flintlock API and schedules microVMs across a fleet of hosts.
* [battery](https://github.com/liquidmetal-dev/battery) (experimental) - a warm pool manager that keeps pre-booted microVMs ready to claim instantly.
* [guest-agent](https://github.com/liquidmetal-dev/guest-agent) (experimental) - an agent inside the microVM that lets the host run commands and copy files over vsock.
* [muster](https://github.com/liquidmetal-dev/muster) (pre-alpha) - runs each GitHub Actions job in a fresh microVM.
* [image-builder](https://github.com/liquidmetal-dev/image-builder) - builds the container images that we use for microVM kernels and root volumes.

### :flashlight: What else is there?

* [hammertime](https://github.com/liquidmetal-dev/hammertime) and [fl](https://github.com/liquidmetal-dev/fl) - CLIs for interacting with Flintlock.
* [mikrolite](https://github.com/liquidmetal-dev/mikrolite) - an experimental CLI for creating microVMs without Flintlock.
* [flintlock-terraform](https://github.com/liquidmetal-dev/flintlock-terraform) and [terraform-equinix-liquidmetal](https://github.com/liquidmetal-dev/terraform-equinix-liquidmetal) - Terraform support for Flintlock and for a Liquid Metal platform on Equinix Metal.
* [EKS-Anywhere (EKS-A)](https://anywhere.eks.amazonaws.com/) (poc) - we have been working on [adding CAPMVM as a provider](https://github.com/liquidmetal-dev/eks-anywhere/tree/capmvm_provider) to EKS-A.

### :pencil2: Want to know more?

Get in contact with us if you want to learn more about Liquid Metal. You can hit us up in any of these ways:

* [Liquid Metal channel on the CNCF Slack](https://cloud-native.slack.com/archives/C07B5R5BLBZ)
* By creating an issue / discussion in one of the projects

### :books: Some extra reading

* [Liquid Metal: multi-cluster Kubernetes on bare metal with microVMs](https://web.archive.org/web/20221128021814/https://www.weave.works/blog/multi-cluster-kubernetes-on-microvms-for-bare-metal) (Blog)
