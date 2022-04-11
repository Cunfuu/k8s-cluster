# k8s-cluster
# most of the stuff here is WIP please post your issues maybe try to contact me :3 


spin up three node cluster with two different ips one is for nat the other is k8 connectinos (WIP)

* 192.168.33.11 -192.168.33.12 master
* 192.168.33.13 -192.168.33.14 worker-1
* 192.168.33.15 192.168.33.16 worker-2

see the corresponding post from [here](https://baykara.medium.com/setup-own-kubernetes-cluster-via-virtualbox-99a82605bfcc)

* requirements
```
vagrant
virtualbox
```

Fire up vms
``` 
vagrant up
```
To access each machine respectively via 
```
vagrant ssh master
```
in master node

```
1. set root password
2. switch root account
3. kubeadm init --apiserver-advertise-address 192.168.33.13 --pod-network-cidr=10.244.0.0/16
4. remove --port 0 from /etc/kubernetes/manifests/kube-[controller-api| scheduler].yaml
5. join workers to master node
```
for workers
```
vagrant ssh [worker1|worker2]
```
