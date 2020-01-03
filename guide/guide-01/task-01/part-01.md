## INSTALL FOR MASTER & WORKER NODE


1. Change Root user form common user

```
sudo su -
```

2. Install Required packages and apt keys

```
sudo apt-get update && sudo apt-get install -y apt-transport-https
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
```

3. Turn Off Swap Space

```
swapoff -a
sed -i '/ swap / s/^\(.*\)$/#\1/g' /etc/fstab
```

4. Install And Enable Docker

```
apt install docker.io -y
usermod -aG docker ubuntu
systemctl restart docker
systemctl enable docker.service
```

5. Install kubeadm, Kubelet And Kubectl

```
apt-get install -y kubelet kubeadm kubectl kubernetes-cni
```

6. Enable and start kubelet service

```
systemctl daemon-reload
systemctl start kubelet
systemctl enable kubelet.service
```

