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