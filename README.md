# k8s-vagrant-ansible
The porject provides necessary vagrant and ansible scripts to set up a simple Kubernetes cluster on one machine. The cluster has 3 nodes running as VirtualBox instances - one master and two workers. It is useful for testing purposes specially for the cases where more than one node is required.

The code is mainly taken from this article: https://kubernetes.io/blog/2019/03/15/kubernetes-setup-using-ansible-and-vagrant/ hovewer some corrections were also made.

Prerequisites for running the cluster
1. Oracle VirtualBox
2. Ansible
3. Vagrant

To start cluster use the following command:
```
      vagrant up
```      
After cluster is started use this command to ssh to master node:
```
      vagrant ssh k8s-master
```
On master use kubectl utility to manage kubernetes containers. E.g. using command like this:
```
      kubectl get pods -o wide --all-namespaces
```      
It dumps all running containers with their node and IP information.

To completely remove the cluster use:
```
      vagrant destroy -f
```      
