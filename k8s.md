[Facebook](https://www.facebook.com/cloudspinx "Facebook") [GitHub](https://github.com/cloudspinx "GitHub") [Linkedin](https://ke.linkedin.com/in/mutai-josphat-37bb08bb "Linkedin") [Skype](https://join.skype.com/invite/LXvZG1u2bU50 "Skype") [Twitter](https://twitter.com/cloud_spinx "Twitter")

-   [How To](https://computingforgeeks.com/category/how-to/)
-   [Automation](https://computingforgeeks.com/category/automation/)
-   [Virtualization](https://computingforgeeks.com/category/virtualization/)
-   [Containers](https://computingforgeeks.com/category/containers/)
-   [Databases](https://computingforgeeks.com/category/databases/)
-   [Electronics](https://computingforgeeks.com/category/gadgets/)
-   [Books](https://computingforgeeks.com/category/books/)
-   [Courses](https://computingforgeeks.com/category/courses/)
-   [HIRE US](https://cloudspinx.com/)

Search 

-   [CentOS](https://computingforgeeks.com/category/centos/)
-   [Ubuntu](https://computingforgeeks.com/category/ubuntu/)
-   [Fedora](https://computingforgeeks.com/category/fedora/)
-   [Debian](https://computingforgeeks.com/category/debian/)
-   [Rocky](https://computingforgeeks.com/category/rocky-linux/)
-   [FreeBSD](https://computingforgeeks.com/category/freebsd/)
-   [Openstack](https://computingforgeeks.com/category/openstack/)
-   [Windows](https://computingforgeeks.com/category/windows/)
-   [About Us](https://computingforgeeks.com/about-us/)
-   [Contact us](https://computingforgeeks.com/contact-us/)
-   [Terms](https://computingforgeeks.com/terms-of-service/)
-   [Affiliates Disclosure](https://computingforgeeks.com/affiliate-links-disclosure/)

[](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#)

Sign in

Welcome! Log into your account

your username

your password

[Forgot your password? Get help](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#)

Password recovery

Recover your password

your email

A password will be e-mailed to you.

 [![ComputingForGeeks](https://computingforgeeks.com/wp-content/uploads/2019/05/cf_white-1.png?ezimgfmt=rs:272x90/rscb23/ng:webp/ngcb23 "ComputingForGeeks") ComputingForGeeks](https://computingforgeeks.com/)

.tdi\_1.td-a-rec{text-align:center}.tdi\_1 .td-element-style{z-index:-1}.tdi\_1.td-a-rec-img{text-align:left}.tdi\_1.td-a-rec-img img{margin:0 auto 0 0}@media(max-width:767px){.tdi\_1.td-a-rec-img{text-align:center}}

[](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#)

[![ComputingForGeeks](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22272%22%20height=%2290%22%3E%3C/svg%3E "ComputingForGeeks")](https://computingforgeeks.com/)

-   [How To](https://computingforgeeks.com/category/how-to/)
-   [Automation](https://computingforgeeks.com/category/automation/)
-   [Virtualization](https://computingforgeeks.com/category/virtualization/)
-   [Containers](https://computingforgeeks.com/category/containers/)
-   [Databases](https://computingforgeeks.com/category/databases/)
-   [Electronics](https://computingforgeeks.com/category/gadgets/)
-   [Books](https://computingforgeeks.com/category/books/)
-   [Courses](https://computingforgeeks.com/category/courses/)
-   [HIRE US](https://cloudspinx.com/)

[](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#)[](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#)

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[728,90\],"computingforgeeks\_com-box-2","ezslot\_16",109,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-box-2-0");

[Home](https://computingforgeeks.com/) [Kubernetes](https://computingforgeeks.com/category/kubernetes/ "View all posts in Kubernetes") Install Kubernetes Cluster on Ubuntu 20.04 with kubeadm

-   [Kubernetes](https://computingforgeeks.com/category/kubernetes/)
-   [Containers](https://computingforgeeks.com/category/containers/)
-   [How To](https://computingforgeeks.com/category/how-to/)
-   [Linux Tutorials](https://computingforgeeks.com/category/linux-tutorials/)

# Install Kubernetes Cluster on Ubuntu 20.04 with kubeadm

By

[Josphat Mutai](https://computingforgeeks.com/author/mutai-josphat/)

\-

August 17, 2023

307891

[82](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm/#comments)

.tdi\_3.td-a-rec{text-align:center}.tdi\_3 .td-element-style{z-index:-1}.tdi\_3.td-a-rec-img{text-align:left}.tdi\_3.td-a-rec-img img{margin:0 auto 0 0}@media(max-width:767px){.tdi\_3.td-a-rec-img{text-align:center}}

Kubernetes is a tool for orchestrating and managing containerized applications at scale on on-premise server or across hybrid cloud environments. Kubeadm is a tool provided with Kubernetes to help users install a production ready Kubernetes cluster with best practices enforcement. This tutorial will demonstrate how one can install a Kubernetes Cluster on Ubuntu 20.04 with kubeadm.

For Debian installation: [Deploy Kubernetes Cluster on Debian 10 with Kubespray](https://computingforgeeks.com/deploy-kubernetes-cluster-debian-with-kubespray/)if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-box-3","ezslot\_11",165,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-box-3-0");

For Rocky Linux 8: [Install Kubernetes Cluster on Rocky Linux 8 with Kubeadm & CRI-O](https://computingforgeeks.com/install-kubernetes-cluster-on-rocky-linux-with-kubeadm-crio/)

.tdi\_2.td-a-rec{text-align:center}.tdi\_2 .td-element-style{z-index:-1}.tdi\_2.td-a-rec-img{text-align:left}.tdi\_2.td-a-rec-img img{margin:0 auto 0 0}@media(max-width:767px){.tdi\_2.td-a-rec-img{text-align:center}}

There are two server types used in deployment of Kubernetes clusters:if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[580,400\],"computingforgeeks\_com-medrectangle-3","ezslot\_5",173,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-medrectangle-3-0");

-   **Master**: A Kubernetes Master is where control API calls for the pods, replications controllers, services, nodes and other components of a Kubernetes cluster are executed.
-   **Node**: A Node is a system that provides the run-time environments for the containers. A set of container pods can span multiple nodes.

The minimum requirements for the viable setup are:

-   Memory: **2 GiB** or more of RAM per machine
-   CPUs: At least **2 CPUs** on the control plane machine.
-   Internet connectivity for pulling containers required (Private registry can also be used)
-   Full network connectivity between machines in the cluster – This is private or public

## Install Kubernetes Cluster on Ubuntu 20.04

My Lab setup contain three servers. One control plane machine and two nodes to be used for running containerized workloads. You can add more nodes to suit your desired use case and load, for example using **three** control plane nodes for HA.if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[580,400\],"computingforgeeks\_com-medrectangle-4","ezslot\_6",167,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-medrectangle-4-0");

<table><tbody><tr><td><span class="has-inline-color has-luminous-vivid-orange-color">Server Type</span></td><td><span class="has-inline-color has-luminous-vivid-orange-color">Server Hostname</span></td><td><span class="has-inline-color has-luminous-vivid-orange-color">Specs</span></td></tr><tr><td>Master</td><td>k8s-master01.computingforgeeks.com</td><td>4GB Ram, 2vcpus</td></tr><tr><td>Worker</td><td>k8s-worker01.computingforgeeks.com</td><td>4GB Ram, 2vcpus</td></tr><tr><td>Worker</td><td>k8s-worker02.computingforgeeks.com</td><td>4GB Ram, 2vcpus</td></tr></tbody></table>

### Step 1: Install Kubernetes Servers

Provision the servers to be used in the deployment of Kubernetes on Ubuntu 20.04. The setup process will vary depending on the virtualization or cloud environment you’re using.

Once the servers are ready, update them.

```
sudo apt update && sudo apt -y full-upgrade
[ -f /var/run/reboot-required ] && sudo reboot -f
```

### Step 2: Install kubelet, kubeadm and kubectl

Once the servers are rebooted, add Kubernetes repository for Ubuntu 20.04 to all the servers.

```
sudo apt -y install curl apt-transport-https
curl  -fsSL  https://packages.cloud.google.com/apt/doc/apt-key.gpg|sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/kubernetes.gpg
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
```

Then install required packages.

```
sudo apt update
sudo apt -y install vim git curl wget kubelet kubeadm kubectl
sudo apt-mark hold kubelet kubeadm kubectl
```

Confirm installation by checking the version of kubectl.

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-large-leaderboard-2","ezslot\_28",550,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-large-leaderboard-2-0");

```
$ kubectl version --client && kubeadm version
Client Version: version.Info{Major:"1", Minor:"27", GitVersion:"v1.27.2", GitCommit:"7f6f68fdabc4df88cfea2dcf9a19b2b830f1e647", GitTreeState:"clean", BuildDate:"2023-05-17T14:20:07Z", GoVersion:"go1.20.4", Compiler:"gc", Platform:"linux/amd64"}
Kustomize Version: v5.0.1
kubeadm version: &version.Info{Major:"1", Minor:"27", GitVersion:"v1.27.2", GitCommit:"7f6f68fdabc4df88cfea2dcf9a19b2b830f1e647", GitTreeState:"clean", BuildDate:"2023-05-17T14:18:49Z", GoVersion:"go1.20.4", Compiler:"gc", Platform:"linux/amd64"}
```

### Step 3: Disable Swap

Turn off swap.

```
sudo sed -i '/ swap / s/^\(.*\)$/#\1/g' /etc/fstab
```

Now disable Linux swap space permanently in `/etc/fstab`. Search for a swap line and add `#` (hashtag) sign in front of the line.if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[250,250\],"computingforgeeks\_com-banner-1","ezslot\_30",169,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-banner-1-0");

```
$ sudo vim /etc/fstab
#/swap.imgnoneswapsw00
```

Confirm setting is correct

```
sudo swapoff -a
sudo mount -a
free -h
```

Enable kernel modules and configure sysctl.

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[250,250\],"computingforgeeks\_com-leader-1","ezslot\_18",560,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-leader-1-0");

```
# Enable kernel modules
sudo modprobe overlay
sudo modprobe br_netfilter

# Add some settings to sysctl
sudo tee /etc/sysctl.d/kubernetes.conf<<EOF
net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.ip_forward = 1
EOF

# Reload sysctl
sudo sysctl --system
```

### Step 4: Install Container runtime

To run containers in Pods, Kubernetes uses a container runtime. Supported container runtimes are:

-   Docker
-   CRI-O
-   Containerd

**NOTE**: You have to choose one runtime at a time.

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[250,250\],"computingforgeeks\_com-large-mobile-banner-2","ezslot\_17",700,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-large-mobile-banner-2-0");

#### Option 1: Install and Use Docker CE runtime:

```
# Add repo and Install packages
sudo apt update
sudo apt install -y curl gnupg2 software-properties-common apt-transport-https ca-certificates
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/docker-archive-keyring.gpg
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt update
sudo apt install -y containerd.io docker-ce docker-ce-cli

# Create required directories
sudo mkdir -p /etc/systemd/system/docker.service.d

# Create daemon json config file
sudo tee /etc/docker/daemon.json <<EOF
{
  "exec-opts": ["native.cgroupdriver=systemd"],
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "100m"
  },
  "storage-driver": "overlay2"
}
EOF

# Start and enable Services
sudo systemctl daemon-reload 
sudo systemctl restart docker
sudo systemctl enable docker
```

For Docker Engine you need a shim interface. You can install Mirantis cri-dockerd as covered in the guide below.

-   [Install Mirantis cri-dockerd as Docker Engine shim for Kubernetes](https://computingforgeeks.com/install-mirantis-cri-dockerd-as-docker-engine-shim-for-kubernetes/)

Mirantis cri-dockerd CRI socket file path is `/run/cri-dockerd.sock`. This is what will be used when configuring Kubernetes cluster.

#### Option 2: Install and Use CRI-O:

```
# Ensure you load modules
sudo modprobe overlay
sudo modprobe br_netfilter

# Set up required sysctl params
sudo tee /etc/sysctl.d/kubernetes.conf<<EOF
net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.ip_forward = 1
EOF

# Reload sysctl
sudo sysctl --system

# Add Cri-o repo
sudo su -
OS="xUbuntu_20.04"
VERSION=1.27
echo "deb https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/$OS/ /" > /etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list
echo "deb http://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable:/cri-o:/$VERSION/$OS/ /" > /etc/apt/sources.list.d/devel:kubic:libcontainers:stable:cri-o:$VERSION.list
curl -L https://download.opensuse.org/repositories/devel:kubic:libcontainers:stable:cri-o:$VERSION/$OS/Release.key | apt-key add -
curl -L https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/$OS/Release.key | apt-key add -

# Install CRI-O
sudo apt update
sudo apt install cri-o cri-o-runc

# Update CRI-O CIDR subnet
sudo sed -i 's/10.85.0.0/172.24.0.0/g' /etc/cni/net.d/100-crio-bridge.conf
sudo sed -i 's/10.85.0.0/172.24.0.0/g' /etc/cni/net.d/100-crio-bridge.conflist

# Start and enable Service
sudo systemctl daemon-reload
sudo systemctl restart crio
sudo systemctl enable crio
sudo systemctl status crio
```

#### Option 3: Install and Use Containerd:

```
# Configure persistent loading of modules
sudo tee /etc/modules-load.d/containerd.conf <<EOF
overlay
br_netfilter
EOF

# Load at runtime
sudo modprobe overlay
sudo modprobe br_netfilter

# Ensure sysctl params are set
sudo tee /etc/sysctl.d/kubernetes.conf<<EOF
net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.ip_forward = 1
EOF

# Reload configs
sudo sysctl --system

# Install required packages
sudo apt install -y curl gnupg2 software-properties-common apt-transport-https ca-certificates

# Add Docker repo
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/docker-archive-keyring.gpg
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

# Install containerd
sudo apt update
sudo apt install -y containerd.io

# Configure containerd and start service
sudo mkdir -p /etc/containerd
sudo containerd config default|sudo tee /etc/containerd/config.toml

# restart containerd
sudo systemctl restart containerd
sudo systemctl enable containerd
systemctl status  containerd
```

To use the systemd cgroup driver, set **plugins.cri.systemd\_cgroup = true** in `/etc/containerd/config.toml`. When using kubeadm, manually configure the [cgroup driver for kubelet](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/#configure-cgroup-driver-used-by-kubelet-on-control-plane-node)

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[250,250\],"computingforgeeks\_com-leader-2","ezslot\_19",701,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-leader-2-0");

### Step 5: Initialize master node

Login to the server to be used as master and make sure that the _br\_netfilter_ module is loaded:

```
$ lsmod | grep br_netfilter
br_netfilter           22256  0 
bridge                151336  2 br_netfilter,ebtable_broute
```

Enable kubelet service.

```
sudo systemctl enable kubelet
```

We now want to initialize the machine that will run the control plane components which includes _etcd_ (the cluster database) and the API Server.

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-leader-3","ezslot\_20",702,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-leader-3-0");if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-large-mobile-banner-1","ezslot\_2",703,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-large-mobile-banner-1-0");

Pull container images:

```
$ sudo kubeadm config images pull
[config/images] Pulled registry.k8s.io/kube-apiserver:v1.27.2
[config/images] Pulled registry.k8s.io/kube-controller-manager:v1.27.2
[config/images] Pulled registry.k8s.io/kube-scheduler:v1.27.2
[config/images] Pulled registry.k8s.io/kube-proxy:v1.27.2
[config/images] Pulled registry.k8s.io/pause:3.9
[config/images] Pulled registry.k8s.io/etcd:3.5.7-0
[config/images] Pulled registry.k8s.io/coredns/coredns:v1.10.1
```

If you have multiple CRI sockets, please use `--cri-socket` to select one:

```
# CRI-O
sudo kubeadm config images pull --cri-socket unix:///var/run/crio/crio.sock

# Containerd
sudo kubeadm config images pull --cri-socket unix:///run/containerd/containerd.sock

# Docker
sudo kubeadm config images pull --cri-socket unix:///run/cri-dockerd.sock 
```

These are the basic `kubeadm init` options that are used to bootstrap cluster.

```
--control-plane-endpoint :  set the shared endpoint for all control-plane nodes. Can be DNS/IP
--pod-network-cidr : Used to set a Pod network add-on CIDR
--cri-socket : Use if have more than one container runtime to set runtime socket path
--apiserver-advertise-address : Set advertise address for this particular control-plane node's API server
```

#### Bootstrap without shared endpoint

To bootstrap a cluster without using DNS endpoint, run:

```
### With Docker CE ###
sudo sysctl -p
sudo kubeadm init \
  --pod-network-cidr=172.24.0.0/16 \
  --cri-socket unix:///run/cri-dockerd.sock 

### With CRI-O###
sudo sysctl -p
sudo kubeadm init \
  --pod-network-cidr=172.24.0.0/16 \
  --cri-socket unix:///var/run/crio/crio.sock

### With Containerd ###
sudo sysctl -p
sudo kubeadm init \
  --pod-network-cidr=172.24.0.0/16 \
  --cri-socket unix:///run/containerd/containerd.sock
```

#### Bootstrap with shared endpoint (DNS name for control plane API)

Set cluster endpoint DNS name or add record to /etc/hosts file.

```
$ sudo vim /etc/hosts
172.29.20.5 k8s-cluster.computingforgeeks.com
```

**Create cluster:**

```
sudo sysctl -p
sudo kubeadm init \
  --pod-network-cidr=172.24.0.0/16 \
  --upload-certs \
  --control-plane-endpoint=k8s-cluster.computingforgeeks.com
```

**Note**: If _**172.24.0.0/16**_ is already in use within your network you must select a different pod network CIDR, replacing 172.24.0.0/16 in the above command.

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[250,250\],"computingforgeeks\_com-leader-4","ezslot\_21",704,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-leader-4-0");

Container runtime sockets:

| Runtime | Path to Unix domain socket |
| --- | --- |
| Docker | `unix:///run/cri-dockerd.sock` |
| containerd | `unix:///run/containerd/containerd.sock` |
| CRI-O | `unix:///var/run/crio/crio.sock` |

You can optionally pass Socket file for runtime and advertise address depending on your setup.

```
# CRI-O
sudo kubeadm init \
  --pod-network-cidr=172.24.0.0/16 \
  --cri-socket unix:///var/run/crio/crio.sock \
  --upload-certs \
  --control-plane-endpoint=k8s-cluster.computingforgeeks.com

# Containerd
sudo kubeadm init \
  --pod-network-cidr=172.24.0.0/16 \
  --cri-socket unix:///run/containerd/containerd.sock \
  --upload-certs \
  --control-plane-endpoint=k8s-cluster.computingforgeeks.com

# Docker
# Must do https://computingforgeeks.com/install-mirantis-cri-dockerd-as-docker-engine-shim-for-kubernetes/
sudo kubeadm init \
  --pod-network-cidr=172.24.0.0/16 \
  --cri-socket unix:///run/cri-dockerd.sock  \
  --upload-certs \
  --control-plane-endpoint=k8s-cluster.computingforgeeks.com
```

Here is the output of my initialization command.

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-mobile-leaderboard-1","ezslot\_22",705,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-mobile-leaderboard-1-0");

```
....
[init] Using Kubernetes version: v1.27.2
[preflight] Running pre-flight checks
[WARNING Firewalld]: firewalld is active, please ensure ports [6443 10250] are open or your cluster may not function correctly
[preflight] Pulling images required for setting up a Kubernetes cluster
[preflight] This might take a minute or two, depending on the speed of your internet connection
[preflight] You can also perform this action in beforehand using 'kubeadm config images pull'
[kubelet-start] Writing kubelet environment file with flags to file "/var/lib/kubelet/kubeadm-flags.env"
[kubelet-start] Writing kubelet configuration to file "/var/lib/kubelet/config.yaml"
[kubelet-start] Starting the kubelet
[certs] Using certificateDir folder "/etc/kubernetes/pki"
[certs] Using existing ca certificate authority
[certs] Using existing apiserver certificate and key on disk
[certs] Using existing apiserver-kubelet-client certificate and key on disk
[certs] Using existing front-proxy-ca certificate authority
[certs] Using existing front-proxy-client certificate and key on disk
[certs] Using existing etcd/ca certificate authority
[certs] Using existing etcd/server certificate and key on disk
[certs] Using existing etcd/peer certificate and key on disk
[certs] Using existing etcd/healthcheck-client certificate and key on disk
[certs] Using existing apiserver-etcd-client certificate and key on disk
[certs] Using the existing "sa" key
[kubeconfig] Using kubeconfig folder "/etc/kubernetes"
[kubeconfig] Using existing kubeconfig file: "/etc/kubernetes/admin.conf"
[kubeconfig] Using existing kubeconfig file: "/etc/kubernetes/kubelet.conf"
[kubeconfig] Using existing kubeconfig file: "/etc/kubernetes/controller-manager.conf"
[kubeconfig] Using existing kubeconfig file: "/etc/kubernetes/scheduler.conf"
[control-plane] Using manifest folder "/etc/kubernetes/manifests"
[control-plane] Creating static Pod manifest for "kube-apiserver"
[control-plane] Creating static Pod manifest for "kube-controller-manager"
W0611 22:34:23.276374    4726 manifests.go:225] the default kube-apiserver authorization-mode is "Node,RBAC"; using "Node,RBAC"
[control-plane] Creating static Pod manifest for "kube-scheduler"
W0611 22:34:23.278380    4726 manifests.go:225] the default kube-apiserver authorization-mode is "Node,RBAC"; using "Node,RBAC"
[etcd] Creating static Pod manifest for local etcd in "/etc/kubernetes/manifests"
[wait-control-plane] Waiting for the kubelet to boot up the control plane as static Pods from directory "/etc/kubernetes/manifests". This can take up to 4m0s
[apiclient] All control plane components are healthy after 8.008181 seconds
[upload-config] Storing the configuration used in ConfigMap "kubeadm-config" in the "kube-system" Namespace
[kubelet] Creating a ConfigMap "kubelet-config-1.21" in namespace kube-system with the configuration for the kubelets in the cluster
[upload-certs] Skipping phase. Please see --upload-certs
[mark-control-plane] Marking the node k8s-master01.computingforgeeks.com as control-plane by adding the label "node-role.kubernetes.io/master=''"
[mark-control-plane] Marking the node k8s-master01.computingforgeeks.com as control-plane by adding the taints [node-role.kubernetes.io/master:NoSchedule]
[bootstrap-token] Using token: zoy8cq.6v349sx9ass8dzyj
[bootstrap-token] Configuring bootstrap tokens, cluster-info ConfigMap, RBAC Roles
[bootstrap-token] configured RBAC rules to allow Node Bootstrap tokens to get nodes
[bootstrap-token] configured RBAC rules to allow Node Bootstrap tokens to post CSRs in order for nodes to get long term certificate credentials
[bootstrap-token] configured RBAC rules to allow the csrapprover controller automatically approve CSRs from a Node Bootstrap Token
[bootstrap-token] configured RBAC rules to allow certificate rotation for all node client certificates in the cluster
[bootstrap-token] Creating the "cluster-info" ConfigMap in the "kube-public" namespace
[kubelet-finalize] Updating "/etc/kubernetes/kubelet.conf" to point to a rotatable kubelet client certificate and key
[addons] Applied essential addon: CoreDNS
[addons] Applied essential addon: kube-proxy

Your Kubernetes control-plane has initialized successfully!

To start using your cluster, you need to run the following as a regular user:

  mkdir -p $HOME/.kube
  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
  sudo chown $(id -u):$(id -g) $HOME/.kube/config

You should now deploy a pod network to the cluster.
Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
  https://kubernetes.io/docs/concepts/cluster-administration/addons/

You can now join any number of control-plane nodes by copying certificate authorities
and service account keys on each node and then running the following as root:

  kubeadm join k8s-cluster.computingforgeeks.com:6443 --token sr4l2l.2kvot0pfalh5o4ik \
    --discovery-token-ca-cert-hash sha256:c692fb047e15883b575bd6710779dc2c5af8073f7cab460abd181fd3ddb29a18 \
    --control-plane 

Then you can join any number of worker nodes by running the following on each as root:

kubeadm join k8s-cluster.computingforgeeks.com:6443 --token sr4l2l.2kvot0pfalh5o4ik \
    --discovery-token-ca-cert-hash sha256:c692fb047e15883b575bd6710779dc2c5af8073f7cab460abd181fd3ddb29a18
```

Configure kubectl using commands in the output:

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[250,250\],"computingforgeeks\_com-mobile-leaderboard-2","ezslot\_23",706,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-mobile-leaderboard-2-0");

```
mkdir -p $HOME/.kube
sudo cp -f /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
```

Check cluster status:

```
$ kubectl cluster-info
Kubernetes master is running at https://k8s-cluster.computingforgeeks.com:6443
KubeDNS is running at https://k8s-cluster.computingforgeeks.com:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
```

Additional Master nodes can be added using the command in installation output:

```
kubeadm join k8s-cluster.computingforgeeks.com:6443 --token sr4l2l.2kvot0pfalh5o4ik \
    --discovery-token-ca-cert-hash sha256:c692fb047e15883b575bd6710779dc2c5af8073f7cab460abd181fd3ddb29a18 \
    --control-plane
```

### Step 6: Install network plugin on Master

In this guide we’ll use [Calico](https://projectcalico.org/). You can choose any other [supported network plugins](https://kubernetes.io/docs/concepts/cluster-administration/addons/).

Download operator and custom resource files. See [releases page](https://github.com/projectcalico/calico/releases) for latest version.

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-narrow-sky-1","ezslot\_24",707,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-narrow-sky-1-0");

```
curl -O https://raw.githubusercontent.com/projectcalico/calico/v3.26.1/manifests/tigera-operator.yaml
curl -O https://raw.githubusercontent.com/projectcalico/calico/v3.26.1/manifests/custom-resources.yaml 
```

First, install the operator on your cluster.

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[250,250\],"computingforgeeks\_com-portrait-1","ezslot\_32",708,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-portrait-1-0");

```
$ kubectl create -f tigera-operator.yaml
namespace/tigera-operator created
customresourcedefinition.apiextensions.k8s.io/bgpconfigurations.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/bgppeers.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/blockaffinities.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/caliconodestatuses.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/clusterinformations.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/felixconfigurations.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/globalnetworkpolicies.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/globalnetworksets.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/hostendpoints.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/ipamblocks.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/ipamconfigs.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/ipamhandles.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/ippools.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/ipreservations.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/kubecontrollersconfigurations.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/networkpolicies.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/networksets.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/apiservers.operator.tigera.io created
customresourcedefinition.apiextensions.k8s.io/imagesets.operator.tigera.io created
customresourcedefinition.apiextensions.k8s.io/installations.operator.tigera.io created
customresourcedefinition.apiextensions.k8s.io/tigerastatuses.operator.tigera.io created
serviceaccount/tigera-operator created
clusterrole.rbac.authorization.k8s.io/tigera-operator created
clusterrolebinding.rbac.authorization.k8s.io/tigera-operator created
deployment.apps/tigera-operator created
```

If you wish to customize the Calico install, customize the downloaded custom-resources.yaml. For example we are updating CIDR.

```
sed -ie 's/192.168.0.0/172.24.0.0/g' custom-resources.yaml
```

Use the manifest locally then install Calico:

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-netboard-2","ezslot\_29",709,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-netboard-2-0");

```
$ kubectl create -f custom-resources.yaml
installation.operator.tigera.io/default created
apiserver.operator.tigera.io/default created
```

Confirm that all of the pods are running:

```
$ kubectl get pods --all-namespaces -w
NAMESPACE         NAME                               READY   STATUS    RESTARTS   AGE
kube-system       coredns-5d78c9869d-5fmlg           1/1     Running   0          9m43s
kube-system       coredns-5d78c9869d-gtlwr           1/1     Running   0          9m43s
kube-system       etcd-focal                         1/1     Running   0          10m
kube-system       kube-apiserver-focal               1/1     Running   0          9m58s
kube-system       kube-controller-manager-focal      1/1     Running   0          9m59s
kube-system       kube-proxy-pgvnf                   1/1     Running   0          9m43s
kube-system       kube-scheduler-focal               1/1     Running   0          9m57s
tigera-operator   tigera-operator-549d4f9bdb-gfdcf   1/1     Running   0          91s
```

For Single node cluster allow Pods to run on master nodes:

```
kubectl taint nodes --all node-role.kubernetes.io/master-
kubectl taint nodes --all  node-role.kubernetes.io/control-plane-
```

Confirm master node is ready:

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-narrow-sky-2","ezslot\_25",710,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-narrow-sky-2-0");

```
# CRI-O
$ kubectl get nodes -o wide
NAME     STATUS   ROLES                  AGE   VERSION   INTERNAL-IP      EXTERNAL-IP   OS-IMAGE             KERNEL-VERSION     CONTAINER-RUNTIME
ubuntu   Ready    control-plane,master   38s   v1.27.2   143.198.114.46   <none>        Ubuntu 20.04.3 LTS   5.4.0-88-generic   cri-o://1.27.0

# Containerd
$ kubectl get nodes -o wide
NAME     STATUS   ROLES                  AGE   VERSION   INTERNAL-IP      EXTERNAL-IP   OS-IMAGE             KERNEL-VERSION     CONTAINER-RUNTIME
ubuntu   Ready    control-plane,master   15m   v1.27.2   143.198.114.46   <none>        Ubuntu 20.04.3 LTS   5.4.0-88-generic   containerd://1.6.21

# Docker
$ kubectl get nodes -o wide
NAME           STATUS   ROLES    AGE   VERSION   INTERNAL-IP      EXTERNAL-IP   OS-IMAGE           KERNEL-VERSION     CONTAINER-RUNTIME
k8s-master01   Ready    master   64m   v1.27.2   135.181.28.113   <none>        Ubuntu 20.04 LTS   5.4.0-37-generic   docker://24.0.1
```

### Step 7: Add worker nodes

With the control plane ready you can add worker nodes to the cluster for running scheduled workloads.

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[336,280\],"computingforgeeks\_com-portrait-2","ezslot\_33",711,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-portrait-2-0");

If endpoint address is not in DNS, add record to _/etc/hosts_.

```
$ sudo vim /etc/hosts
172.29.20.5 k8s-cluster.computingforgeeks.com
```

The join command that was given is used to add a worker node to the cluster.

```
kubeadm join k8s-cluster.computingforgeeks.com:6443 \
  --token sr4l2l.2kvot0pfalh5o4ik \
  --discovery-token-ca-cert-hash sha256:c692fb047e15883b575bd6710779dc2c5af8073f7cab460abd181fd3ddb29a18
```

Output:

```
[preflight] Reading configuration from the cluster...
[preflight] FYI: You can look at this config file with 'kubectl -n kube-system get cm kubeadm-config -oyaml'
[kubelet-start] Downloading configuration for the kubelet from the "kubelet-config-1.21" ConfigMap in the kube-system namespace
[kubelet-start] Writing kubelet configuration to file "/var/lib/kubelet/config.yaml"
[kubelet-start] Writing kubelet environment file with flags to file "/var/lib/kubelet/kubeadm-flags.env"
[kubelet-start] Starting the kubelet
[kubelet-start] Waiting for the kubelet to perform the TLS Bootstrap...

This node has joined the cluster:
* Certificate signing request was sent to apiserver and a response was received.
* The Kubelet was informed of the new secure connection details.
```

Run below command on the control-plane to see if the node joined the cluster.

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[250,250\],"computingforgeeks\_com-sky-3","ezslot\_34",712,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-sky-3-0");

```
$ kubectl get nodes
NAME                                 STATUS   ROLES    AGE   VERSION
k8s-master01.computingforgeeks.com   Ready    master   10m   v1.27.2
k8s-worker01.computingforgeeks.com   Ready    <none>   50s   v1.27.2
k8s-worker02.computingforgeeks.com   Ready    <none>   12s   v1.27.2

$ kubectl get nodes -o wide
```

If the join token is expired, refer to our guide on how to join worker nodes.

-   [Join new Kubernetes Worker Node to an existing Cluster](https://computingforgeeks.com/join-new-kubernetes-worker-node-to-existing-cluster/)

### Step 8: Deploy application on cluster

If you only have a single node cluster, check our guide on how to run container pods on master nodes:

-   [Scheduling Pods on Kubernetes Control plane (Master) Nodes](https://computingforgeeks.com/how-to-schedule-pods-on-kubernetes-control-plane-node/)

We need to validate that our cluster is working by deploying an application.

```
kubectl apply -f https://k8s.io/examples/pods/commands.yaml
```

Check to see if pod started

```
$ kubectl get pods
NAME           READY   STATUS      RESTARTS   AGE
command-demo   0/1     Completed   0          16s
```

### Step 9: Install Kubernetes Dashboard (Optional)

Kubernetes dashboard can be used to deploy containerized applications to a Kubernetes cluster, troubleshoot your containerized application, and manage the cluster resources.

Refer to our guide for installation: [How To Install Kubernetes Dashboard with NodePort](https://computingforgeeks.com/how-to-install-kubernetes-dashboard-with-nodeport/)

### Step 10: Install Metrics Server ( For checking Pods and Nodes resource usage)

_Metrics Server_ is a cluster-wide aggregator of resource usage data. It collects metrics from the _Summary API_, exposed by **Kubelet** on each node. Use our guide below to deploy it:

-   [How To Deploy Metrics Server to Kubernetes Cluster](https://computingforgeeks.com/how-to-deploy-metrics-server-to-kubernetes-cluster/)

### Step 11: Deploy Prometheus / Grafana Monitoring

Prometheus is a full fledged solution that enables you to access advanced metrics capabilities in a Kubernetes cluster. Grafana is used for analytics and interactive visualization of metrics that’s collected and stored in Prometheus database. We have a complete guide on how to setup complete monitoring stack on Kubernetes Cluster:

-   [Setup Prometheus and Grafana on Kubernetes using prometheus-operator](https://computingforgeeks.com/setup-prometheus-and-grafana-on-kubernetes/)

### Step 12: Persistent Storage Configuration ideas (Optional)

If you’re also looking for a Persistent storage solution for your Kubernetes, checkout:

-   [How To Deploy Rook Ceph Storage on Kubernetes Cluster](https://computingforgeeks.com/how-to-deploy-rook-ceph-storage-on-kubernetes-cluster/)
-   [Ceph Persistent Storage for Kubernetes with Cephfs](https://computingforgeeks.com/ceph-persistent-storage-for-kubernetes-with-cephfs/)
-   [Persistent Storage for Kubernetes with Ceph RBD](https://computingforgeeks.com/persistent-storage-for-kubernetes-with-ceph-rbd/)
-   [How To Configure Kubernetes Dynamic Volume Provisioning With Heketi & GlusterFS](https://computingforgeeks.com/configure-kubernetes-dynamic-volume-provisioning-with-heketi-glusterfs/)
-   [Deploy and Use OpenEBS Container Storage on Kubernetes](https://computingforgeeks.com/deploy-and-use-openebs-container-storage-on-kubernetes/)

### 13\. Install Nginx Ingress Controller

If Nginx is your preferred Ingress controller for Kubernetes workloads, you can use our guide for the installation process:

-   [Deploy Nginx Ingress Controller on Kubernetes using Helm Chart](https://computingforgeeks.com/deploy-nginx-ingress-controller-on-kubernetes-using-helm-chart/)

### 14\. Deploy MetalLB Load Balancer

Follow the guide below to install and configure MetalLB on Kubernetes:

-   [How To Deploy MetalLB Load Balancer on Kubernetes Cluster](https://computingforgeeks.com/deploy-metallb-load-balancer-on-kubernetes/)

More guides:

-   [Using Horizontal Pod Autoscaler on Kubernetes Cluster](https://computingforgeeks.com/using-horizontal-pod-autoscaler-on-kubernetes/)
-   [Install Kubernetes Metrics Server](https://computingforgeeks.com/how-to-deploy-metrics-server-to-kubernetes-cluster/)

Similar Kubernetes deployment guides:

-   [Install Kubernetes Cluster on CentOS 7 with kubeadm](https://computingforgeeks.com/install-kubernetes-cluster-on-centos-with-kubeadm/)
-   [Install Production Kubernetes Cluster with Rancher RKE](https://computingforgeeks.com/install-kubernetes-production-cluster-using-rancher-rke/)
-   [How To Deploy Lightweight Kubernetes Cluster in 5 minutes with K3s](https://computingforgeeks.com/how-to-deploy-lightweight-kubernetes-cluster-with-k3s/)
-   [Deploy Production Ready Kubernetes Cluster with Ansible & Kubespray](https://computingforgeeks.com/deploy-production-kubernetes-cluster-with-ansible/)

.tdi\_4.td-a-rec{text-align:center}.tdi\_4 .td-element-style{z-index:-1}.tdi\_4.td-a-rec-img{text-align:left}.tdi\_4.td-a-rec-img img{margin:0 auto 0 0}@media(max-width:767px){.tdi\_4.td-a-rec-img{text-align:center}}

### YOU CAN SUPPORT OUR WORK WITH A CUP OF COFFEE

___

As we continue to grow, we would wish to reach and impact more people who visit and take advantage of the guides we have on our blog. This is a big task for us and we are so far extremely grateful for the kind people who have shown amazing support for our work over the time we have been online.

Thank You for your support as we work to give you the best of guides and articles. Click below to buy us a coffee.

[![PayPal Support](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22200%22%20height=%2251%22%3E%3C/svg%3E)](https://paypal.me/techaiops?country.x=BS&locale.x=en_US)

-   TAGS
-   [kubernetes](https://computingforgeeks.com/tag/kubernetes/)

Previous article[Best Books to learn Web Development – PHP, HTML, CSS, JavaScript and jQuery](https://computingforgeeks.com/best-books-to-learn-web-development/)

Next article[Top Terminal Based Monitoring Tools for Linux](https://computingforgeeks.com/top-terminal-based-monitoring-tools-for-linux/)

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2296%22%20height=%2296%22%3E%3C/svg%3E)](https://computingforgeeks.com/author/mutai-josphat/)

[Josphat Mutai](https://computingforgeeks.com/author/mutai-josphat/)

[https://computingforgeeks.com/](https://computingforgeeks.com/)

Founder of Computingforgeeks. Expertise in Virtualization, Cloud, Linux/UNIX Administration, Automation,Storage Systems, Containers, Server Clustering e.t.c.

[Linkedin](https://www.linkedin.com/in/josphat-mutai-37bb08bb "Linkedin") [Twitter](https://twitter.com/jj_mutai "Twitter")

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-netboard-1","ezslot\_26",118,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-netboard-1-0");if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-netboard-1","ezslot\_27",118,"0","1"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-netboard-1-0\_1"); .netboard-1-multi-118{border:none !important;display:block !important;float:none !important;line-height:0px;margin-bottom:15px !important;margin-left:auto !important;margin-right:auto !important;margin-top:15px !important;max-width:100% !important;min-height:250px;min-width:300px;padding:0;text-align:center !important;}

var block\_tdi\_5=new tdBlock();block\_tdi\_5.id="tdi\_5";block\_tdi\_5.atts='{"limit":9,"ajax\_pagination":"next\_prev","live\_filter":"cur\_post\_same\_tags","td\_ajax\_filter\_type":"td\_custom\_related","class":"tdi\_5","td\_column\_number":3,"block\_type":"td\_block\_related\_posts","live\_filter\_cur\_post\_id":59740,"live\_filter\_cur\_post\_author":"3","block\_template\_id":"","header\_color":"","ajax\_pagination\_infinite\_stop":"","offset":"","td\_ajax\_preloading":"","td\_filter\_default\_txt":"","td\_ajax\_filter\_ids":"","el\_class":"","color\_preset":"","ajax\_pagination\_next\_prev\_swipe":"","border\_top":"","css":"","tdc\_css":"","tdc\_css\_class":"tdi\_5","tdc\_css\_class\_style":"tdi\_5\_rand\_style"}';block\_tdi\_5.td\_column\_number="3";block\_tdi\_5.block\_type="td\_block\_related\_posts";block\_tdi\_5.post\_count="9";block\_tdi\_5.found\_posts="86";block\_tdi\_5.header\_color="";block\_tdi\_5.ajax\_pagination\_infinite\_stop="";block\_tdi\_5.max\_num\_pages="10";tdBlocksArray.push(block\_tdi\_5);

#### [RELATED ARTICLES](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#)[MORE FROM AUTHOR](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#)

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22218%22%20height=%22150%22%3E%3C/svg%3E "Upgrading Kubespray Kubernetes Cluster to newer release")](https://computingforgeeks.com/kubespray-kubernetes-cluster-to-newer-release/ "Upgrading Kubespray Kubernetes Cluster to newer release")

[Automation](https://computingforgeeks.com/category/automation/)

### [Upgrading Kubespray Kubernetes Cluster to newer release](https://computingforgeeks.com/kubespray-kubernetes-cluster-to-newer-release/ "Upgrading Kubespray Kubernetes Cluster to newer release")

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22218%22%20height=%22150%22%3E%3C/svg%3E "Perform Safe & Automatic Node Reboots on Kubernetes with Kured")](https://computingforgeeks.com/perform-automatic-node-reboots-on-kubernetes-with-kured/ "Perform Safe & Automatic Node Reboots on Kubernetes with Kured")

[Containers](https://computingforgeeks.com/category/containers/)

### [Perform Safe & Automatic Node Reboots on Kubernetes with Kured](https://computingforgeeks.com/perform-automatic-node-reboots-on-kubernetes-with-kured/ "Perform Safe & Automatic Node Reboots on Kubernetes with Kured")

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22218%22%20height=%22150%22%3E%3C/svg%3E "Install and Use KubeSphere on existing Kubernetes cluster")](https://computingforgeeks.com/install-use-kubesphere-on-existing-kubernetes-cluster/ "Install and Use KubeSphere on existing Kubernetes cluster")

[Automation](https://computingforgeeks.com/category/automation/)

### [Install and Use KubeSphere on existing Kubernetes cluster](https://computingforgeeks.com/install-use-kubesphere-on-existing-kubernetes-cluster/ "Install and Use KubeSphere on existing Kubernetes cluster")

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22218%22%20height=%22150%22%3E%3C/svg%3E "How to deploy Redis StatefulSet Cluster in Kubernetes")](https://computingforgeeks.com/how-to-deploy-redis-statefulset-cluster-in-kubernetes/ "How to deploy Redis StatefulSet Cluster in Kubernetes")

[Cloud](https://computingforgeeks.com/category/cloud/)

### [How to deploy Redis StatefulSet Cluster in Kubernetes](https://computingforgeeks.com/how-to-deploy-redis-statefulset-cluster-in-kubernetes/ "How to deploy Redis StatefulSet Cluster in Kubernetes")

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22218%22%20height=%22150%22%3E%3C/svg%3E "Deploy Kubernetes Cluster on AlmaLinux 8 with Kubeadm")](https://computingforgeeks.com/deploy-kubernetes-cluster-on-almalinux-with-kubeadm/ "Deploy Kubernetes Cluster on AlmaLinux 8 with Kubeadm")

[AlmaLinux](https://computingforgeeks.com/category/almalinux/)

### [Deploy Kubernetes Cluster on AlmaLinux 8 with Kubeadm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-almalinux-with-kubeadm/ "Deploy Kubernetes Cluster on AlmaLinux 8 with Kubeadm")

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22218%22%20height=%22150%22%3E%3C/svg%3E "Install Kubernetes Cluster on Rocky Linux 8 with Kubeadm & CRI-O")](https://computingforgeeks.com/install-kubernetes-cluster-on-rocky-linux-with-kubeadm-crio/ "Install Kubernetes Cluster on Rocky Linux 8 with Kubeadm & CRI-O")

[Containers](https://computingforgeeks.com/category/containers/)

### [Install Kubernetes Cluster on Rocky Linux 8 with Kubeadm & CRI-O](https://computingforgeeks.com/install-kubernetes-cluster-on-rocky-linux-with-kubeadm-crio/ "Install Kubernetes Cluster on Rocky Linux 8 with Kubeadm & CRI-O")

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22218%22%20height=%22150%22%3E%3C/svg%3E "Payment solutions for hotels – everything you need to know")](https://computingforgeeks.com/payment-solutions-for-hotels-everything-you-need-to-know/ "Payment solutions for hotels – everything you need to know")

[Business](https://computingforgeeks.com/category/business/)

### [Payment solutions for hotels – everything you need to know](https://computingforgeeks.com/payment-solutions-for-hotels-everything-you-need-to-know/ "Payment solutions for hotels – everything you need to know")

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22218%22%20height=%22150%22%3E%3C/svg%3E "Run Kubernetes on Debian 11 with Minikube")](https://computingforgeeks.com/run-kubernetes-on-debian-11-with-minikube/ "Run Kubernetes on Debian 11 with Minikube")

[Containers](https://computingforgeeks.com/category/containers/)

### [Run Kubernetes on Debian 11 with Minikube](https://computingforgeeks.com/run-kubernetes-on-debian-11-with-minikube/ "Run Kubernetes on Debian 11 with Minikube")

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22218%22%20height=%22150%22%3E%3C/svg%3E "k0s vs k3s vs microk8s Kubernetes Distributions Comparison")](https://computingforgeeks.com/k0s-vs-k3s-vs-microk8s-kubernetes-distributions-comparison/ "k0s vs k3s vs microk8s Kubernetes Distributions Comparison")

[Automation](https://computingforgeeks.com/category/automation/)

### [k0s vs k3s vs microk8s Kubernetes Distributions Comparison](https://computingforgeeks.com/k0s-vs-k3s-vs-microk8s-kubernetes-distributions-comparison/ "k0s vs k3s vs microk8s Kubernetes Distributions Comparison")

[](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#)[](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#)

#### 82 COMMENTS

1.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Jim [February 17, 2021 At 9:51 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-2150)
    
    Several issues in these steps. Trying to follow with containerd setup – an example error is no step to create /var/lib/kubelet/config.yaml. Another, it enters into a root bash but doesn’t exit. And kubeadm config images pull leads to ‘unknown service runtime.v1alpha2.ImageService’ error.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-2150)
    
2.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Guido [March 25, 2021 At 3:39 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-5605)
    
    This not working:  
    sudo kubeadm config images pull  
    failed to pull image “k8s.gcr.io/kube-apiserver:v1.20.5″: output: time=”2021-03-25T12:37:30Z” level=fatal msg=”pulling image failed: rpc error: code = Unimplemented desc = unknown service runtime.v1alpha2.ImageService”  
    , error: exit status 1  
    To see the stack trace of this error execute with –v=5 or higher
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-5605)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Trinh Dong Nam [May 13, 2022 At 2:52 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10758)
        
        Hi Guido, Because the command install kubelet doesn’t determine the version, if you follow command of this guide, it will install the last version of kubelet, it doesn’t support on Ubuntu 20.4.  
        Replace command install kubelet, kubeadm, kubectl as below:  
        apt update && apt install -y vim git curl wget kubeadm=1.22.1-00 kubelet=1.22.1-00 kubectl=1.22.1-00
        
        Hope it’s helpful for you.
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10758)
        
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Namtd [May 13, 2022 At 2:54 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10759)
        
        Hi Guido, Because the command install kubelet doesn’t determine the version, if you follow command of this guide, it will install the last version of kubelet, it doesn’t support on Ubuntu 20.4.  
        Replace command install kubelet, kubeadm, kubectl as below:  
        apt update && apt install -y vim git curl wget kubeadm=1.22.1-00 kubelet=1.22.1-00 kubectl=1.22.1-00
        
        Hope it is helpful for you.
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10759)
        
3.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) R31 [May 7, 2021 At 12:13 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-7486)
    
    Its working. thanks.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-7486)
    
4.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) regin [July 31, 2021 At 10:59 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8081)
    
    Awesome working example! Thanks.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8081)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [October 13, 2021 At 11:03 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8741)
        
        Welcome!
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8741)
        
5.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) saurabh gore [August 18, 2021 At 9:40 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8212)
    
    after reproducing the steps mentioned I found out that kubectl get nodes does not show the nodes  
    and shows the error The connection to the server localhost:8080 was refused – did you specify the right host or port?  
    Any help asap would be highly appreciated
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8212)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Anand Chettri [October 12, 2021 At 7:11 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8732)
        
        Follow below commands and execute the “kubectl get nodes” using non-root user  
        mkdir -p $HOME/.kube  
        sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config  
        sudo chown $(id -u):$(id -g) $HOME/.kube/config
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8732)
        
6.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) ihc [October 13, 2021 At 3:18 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8739)
    
    To install Calico I had to:  
    curl [https://docs.projectcalico.org/manifests/calico.yaml](https://docs.projectcalico.org/manifests/calico.yaml) -O  
    kubectl apply -f calico.yaml
    
    Steps above did not work.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8739)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [October 13, 2021 At 11:03 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8742)
        
        Any error when using steps in this guide?
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8742)
        
        -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) faraz [October 19, 2021 At 10:52 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8792)
            
            yes
            
            [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8792)
            
        -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) faraz [October 19, 2021 At 10:53 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8793)
            
            root@k-master:~# sudo apt install cri-o cri-o-runc  
            Reading package lists… Done  
            Building dependency tree  
            Reading state information… Done  
            E: Unable to locate package cri-o
            
            kindly check
            
            [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8793)
            
            -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [October 19, 2021 At 2:01 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8797)
                
                Did you follow steps under # Add Cri-o repo?
                
                [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8797)
                
                -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) bordeux [December 19, 2021 At 10:54 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9411)
                    
                    I followed using containerd and looks like @ihc have right. With his help i was able to run cluster
                    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) HB [November 30, 2021 At 4:59 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9214)
        
        I just came here to say, Thank you ihc. Your comment saved me headche.
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9214)
        
7.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) AK [October 16, 2021 At 6:27 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8773)
    
    Some issues getting this to work. Here are the items I changed to get it going:
    
    First, there was an issue getting containerd to start. The issue was that the config was not saved properly. In the “Installing containerd” section above, there was a missing \`>\` in the following command (I really hope my pre and /pre tags work):
    
    containerd config default /etc/containerd/config.toml
    
    It needs to be:
    
    containerd config default > /etc/containerd/config.toml
    
    Then there was an issue with flannel but that resolved itself:  
    [https://github.com/flannel-io/flannel/issues/1482](https://github.com/flannel-io/flannel/issues/1482)
    
    Then, once the control plane node was up, the worker nodes would not go to ready state. I resolved this by setting the containerd.default\_runtime (Again, I really hope my pre and /pre tags work):
    
    \[plugins.”io.containerd.grpc.v1.cri”.containerd.default\_runtime\]  
    runtime\_type = “io.containerd.runtime.v1.linux”
    
    Hopefully this helps someone else…
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8773)
    
8.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Simon [October 19, 2021 At 9:23 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8805)
    
    Thanks for the perfect working example and it worked for me.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8805)
    
9.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Jeffrey [October 22, 2021 At 6:23 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8827)
    
    Where does the IP of “cluster endpoint DNS name” come from? You’re using 172.29.20.5. My controlplane’s IP is 172.17.0.1. Should I use that?
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8827)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [October 22, 2021 At 8:51 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8829)
        
        Hey,
        
        It will be an A record pointing to 172.17.0.1.
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8829)
        
10.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Michael Cooper](http://www.rpihobby.us) [October 25, 2021 At 7:32 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8865)
    
    Hey Everyone,
    
    Great article, however I have a question where are the steps for installing kubenetes on the worker nodes do you follow the same procedure as the Controller Node? Were do you stop to get the worker node properly funtional?
    
    Sorry I am new to kubernetes  
    Thanks,  
    Michael
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8865)
    
11.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [October 27, 2021 At 1:45 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8874)
    
    Hi,
    
    It is captured in step 7.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-8874)
    
12.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Chris [November 14, 2021 At 8:11 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9061)
    
    Following your instructions completely using the CRIO install, no pods can access the internet. The master comes up fine and the nodes come up fine and I can do deployments and everything.
    
    pods just can not access the internet. I tried to setup jenkins and it was not able to access the internet to install the plugins
    
    Something is flawed in your instructions
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9061)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [November 15, 2021 At 12:56 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9072)
        
        Hi Chris.
        
        I noted the issue was with CRIO subnet defined in /etc/cni/net.d/100-crio-bridge.conf config file. It is different from Pod network defined when bootstrapping k8s cluster.
        
        You can retry with updated article. Basically change the subnet with command below:
        
        sudo sed -i ‘s/10.85.0.0/192.168.0.0/g’ /etc/cni/net.d/100-crio-bridge.conf
        
        Then restart crio service and bootstrap cluster. I hope this helps.
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9072)
        
        -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Chris McKenna [November 15, 2021 At 9:43 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9080)
            
            my home network is already running on 192.168.0 subnet. I thought you could not use a pod network the same as an already in use subnet?
            
            [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9080)
            
        -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Chris McKenna [November 16, 2021 At 3:22 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9081)
            
            sudo sed -i ‘s/10.85.0.0/192.168.0.0/g’ /etc/cni/net.d/100-crio-bridge.conf  
            sed: can’t read /etc/cni/net.d/100-crio-bridge.conf: No such file or directory
            
            root@kube-master:~# more /etc/cni/net.d/100-crio-bridge.conf  
            more: stat of /etc/cni/net.d/100-crio-bridge.conf failed: No such file or directory
            
            [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9081)
            
13.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Chris McKenna [November 15, 2021 At 12:57 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9064)
    
    I tried all 3 container management types in this tutorial and none of the pods can access the internet. They can talk to each other but nothing in the outside world. I installed Jenkins in kubernetes and I need to install the plugins but can’t because if this issue. Please advise
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9064)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [November 15, 2021 At 12:40 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9071)
        
        See previous comment
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9071)
        
        -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Chris McKenna [November 15, 2021 At 9:42 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9079)
            
            Thanks for the reply.
            
            I see the same issue when I build with docker or containerd as well
            
            [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9079)
            
            -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Roland [July 1, 2022 At 12:55 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11282)
                
                I’ve been having the same issue too. I’m using docker and none of my worker nodes can access the internet.
                
                [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11282)
                
14.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) shiva [November 30, 2021 At 6:03 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9222)
    
    I am confused by setting the IP for cluster endpoint.  
    The below is my network. What IP can i use for endpoint?
    
    4: docker0: mtu 1500 qdisc noqueue state DOWN group default  
    link/ether 02:42:71:4d:87:43 brd ff:ff:ff:ff:ff:ff  
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0  
    valid\_lft forever preferred\_lft forever
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9222)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [November 30, 2021 At 11:39 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9227)
        
        It is mapped to primary interface IP address of your control plane node.
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9227)
        
15.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Shiva [December 2, 2021 At 6:09 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9238)
    
    Thank you very much! the guide is very helpful and i managed to setup the K8 cluster.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9238)
    
16.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Bram Timmermans [December 2, 2021 At 11:02 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9245)
    
    Clear article!
    
    But when I run:  
    sudo kubeadm config images pull –cri-socket /var/run/docker.sock
    
    Then I get this response:  
    failed to pull image “k8s.gcr.io/kube-apiserver:v1.22.4″: output: time=”2021-12-02T20:00:52Z” level=fatal msg=”connect: connect endpoint ‘unix:///var/run/docker.sock’, make sure you are running as root and the endpoint has been started: context deadline exceeded”  
    , error: exit status 1  
    To see the stack trace of this error execute with –v=5 or higher
    
    Does anyone know how to fix this?
    
    All the previous steps were executed succesfully.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9245)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [December 4, 2021 At 9:12 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9268)
        
        Please check if Docker service is up – systemctl status docker
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9268)
        
        -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Pranav [March 8, 2022 At 11:02 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10190)
            
            Hi Josphat, Thank for writing this article. But I am facing similiar issue. Docker service is up for me but still not able to connect to this CRI-socket
            
            user “test” has been added to group docker and changes applied with “newGrp docker” command.
            
            K8s Version : 1.22  
            test@l2030017515:~$ docker version  
            Client: Docker Engine – Community  
            Version: 19.03.15  
            API version: 1.40  
            Go version: go1.13.15  
            Git commit: 99e3ed8919  
            Built: Sat Jan 30 03:17:01 2021  
            OS/Arch: linux/amd64  
            Experimental: false
            
            Server: Docker Engine – Community  
            Engine:  
            Version: 19.03.15  
            API version: 1.40 (minimum version 1.12)  
            Go version: go1.13.15  
            Git commit: 99e3ed8919  
            Built: Sat Jan 30 03:15:30 2021  
            OS/Arch: linux/amd64  
            Experimental: false  
            containerd:  
            Version: 1.4.13  
            GitCommit: 9cc61520f4cd876b86e77edfeb88fbcd536d1f9d  
            runc:  
            Version: 1.0.3  
            GitCommit: v1.0.3-0-gf46b6ba  
            docker-init:  
            Version: 0.18.0  
            GitCommit: fec3683  
            test@l2030017515:~$
            
            test@l2030017515:~$ sudo systemctl status docker  
            ● docker.service – Docker Application Container Engine  
            Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)  
            Active: active (running) since Tue 2022-03-08 13:23:10 IST; 18s ago  
            TriggeredBy: ● docker.socket  
            Docs: [https://docs.docker.com](https://docs.docker.com)  
            Main PID: 589981 (dockerd)  
            Tasks: 14  
            Memory: 39.1M  
            CGroup: /system.slice/docker.service  
            └─589981 /usr/bin/dockerd -H fd:// –containerd=/run/containerd/containerd.sock
            
            Mar 08 13:23:09 l2030017515 dockerd\[589981\]: time=”2022-03-08T13:23:09.549821158+05:30″ level=warning msg=”Your kernel does not support cgroup rt runtime”  
            Mar 08 13:23:09 l2030017515 dockerd\[589981\]: time=”2022-03-08T13:23:09.549833221+05:30″ level=warning msg=”Your kernel does not support cgroup blkio weight”  
            Mar 08 13:23:09 l2030017515 dockerd\[589981\]: time=”2022-03-08T13:23:09.549844854+05:30″ level=warning msg=”Your kernel does not support cgroup blkio weight\_device”  
            Mar 08 13:23:09 l2030017515 dockerd\[589981\]: time=”2022-03-08T13:23:09.550067148+05:30″ level=info msg=”Loading containers: start.”  
            Mar 08 13:23:09 l2030017515 dockerd\[589981\]: time=”2022-03-08T13:23:09.930384654+05:30″ level=info msg=”Default bridge (docker0) is assigned with an IP address 172.17.0.0/16. Daemon option>  
            Mar 08 13:23:10 l2030017515 dockerd\[589981\]: time=”2022-03-08T13:23:10.065481959+05:30″ level=info msg=”Loading containers: done.”  
            Mar 08 13:23:10 l2030017515 dockerd\[589981\]: time=”2022-03-08T13:23:10.431063768+05:30″ level=info msg=”Docker daemon” commit=99e3ed8919 graphdriver(s)=overlay2 version=19.03.15  
            Mar 08 13:23:10 l2030017515 dockerd\[589981\]: time=”2022-03-08T13:23:10.431230178+05:30″ level=info msg=”Daemon has completed initialization”  
            Mar 08 13:23:10 l2030017515 systemd\[1\]: Started Docker Application Container Engine.  
            Mar 08 13:23:10 l2030017515 dockerd\[589981\]: time=”2022-03-08T13:23:10.602166953+05:30″ level=info msg=”API listen on /run/docker.sock”
            
            Error :
            
            test@l2030017515:~$ sudo kubeadm init –apiserver-advertise-address=$IP –pod-network-cidr=192.168.0.0/16 –cri-socket /run/docker.sock –upload-certs  
            I0308 13:23:46.930188 590324 version.go:255\] remote version is much newer: v1.23.4; falling back to: stable-1.22  
            \[init\] Using Kubernetes version: v1.22.7  
            \[preflight\] Running pre-flight checks  
            error execution phase preflight: \[preflight\] Some fatal errors occurred:  
            \[ERROR CRI\]: container runtime is not running: output: time=”2022-03-08T13:23:52+05:30″ level=fatal msg=”connect: connect endpoint ‘unix:///run/docker.sock’, make sure you are running as root and the endpoint has been started: context deadline exceeded”  
            , error: exit status 1  
            \[preflight\] If you know what you are doing, you can make a check non-fatal with \`–ignore-preflight-errors=…\`  
            To see the stack trace of this error execute with –v=5 or higher
            
            Would be great of you suggest a resolution for the same.
            
            br
            
            [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10190)
            
        -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) sunjoyo [April 15, 2022 At 10:21 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10499)
            
            sysadmin@sysadmin-virtual-machine:~$ systemctl status docker  
            ● docker.service – Docker Application Container Engine  
            Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)  
            Active: active (running) since Fri 2022-04-15 13:56:06 WIB; 22min ago  
            TriggeredBy: ● docker.socket  
            Docs: [https://docs.docker.com](https://docs.docker.com)  
            Main PID: 8624 (dockerd)  
            Tasks: 19  
            Memory: 44.3M  
            CGroup: /system.slice/docker.service  
            └─8624 /usr/bin/dockerd -H fd:// –containerd=/run/containerd/containerd.sock
            
            Apr 15 13:56:18 sysadmin-virtual-machine dockerd\[8624\]: time=”2022-04-15T13:56:18.628776532+07:00″ level=info msg=”ignoring event” container=97a7af489a4131d6ccd4022ab9>  
            Apr 15 13:56:21 sysadmin-virtual-machine dockerd\[8624\]: time=”2022-04-15T13:56:21.884168954+07:00″ level=info msg=”ignoring event” container=e98e6eefe307e1161257876fbf>  
            Apr 15 13:56:21 sysadmin-virtual-machine dockerd\[8624\]: time=”2022-04-15T13:56:21.920915826+07:00″ level=info msg=”ignoring event” container=7b98046840f84ac9f6148e3670>  
            Apr 15 13:56:25 sysadmin-virtual-machine dockerd\[8624\]: time=”2022-04-15T13:56:25.571995048+07:00″ level=info msg=”ignoring event” container=b27cd9e8045fdb6145b4afd634>  
            Apr 15 13:56:25 sysadmin-virtual-machine dockerd\[8624\]: time=”2022-04-15T13:56:25.614309354+07:00″ level=info msg=”ignoring event” container=8a11505137a45fddf3df7c2cec>  
            Apr 15 13:56:28 sysadmin-virtual-machine dockerd\[8624\]: time=”2022-04-15T13:56:28.878086757+07:00″ level=info msg=”ignoring event” container=4ec09c5edf4939b4f567b82d0d>  
            Apr 15 13:56:29 sysadmin-virtual-machine dockerd\[8624\]: time=”2022-04-15T13:56:29.892410616+07:00″ level=info msg=”ignoring event” container=00207f98f2cb6276e58d9509bc>  
            Apr 15 13:56:31 sysadmin-virtual-machine dockerd\[8624\]: time=”2022-04-15T13:56:31.952429432+07:00″ level=info msg=”ignoring event” container=f218022d2f2c50fb3a63401f29>  
            Apr 15 13:56:32 sysadmin-virtual-machine dockerd\[8624\]: time=”2022-04-15T13:56:32.992268870+07:00″ level=info msg=”ignoring event” container=a29f524abb16b085cdbd4af591>  
            Apr 15 13:56:35 sysadmin-virtual-machine dockerd\[8624\]: time=”2022-04-15T13:56:35.043274360+07:00″ level=info msg=”ignoring event” container=8c3a0f063ddcfc5e4f2cb606a3>  
            lines 1-21/21 (END)  
            ^C  
            sysadmin@sysadmin-virtual-machine:~$ sudo kubeadm config images pull –cri-socket /var/run/docker.sock  
            \[sudo\] password for sysadmin:  
            failed to pull image “k8s.gcr.io/kube-apiserver:v1.23.5″: output: time=”2022-04-15T14:19:22+07:00″ level=fatal msg=”connect: connect endpoint ‘unix:///var/run/docker.sock’, make sure you are running as root and the endpoint has been started: context deadline exceeded”  
            , error: exit status 1  
            To see the stack trace of this error execute with –v=5 or higher  
            sysadmin@sysadmin-virtual-machine:~$
            
            still same problem, docker status “running”
            
            [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10499)
            
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [mousepotato](https://octopusgarden.page/) [December 27, 2021 At 7:41 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9468)
        
        If you only installed Docker runtime, you don’t need to run this command again. You just need sudo kubeadm config images pull
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9468)
        
17.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) jkruse [December 4, 2021 At 7:54 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9270)
    
    The certificate created in the init command is invalid and flagged by Chrome/Safari when trying to progress through step 10 installing the dashboard.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9270)
    
18.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Ivan [December 30, 2021 At 2:20 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9483)
    
    Woooowwwwwwww !!! You have been enriching the POST, I congratulate you and very complete … !!!
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9483)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [December 30, 2021 At 9:37 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9487)
        
        Thanks for the positive vibe you’re dropping our way. We’re humbled.
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9487)
        
19.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Jacob Willig](http://lazymen.eu) [January 16, 2022 At 5:20 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9739)
    
    I ran into this problem. See console log, docker is installed and running:
    
    jacob@lazykub1:~$ sudo kubeadm config images pull –cri-socket /var/run/docker.sock  
    failed to pull image “k8s.gcr.io/kube-apiserver:v1.23.1″: output: time=”2022-01-16T14:14:45Z” level=fatal msg=”connect: connect endpoint ‘unix:///var/run/docker.sock’, make sure you are running as root and the endpoint has been started: context deadline exceeded”  
    , error: exit status 1  
    To see the stack trace of this error execute with –v=5 or higher  
    jacob@lazykub1:~$ sudo systemctl status docker  
    ● docker.service – Docker Application Container Engine  
    Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)  
    Active: active (running) since Sun 2022-01-16 14:14:21 UTC; 3min 23s ago  
    TriggeredBy: ● docker.socket  
    Docs: [https://docs.docker.com](https://docs.docker.com)  
    Main PID: 4187 (dockerd)  
    Tasks: 8  
    Memory: 33.7M  
    CGroup: /system.slice/docker.service  
    └─4187 /usr/bin/dockerd -H fd:// –containerd=/run/containerd/containerd.sock
    
    Jan 16 14:14:20 lazykub1 dockerd\[4187\]: time=”2022-01-16T14:14:20.947413897Z” level=warning msg=”Your kernel does not support CPU realtime scheduler”  
    Jan 16 14:14:20 lazykub1 dockerd\[4187\]: time=”2022-01-16T14:14:20.947421586Z” level=warning msg=”Your kernel does not support cgroup blkio weight”  
    Jan 16 14:14:20 lazykub1 dockerd\[4187\]: time=”2022-01-16T14:14:20.947428108Z” level=warning msg=”Your kernel does not support cgroup blkio weight\_device”  
    Jan 16 14:14:20 lazykub1 dockerd\[4187\]: time=”2022-01-16T14:14:20.947609517Z” level=info msg=”Loading containers: start.”  
    Jan 16 14:14:21 lazykub1 dockerd\[4187\]: time=”2022-01-16T14:14:21.077788214Z” level=info msg=”Default bridge (docker0) is assigned with an IP address 172.17.0.0/16. Daemon option –bip can be used to set a preferred IP address”  
    Jan 16 14:14:21 lazykub1 dockerd\[4187\]: time=”2022-01-16T14:14:21.111888405Z” level=info msg=”Loading containers: done.”  
    Jan 16 14:14:21 lazykub1 dockerd\[4187\]: time=”2022-01-16T14:14:21.133944179Z” level=info msg=”Docker daemon” commit=459d0df graphdriver(s)=overlay2 version=20.10.12  
    Jan 16 14:14:21 lazykub1 dockerd\[4187\]: time=”2022-01-16T14:14:21.134263733Z” level=info msg=”Daemon has completed initialization”  
    Jan 16 14:14:21 lazykub1 systemd\[1\]: Started Docker Application Container Engine.  
    Jan 16 14:14:21 lazykub1 dockerd\[4187\]: time=”2022-01-16T14:14:21.154710559Z” level=info msg=”API listen on /run/docker.sock”  
    jacob@lazykub1:~$
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9739)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [yhs](http://www.vmx.id) [April 15, 2022 At 9:56 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10498)
        
        are you manage to solve your problem? iam also facing same problem
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10498)
        
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [April 15, 2022 At 11:29 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10500)
        
        I see your socket path is /run/containerd/containerd.sock
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10500)
        
20.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Jacob Wilig](http://lazymen.eu) [January 16, 2022 At 5:25 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9740)
    
    swap statement is not working for me.  
    “sudo sed -i ‘/ swap / s/^\\(.\*\\)$/#\\1/g’ /etc/fstab”  
    It does not comment out the swap line
    
    \# /etc/fstab: static file system information.  
    #  
    \# Use ‘blkid’ to print the universally unique identifier for a  
    \# device; this may be used with UUID= as a more robust way to name devices  
    \# that works even if disks are added and removed. See fstab(5).  
    #  
    #  
    \# / was on /dev/ubuntu-vg/ubuntu-lv during curtin installation  
    /dev/disk/by-id/dm-uuid-LVM-LMZ6lL63Lq08X4WdpxYG1q2BXTyEcLs2cS2oIdfaWHUALXM3rHgG4j26DG8Hys2M / ext4 defaults 0 1  
    \# /boot was on /dev/sda2 during curtin installation  
    /dev/disk/by-uuid/d13a56c4-40f8-4994-8b23-06b8f2785f5d /boot ext4 defaults 0 1  
    /swap.img none swap sw 0 0
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9740)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [January 18, 2022 At 9:32 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9775)
        
        Hi,
        
        What are the contents of your fstab file?
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9775)
        
21.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Alexandre [January 25, 2022 At 12:17 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9817)
    
    Thank you for the tutorial!!!
    
    After some tries finally seems I got it working, now I’m looking how to integrate on GitLab.
    
    An quick hint for those with problems on coredns failing or dont get ready.
    
    Don’t change the range IP, post says its possible to customize and use seed for change after install, all time I have did that, pod never started, reading the file:
    
    [https://docs.projectcalico.org/manifests/custom-resources.yaml](https://docs.projectcalico.org/manifests/custom-resources.yaml)
    
    There’s the note:
    
    \# Note: The ipPools section cannot be modified post-install.
    
    And the default range is 192.168.0.0/16
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9817)
    
22.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) zoom2x [January 27, 2022 At 6:46 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9844)
    
    sudo sed -i ‘s/10.85.0.0/192.168.0.0/g’ /etc/cni/net.d/100-crio-bridge.conf  
    sed: can’t read /etc/cni/net.d/100-crio-bridge.conf: No such file or directory
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9844)
    
23.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) n1234 [January 31, 2022 At 7:27 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9892)
    
    Also seeing the following error which then stops anything further on working:
    
    sudo kubeadm config images pull –cri-socket /var/run/docker.sock  
    failed to pull image “k8s.gcr.io/kube-apiserver:v1.23.3″: output: time=”2022-01-31T16:26:47Z” level=fatal msg=”connect: connect endpoint ‘unix:///var/run/docker.sock’, make sure you are running as root and the endpoint has been started: context deadline exceeded”  
    , error: exit status 1  
    To see the stack trace of this error execute with –v=5 or higher
    
    any ideas?
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-9892)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [February 16, 2022 At 7:51 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10047)
        
        Are you using Docker container engine?. If so, is the service running?
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10047)
        
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [April 15, 2022 At 10:00 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10506)
        
        We’ve updated the guide to use cri-dockerd shim. Also covered in a separate guide: [https://computingforgeeks.com/install-mirantis-cri-dockerd-as-docker-engine-shim-for-kubernetes/](https://computingforgeeks.com/install-mirantis-cri-dockerd-as-docker-engine-shim-for-kubernetes/)
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10506)
        
24.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) herlant [May 13, 2022 At 3:09 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10760)
    
    Hello  
    I have an issue with this tutorial : My install is in 1.24.0. All works good but i have a problem with tokens in service account. Any token is generated when i create sa, and i have no token in the default sa. Can you help me ?
    
    Thx
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10760)
    
25.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Steeven Herlant [May 13, 2022 At 5:00 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10762)
    
    Hello, i have an issue with this guide.  
    I have successfully installed my cluster with containerd and calico.  
    Every works good except one thing :  
    I haven’t any token generated for services account. When i type this command :  
    kubectl get sa  
    The default sa is present but with 0 secrets. The token section is set to  
    It’s similar when i tried to create a new sa, no token.  
    Can i have help please ?
    
    Thanks
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10762)
    
26.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) De Bruyn Annandale [May 15, 2022 At 12:07 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10775)
    
    IF you need to specify a different pod cidr as “192.168.0.0/16” you need to edit the custom-resources.yaml for calico before applying.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10775)
    
27.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Avinash Reddy](http://none) [May 19, 2022 At 12:30 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10812)
    
    Hi,  
    A great post, which helped me a lot.  
    I have been trying to host k8 on AWS EC2 Instances ( an task )
    
    i have encountered two issues
    
    1# at worker node
    
    Found multiple CRI endpoints on the host. Please define which one do you wish to use by setting the ‘criSocket’ field in the kubeadm configuration file: unix:///var/run/containerd/containerd.sock, unix:///var/run/cri-dockerd.sock  
    To see the stack trace of this error execute with –v=5 or higher
    
    for this i have tried  
    sudo kubeadm join {ip address} –token xgr4i8.kokoqjxo6yvs3d19 –discovery-token-ca-cert-hash sha256:d1b4e8ea7a87ae6b91198a2c0ac85663c48b2f2f9181d7075d13294336684379  
    –cri-socket /run/cri-dockerd.sock
    
    but my command is being struck
    
    2#  
    \[preflight\] Running pre-flight checks  
    \[WARNING SystemVerification\]: missing optional cgroups: blkio
    
    with above message its been stuck, help me please
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-10812)
    
28.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Ranjit [June 2, 2022 At 11:19 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11000)
    
    I installed the K8s cluster (1 master, 2 worker) using this guide. I used docker as Container Runtime. However, when I create Pods, the Pods in different worker nodes take overlapping Ips. Pod from one node can’t talk to pod from another node.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11000)
    
29.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Phil [June 6, 2022 At 6:34 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11036)
    
    Took me a few attempts but got there in the end! Thanks for taking the time to put together.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11036)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [June 16, 2022 At 12:49 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11145)
        
        Welcome Phil
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11145)
        
30.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Andre Santana [June 15, 2022 At 10:42 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11142)
    
    Thank you very much.  
    If I’d add something to make this perfect is to add the details on how to generate the join token to add new workers.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11142)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [June 17, 2022 At 3:22 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11161)
        
        There is a link to a separate guide under “Join new Kubernetes Worker Node to an existing Cluster” on joining new node to an existing cluster.
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11161)
        
31.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Jason [June 30, 2022 At 4:39 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11273)
    
    I followed this guide (docker runtime) with an additional step for Calico:
    
    kubectl apply -f [https://projectcalico.docs.tigera.io/v3.23/manifests/calico.yaml](https://projectcalico.docs.tigera.io/v3.23/manifests/calico.yaml)
    
    An outstanding issue I have is even though I specified a pod network with kubeadm init, the pods are getting assigned addresses from the docker0 network (172.17.0.0/16) instead of the pod network.
    
    Any ideas how to resolve? I found a few similar issues on Stackoverflow but haven’t been able to resolve mine.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11273)
    
32.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Matej](http://fcode-it.com) [July 22, 2022 At 12:34 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11523)
    
    I have problem about docker container cannot access external calls.  
    I build a simple application which do api call and it says “resource temporarily unavailable”, after trying to exec into container and do apt-get update it says that cannot connect to deb.  
    Any help about this ? i setup cluster as described above.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11523)
    
33.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Matej](http://fcode-it.com) [July 22, 2022 At 3:16 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11526)
    
    Very nice article !  
    I did manage to setup k8s but recently i started getting errors in my pods “resource temporarily unavailable” when doing external http call, anyone have some solution ?
    
    btw, i tried to exec into container and do “apt-get update” but it says that i cannot connect to deb.
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11526)
    
34.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Scott Senften [August 9, 2022 At 2:38 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11656)
    
    After installing the CRI-O runtime and using Calico as suggested, my calico-kube-controller is stuck in a Pending status.
    
    NAMESPACE NAME READY STATUS RESTARTS AGE  
    calico-system calico-kube-controllers-657d56796-bvh25 0/1 Pending 0 30m  
    calico-system calico-node-tdkjf 1/1 Running 0 30m  
    calico-system calico-typha-89d87cb5c-fn887 1/1 Running 0 30m  
    kube-system coredns-6d4b75cb6d-dbbmk 1/1 Running 0 31m  
    kube-system coredns-6d4b75cb6d-twlkk 1/1 Running 0 31m  
    kube-system etcd-res-u20-template 1/1 Running 0 32m  
    kube-system kube-apiserver-res-u20-template 1/1 Running 0 32m  
    kube-system kube-controller-manager-res-u20-template 1/1 Running 0 32m  
    kube-system kube-proxy-cxmvt 1/1 Running 0 31m  
    kube-system kube-scheduler-res-u20-template 1/1 Running 0 32m  
    tigera-operator tigera-operator-6995cc5df5-4w9rt 1/1 Running 0 30m
    
    The only thing in the log that drew my attention was  
    “E0808 23:12:25.258702 1 disruption.go:534\] Error syncing PodDisruptionBudget calico-system/calico-typha, requeuing: Operation cannot be fulfilled on poddisruptionbudgets.policy “calico-typha”: the object has been modified; please apply your changes to the latest version and try again”
    
    Has anyone seen this issue? suggestions?
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11656)
    
35.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Scott Senften [August 9, 2022 At 9:19 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11661)
    
    After installing the CRI-O runtime and the Calico network plugin, the calico-kube-controllers stay in a \`Pending\` state.
    
    senften@res-k8s-master:~$ kubectl get pods –all-namespaces  
    NAMESPACE NAME READY STATUS RESTARTS AGE  
    calico-system calico-kube-controllers-657d56796-qzhxw 0/1 Pending 0 17h  
    calico-system calico-node-62k9g 1/1 Running 0 17h  
    calico-system calico-typha-8fdfcb55c-k6zcq 1/1 Running 0 17h  
    kube-system coredns-6d4b75cb6d-bknbp 1/1 Running 0 17h  
    kube-system coredns-6d4b75cb6d-jkfk7 1/1 Running 0 17h  
    kube-system etcd-res-k8s-master 1/1 Running 0 17h  
    kube-system kube-apiserver-res-k8s-master 1/1 Running 0 17h  
    kube-system kube-controller-manager-res-k8s-master 1/1 Running 0 17h  
    kube-system kube-proxy-jht5p 1/1 Running 0 17h  
    kube-system kube-scheduler-res-k8s-master 1/1 Running 0 17h  
    tigera-operator tigera-operator-6995cc5df5-j64s6 1/1 Running 0 17h
    
    I think it may be related to this bug, \[calico-kube-controllers pending since not tolerate the “node-role.kubernetes.io/control-plane” · Issue #6087 · projectcalico/calico\]([https://github.com/projectcalico/calico/issues/6087](https://github.com/projectcalico/calico/issues/6087)), but, after reading through the issue, I am still uncertain how to proceed or even sure this is the issue I’ve run into.
    
    Any advice? Anyone else seeing this?  
    Thanks
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11661)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [August 10, 2022 At 9:30 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11672)
        
        For single node setup allow Pods to run on master nodes – [https://computingforgeeks.com/how-to-schedule-pods-on-kubernetes-control-plane-node/](https://computingforgeeks.com/how-to-schedule-pods-on-kubernetes-control-plane-node/)
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11672)
        
        -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Scott Senften [August 12, 2022 At 9:21 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11699)
            
            Thank you. Greatly appreciated.  
            I also found an answer by new-mikha in the comments of [https://github.com/projectcalico/calico/issues/6087](https://github.com/projectcalico/calico/issues/6087) so I downloaded [https://docs.projectcalico.org/manifests/custom-resources.yaml](https://docs.projectcalico.org/manifests/custom-resources.yaml) referenced in step 6 and added
            
            controlPlaneTolerations:  
            – key: node-role.kubernetes.io/control-plane  
            effect: NoSchedule  
            – key: node-role.kubernetes.io/master  
            effect: NoSchedule
            
            as described in the comment and then, probably obviously, created the resources with this edited file.
            
            [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11699)
            
36.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) wp [August 29, 2022 At 8:14 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11843)
    
    How do you add additional master node into the cluster?
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-11843)
    
37.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Ashish](https://Gmail) [October 13, 2022 At 9:30 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12198)
    
    While running this command  
    sudo kubeadm config images pull –cri-socket unix:///run/cri-dockerd.sock  
    i m getting this error  
    failed to pull image “registry.k8s.io/kube-apiserver:v1.25.2″: output: time=”2022-10-13T11:52:55+05:30″ level=fatal msg=”unable to determine image API version: rpc error: code = Unavailable desc = connection error: desc = \\”transport: Error while dialing dial unix /run/cri-dockerd.sock: connect: no such file or directory\\””  
    , error: exit status 1  
    To see the stack trace of this error execute with –v=5 or higher
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12198)
    
38.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Ashish](https://Gmail) [October 13, 2022 At 10:00 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12199)
    
    i don’t know why i m not able to create file for docker at the given file i m following all steps  
    Whenever i run this command sudo kubeadm config images pull –cri-socket unix:///run/cri-dockerd.sock  
    i m getting this following error failed to pull image “registry.k8s.io/kube-apiserver:v1.25.2″: output: time=”2022-10-13T12:29:44+05:30″ level=fatal msg=”unable to determine image API version: rpc error: code = Unavailable desc = connection error: desc = \\”transport: Error while dialing dial unix /run/cri-dockerd.sock: connect: no such file or directory\\””  
    , error: exit status 1  
    To see the stack trace of this error execute with –v=5 or higher
    
    Any solution ??
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12199)
    
39.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [sagar H M](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm/) [October 25, 2022 At 1:43 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12339)
    
    thanks for ur blogs its helps most of them and reilf more stress .  
    Here im beginer to these .whats the use of docker . kubernates run upon or docker , or docker container runs inside the pod ? plzzz tell me im confused about all these help me out plzzz
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12339)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [October 27, 2022 At 12:40 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12363)
        
        See some resources that tries to explain the difference:  
        – [https://www.dynatrace.com/news/blog/kubernetes-vs-docker/](https://www.dynatrace.com/news/blog/kubernetes-vs-docker/)  
        – [https://azure.microsoft.com/en-us/topic/kubernetes-vs-docker/](https://azure.microsoft.com/en-us/topic/kubernetes-vs-docker/)  
        – [https://www.ibm.com/cloud/blog/kubernetes-vs-docker](https://www.ibm.com/cloud/blog/kubernetes-vs-docker)
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12363)
        
40.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Olubodun [November 30, 2022 At 4:26 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12764)
    
    Phew, got my master node all setup finally, thanks for the workthrough. It’s briliant and requires some patience 🙂
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12764)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [November 30, 2022 At 10:32 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12766)
        
        Awesome… We are 😄 for you!
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-12766)
        
41.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) nagendra [January 26, 2023 At 5:28 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-13536)
    
    Thanks
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-13536)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [January 27, 2023 At 8:32 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-13541)
        
        Thanks for the comment and welcome
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-13541)
        
42.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Jack Chuong [March 17, 2023 At 4:51 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-14250)
    
    I followed your guide :
    
    Host OS: Ubuntu 22.04  
    CNI and version: Flannel latest  
    CRI and version: CRI-O latest
    
    kubeadm init –v=5 –pod-network-cidr=10.244.0.0/16 –upload-certs –control-plane-endpoint=k8s.mydomain.com
    
    The cluster initialized successfully but coredns pods cannot started
    
    kubectl version –short  
    Client Version: v1.26.2  
    Kustomize Version: v4.5.7  
    Server Version: v1.26.2
    
    kubectl cluster-info  
    Kubernetes control plane is running at [https://k8s.mydomain.com:6443](https://k8s.mydomain.com:6443)  
    CoreDNS is running at [https://k8s.mydomain.com:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy](https://k8s.mydomain.com:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy)
    
    kubectl get pod -n kube-system  
    NAME READY STATUS RESTARTS AGE  
    coredns-787d4945fb-g8hhj 0/1 CreateContainerError 0 7m1s  
    coredns-787d4945fb-nkssp 0/1 CreateContainerError 0 6m29s  
    etcd-k8s-52ts-master1 1/1 Running 1 12h  
    kube-apiserver-k8s-52ts-master1 1/1 Running 1 12h  
    kube-controller-manager-k8s-52ts-master1 1/1 Running 1 12h  
    kube-proxy-m4mhc 1/1 Running 1 12h  
    kube-proxy-rrdpb 1/1 Running 0 12h  
    kube-scheduler-k8s-52ts-master1 1/1 Running 1 12h
    
    kubectl describe pod coredns-787d4945fb-g8hhj -n kube-system  
    Events:  
    Type Reason Age From Message  
    —- —— —- —- ——-  
    Normal Scheduled 65s default-scheduler Successfully assigned kube-system/coredns-787d4945fb-g8hhj to k8s-52ts-worker1  
    Warning Failed 64s kubelet Error: container create failed: time=”2023-03-17T08:26:01+07:00″ level=warning msg=”unable to get oom kill count” error=”openat2 /sys/fs/cgroup/kubepods.slice/kubepods-burstable.slice/kubepods-burstable-podd45fe767\_098b\_401f\_8da9\_1a1760d804f6.slice/crio-105d630363803602c6bfe9c1516b128192b95c519ff321ed1177fe0cacdc9b42.scope/memory.events: no such file or directory”  
    time=”2023-03-17T08:26:01+07:00″ level=error msg=”container\_linux.go:380: starting container process caused: exec: \\”/coredns\\”: stat /coredns: no such file or directory”  
    Warning Failed 63s kubelet Error: container create failed: time=”2023-03-17T08:26:02+07:00″ level=warning msg=”unable to get oom kill count” error=”openat2 /sys/fs/cgroup/kubepods.slice/kubepods-burstable.slice/kubepods-burstable-podd45fe767\_098b\_401f\_8da9\_1a1760d804f6.slice/crio-2bbebc0f6e74a3c5a8f5e460e758e322a94ffe97964f34e357d831ce3fced345.scope/memory.events: no such file or directory”  
    time=”2023-03-17T08:26:02+07:00″ level=error msg=”container\_linux.go:380: starting container process caused: exec: \\”/coredns\\”: stat /coredns: no such file or directory”  
    Warning Failed 47s kubelet Error: container create failed: time=”2023-03-17T08:26:18+07:00″ level=error msg=”container\_linux.go:380: starting container process caused: exec: \\”/coredns\\”: stat /coredns: no such file or directory”  
    Warning Failed 34s kubelet Error: container create failed: time=”2023-03-17T08:26:31+07:00″ level=error msg=”container\_linux.go:380: starting container process caused: exec: \\”/coredns\\”: stat /coredns: no such file or directory”  
    Warning Failed 19s kubelet Error: container create failed: time=”2023-03-17T08:26:46+07:00″ level=error msg=”container\_linux.go:380: starting container process caused: exec: \\”/coredns\\”: stat /coredns: no such file or directory”  
    Normal Pulled 9s (x6 over 64s) kubelet Container image “registry.k8s.io/coredns/coredns:v1.9.3” already present on machine
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-14250)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [March 17, 2023 At 10:14 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-14255)
        
        Hi,
        
        Did you install network plugin?
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-14255)
        
        -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Jack Chuong [March 18, 2023 At 5:10 am](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-14266)
            
            Hi, I reinstalled cluster with docker CRI docker and Mirantis cri-dockerd as shim , CNI Flannel and it works now.
            
            [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-14266)
            
43.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) Ayoub Habra [May 21, 2023 At 2:18 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-39306)
    
    Hi ,  
    Thanks for this great tutorial, It’s really useful and helped me to bootstrap multiple clusters since 2022.  
    I want to mention two points and hope that it will help someone.  
    1 – For containerd, the old debian package 1.4 does not work with v1.25 and higher. the version that works it 1.6 . Here is one of the related errors :  
    failed to pull image “registry.k8s.io/kube-apiserver:v1.25.10″: output: time=”2023-05-21T10:16:39Z” level=fatal msg=”validate service connection: CRI v1 image API is not implemented for endpoint \\”unix:///var/run/containerd/containerd.sock\\”: rpc error: code = Unimplemented desc = unknown service runtime.v1.ImageService”
    
    2 – The Urls on calico setup are not working anymore , the updated version could be found here :  
    [https://docs.tigera.io/calico/latest/getting-started/kubernetes/self-managed-onprem/onpremises](https://docs.tigera.io/calico/latest/getting-started/kubernetes/self-managed-onprem/onpremises)
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-39306)
    
44.  ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) John Gong [July 26, 2023 At 3:35 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-73248)
    
    Hi Josphat  
    Thanks for this guide, very detail and helpful.  
    Adding one more thing to the Calico installation part  
    curl [https://raw.githubusercontent.com/projectcalico/calico/v3.25.1/manifests/custom-resources.yaml](https://raw.githubusercontent.com/projectcalico/calico/v3.25.1/manifests/custom-resources.yaml) -O  
    as the resources.yaml seems using 192.168.0.0/16 as default cidr, but your cluster init command above is using –pod-network-cidr=172.24.0.0/16  
    If one want to deploy Calico network plugin, he must manually update the cidr in this yaml file to have  
    cidr: 172.24.0.0/16
    
    [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-73248)
    
    -   ![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%2250%22%20height=%2250%22%3E%3C/svg%3E) [Josphat Mutai](https://computingforgeeks.com/) [July 26, 2023 At 9:03 pm](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-73268)
        
        Thanks for this powerful comment we’ve updated the article it now reflects.
        
        [Reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm//#comment-73268)
        

### LEAVE A REPLY [Cancel reply](https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm/#respond)

Please enter your comment!

Please enter your name here

You have entered an incorrect email address!

Please enter your email address here

Save my name, email, and website in this browser for the next time I comment.

  

Δdocument.getElementById("ak\_js\_1").setAttribute("value",(new Date()).getTime());

<iframe id="ob_iframe" src="https://widgets.outbrain.com/widgetOBUserSync/obUserSync.html#pid=6420&amp;dmpenabled=true&amp;filterDMP=&amp;d=YGcfcv2DjvAipqUyMEnD06xwlJH09QVnGPAso4cj5Bgf4PcRcFOXWsdRB0nrCgG7&amp;gdpr=0&amp;cmpNeeded=false&amp;gdprVer=null&amp;ccpa=1---&amp;country=IN&amp;obRecsAbtestAndVars=1024-3192,833-3369,386-2483,1090-3454,1155-3748,1164-3777,1103-3503,784-2396,1169-3791,1300-4501,980-4244,981-4504,792-2896,1309-4483,927-3026,1125-3605,998-3155,1323-4540,1326-4546,1328-4554,1203-3959,822-2522,1082-3419,699-2821,1149-3716" style="display: none; width: 1px; height: 1px;"></iframe>

/\* dynamic basic css \*/ .CRAB\_1.ob-widget .ob-widget-items-container {margin:0;padding:0;} .CRAB\_1.ob-widget .ob-widget-items-container .ob-clearfix {display:block;width:100%;float:none;clear:both;height:0px;line-height:0px;font-size:0px;} .CRAB\_1.ob-widget .ob-widget-items-container.ob-multi-row {padding-top: 2%;} .CRAB\_1.ob-widget .ob-dynamic-rec-container {position:relative;margin:0;padding;0;} .CRAB\_1.ob-widget .ob-dynamic-rec-link, .CRAB\_1.ob-widget .ob-dynamic-rec-link:hover {text-decoration:none;} .CRAB\_1.ob-widget .ob-rec-image-container .ob-video-icon-container {position:absolute;left:0;height:50%;width:100%;text-align:center;top:25%;} .CRAB\_1.ob-widget .ob-rec-image-container .ob-video-icon {display:inline-block;height:100%;float:none;opacity:0.7;transition: opacity 500ms;} .CRAB\_1.ob-widget .ob-rec-image-container .ob-video-icon:hover {opacity:1;} .CRAB\_1 .ob\_what a:after {content: "";;;background-image: url('https://widgets.outbrain.com/images/widgetIcons/achoice.svg');background-size:100% 100%;width:12px;height:12px;padding-left:4px;display:inline-block;background-repeat:no-repeat;background-position:right center;border-left:1px solid #999;} .CRAB\_1.ob-widget .ob\_what{direction:ltr;clear:both;padding:5px 10px 0px;} .CRAB\_1.ob-widget .ob\_what a{color:#757575;font-size:11px;font-family:arial;text-decoration: none;} .CRAB\_1.ob-widget .ob\_what.ob-hover:hover a{text-decoration: underline;} .CRAB\_1.ob-widget .ob\_amelia, .CRAB\_1.ob-widget .ob\_amelia\_covid, .CRAB\_1.ob-widget .ob\_logo, .CRAB\_1.ob-widget .ob\_feed\_logo, .CRAB\_1.ob-widget .ob\_sfeed\_logo, .CRAB\_1.ob-widget .ob\_text\_logo{vertical-align:baseline !important;display:inline-block;vertical-align:text-bottom;padding:0px 5px;box-sizing:content-box;-moz-box-sizing:content-box;-webkit-box-sizing:content-box;}.CRAB\_1.ob-widget .ob\_logo{background:url('https://widgets.outbrain.com/images/widgetIcons/ob\_logo\_67x12.png') no-repeat center top;width:67px;height:12px;}.CRAB\_1.ob-widget:hover .ob\_amelia, .CRAB\_1.ob-widget:hover .ob\_logo, .CRAB\_1.ob-widget:hover .ob\_text\_logo{background-position:center bottom;} .CRAB\_1.ob-widget .ob\_what{text-align:right;} .CRAB\_1.ob-widget .ob-rec-image-container .ob-rec-image {display:block;} .CRAB\_1.ob-widget .ob-rec-description {max-height:49.0px;overflow:hidden;font-weight:normal;} /\* dynamic strip css \*/ .CRAB\_1.ob-widget .ob-rec-image-container {position:relative;} .CRAB\_1.ob-widget .ob-rec-image-container .ob-image-ratio {height:0px;line-height:0px;padding-top:100.0%;} .CRAB\_1.ob-widget .ob-rec-image-container img.ob-rec-image {width:100%;position:absolute;top:0;bottom:0;left:0;right:0;opacity:0;transition:all 750ms;} .CRAB\_1.ob-widget .ob-rec-image-container img.ob-show {opacity:1;} .CRAB\_1.ob-widget .ob-rec-image-container .ob-rec-label {position:absolute;bottom:0px;left:0px;padding:0px 3px;background-color:#666;color:white;font-size:10px;line-height:15px;} .CRAB\_1.ob-widget .ob-rec-image-container .ob-rec-video {position:absolute;top:0;left:0;right:0;bottom:0;width:100%;height:100%;min-height:0;min-width:0} .CRAB\_1.ob-widget {width:auto;min-width:180px;} .CRAB\_1.ob-widget .ob-dynamic-rec-container {display:inline-block;vertical-align:top;min-width:50px;width:31.8%;box-sizing:border-box;-moz-box-sizing:border-box;} .CRAB\_1.ob-widget .ob-unit.ob-rec-brandName, .CRAB\_1.ob-widget .ob-unit.ob-rec-brandLogo-container, .CRAB\_1.ob-widget .ob-rec-brandLogoAndName {display:inline-block;} .CRAB\_1.ob-widget .ob-rec-brandLogo {width:20px;height:20px;} .CRAB\_1.ob-widget .ob-rec-brandName {vertical-align:bottom;} .CRAB\_1.ob-widget .ob-unit.ob-rec-brandName {vertical-align:super;} .CRAB\_1.ob-widget .ob-widget-items-container {direction: ltr;} .CRAB\_1.ob-widget .ob-dynamic-rec-container {margin-left:0;} .CRAB\_1.ob-widget .ob-dynamic-rec-container ~ .ob-dynamic-rec-container {margin:0 0 0 2.3%; } .CRAB\_1.ob-widget .ob-widget-header {direction:ltr; font-weight:bold;} .CRAB\_1.ob-widget .ob-unit {display:block;} .CRAB\_1.ob-widget .ob-rec-text {max-height:53.0px;overflow:hidden;font-weight:bold;} .CRAB\_1.ob-widget .ob-rec-source {} .CRAB\_1.ob-widget .ob-rec-description {overflow:hidden;} .CRAB\_1.ob-widget .ob-rec-date {font-weight:bold;} .CRAB\_1.ob-widget .ob-rec-description {max-height:49.0px;overflow:hidden;font-weight:normal;} /\* dynamic customized css \*/ .CRAB\_1.ob-strip-layout .ob-widget-header {font-family:inherit;font-size:18px;color:black;padding-bottom:12px;padding-top:0px;} .CRAB\_1.ob-strip-layout .ob-dynamic-rec-container {max-width:275px;} .CRAB\_1.ob-strip-layout .ob-rec-text {font-family:inherit;color:black;padding:5px 0 0px;text-align:left;line-height:1.25;font-size:14px;} .CRAB\_1.ob-strip-layout .ob-rec-text:hover {color:#463636;} .CRAB\_1.ob-strip-layout .ob-rec-source {font-family:inherit;color:#888;padding:0px 0 5px;text-align:left;font-size:13px;} .CRAB\_1.ob-strip-layout .ob-rec-date {font-family:inherit;color:black;padding:0px 0 0px;text-align:left;font-size:12px;} .CRAB\_1.ob-strip-layout .ob-rec-author {font-family:inherit;color:black;padding:0px 0 0px;text-align:left;font-size:12px;} .CRAB\_1.ob-strip-layout .ob-rec-description {font-family:inherit;color:black;margin:;text-align:none;font-size:13px;line-height:1.25;} .CRAB\_1.ob-strip-layout .ob-rec-brandName {font-family:inherit;padding:5px 0 0px;line-height:1.25;font-size:13px;font-weight:400;} .CRAB\_1.ob-strip-layout .ob-rec-brandLogo {width:20px;height:20px;} .CRAB\_1.ob-widget .ob-widget-items-container { margin: 0; padding: 0; margin-right: 17px;}.CRAB\_1 img.ob-rec-image.ob-show { border: none!important;}@media (min-width: 1px) and (max-width: 450px) { .CRAB\_1.ob-widget .ob-dynamic-rec-container { min-width: 50px; width: 100%; } .CRAB\_1.ob-widget .ob-dynamic-rec-container~.ob-dynamic-rec-container { margin: 0 0 0 0; } .CRAB\_1.ob-widget { width: auto; min-width: initial; }}/\*image resolution hack\*/.CRAB\_1.ob-strip-layout .ob-dynamic-rec-container { max-width: 600px;}/\*overwrite CSS\*/.CRAB\_1.ob-strip-layout .ob-dynamic-rec-container { background: none; float: none;}

Sponsored Content

-    [![This is How Much a Hearing Aid Should Cost in 2023](https://images.outbrainimg.com/transform/v3/eyJpdSI6IjBlOTY3YzAxNWNkNDk3ZGQwMzY2ZGZlY2RiMGYyZDFiZDhlZjhiZTdmOWI1MDIzOTdhODMwNzc5NGU0YzQ1YTgiLCJ3IjoyNzUsImgiOjI3NSwiZCI6MS4wLCJjcyI6MCwiZiI6NH0.webp "This is How Much a Hearing Aid Should Cost in 2023")This is How Much a Hearing Aid Should Cost in 2023 Sponsored links](https://powerredirect.com?mk=hE0gPJyJ0v&ci=003c5635fecb213666bd93cfc33b282f0d&ad_id=0023e08a028b6073b258a326f7414f71be&site_id=$publisher_id$&section_id=$section_id$&adtitle=This+is+How+Much+a+Hearing+Aid+Should+Cost+in+2023&timestamp=$time_stamp$&source=4&ct=Hearing+Aids&mp=IN&ln=EN&click_id=$ob_click_id$&pixel_id=009175d34916983de736216bf4fb4b12e9&publisher_name=$publisher_name$&section_name=$section_name$&click_event=570Pixel&pbd=0&obOrigUrl=true)
-    [![Residents of India Might Get a US Visa Easily](https://images.outbrainimg.com/transform/v3/eyJpdSI6IjY5YzZjNDExNGE4NGM5ZjlmMTk1MzJkMWRhYjFjOGRjZWM2NzQyZjA1OGNhNGNlNTE1N2U3MWIzNWNiMTA1MjEiLCJ3IjoyNzUsImgiOjI3NSwiZCI6MS4wLCJjcyI6MCwiZiI6NH0.webp "Residents of India Might Get a US Visa Easily")Residents of India Might Get a US Visa Easily US Visa](http://a-great-us-visa-intl.fyi/?ref=Outbrain_$publisher_name$&sub_id=USvisa_IN_all_OB.00e02f9175db6116e3a2500e2a792589db&sub_id2=$section_id$~obsearch2&obid=00d74ebef9d90584fff7a949b06aac5dd0&obland=pv&obserp=search&compkey=US+Visa+for+India+Residents&obOrigUrl=true)
-    [![Drive Kia Sonet with 5-Year Warranty Coverage*](https://images.outbrainimg.com/transform/v3/eyJpdSI6IjdiYTc4OWU5NmM4NWEyMmNkNDVjN2QzY2EzZjNkOTRjOWIwMmFiZGQ0MzIyYWFiYTVkNmJlYWYzZTU1ZTM3MDgiLCJ3IjoyNzUsImgiOjI3NSwiZCI6MS4wLCJjcyI6MCwiZiI6NH0.webp "Drive Kia Sonet with 5-Year Warranty Coverage*")Drive Kia Sonet with 5-Year Warranty Coverage\* Kia India](https://www.kia.com/in/our-vehicles/sonet/showroom.html?utm_source=onenative&utm_medium=cpc&utm_campaign=sonet_performance&utm_content=warranty&dclid=CjkKEQjwi7GnBhDM6tKloYupkcEBEiQA-SdJZDxncvaxc3m4aMHK0JeWDRY6g0BlvDLZkyoyerxah1fw_wcB&obOrigUrl=true)

[](https://www.outbrain.com/what-is/default/en)

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-box-1","ezslot\_7",142,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-box-1-0");

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-box-1","ezslot\_8",142,"0","1"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-box-1-0\_1");

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-box-1","ezslot\_9",142,"0","2"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-box-1-0\_2");

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-box-1","ezslot\_10",142,"0","3"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-box-1-0\_3");

.box-1-multi-142{border:none !important;display:block !important;float:none !important;line-height:0px;margin-bottom:3px !important;margin-left:auto !important;margin-right:auto !important;margin-top:3px !important;max-width:100% !important;min-height:250px;min-width:300px;padding:0;text-align:center !important;}.td-theme-wrap .tdi\_8 .td-pulldown-filter-link:hover,.td-theme-wrap .tdi\_8 .td-subcat-item a:hover,.td-theme-wrap .tdi\_8 .td-subcat-item .td-cur-simple-item{color:#e95420}.td-theme-wrap .tdi\_8 .block-title>\*,.td-theme-wrap .tdi\_8 .td-subcat-dropdown:hover .td-subcat-more{background-color:#e95420}.td-theme-wrap .td-footer-wrapper .tdi\_8 .block-title>\*{padding:6px 7px 5px;line-height:1}.td-theme-wrap .tdi\_8 .block-title{border-color:#e95420}.td-theme-wrap .tdi\_8 .td\_module\_wrap:hover .entry-title a,.td-theme-wrap .tdi\_8 .td\_quote\_on\_blocks,.td-theme-wrap .tdi\_8 .td-opacity-cat .td-post-category:hover,.td-theme-wrap .tdi\_8 .td-opacity-read .td-read-more a:hover,.td-theme-wrap .tdi\_8 .td-opacity-author .td-post-author-name a:hover,.td-theme-wrap .tdi\_8 .td-instagram-user a{color:#e95420}.td-theme-wrap .tdi\_8 .td-next-prev-wrap a:hover,.td-theme-wrap .tdi\_8 .td-load-more-wrap a:hover{background-color:#e95420;border-color:#e95420}.td-theme-wrap .tdi\_8 .td-read-more a,.td-theme-wrap .tdi\_8 .td-weather-information:before,.td-theme-wrap .tdi\_8 .td-weather-week:before,.td-theme-wrap .tdi\_8 .td-exchange-header:before,.td-theme-wrap .td-footer-wrapper .tdi\_8 .td-post-category,.td-theme-wrap .tdi\_8 .td-post-category:hover{background-color:#e95420}var block\_tdi\_8=new tdBlock();block\_tdi\_8.id="tdi\_8";block\_tdi\_8.atts='{"custom\_title":"Recent Posts","custom\_url":"","block\_template\_id":"","header\_color":"#e95420","header\_text\_color":"#","accent\_text\_color":"#","m6\_tl":"","limit":"8","offset":"","el\_class":"","post\_ids":"-59740","category\_id":"","category\_ids":"","tag\_slug":"","autors\_id":"","installed\_post\_types":"","sort":"","td\_ajax\_filter\_type":"","td\_ajax\_filter\_ids":"","td\_filter\_default\_txt":"All","td\_ajax\_preloading":"","ajax\_pagination":"","ajax\_pagination\_infinite\_stop":"","class":"td\_block\_widget tdi\_8","block\_type":"td\_block\_7","separator":"","taxonomies":"","in\_all\_terms":"","include\_cf\_posts":"","exclude\_cf\_posts":"","linked\_posts":"","favourite\_only":"","open\_in\_new\_window":"","show\_modified\_date":"","time\_ago":"","time\_ago\_add\_txt":"ago","time\_ago\_txt\_pos":"","f\_header\_font\_header":"","f\_header\_font\_title":"Block header","f\_header\_font\_settings":"","f\_header\_font\_family":"","f\_header\_font\_size":"","f\_header\_font\_line\_height":"","f\_header\_font\_style":"","f\_header\_font\_weight":"","f\_header\_font\_transform":"","f\_header\_font\_spacing":"","f\_header\_":"","f\_ajax\_font\_title":"Ajax categories","f\_ajax\_font\_settings":"","f\_ajax\_font\_family":"","f\_ajax\_font\_size":"","f\_ajax\_font\_line\_height":"","f\_ajax\_font\_style":"","f\_ajax\_font\_weight":"","f\_ajax\_font\_transform":"","f\_ajax\_font\_spacing":"","f\_ajax\_":"","f\_more\_font\_title":"Load more button","f\_more\_font\_settings":"","f\_more\_font\_family":"","f\_more\_font\_size":"","f\_more\_font\_line\_height":"","f\_more\_font\_style":"","f\_more\_font\_weight":"","f\_more\_font\_transform":"","f\_more\_font\_spacing":"","f\_more\_":"","m6f\_title\_font\_header":"","m6f\_title\_font\_title":"Article title","m6f\_title\_font\_settings":"","m6f\_title\_font\_family":"","m6f\_title\_font\_size":"","m6f\_title\_font\_line\_height":"","m6f\_title\_font\_style":"","m6f\_title\_font\_weight":"","m6f\_title\_font\_transform":"","m6f\_title\_font\_spacing":"","m6f\_title\_":"","m6f\_cat\_font\_title":"Article category tag","m6f\_cat\_font\_settings":"","m6f\_cat\_font\_family":"","m6f\_cat\_font\_size":"","m6f\_cat\_font\_line\_height":"","m6f\_cat\_font\_style":"","m6f\_cat\_font\_weight":"","m6f\_cat\_font\_transform":"","m6f\_cat\_font\_spacing":"","m6f\_cat\_":"","m6f\_meta\_font\_title":"Article meta info","m6f\_meta\_font\_settings":"","m6f\_meta\_font\_family":"","m6f\_meta\_font\_size":"","m6f\_meta\_font\_line\_height":"","m6f\_meta\_font\_style":"","m6f\_meta\_font\_weight":"","m6f\_meta\_font\_transform":"","m6f\_meta\_font\_spacing":"","m6f\_meta\_":"","ajax\_pagination\_next\_prev\_swipe":"","css":"","tdc\_css":"","td\_column\_number":1,"color\_preset":"","border\_top":"","tdc\_css\_class":"tdi\_8","tdc\_css\_class\_style":"tdi\_8\_rand\_style"}';block\_tdi\_8.td\_column\_number="1";block\_tdi\_8.block\_type="td\_block\_7";block\_tdi\_8.post\_count="8";block\_tdi\_8.found\_posts="3237";block\_tdi\_8.header\_color="#e95420";block\_tdi\_8.ajax\_pagination\_infinite\_stop="";block\_tdi\_8.max\_num\_pages="405";tdBlocksArray.push(block\_tdi\_8);

#### Recent Posts

[![](https://computingforgeeks.com/wp-content/uploads/2023/08/ASUS-ROG-Strix-G16-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "10 Cheap Laptops with Intel Core i9 Processor for 2023")](https://computingforgeeks.com/cheap-laptops-with-intel-core-i9-processor/ "10 Cheap Laptops with Intel Core i9 Processor for 2023")

### [10 Cheap Laptops with Intel Core i9 Processor for 2023](https://computingforgeeks.com/cheap-laptops-with-intel-core-i9-processor/ "10 Cheap Laptops with Intel Core i9 Processor for 2023")

Modified date: August 16, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2023/08/Working-with-AWS-FSx-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Working with AWS FSx: Instant File System on AWS")](https://computingforgeeks.com/working-with-aws-fsx-instant-file-system-on-aws/ "Working with AWS FSx: Instant File System on AWS")

### [Working with AWS FSx: Instant File System on AWS](https://computingforgeeks.com/working-with-aws-fsx-instant-file-system-on-aws/ "Working with AWS FSx: Instant File System on AWS")

Modified date: August 15, 2023

[![Mattermost Server on Debian 12](https://computingforgeeks.com/wp-content/uploads/2023/08/Deploying-Mattermost-Server-on-Debian-12-Bookworm-6-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Deploying Mattermost Server on Debian 12 (Bookworm)")](https://computingforgeeks.com/deploying-mattermost-server-on-debian/ "Deploying Mattermost Server on Debian 12 (Bookworm)")

### [Deploying Mattermost Server on Debian 12 (Bookworm)](https://computingforgeeks.com/deploying-mattermost-server-on-debian/ "Deploying Mattermost Server on Debian 12 (Bookworm)")

Modified date: August 16, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2023/08/Stellar-Repair-for-MySQL-02-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Stellar Repair for MySQL: A Powerful Tool for MySQL Database Administrators")](https://computingforgeeks.com/stellar-repair-for-mysql-powerful-tool-for-mysql-database-administrators/ "Stellar Repair for MySQL: A Powerful Tool for MySQL Database Administrators")

### [Stellar Repair for MySQL: A Powerful Tool for MySQL Database Administrators](https://computingforgeeks.com/stellar-repair-for-mysql-powerful-tool-for-mysql-database-administrators/ "Stellar Repair for MySQL: A Powerful Tool for MySQL Database Administrators")

Modified date: August 17, 2023

[![Automated Logical Volume Manager (LVM) Management on Linux using Ansible](https://computingforgeeks.com/wp-content/uploads/2023/07/Automated-Logical-Volume-Manager-LVM-Management-on-Linux-using-Ansible-5-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Automated Logical Volume Manager (LVM) Management on Linux using Ansible")](https://computingforgeeks.com/automated-logical-volume-manager-lvm-management-using-ansible/ "Automated Logical Volume Manager (LVM) Management on Linux using Ansible")

### [Automated Logical Volume Manager (LVM) Management on Linux using Ansible](https://computingforgeeks.com/automated-logical-volume-manager-lvm-management-using-ansible/ "Automated Logical Volume Manager (LVM) Management on Linux using Ansible")

Modified date: August 14, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2023/08/Photon-OS-100x70.jpeg?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Manage Photon OS from Command Line Interface (CLI)")](https://computingforgeeks.com/manage-photon-os-from-command-line-interface-cli/ "Manage Photon OS from Command Line Interface (CLI)")

### [Manage Photon OS from Command Line Interface (CLI)](https://computingforgeeks.com/manage-photon-os-from-command-line-interface-cli/ "Manage Photon OS from Command Line Interface (CLI)")

Modified date: August 13, 2023

[![Install and Configure Pomerium Proxy for your Services](https://computingforgeeks.com/wp-content/uploads/2023/07/Install-and-Configure-Pomerium-Proxy-for-your-Services-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Install and Configure Pomerium Proxy for your Services")](https://computingforgeeks.com/install-pomerium-proxy-for-your-services/ "Install and Configure Pomerium Proxy for your Services")

### [Install and Configure Pomerium Proxy for your Services](https://computingforgeeks.com/install-pomerium-proxy-for-your-services/ "Install and Configure Pomerium Proxy for your Services")

Modified date: August 13, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2023/08/openproject-ssl-apache-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Secure OpenProject with Let’s Encrypt SSL Certificate")](https://computingforgeeks.com/secure-openproject-with-lets-encrypt-ssl-certificate/ "Secure OpenProject with Let’s Encrypt SSL Certificate")

### [Secure OpenProject with Let’s Encrypt SSL Certificate](https://computingforgeeks.com/secure-openproject-with-lets-encrypt-ssl-certificate/ "Secure OpenProject with Let’s Encrypt SSL Certificate")

Modified date: August 11, 2023

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-large-leaderboard-1","ezslot\_12",106,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-large-leaderboard-1-0");

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-large-leaderboard-1","ezslot\_13",106,"0","1"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-large-leaderboard-1-0\_1");

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-large-leaderboard-1","ezslot\_14",106,"0","2"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-large-leaderboard-1-0\_2");

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-large-leaderboard-1","ezslot\_15",106,"0","3"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-large-leaderboard-1-0\_3");

.large-leaderboard-1-multi-106{border:none !important;display:block !important;float:none !important;line-height:0px;margin-bottom:5px !important;margin-left:auto !important;margin-right:auto !important;margin-top:5px !important;max-width:100% !important;min-height:250px;min-width:300px;padding:0;text-align:center !important;}

.td-theme-wrap .tdi\_9 .td-pulldown-filter-link:hover,.td-theme-wrap .tdi\_9 .td-subcat-item a:hover,.td-theme-wrap .tdi\_9 .td-subcat-item .td-cur-simple-item{color:#9fc31a}.td-theme-wrap .tdi\_9 .block-title>\*,.td-theme-wrap .tdi\_9 .td-subcat-dropdown:hover .td-subcat-more{background-color:#9fc31a}.td-theme-wrap .td-footer-wrapper .tdi\_9 .block-title>\*{padding:6px 7px 5px;line-height:1}.td-theme-wrap .tdi\_9 .block-title{border-color:#9fc31a}.td-theme-wrap .tdi\_9 .td\_module\_wrap:hover .entry-title a,.td-theme-wrap .tdi\_9 .td\_quote\_on\_blocks,.td-theme-wrap .tdi\_9 .td-opacity-cat .td-post-category:hover,.td-theme-wrap .tdi\_9 .td-opacity-read .td-read-more a:hover,.td-theme-wrap .tdi\_9 .td-opacity-author .td-post-author-name a:hover,.td-theme-wrap .tdi\_9 .td-instagram-user a{color:#9fc31a}.td-theme-wrap .tdi\_9 .td-next-prev-wrap a:hover,.td-theme-wrap .tdi\_9 .td-load-more-wrap a:hover{background-color:#9fc31a;border-color:#9fc31a}.td-theme-wrap .tdi\_9 .td-read-more a,.td-theme-wrap .tdi\_9 .td-weather-information:before,.td-theme-wrap .tdi\_9 .td-weather-week:before,.td-theme-wrap .tdi\_9 .td-exchange-header:before,.td-theme-wrap .td-footer-wrapper .tdi\_9 .td-post-category,.td-theme-wrap .tdi\_9 .td-post-category:hover{background-color:#9fc31a}var block\_tdi\_9=new tdBlock();block\_tdi\_9.id="tdi\_9";block\_tdi\_9.atts='{"custom\_title":"More Content","custom\_url":"","block\_template\_id":"","header\_color":"#9FC31A","header\_text\_color":"#","accent\_text\_color":"#","m6\_tl":"","limit":"10","offset":"","el\_class":"","post\_ids":"-59740","category\_id":"","category\_ids":"-36922,-36279,-1717,-120,-832,-119","tag\_slug":"","autors\_id":"","installed\_post\_types":"","sort":"random\_posts","td\_ajax\_filter\_type":"","td\_ajax\_filter\_ids":"","td\_filter\_default\_txt":"All","td\_ajax\_preloading":"","ajax\_pagination":"","ajax\_pagination\_infinite\_stop":"","taxonomies":"","time\_ago\_add\_txt":"ago","class":"td\_block\_widget tdi\_9","block\_type":"td\_block\_7","separator":"","in\_all\_terms":"","include\_cf\_posts":"","exclude\_cf\_posts":"","linked\_posts":"","favourite\_only":"","open\_in\_new\_window":"","show\_modified\_date":"","time\_ago":"","time\_ago\_txt\_pos":"","f\_header\_font\_header":"","f\_header\_font\_title":"Block header","f\_header\_font\_settings":"","f\_header\_font\_family":"","f\_header\_font\_size":"","f\_header\_font\_line\_height":"","f\_header\_font\_style":"","f\_header\_font\_weight":"","f\_header\_font\_transform":"","f\_header\_font\_spacing":"","f\_header\_":"","f\_ajax\_font\_title":"Ajax categories","f\_ajax\_font\_settings":"","f\_ajax\_font\_family":"","f\_ajax\_font\_size":"","f\_ajax\_font\_line\_height":"","f\_ajax\_font\_style":"","f\_ajax\_font\_weight":"","f\_ajax\_font\_transform":"","f\_ajax\_font\_spacing":"","f\_ajax\_":"","f\_more\_font\_title":"Load more button","f\_more\_font\_settings":"","f\_more\_font\_family":"","f\_more\_font\_size":"","f\_more\_font\_line\_height":"","f\_more\_font\_style":"","f\_more\_font\_weight":"","f\_more\_font\_transform":"","f\_more\_font\_spacing":"","f\_more\_":"","m6f\_title\_font\_header":"","m6f\_title\_font\_title":"Article title","m6f\_title\_font\_settings":"","m6f\_title\_font\_family":"","m6f\_title\_font\_size":"","m6f\_title\_font\_line\_height":"","m6f\_title\_font\_style":"","m6f\_title\_font\_weight":"","m6f\_title\_font\_transform":"","m6f\_title\_font\_spacing":"","m6f\_title\_":"","m6f\_cat\_font\_title":"Article category tag","m6f\_cat\_font\_settings":"","m6f\_cat\_font\_family":"","m6f\_cat\_font\_size":"","m6f\_cat\_font\_line\_height":"","m6f\_cat\_font\_style":"","m6f\_cat\_font\_weight":"","m6f\_cat\_font\_transform":"","m6f\_cat\_font\_spacing":"","m6f\_cat\_":"","m6f\_meta\_font\_title":"Article meta info","m6f\_meta\_font\_settings":"","m6f\_meta\_font\_family":"","m6f\_meta\_font\_size":"","m6f\_meta\_font\_line\_height":"","m6f\_meta\_font\_style":"","m6f\_meta\_font\_weight":"","m6f\_meta\_font\_transform":"","m6f\_meta\_font\_spacing":"","m6f\_meta\_":"","ajax\_pagination\_next\_prev\_swipe":"","css":"","tdc\_css":"","td\_column\_number":1,"color\_preset":"","border\_top":"","tdc\_css\_class":"tdi\_9","tdc\_css\_class\_style":"tdi\_9\_rand\_style"}';block\_tdi\_9.td\_column\_number="1";block\_tdi\_9.block\_type="td\_block\_7";block\_tdi\_9.post\_count="10";block\_tdi\_9.found\_posts="2266";block\_tdi\_9.header\_color="#9FC31A";block\_tdi\_9.ajax\_pagination\_infinite\_stop="";block\_tdi\_9.max\_num\_pages="227";tdBlocksArray.push(block\_tdi\_9);

#### More Content

[![](https://computingforgeeks.com/wp-content/uploads/2018/07/hugo-site-generator-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Install and Use Hugo On Ubuntu 22.04|20.04|18.04")](https://computingforgeeks.com/how-to-install-hugo-on-ubuntu-debian/ "Install and Use Hugo On Ubuntu 22.04|20.04|18.04")

### [Install and Use Hugo On Ubuntu 22.04|20.04|18.04](https://computingforgeeks.com/how-to-install-hugo-on-ubuntu-debian/ "Install and Use Hugo On Ubuntu 22.04|20.04|18.04")

Modified date: March 13, 2022

[![](https://computingforgeeks.com/wp-content/uploads/2021/12/How-To-Install-CentOS-Stream-9-Complete-Steps-With-Screenshots-30-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Install CentOS Stream 9 – Complete Steps With Screenshots")](https://computingforgeeks.com/install-centos-stream-9-complete-steps-with-screenshots/ "Install CentOS Stream 9 – Complete Steps With Screenshots")

### [Install CentOS Stream 9 – Complete Steps With Screenshots](https://computingforgeeks.com/install-centos-stream-9-complete-steps-with-screenshots/ "Install CentOS Stream 9 – Complete Steps With Screenshots")

Modified date: May 25, 2022

[![](https://computingforgeeks.com/wp-content/uploads/2019/03/consul-cluster-ui-centos7-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "How To Setup Consul Cluster on CentOS / RHEL 7/8")](https://computingforgeeks.com/how-to-setup-consul-cluster-on-centos-rhel/ "How To Setup Consul Cluster on CentOS / RHEL 7/8")

### [How To Setup Consul Cluster on CentOS / RHEL 7/8](https://computingforgeeks.com/how-to-setup-consul-cluster-on-centos-rhel/ "How To Setup Consul Cluster on CentOS / RHEL 7/8")

Modified date: January 4, 2020

[![](https://computingforgeeks.com/wp-content/uploads/2019/03/countdown-timer-hours-minutes-seconds-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Best Countdown Timer App for Linux")](https://computingforgeeks.com/best-countdown-timer-app-for-linux/ "Best Countdown Timer App for Linux")

### [Best Countdown Timer App for Linux](https://computingforgeeks.com/best-countdown-timer-app-for-linux/ "Best Countdown Timer App for Linux")

Modified date: February 11, 2021

[![](https://computingforgeeks.com/wp-content/uploads/2019/09/openstack-list-instances-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "How To Configure OpenStack Instances / VMs to Autostart after Nova compute reboot")](https://computingforgeeks.com/configure-openstack-instances-vms-to-autostart-after-boot/ "How To Configure OpenStack Instances / VMs to Autostart after Nova compute reboot")

### [How To Configure OpenStack Instances / VMs to Autostart after Nova...](https://computingforgeeks.com/configure-openstack-instances-vms-to-autostart-after-boot/ "How To Configure OpenStack Instances / VMs to Autostart after Nova compute reboot")

Modified date: September 17, 2019

[![](https://computingforgeeks.com/wp-content/uploads/2018/12/install-percona-toolkit-ubuntu-18.04-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Install Percona MySQL Server 8.0 on Ubuntu 22.04|20.04|18.04")](https://computingforgeeks.com/install-percona-mysql-server-ubuntu-debian/ "Install Percona MySQL Server 8.0 on Ubuntu 22.04|20.04|18.04")

### [Install Percona MySQL Server 8.0 on Ubuntu 22.04|20.04|18.04](https://computingforgeeks.com/install-percona-mysql-server-ubuntu-debian/ "Install Percona MySQL Server 8.0 on Ubuntu 22.04|20.04|18.04")

Modified date: June 3, 2022

[![](https://computingforgeeks.com/wp-content/uploads/2020/10/Create-File-System-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "How To Mount AWS EFS File System on EC2 Instance")](https://computingforgeeks.com/mount-aws-efs-file-system-on-ec2/ "How To Mount AWS EFS File System on EC2 Instance")

### [How To Mount AWS EFS File System on EC2 Instance](https://computingforgeeks.com/mount-aws-efs-file-system-on-ec2/ "How To Mount AWS EFS File System on EC2 Instance")

Modified date: April 15, 2023

[![kibana_logs](https://computingforgeeks.com/wp-content/uploads/2021/03/kibana_logs-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Forward Kubernetes Logs to Elasticsearch (ELK) using Fluentbit")](https://computingforgeeks.com/forward-kubernetes-logs-to-elasticsearch-using-fluentbit/ "Forward Kubernetes Logs to Elasticsearch (ELK) using Fluentbit")

### [Forward Kubernetes Logs to Elasticsearch (ELK) using Fluentbit](https://computingforgeeks.com/forward-kubernetes-logs-to-elasticsearch-using-fluentbit/ "Forward Kubernetes Logs to Elasticsearch (ELK) using Fluentbit")

Modified date: March 30, 2021

[![](https://computingforgeeks.com/wp-content/uploads/2018/08/install-librenms-ubuntu-18.04-01-login-min-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "How To Install LibreNMS on Ubuntu 22.04/20.04/18.04")](https://computingforgeeks.com/how-to-install-librenms-on-ubuntu/ "How To Install LibreNMS on Ubuntu 22.04/20.04/18.04")

### [How To Install LibreNMS on Ubuntu 22.04/20.04/18.04](https://computingforgeeks.com/how-to-install-librenms-on-ubuntu/ "How To Install LibreNMS on Ubuntu 22.04/20.04/18.04")

Modified date: August 16, 2023

[![Android Google Searc API Image](https://computingforgeeks.com/wp-content/uploads/2019/11/map_android-100x70.jpeg?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Android: Select location on the map using draggable markers and Google Search API")](https://computingforgeeks.com/select-location-on-the-map-using-draggable-markers-and-google-search-api/ "Android: Select location on the map using draggable markers and Google Search API")

### [Android: Select location on the map using draggable markers and Google...](https://computingforgeeks.com/select-location-on-the-map-using-draggable-markers-and-google-search-api/ "Android: Select location on the map using draggable markers and Google Search API")

Modified date: December 22, 2020

.td-theme-wrap .tdi\_10 .td-pulldown-filter-link:hover,.td-theme-wrap .tdi\_10 .td-subcat-item a:hover,.td-theme-wrap .tdi\_10 .td-subcat-item .td-cur-simple-item{color:#8b006f}.td-theme-wrap .tdi\_10 .block-title>\*,.td-theme-wrap .tdi\_10 .td-subcat-dropdown:hover .td-subcat-more{background-color:#8b006f}.td-theme-wrap .td-footer-wrapper .tdi\_10 .block-title>\*{padding:6px 7px 5px;line-height:1}.td-theme-wrap .tdi\_10 .block-title{border-color:#8b006f}.td-theme-wrap .tdi\_10 .td\_module\_wrap:hover .entry-title a,.td-theme-wrap .tdi\_10 .td\_quote\_on\_blocks,.td-theme-wrap .tdi\_10 .td-opacity-cat .td-post-category:hover,.td-theme-wrap .tdi\_10 .td-opacity-read .td-read-more a:hover,.td-theme-wrap .tdi\_10 .td-opacity-author .td-post-author-name a:hover,.td-theme-wrap .tdi\_10 .td-instagram-user a{color:#8b006f}.td-theme-wrap .tdi\_10 .td-next-prev-wrap a:hover,.td-theme-wrap .tdi\_10 .td-load-more-wrap a:hover{background-color:#8b006f;border-color:#8b006f}.td-theme-wrap .tdi\_10 .td-read-more a,.td-theme-wrap .tdi\_10 .td-weather-information:before,.td-theme-wrap .tdi\_10 .td-weather-week:before,.td-theme-wrap .tdi\_10 .td-exchange-header:before,.td-theme-wrap .td-footer-wrapper .tdi\_10 .td-post-category,.td-theme-wrap .tdi\_10 .td-post-category:hover{background-color:#8b006f}var block\_tdi\_10=new tdBlock();block\_tdi\_10.id="tdi\_10";block\_tdi\_10.atts='{"custom\_title":"Books","custom\_url":"","block\_template\_id":"","header\_color":"#8b006f","header\_text\_color":"#","accent\_text\_color":"#","m6\_tl":"","limit":"30","offset":"","el\_class":"","post\_ids":"-59740","category\_id":"1077","category\_ids":"","tag\_slug":"","autors\_id":"","installed\_post\_types":"","sort":"random\_posts","td\_ajax\_filter\_type":"","td\_ajax\_filter\_ids":"","td\_filter\_default\_txt":"All","td\_ajax\_preloading":"","ajax\_pagination":"","ajax\_pagination\_infinite\_stop":"","class":"td\_block\_widget tdi\_10","block\_type":"td\_block\_7","separator":"","taxonomies":"","in\_all\_terms":"","include\_cf\_posts":"","exclude\_cf\_posts":"","linked\_posts":"","favourite\_only":"","open\_in\_new\_window":"","show\_modified\_date":"","time\_ago":"","time\_ago\_add\_txt":"ago","time\_ago\_txt\_pos":"","f\_header\_font\_header":"","f\_header\_font\_title":"Block header","f\_header\_font\_settings":"","f\_header\_font\_family":"","f\_header\_font\_size":"","f\_header\_font\_line\_height":"","f\_header\_font\_style":"","f\_header\_font\_weight":"","f\_header\_font\_transform":"","f\_header\_font\_spacing":"","f\_header\_":"","f\_ajax\_font\_title":"Ajax categories","f\_ajax\_font\_settings":"","f\_ajax\_font\_family":"","f\_ajax\_font\_size":"","f\_ajax\_font\_line\_height":"","f\_ajax\_font\_style":"","f\_ajax\_font\_weight":"","f\_ajax\_font\_transform":"","f\_ajax\_font\_spacing":"","f\_ajax\_":"","f\_more\_font\_title":"Load more button","f\_more\_font\_settings":"","f\_more\_font\_family":"","f\_more\_font\_size":"","f\_more\_font\_line\_height":"","f\_more\_font\_style":"","f\_more\_font\_weight":"","f\_more\_font\_transform":"","f\_more\_font\_spacing":"","f\_more\_":"","m6f\_title\_font\_header":"","m6f\_title\_font\_title":"Article title","m6f\_title\_font\_settings":"","m6f\_title\_font\_family":"","m6f\_title\_font\_size":"","m6f\_title\_font\_line\_height":"","m6f\_title\_font\_style":"","m6f\_title\_font\_weight":"","m6f\_title\_font\_transform":"","m6f\_title\_font\_spacing":"","m6f\_title\_":"","m6f\_cat\_font\_title":"Article category tag","m6f\_cat\_font\_settings":"","m6f\_cat\_font\_family":"","m6f\_cat\_font\_size":"","m6f\_cat\_font\_line\_height":"","m6f\_cat\_font\_style":"","m6f\_cat\_font\_weight":"","m6f\_cat\_font\_transform":"","m6f\_cat\_font\_spacing":"","m6f\_cat\_":"","m6f\_meta\_font\_title":"Article meta info","m6f\_meta\_font\_settings":"","m6f\_meta\_font\_family":"","m6f\_meta\_font\_size":"","m6f\_meta\_font\_line\_height":"","m6f\_meta\_font\_style":"","m6f\_meta\_font\_weight":"","m6f\_meta\_font\_transform":"","m6f\_meta\_font\_spacing":"","m6f\_meta\_":"","ajax\_pagination\_next\_prev\_swipe":"","css":"","tdc\_css":"","td\_column\_number":1,"color\_preset":"","border\_top":"","tdc\_css\_class":"tdi\_10","tdc\_css\_class\_style":"tdi\_10\_rand\_style"}';block\_tdi\_10.td\_column\_number="1";block\_tdi\_10.block\_type="td\_block\_7";block\_tdi\_10.post\_count="30";block\_tdi\_10.found\_posts="88";block\_tdi\_10.header\_color="#8b006f";block\_tdi\_10.ajax\_pagination\_infinite\_stop="";block\_tdi\_10.max\_num\_pages="3";tdBlocksArray.push(block\_tdi\_10);

#### Books

[![](https://computingforgeeks.com/wp-content/uploads/2020/08/students-learn-100x70.jpeg?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Which Programming Language to Learn in 2022? Top 4 Choices")](https://computingforgeeks.com/programming-language-to-learn-in-new-year/ "Which Programming Language to Learn in 2022? Top 4 Choices")

### [Which Programming Language to Learn in 2022? Top 4 Choices](https://computingforgeeks.com/programming-language-to-learn-in-new-year/ "Which Programming Language to Learn in 2022? Top 4 Choices")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2020/05/Go-programming-books-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Best Go Programming Books for Beginners and Experts 2023")](https://computingforgeeks.com/best-go-programming-books-for-beginners-and-experts/ "Best Go Programming Books for Beginners and Experts 2023")

### [Best Go Programming Books for Beginners and Experts 2023](https://computingforgeeks.com/best-go-programming-books-for-beginners-and-experts/ "Best Go Programming Books for Beginners and Experts 2023")

Modified date: June 13, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2023/07/Learning-Kali-Linux-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Recommended Books To Master Kali Linux Penetration Testing")](https://computingforgeeks.com/recommended-books-to-master-kali-linux-penetration-testing/ "Recommended Books To Master Kali Linux Penetration Testing")

### [Recommended Books To Master Kali Linux Penetration Testing](https://computingforgeeks.com/recommended-books-to-master-kali-linux-penetration-testing/ "Recommended Books To Master Kali Linux Penetration Testing")

Modified date: July 14, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2019/07/best-kubernetes-books-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Best Kubernetes Study books for 2023")](https://computingforgeeks.com/best-kubernetes-study-books/ "Best Kubernetes Study books for 2023")

### [Best Kubernetes Study books for 2023](https://computingforgeeks.com/best-kubernetes-study-books/ "Best Kubernetes Study books for 2023")

Modified date: June 14, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2019/09/Certified_Scrum_Master-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Certified Scrum Master Preparation Books 2023")](https://computingforgeeks.com/best-certified-scrum-master-preparation-books/ "Best Certified Scrum Master Preparation Books 2023")

### [Best Certified Scrum Master Preparation Books 2023](https://computingforgeeks.com/best-certified-scrum-master-preparation-books/ "Best Certified Scrum Master Preparation Books 2023")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2019/07/rhcsa-rhce-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Top RHCSA / RHCE Certification Study Books 2023")](https://computingforgeeks.com/top-rhcsa-rhce-certification-study-books/ "Top RHCSA / RHCE Certification Study Books 2023")

### [Top RHCSA / RHCE Certification Study Books 2023](https://computingforgeeks.com/top-rhcsa-rhce-certification-study-books/ "Top RHCSA / RHCE Certification Study Books 2023")

Modified date: June 14, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2019/02/best-ccna-security-study-books-100x70.png?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best CCNA Security (210-260) Certification Study Books 2023")](https://computingforgeeks.com/best-ccna-security-certification-study-books/ "Best CCNA Security (210-260) Certification Study Books 2023")

### [Best CCNA Security (210-260) Certification Study Books 2023](https://computingforgeeks.com/best-ccna-security-certification-study-books/ "Best CCNA Security (210-260) Certification Study Books 2023")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/04/digital-marketing-feature-image-100x70.png?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Online Marketing Books To Read in 2023")](https://computingforgeeks.com/top-recommended-books-on-online-marketing/ "Best Online Marketing Books To Read in 2023")

### [Best Online Marketing Books To Read in 2023](https://computingforgeeks.com/top-recommended-books-on-online-marketing/ "Best Online Marketing Books To Read in 2023")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2019/07/best-ccnp-rs-books-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best CCNP R&S Certification Preparation books 2023")](https://computingforgeeks.com/best-ccnp-certification-preparation-books/ "Best CCNP R&S Certification Preparation books 2023")

### [Best CCNP R&S Certification Preparation books 2023](https://computingforgeeks.com/best-ccnp-certification-preparation-books/ "Best CCNP R&S Certification Preparation books 2023")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/09/rabbitmq-feature-image-100x70.png?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Books To Learn Rabbitmq/Activemq/Zeromq in 2023")](https://computingforgeeks.com/best-books-to-learn-rabbitmq-activemq-zeromq/ "Books To Learn Rabbitmq/Activemq/Zeromq in 2023")

### [Books To Learn Rabbitmq/Activemq/Zeromq in 2023](https://computingforgeeks.com/best-books-to-learn-rabbitmq-activemq-zeromq/ "Books To Learn Rabbitmq/Activemq/Zeromq in 2023")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2023/06/Best-Books-To-Learn-Node.js-Programming-in-2023-1-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Books To Learn Node.js Programming in 2023")](https://computingforgeeks.com/best-books-to-learn-nodejs-programming/ "Best Books To Learn Node.js Programming in 2023")

### [Best Books To Learn Node.js Programming in 2023](https://computingforgeeks.com/best-books-to-learn-nodejs-programming/ "Best Books To Learn Node.js Programming in 2023")

Modified date: June 13, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/01/linux-kernel-development-100x70.png?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Linux Kernel Programming Books in 2023")](https://computingforgeeks.com/best-linux-kernel-programming-books/ "Best Linux Kernel Programming Books in 2023")

### [Best Linux Kernel Programming Books in 2023](https://computingforgeeks.com/best-linux-kernel-programming-books/ "Best Linux Kernel Programming Books in 2023")

Modified date: June 19, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/09/OpenCV-Feature-Image-100x70.png?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Books To Learn OpenCV & Computer Vision in 2023")](https://computingforgeeks.com/best-books-to-learn-opencv-computer-vision/ "Best Books To Learn OpenCV & Computer Vision in 2023")

### [Best Books To Learn OpenCV & Computer Vision in 2023](https://computingforgeeks.com/best-books-to-learn-opencv-computer-vision/ "Best Books To Learn OpenCV & Computer Vision in 2023")

Modified date: January 13, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2019/04/best-python-books-100x70.png?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Books for Learning Python Programming 2023")](https://computingforgeeks.com/best-books-for-learning-python-programming/ "Best Books for Learning Python Programming 2023")

### [Best Books for Learning Python Programming 2023](https://computingforgeeks.com/best-books-for-learning-python-programming/ "Best Books for Learning Python Programming 2023")

Modified date: July 6, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/02/programming-for-kids-100x70.png?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Programming Books for Kids in 2022")](https://computingforgeeks.com/best-programming-books-for-kids/ "Best Programming Books for Kids in 2022")

### [Best Programming Books for Kids in 2022](https://computingforgeeks.com/best-programming-books-for-kids/ "Best Programming Books for Kids in 2022")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2020/05/freebsd-mastery-books-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Books To Learn and Master FreeBSD in 2022")](https://computingforgeeks.com/best-books-to-learn-and-master-freebsd/ "Best Books To Learn and Master FreeBSD in 2022")

### [Best Books To Learn and Master FreeBSD in 2022](https://computingforgeeks.com/best-books-to-learn-and-master-freebsd/ "Best Books To Learn and Master FreeBSD in 2022")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2019/02/best-linux-books-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Linux Books for Beginners & Experts 2023")](https://computingforgeeks.com/best-rated-top-linux-books-for-beginners/ "Best Linux Books for Beginners & Experts 2023")

### [Best Linux Books for Beginners & Experts 2023](https://computingforgeeks.com/best-rated-top-linux-books-for-beginners/ "Best Linux Books for Beginners & Experts 2023")

Modified date: June 7, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/05/Nginx-Apache-image-100x70.png?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Apache and Nginx reference Books for 2023")](https://computingforgeeks.com/best-apache-and-nginx-reference-books/ "Best Apache and Nginx reference Books for 2023")

### [Best Apache and Nginx reference Books for 2023](https://computingforgeeks.com/best-apache-and-nginx-reference-books/ "Best Apache and Nginx reference Books for 2023")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/07/cybersecurity-feature-image-100x70.png?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Cybersecurity Books To Read in 2023")](https://computingforgeeks.com/best-cybersecurity-books-to-read/ "Best Cybersecurity Books To Read in 2023")

### [Best Cybersecurity Books To Read in 2023](https://computingforgeeks.com/best-cybersecurity-books-to-read/ "Best Cybersecurity Books To Read in 2023")

Modified date: July 19, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/01/ios-books-100x70.png?ezimgfmt=rs:100x70/rscb23/ngcb23/notWebP "Best Books To Learn iOS Programming in 2023")](https://computingforgeeks.com/best-books-to-learn-ios-programming/ "Best Books To Learn iOS Programming in 2023")

### [Best Books To Learn iOS Programming in 2023](https://computingforgeeks.com/best-books-to-learn-ios-programming/ "Best Books To Learn iOS Programming in 2023")

Modified date: July 12, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/02/R-Cover-image-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Best Books To Master R Programming in 2023")](https://computingforgeeks.com/best-books-to-master-r-programming/ "Best Books To Master R Programming in 2023")

### [Best Books To Master R Programming in 2023](https://computingforgeeks.com/best-books-to-master-r-programming/ "Best Books To Master R Programming in 2023")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/04/wordpress-books-feature-image-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Best Books To Learn WordPress Development in 2023")](https://computingforgeeks.com/best-books-to-learn-wordpress-development/ "Best Books To Learn WordPress Development in 2023")

### [Best Books To Learn WordPress Development in 2023](https://computingforgeeks.com/best-books-to-learn-wordpress-development/ "Best Books To Learn WordPress Development in 2023")

Modified date: July 22, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/03/scala-books-featured-image-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Best Books To Learn Scala Programming in 2023")](https://computingforgeeks.com/best-books-to-learn-scala-programming/ "Best Books To Learn Scala Programming in 2023")

### [Best Books To Learn Scala Programming in 2023](https://computingforgeeks.com/best-books-to-learn-scala-programming/ "Best Books To Learn Scala Programming in 2023")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2019/07/learn-docker-1-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Best Books To learn Docker and Ansible Automation 2023")](https://computingforgeeks.com/best-books-to-learn-docker-and-ansible-automation/ "Best Books To learn Docker and Ansible Automation 2023")

### [Best Books To learn Docker and Ansible Automation 2023](https://computingforgeeks.com/best-books-to-learn-docker-and-ansible-automation/ "Best Books To learn Docker and Ansible Automation 2023")

Modified date: July 11, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/02/C-Cover-image-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Best Books To Learn C# and .NET Programming in 2023")](https://computingforgeeks.com/best-books-to-learn-c-dot-net-programming/ "Best Books To Learn C# and .NET Programming in 2023")

### [Best Books To Learn C# and .NET Programming in 2023](https://computingforgeeks.com/best-books-to-learn-c-dot-net-programming/ "Best Books To Learn C# and .NET Programming in 2023")

Modified date: July 12, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2021/02/Perl-Books-Featured-Image-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Best Books To Learn Perl Programming in 2023")](https://computingforgeeks.com/best-books-to-learn-perl-programming/ "Best Books To Learn Perl Programming in 2023")

### [Best Books To Learn Perl Programming in 2023](https://computingforgeeks.com/best-books-to-learn-perl-programming/ "Best Books To Learn Perl Programming in 2023")

Modified date: July 20, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2022/02/CompTIA-Security-Feature-iMAGE-100x70.png?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Best CompTIA Security+ (SY0-601) Certification Books 2022")](https://computingforgeeks.com/best-comptia-security-certification-books/ "Best CompTIA Security+ (SY0-601) Certification Books 2022")

### [Best CompTIA Security+ (SY0-601) Certification Books 2022](https://computingforgeeks.com/best-comptia-security-certification-books/ "Best CompTIA Security+ (SY0-601) Certification Books 2022")

Modified date: May 29, 2023

[![](https://computingforgeeks.com/wp-content/uploads/2019/04/lpi-certification-books-01-100x70.jpg?ezimgfmt=rs:100x70/rscb23/ng:webp/ngcb23 "Best LPIC-1 and LPIC-2 certification study books 2023")](https://computingforgeeks.com/best-lpic-1-and-lpic-2-certification-study-books/ "Best LPIC-1 and LPIC-2 certification study books 2023")

### [Best LPIC-1 and LPIC-2 certification study books 2023](https://computingforgeeks.com/best-lpic-1-and-lpic-2-certification-study-books/ "Best LPIC-1 and LPIC-2 certification study books 2023")

Modified date: July 6, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Best Books To Master Azure Cloud Platform in 2023")](https://computingforgeeks.com/best-books-to-master-azure-cloud-platform/ "Best Books To Master Azure Cloud Platform in 2023")

### [Best Books To Master Azure Cloud Platform in 2023](https://computingforgeeks.com/best-books-to-master-azure-cloud-platform/ "Best Books To Master Azure Cloud Platform in 2023")

Modified date: July 19, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Best books for Learning OpenStack Cloud Platform 2023")](https://computingforgeeks.com/best-books-for-learning-openstack-cloud-platform/ "Best books for Learning OpenStack Cloud Platform 2023")

### [Best books for Learning OpenStack Cloud Platform 2023](https://computingforgeeks.com/best-books-for-learning-openstack-cloud-platform/ "Best books for Learning OpenStack Cloud Platform 2023")

Modified date: July 11, 2023

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[300,250\],"computingforgeeks\_com-banner-2","ezslot\_3",143,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-banner-2-0");[![Ezoic](https://go.ezodn.com/utilcave_com/img/ezoic.png)](https://www.ezoic.com/what-is-ezoic/)report this ad

var block\_tdi\_12=new tdBlock();block\_tdi\_12.id="tdi\_12";block\_tdi\_12.atts='{"custom\_title":"FEATURED POSTS","limit":9,"sort":"featured","block\_type":"td\_block\_7","separator":"","custom\_url":"","block\_template\_id":"","m6\_tl":"","post\_ids":"-59740","category\_id":"","taxonomies":"","category\_ids":"","in\_all\_terms":"","tag\_slug":"","autors\_id":"","installed\_post\_types":"","include\_cf\_posts":"","exclude\_cf\_posts":"","linked\_posts":"","favourite\_only":"","offset":"","open\_in\_new\_window":"","show\_modified\_date":"","time\_ago":"","time\_ago\_add\_txt":"ago","time\_ago\_txt\_pos":"","el\_class":"","td\_ajax\_filter\_type":"","td\_ajax\_filter\_ids":"","td\_filter\_default\_txt":"All","td\_ajax\_preloading":"","f\_header\_font\_header":"","f\_header\_font\_title":"Block header","f\_header\_font\_settings":"","f\_header\_font\_family":"","f\_header\_font\_size":"","f\_header\_font\_line\_height":"","f\_header\_font\_style":"","f\_header\_font\_weight":"","f\_header\_font\_transform":"","f\_header\_font\_spacing":"","f\_header\_":"","f\_ajax\_font\_title":"Ajax categories","f\_ajax\_font\_settings":"","f\_ajax\_font\_family":"","f\_ajax\_font\_size":"","f\_ajax\_font\_line\_height":"","f\_ajax\_font\_style":"","f\_ajax\_font\_weight":"","f\_ajax\_font\_transform":"","f\_ajax\_font\_spacing":"","f\_ajax\_":"","f\_more\_font\_title":"Load more button","f\_more\_font\_settings":"","f\_more\_font\_family":"","f\_more\_font\_size":"","f\_more\_font\_line\_height":"","f\_more\_font\_style":"","f\_more\_font\_weight":"","f\_more\_font\_transform":"","f\_more\_font\_spacing":"","f\_more\_":"","m6f\_title\_font\_header":"","m6f\_title\_font\_title":"Article title","m6f\_title\_font\_settings":"","m6f\_title\_font\_family":"","m6f\_title\_font\_size":"","m6f\_title\_font\_line\_height":"","m6f\_title\_font\_style":"","m6f\_title\_font\_weight":"","m6f\_title\_font\_transform":"","m6f\_title\_font\_spacing":"","m6f\_title\_":"","m6f\_cat\_font\_title":"Article category tag","m6f\_cat\_font\_settings":"","m6f\_cat\_font\_family":"","m6f\_cat\_font\_size":"","m6f\_cat\_font\_line\_height":"","m6f\_cat\_font\_style":"","m6f\_cat\_font\_weight":"","m6f\_cat\_font\_transform":"","m6f\_cat\_font\_spacing":"","m6f\_cat\_":"","m6f\_meta\_font\_title":"Article meta info","m6f\_meta\_font\_settings":"","m6f\_meta\_font\_family":"","m6f\_meta\_font\_size":"","m6f\_meta\_font\_line\_height":"","m6f\_meta\_font\_style":"","m6f\_meta\_font\_weight":"","m6f\_meta\_font\_transform":"","m6f\_meta\_font\_spacing":"","m6f\_meta\_":"","ajax\_pagination":"","ajax\_pagination\_next\_prev\_swipe":"","ajax\_pagination\_infinite\_stop":"","css":"","tdc\_css":"","td\_column\_number":1,"header\_color":"","color\_preset":"","border\_top":"","class":"tdi\_12","tdc\_css\_class":"tdi\_12","tdc\_css\_class\_style":"tdi\_12\_rand\_style"}';block\_tdi\_12.td\_column\_number="1";block\_tdi\_12.block\_type="td\_block\_7";block\_tdi\_12.post\_count="9";block\_tdi\_12.found\_posts="65";block\_tdi\_12.header\_color="";block\_tdi\_12.ajax\_pagination\_infinite\_stop="";block\_tdi\_12.max\_num\_pages="8";tdBlocksArray.push(block\_tdi\_12);

#### FEATURED POSTS

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Install Flatcar Container Linux on VMware ESXI / vCenter")](https://computingforgeeks.com/install-flatcar-container-linux-on-vmware-esxi-vcenter/ "Install Flatcar Container Linux on VMware ESXI / vCenter")

### [Install Flatcar Container Linux on VMware ESXI / vCenter](https://computingforgeeks.com/install-flatcar-container-linux-on-vmware-esxi-vcenter/ "Install Flatcar Container Linux on VMware ESXI / vCenter")

Modified date: August 7, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Deploy Kubernetes Cluster using VMware Photon OS")](https://computingforgeeks.com/deploy-kubernetes-cluster-using-vmware-photon-os/ "Deploy Kubernetes Cluster using VMware Photon OS")

### [Deploy Kubernetes Cluster using VMware Photon OS](https://computingforgeeks.com/deploy-kubernetes-cluster-using-vmware-photon-os/ "Deploy Kubernetes Cluster using VMware Photon OS")

Modified date: June 14, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Configure WordPress To Use Gmail using WP Mail SMTP")](https://computingforgeeks.com/configure-wordpress-with-gmail-smtp/ "Configure WordPress To Use Gmail using WP Mail SMTP")

### [Configure WordPress To Use Gmail using WP Mail SMTP](https://computingforgeeks.com/configure-wordpress-with-gmail-smtp/ "Configure WordPress To Use Gmail using WP Mail SMTP")

Modified date: May 22, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Install and Use KubeSphere on existing Kubernetes cluster")](https://computingforgeeks.com/install-use-kubesphere-on-existing-kubernetes-cluster/ "Install and Use KubeSphere on existing Kubernetes cluster")

### [Install and Use KubeSphere on existing Kubernetes cluster](https://computingforgeeks.com/install-use-kubesphere-on-existing-kubernetes-cluster/ "Install and Use KubeSphere on existing Kubernetes cluster")

Modified date: June 8, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Install and Configure Traefik Ingress Controller on Kubernetes")](https://computingforgeeks.com/install-configure-traefik-ingress-controller-on-kubernetes/ "Install and Configure Traefik Ingress Controller on Kubernetes")

### [Install and Configure Traefik Ingress Controller on Kubernetes](https://computingforgeeks.com/install-configure-traefik-ingress-controller-on-kubernetes/ "Install and Configure Traefik Ingress Controller on Kubernetes")

Modified date: June 8, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Top Smart Plug Power Strips To Buy in 2023")](https://computingforgeeks.com/top-smart-plug-power-strips-to-buy/ "Top Smart Plug Power Strips To Buy in 2023")

### [Top Smart Plug Power Strips To Buy in 2023](https://computingforgeeks.com/top-smart-plug-power-strips-to-buy/ "Top Smart Plug Power Strips To Buy in 2023")

Modified date: March 10, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "How To Run Ansible AWX on Kubernetes / OpenShift Cluster")](https://computingforgeeks.com/run-ansible-awx-on-kubernetes-openshift-cluster/ "How To Run Ansible AWX on Kubernetes / OpenShift Cluster")

### [How To Run Ansible AWX on Kubernetes / OpenShift Cluster](https://computingforgeeks.com/run-ansible-awx-on-kubernetes-openshift-cluster/ "How To Run Ansible AWX on Kubernetes / OpenShift Cluster")

Modified date: June 8, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Configure NFS as Kubernetes Persistent Volume Storage")](https://computingforgeeks.com/configure-nfs-as-kubernetes-persistent-volume-storage/ "Configure NFS as Kubernetes Persistent Volume Storage")

### [Configure NFS as Kubernetes Persistent Volume Storage](https://computingforgeeks.com/configure-nfs-as-kubernetes-persistent-volume-storage/ "Configure NFS as Kubernetes Persistent Volume Storage")

Modified date: June 8, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "How To Deploy Multi-Node OKD 4 Cluster using Fedora CoreOS")](https://computingforgeeks.com/deploy-multi-node-okd-cluster-using-fedora-coreos/ "How To Deploy Multi-Node OKD 4 Cluster using Fedora CoreOS")

### [How To Deploy Multi-Node OKD 4 Cluster using Fedora CoreOS](https://computingforgeeks.com/deploy-multi-node-okd-cluster-using-fedora-coreos/ "How To Deploy Multi-Node OKD 4 Cluster using Fedora CoreOS")

Modified date: June 19, 2023

var block\_tdi\_13=new tdBlock();block\_tdi\_13.id="tdi\_13";block\_tdi\_13.atts='{"custom\_title":"HOT PICKS","limit":9,"sort":"random","block\_type":"td\_block\_7","separator":"","custom\_url":"","block\_template\_id":"","m6\_tl":"","post\_ids":"-59740","category\_id":"","taxonomies":"","category\_ids":"","in\_all\_terms":"","tag\_slug":"","autors\_id":"","installed\_post\_types":"","include\_cf\_posts":"","exclude\_cf\_posts":"","linked\_posts":"","favourite\_only":"","offset":"","open\_in\_new\_window":"","show\_modified\_date":"","time\_ago":"","time\_ago\_add\_txt":"ago","time\_ago\_txt\_pos":"","el\_class":"","td\_ajax\_filter\_type":"","td\_ajax\_filter\_ids":"","td\_filter\_default\_txt":"All","td\_ajax\_preloading":"","f\_header\_font\_header":"","f\_header\_font\_title":"Block header","f\_header\_font\_settings":"","f\_header\_font\_family":"","f\_header\_font\_size":"","f\_header\_font\_line\_height":"","f\_header\_font\_style":"","f\_header\_font\_weight":"","f\_header\_font\_transform":"","f\_header\_font\_spacing":"","f\_header\_":"","f\_ajax\_font\_title":"Ajax categories","f\_ajax\_font\_settings":"","f\_ajax\_font\_family":"","f\_ajax\_font\_size":"","f\_ajax\_font\_line\_height":"","f\_ajax\_font\_style":"","f\_ajax\_font\_weight":"","f\_ajax\_font\_transform":"","f\_ajax\_font\_spacing":"","f\_ajax\_":"","f\_more\_font\_title":"Load more button","f\_more\_font\_settings":"","f\_more\_font\_family":"","f\_more\_font\_size":"","f\_more\_font\_line\_height":"","f\_more\_font\_style":"","f\_more\_font\_weight":"","f\_more\_font\_transform":"","f\_more\_font\_spacing":"","f\_more\_":"","m6f\_title\_font\_header":"","m6f\_title\_font\_title":"Article title","m6f\_title\_font\_settings":"","m6f\_title\_font\_family":"","m6f\_title\_font\_size":"","m6f\_title\_font\_line\_height":"","m6f\_title\_font\_style":"","m6f\_title\_font\_weight":"","m6f\_title\_font\_transform":"","m6f\_title\_font\_spacing":"","m6f\_title\_":"","m6f\_cat\_font\_title":"Article category tag","m6f\_cat\_font\_settings":"","m6f\_cat\_font\_family":"","m6f\_cat\_font\_size":"","m6f\_cat\_font\_line\_height":"","m6f\_cat\_font\_style":"","m6f\_cat\_font\_weight":"","m6f\_cat\_font\_transform":"","m6f\_cat\_font\_spacing":"","m6f\_cat\_":"","m6f\_meta\_font\_title":"Article meta info","m6f\_meta\_font\_settings":"","m6f\_meta\_font\_family":"","m6f\_meta\_font\_size":"","m6f\_meta\_font\_line\_height":"","m6f\_meta\_font\_style":"","m6f\_meta\_font\_weight":"","m6f\_meta\_font\_transform":"","m6f\_meta\_font\_spacing":"","m6f\_meta\_":"","ajax\_pagination":"","ajax\_pagination\_next\_prev\_swipe":"","ajax\_pagination\_infinite\_stop":"","css":"","tdc\_css":"","td\_column\_number":1,"header\_color":"","color\_preset":"","border\_top":"","class":"tdi\_13","tdc\_css\_class":"tdi\_13","tdc\_css\_class\_style":"tdi\_13\_rand\_style"}';block\_tdi\_13.td\_column\_number="1";block\_tdi\_13.block\_type="td\_block\_7";block\_tdi\_13.post\_count="9";block\_tdi\_13.found\_posts="3237";block\_tdi\_13.header\_color="";block\_tdi\_13.ajax\_pagination\_infinite\_stop="";block\_tdi\_13.max\_num\_pages="360";tdBlocksArray.push(block\_tdi\_13);

#### HOT PICKS

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "10 Cheap Laptops with Intel Core i9 Processor for 2023")](https://computingforgeeks.com/cheap-laptops-with-intel-core-i9-processor/ "10 Cheap Laptops with Intel Core i9 Processor for 2023")

### [10 Cheap Laptops with Intel Core i9 Processor for 2023](https://computingforgeeks.com/cheap-laptops-with-intel-core-i9-processor/ "10 Cheap Laptops with Intel Core i9 Processor for 2023")

Modified date: August 16, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Working with AWS FSx: Instant File System on AWS")](https://computingforgeeks.com/working-with-aws-fsx-instant-file-system-on-aws/ "Working with AWS FSx: Instant File System on AWS")

### [Working with AWS FSx: Instant File System on AWS](https://computingforgeeks.com/working-with-aws-fsx-instant-file-system-on-aws/ "Working with AWS FSx: Instant File System on AWS")

Modified date: August 15, 2023

[![Mattermost Server on Debian 12](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Deploying Mattermost Server on Debian 12 (Bookworm)")](https://computingforgeeks.com/deploying-mattermost-server-on-debian/ "Deploying Mattermost Server on Debian 12 (Bookworm)")

### [Deploying Mattermost Server on Debian 12 (Bookworm)](https://computingforgeeks.com/deploying-mattermost-server-on-debian/ "Deploying Mattermost Server on Debian 12 (Bookworm)")

Modified date: August 16, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Stellar Repair for MySQL: A Powerful Tool for MySQL Database Administrators")](https://computingforgeeks.com/stellar-repair-for-mysql-powerful-tool-for-mysql-database-administrators/ "Stellar Repair for MySQL: A Powerful Tool for MySQL Database Administrators")

### [Stellar Repair for MySQL: A Powerful Tool for MySQL Database Administrators](https://computingforgeeks.com/stellar-repair-for-mysql-powerful-tool-for-mysql-database-administrators/ "Stellar Repair for MySQL: A Powerful Tool for MySQL Database Administrators")

Modified date: August 17, 2023

[![Automated Logical Volume Manager (LVM) Management on Linux using Ansible](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Automated Logical Volume Manager (LVM) Management on Linux using Ansible")](https://computingforgeeks.com/automated-logical-volume-manager-lvm-management-using-ansible/ "Automated Logical Volume Manager (LVM) Management on Linux using Ansible")

### [Automated Logical Volume Manager (LVM) Management on Linux using Ansible](https://computingforgeeks.com/automated-logical-volume-manager-lvm-management-using-ansible/ "Automated Logical Volume Manager (LVM) Management on Linux using Ansible")

Modified date: August 14, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Manage Photon OS from Command Line Interface (CLI)")](https://computingforgeeks.com/manage-photon-os-from-command-line-interface-cli/ "Manage Photon OS from Command Line Interface (CLI)")

### [Manage Photon OS from Command Line Interface (CLI)](https://computingforgeeks.com/manage-photon-os-from-command-line-interface-cli/ "Manage Photon OS from Command Line Interface (CLI)")

Modified date: August 13, 2023

[![Install and Configure Pomerium Proxy for your Services](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Install and Configure Pomerium Proxy for your Services")](https://computingforgeeks.com/install-pomerium-proxy-for-your-services/ "Install and Configure Pomerium Proxy for your Services")

### [Install and Configure Pomerium Proxy for your Services](https://computingforgeeks.com/install-pomerium-proxy-for-your-services/ "Install and Configure Pomerium Proxy for your Services")

Modified date: August 13, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Secure OpenProject with Let’s Encrypt SSL Certificate")](https://computingforgeeks.com/secure-openproject-with-lets-encrypt-ssl-certificate/ "Secure OpenProject with Let’s Encrypt SSL Certificate")

### [Secure OpenProject with Let’s Encrypt SSL Certificate](https://computingforgeeks.com/secure-openproject-with-lets-encrypt-ssl-certificate/ "Secure OpenProject with Let’s Encrypt SSL Certificate")

Modified date: August 11, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "How To Install OpenProject on Debian 12 (Bookworm)")](https://computingforgeeks.com/how-to-install-openproject-on-debian-linux/ "How To Install OpenProject on Debian 12 (Bookworm)")

### [How To Install OpenProject on Debian 12 (Bookworm)](https://computingforgeeks.com/how-to-install-openproject-on-debian-linux/ "How To Install OpenProject on Debian 12 (Bookworm)")

Modified date: August 14, 2023

.td\_block\_popular\_categories{padding-bottom:0}

#### POPULAR CATEGORY

-   [How To2862](https://computingforgeeks.com/category/how-to/)
-   [Linux Tutorials1884](https://computingforgeeks.com/category/linux-tutorials/)
-   [Tech822](https://computingforgeeks.com/category/tech/)
-   [News667](https://computingforgeeks.com/category/news/)
-   [Ubuntu511](https://computingforgeeks.com/category/ubuntu/)
-   [CentOS450](https://computingforgeeks.com/category/centos/)
-   [Tips & Tricks329](https://computingforgeeks.com/category/tips-tricks/)
-   [Dev300](https://computingforgeeks.com/category/dev/)
-   [Debian300](https://computingforgeeks.com/category/debian/)

var block\_tdi\_15=new tdBlock();block\_tdi\_15.id="tdi\_15";block\_tdi\_15.atts='{"custom\_title":"Books","custom\_url":"","block\_template\_id":"","header\_color":"#","header\_text\_color":"#","accent\_text\_color":"#","m6\_tl":"","limit":"5","offset":"","el\_class":"","post\_ids":"-59740","category\_id":"1077","category\_ids":"","tag\_slug":"","autors\_id":"","installed\_post\_types":"","sort":"random\_posts","td\_ajax\_filter\_type":"","td\_ajax\_filter\_ids":"","td\_filter\_default\_txt":"All","td\_ajax\_preloading":"","ajax\_pagination":"","ajax\_pagination\_infinite\_stop":"","class":"td\_block\_widget tdi\_15","block\_type":"td\_block\_7","separator":"","taxonomies":"","in\_all\_terms":"","include\_cf\_posts":"","exclude\_cf\_posts":"","linked\_posts":"","favourite\_only":"","open\_in\_new\_window":"","show\_modified\_date":"","time\_ago":"","time\_ago\_add\_txt":"ago","time\_ago\_txt\_pos":"","f\_header\_font\_header":"","f\_header\_font\_title":"Block header","f\_header\_font\_settings":"","f\_header\_font\_family":"","f\_header\_font\_size":"","f\_header\_font\_line\_height":"","f\_header\_font\_style":"","f\_header\_font\_weight":"","f\_header\_font\_transform":"","f\_header\_font\_spacing":"","f\_header\_":"","f\_ajax\_font\_title":"Ajax categories","f\_ajax\_font\_settings":"","f\_ajax\_font\_family":"","f\_ajax\_font\_size":"","f\_ajax\_font\_line\_height":"","f\_ajax\_font\_style":"","f\_ajax\_font\_weight":"","f\_ajax\_font\_transform":"","f\_ajax\_font\_spacing":"","f\_ajax\_":"","f\_more\_font\_title":"Load more button","f\_more\_font\_settings":"","f\_more\_font\_family":"","f\_more\_font\_size":"","f\_more\_font\_line\_height":"","f\_more\_font\_style":"","f\_more\_font\_weight":"","f\_more\_font\_transform":"","f\_more\_font\_spacing":"","f\_more\_":"","m6f\_title\_font\_header":"","m6f\_title\_font\_title":"Article title","m6f\_title\_font\_settings":"","m6f\_title\_font\_family":"","m6f\_title\_font\_size":"","m6f\_title\_font\_line\_height":"","m6f\_title\_font\_style":"","m6f\_title\_font\_weight":"","m6f\_title\_font\_transform":"","m6f\_title\_font\_spacing":"","m6f\_title\_":"","m6f\_cat\_font\_title":"Article category tag","m6f\_cat\_font\_settings":"","m6f\_cat\_font\_family":"","m6f\_cat\_font\_size":"","m6f\_cat\_font\_line\_height":"","m6f\_cat\_font\_style":"","m6f\_cat\_font\_weight":"","m6f\_cat\_font\_transform":"","m6f\_cat\_font\_spacing":"","m6f\_cat\_":"","m6f\_meta\_font\_title":"Article meta info","m6f\_meta\_font\_settings":"","m6f\_meta\_font\_family":"","m6f\_meta\_font\_size":"","m6f\_meta\_font\_line\_height":"","m6f\_meta\_font\_style":"","m6f\_meta\_font\_weight":"","m6f\_meta\_font\_transform":"","m6f\_meta\_font\_spacing":"","m6f\_meta\_":"","ajax\_pagination\_next\_prev\_swipe":"","css":"","tdc\_css":"","td\_column\_number":1,"color\_preset":"","border\_top":"","tdc\_css\_class":"tdi\_15","tdc\_css\_class\_style":"tdi\_15\_rand\_style"}';block\_tdi\_15.td\_column\_number="1";block\_tdi\_15.block\_type="td\_block\_7";block\_tdi\_15.post\_count="5";block\_tdi\_15.found\_posts="88";block\_tdi\_15.header\_color="#";block\_tdi\_15.ajax\_pagination\_infinite\_stop="";block\_tdi\_15.max\_num\_pages="18";tdBlocksArray.push(block\_tdi\_15);

#### Books

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Best Books To Learn Node.js Programming in 2023")](https://computingforgeeks.com/best-books-to-learn-nodejs-programming/ "Best Books To Learn Node.js Programming in 2023")

### [Best Books To Learn Node.js Programming in 2023](https://computingforgeeks.com/best-books-to-learn-nodejs-programming/ "Best Books To Learn Node.js Programming in 2023")

Modified date: June 13, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Best Books To Learn Tomcat|Jboss|Jetty web servers in 2022")](https://computingforgeeks.com/best-books-to-learn-tomcat-boss-jetty-web-servers/ "Best Books To Learn Tomcat|Jboss|Jetty web servers in 2022")

### [Best Books To Learn Tomcat|Jboss|Jetty web servers in 2022](https://computingforgeeks.com/best-books-to-learn-tomcat-boss-jetty-web-servers/ "Best Books To Learn Tomcat|Jboss|Jetty web servers in 2022")

Modified date: July 20, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Best CCNP R&S Certification Preparation books 2023")](https://computingforgeeks.com/best-ccnp-certification-preparation-books/ "Best CCNP R&S Certification Preparation books 2023")

### [Best CCNP R&S Certification Preparation books 2023](https://computingforgeeks.com/best-ccnp-certification-preparation-books/ "Best CCNP R&S Certification Preparation books 2023")

Modified date: July 20, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "Best Books To Learn Joomla Web Development in 2023")](https://computingforgeeks.com/best-books-to-learn-joomla-web-development/ "Best Books To Learn Joomla Web Development in 2023")

### [Best Books To Learn Joomla Web Development in 2023](https://computingforgeeks.com/best-books-to-learn-joomla-web-development/ "Best Books To Learn Joomla Web Development in 2023")

Modified date: July 20, 2023

[![](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22100%22%20height=%2270%22%3E%3C/svg%3E "SSH Mastery – Best Book to Master OpenSSH, PuTTY, Tunnels")](https://computingforgeeks.com/best-book-to-master-openssh-putty-tunnels/ "SSH Mastery – Best Book to Master OpenSSH, PuTTY, Tunnels")

### [SSH Mastery – Best Book to Master OpenSSH, PuTTY, Tunnels](https://computingforgeeks.com/best-book-to-master-openssh-putty-tunnels/ "SSH Mastery – Best Book to Master OpenSSH, PuTTY, Tunnels")

Modified date: July 20, 2023

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[250,250\],"computingforgeeks\_com-medrectangle-1","ezslot\_31",280,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-medrectangle-1-0");[![Ezoic](https://go.ezodn.com/utilcave_com/img/ezoic.png)](https://www.ezoic.com/what-is-ezoic/)report this ad

[![ComputingForGeeks](data:image/svg+xml,%3Csvg%20xmlns=%22http://www.w3.org/2000/svg%22%20width=%22272%22%20height=%2290%22%3E%3C/svg%3E "ComputingForGeeks")](https://computingforgeeks.com/)

ABOUT US

ComputingForGeeks is a technology blog covering Linux/Windows/Unix server configurations, networking, Cloud, Container solutions, Security systems, Virtualization, Automation, DevOps, Development guides and trending stuff in Technology.

Contact us: [computingforgeeks@gmail.com](mailto: computingforgeeks@gmail.com)

FOLLOW US

[Facebook](https://www.facebook.com/cloudspinx "Facebook") [GitHub](https://github.com/cloudspinx "GitHub") [Linkedin](https://ke.linkedin.com/in/mutai-josphat-37bb08bb "Linkedin") [Skype](https://join.skype.com/invite/LXvZG1u2bU50 "Skype") [Twitter](https://twitter.com/cloud_spinx "Twitter")

-   [CentOS](https://computingforgeeks.com/category/centos/)
-   [Ubuntu](https://computingforgeeks.com/category/ubuntu/)
-   [Fedora](https://computingforgeeks.com/category/fedora/)
-   [Debian](https://computingforgeeks.com/category/debian/)
-   [Rocky](https://computingforgeeks.com/category/rocky-linux/)
-   [FreeBSD](https://computingforgeeks.com/category/freebsd/)
-   [Openstack](https://computingforgeeks.com/category/openstack/)
-   [Windows](https://computingforgeeks.com/category/windows/)
-   [About Us](https://computingforgeeks.com/about-us/)
-   [Contact us](https://computingforgeeks.com/contact-us/)
-   [Terms](https://computingforgeeks.com/terms-of-service/)
-   [Affiliates Disclosure](https://computingforgeeks.com/affiliate-links-disclosure/)

© 2014-2022 - ComputingforGeeks - Home for \*NIX Enthusiasts

pre{background-color:#051e30;color:#fff;padding:4px 10px;border:none;border-radius:0;margin-top:24px;white-space:pre;word-wrap:break-word;border-top:#289ff4 1px solid;border-right:#289ff4 1px solid;border-bottom:#289ff4 1px solid;border-left:#289ff4 4px solid}code{background-color:#051e30;color:#fff;position:relative;top:-1px;border:none;padding:0 0 6px}.wp-block-code code{white-space:inherit}::-webkit-scrollbar{height:4px}::-webkit-scrollbar-thumb{background:#ababab;border-radius:14px}::-webkit-scrollbar-thumb:hover{background:#cacaca}var tds\_js\_globals={"wpRestNonce":"a5634af86f","wpRestUrl":"https:\\/\\/computingforgeeks.com\\/wp-json\\/","permalinkStructure":"\\/%postname%\\/"};var td\_res\_context\_registered\_atts=\["style\_general\_popular\_categories"\];ezoicSiteSpeed(jQuery(),String(/documentReady/).substring(1).slice(0,-1),String(/jQuery-document-dot-ready/).substring(1).slice(0,-1),function jQuery\_ready(){tdAjaxCount.tdGetViewsCountsAjax("post","\[59740\]");});

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[728,90\],"computingforgeeks\_com-medrectangle-2","ezslot\_4",100,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-medrectangle-2-0");

x

if(typeof ez\_ad\_units != "undefined"){ez\_ad\_units.push(\[\[160,600\],"computingforgeeks\_com-edge-1","ezslot\_1",174,"0","0"\])};\_\_ez\_fad\_position("div-gpt-ad-computingforgeeks\_com-edge-1-0");

x
