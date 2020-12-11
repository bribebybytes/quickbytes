```bash
# install docker
https://docs.docker.com/engine/install/debian/


# install kind
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.9.0/kind-linux-amd64
chmod +x ./kind
mv ./kind /usr/local/bin

narayanan_kmu@bribebybytes:~/e003$ kind version
kind v0.9.0 go1.15.2 linux/amd64



git clone https://github.com/bribebybytes/quickbytes.git
cd freaky_fridays/e003

# Delete if already there
# kind delete cluster --name ff-e003-affinity-airplane

kind create cluster --name=ff-e003-affinity-airplane --config airplane-config.yaml 
kubectl label nodes ff-e003-affinity-airplane-worker class=business color=orange
kubectl label nodes ff-e003-affinity-airplane-worker2 class=business color=orange
kubectl label nodes ff-e003-affinity-airplane-worker3 class=economy color=blue exitdoors=present
kubectl label nodes ff-e003-affinity-airplane-worker4 class=economy color=blue 
```
If you like to preview your cluster in light weight tool use this. (This is my custom version of [k8bit](https://github.com/learnk8s/k8bit) with ordering of nodes and coloring of kube-system vs default namespace pods.)

```
cd bribebybytes/prod-grade-k8s/helper/k8bit
kubectl proxy --www=.
```