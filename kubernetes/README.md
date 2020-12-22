kubernetes
==========

Getting started
---------------

1. `vagrant up --no-parallel`
1. `kubeadm init` on kube1.vagrant
1. `kubeadm join ...` on kube2.vagrant
1. `kubeadm join ...` on kube3.vagrant
1. `kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"` on kube1.vagrant
1. `kubectl get nodes` on kube1.vagrant
1. `git clone https://github.com/microservices-demo/microservices-demo` on kube1.vagrant
1. `kubectl apply -f microservices-demo/deploy/kubernetes/manifests` on kube1.vagrant
1. `kubectl get pods` on kube1.vagrant

