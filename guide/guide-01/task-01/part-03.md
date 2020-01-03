## INSTALL FOR ONLY MASTER NODE


1. Switch to the root user

```
sudo su -
```

2. # Initialize Kuberates master by executing below commond

```
kubeadm init
```

3. Exit root user & exeucte as normal user

```
exit
```

4. Make kube config

```
mkdir -p $HOME/ .kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/ .kube/config
```

5. to verify, if kubectl is working or not, run the following command

```
kubectl get pods -o wide --all-namespaces
```

6. install the weave pod network, run the following command:

```
kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"
kubectl get nodes
kubectl get pods --all-namespaces
```

7. Get token

```
kubeadm token create --print-join-command
```

