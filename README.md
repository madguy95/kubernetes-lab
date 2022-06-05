# kubernetes-lab

# ISSUES

There are few things that might help:

Check the config file in ~/.kube/config

kubectl config view
Is current-context set to: microk8s?

Try to use:

kubectl config get-contexts

kubectl config set-context

kubectl config use-context

Check if you are refering to the config from ~/.kube/config and not your own private config from somewhere else.

Check if you have a KUBECONFIG environment variable (echo $KUBECONFIG)

- https://digitalvarys.com/install-kubernetes-cluster-with-kubeadm-and-ansible-ubuntu/
- https://www.arubacloud.com/tutorial/how-to-create-kubernetes-cluster-with-kubeadm-and-ansible-ubuntu-20-04.aspx


## Testing

DNS https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/
    https://kubernetes.io/docs/tasks/debug/debug-application/debug-service/

/etc/resolv.conf https://github.com/coredns/coredns/blob/master/plugin/loop/README.md#troubleshooting-loops-in-kubernetes-clusters

Íntallation https://kubernetes.io/blog/2019/03/15/kubernetes-setup-using-ansible-and-vagrant/
    https://github.com/boeboe/k8s-calico-vagrant/blob/master/k8s-ansible/master-playbook.yml
    https://github.com/kelseyhightower/kubernetes-the-hard-way
    https://gitlab.com/biscuit.ninja/ansibleExamples/-/tree/main/kubernetes/roles/k8sControlPlane
    https://www.linuxsysadmins.com/install-kubernetes-cluster-with-ansible/

kubectl set env daemonset/calico-node -n kube-system IP_AUTODETECTION_METHOD=interface=eth1
kubectl rollout restart -n kube-system deployment/coredns