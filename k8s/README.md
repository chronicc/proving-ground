kubernetes
==========

Fully automated kubernetes cluster setup with 2 nodes - a control plane node and a worker node.

## Getting Started

1. Run `vagrant up`
2. Wait until vagrant has finished the provisioning phase.
3. Talk with the cluster by using the provided `admin.conf`.
    ```
    kubectl --kubeconfig admin.conf get nodes
    ```
