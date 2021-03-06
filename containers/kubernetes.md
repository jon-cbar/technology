# [Technology How To](/readme.md)

## Containers

### [Kubernetes](/containers/kubernetes.md)

> Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications [1].

#### Installing a Kubernetes cluster

##### Swap

First of all, to run Kubernetes on Ubuntu, it is necessary to disable `Swap`.
To avoid `Swap` be loaded again when restarting the server, then disable (comment) it in `/etc/fstab` too.

```sh
sudo swapoff -a
```

##### Docker

So, we need a container runtime.
If you don't have one, I suggest install Docker to start.
I'm on Ubuntu.

```sh
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
docker --version
```

##### Kubernetes Commands

Let's add three Kubernetes commands: `kubeadm`, `kubectl` and `kubelet`.

```sh
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb http://apt.kubernetes.io/ kubernetes-xenial main" > sudo /etc/apt/sources.list.d/kubernetes.list
```

#### References

[1] [Kubernetes website](https://kubernetes.io/)
