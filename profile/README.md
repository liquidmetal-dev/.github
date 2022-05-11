![Weaveworks Logo](images/weaveWorks_colour_logo_POS_RGB_144x60.png)

## Hi there 👋

Thanks for visiting, this organization contains all the projects related to Weaveworks **Liquid Metal**.

### :raising_hand: What is Liquid Metal?

Liquid Metal is a set of solutions to:

* **Declaratively** provision Kubernetes clusters **dynamically** on lightweight virtual machines (i.e. microVMs) and bare-metal
* Create **lightweight** clusters to **maximize the available [edge] compute**
  * microVMs are our friend
  * More clusters/nodes on the available bare-metal hosts
  * Minimizing resource footprint without sacrificing hard isolation
* Support clusters where **direct access to hardware acceleration** is needed (i.e. 5G networks)  
* Using standard kubernetes and linux kernel and operating system capabilities

> Hang on, what is this **microvm** thing you mention!?! A microvm is a very lightweight virtual machine that optimizes for speed and less resource consumption over supporting a wide array of devices/etc. We support [Firecracker](https://firecracker-microvm.github.io/) and experimentally [Cloud Hypervisor](https://www.cloudhypervisor.org/). Read more about this [here](https://www.techtarget.com/searchsecurity/definition/micro-VM-micro-virtual-machine) and [here](https://itnext.io/microvm-another-level-of-abstraction-for-serverless-computing-5f106b030f15).

### :sparkles: What are the main projects?

* [flintlock](https://github.com/weaveworks-liquidmetal/flintlock) - this is an agent that's deployed to a host machine (physical or virtual) which enables you to start/manage microvms via API calls. It does not know of Kubernetes and could therefore be used to start a microvm to accomplish any task you choose. We integrate heavily with containerd as a way to use container images as the volumes for the microvm....copying rawfs files around is a real pain and very slow.
* [Cluster API Provider Microvm (CAPMVM)](https://github.com/weaveworks-liquidmetal/cluster-api-provider-microvm) - this provides the Kubernetes cluster creation/lifecycle management (along with the [Cluster API](https://cluster-api.sigs.k8s.io/) more generally). Its responsible for creating microvms on various hosts via calls to Flintlock and bootstrapping Kubernetes on those microvms. So a microvm becomes a whole Kubernetes node.
* [Image Builder](https://github.com/weaveworks-liquidmetal/image-builder) - this is where we build the container images that we use for root volumes and kernels for the microvm.



### :flashlight: What else are we looking at?

* [EKS-Anywhere (EKS-A)](https://anywhere.eks.amazonaws.com/) (poc) - we have been working on [adding CAPMVM as a provider](https://github.com/weaveworks-liquidmetal/eks-anywhere/tree/capmvm_provider) to EKS-A.
* Microvm Scheduler (in-development) - this will enable the dynamic placement of microvms on the available pool of hosts machines taking into account resource availability/requirements, labels etc. So, a bit like kube-scheduler but for microvms. We will be providing some integration points so that the scheduler can automatically determine the available baremetal hosts, and we'll add an integration for Tinkerbell (and probably Ironic & MaaS).

### :pencil2: Want to know more?

Get in contact with us if you want to learn more about Liquid Metal. You can hit us up in any of these ways:

* [Weavework Community Slack](https://weave-community.slack.com/archives/C02KARWGR7S)
* [Via our website](https://www.weave.works/contact/)
* By creating an issue / discussion in one of the projects

### :books: Some extra reading

* [Liquid Metal: multi-cluster Kubernetes on bare metal with microVMs](https://www.weave.works/blog/multi-cluster-kubernetes-on-microvms-for-bare-metal) (Blog)
