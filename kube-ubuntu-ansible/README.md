# ANSIBLE
## kube-ansible is to install and configure kubernetes with ansible

Ansible communicates with Linux target hosts via SSH. Rather than having to specify credentials each time, we can set up SSH key authentication.

To do so, generate a key on the Ansible machine by running:

```console
ssh-keygen
```

This will generate a new public/private rsa key pair:

```console
Generating public/private rsa key pair.
Enter file in which to save the key (/home/user/.ssh/id_rsa):
```

We then need to add the public key to the target host’s ~/.ssh/authorized_keys file. You can simply display (e.g. # cat id_rsa.pub) the public key on the Ansible machine then paste it into the authorized_keys file on the target

You can use:

```console
ssh-copy-id -i ~/.ssh/mykey user@host
```

Refer: [click for more](https://www.digitalocean.com/community/tutorials/how-to-configure-ssh-key-based-authentication-on-a-linux-server)

## Setting up Ansible to Deploy Kubernetes

```sh
git clone
```

change hosts file, to tell Ansible how to communicate with the Kubernetes master and worker nodes.

```text
[masters]
master ansible_host=192.168.88.180 ansible_user=vagrant

[workers]
worker1 ansible_host=192.168.88.181 ansible_user=vagrant
worker2 ansible_host=192.168.88.182 ansible_user=vagrant
```

Finally, with that done, we can test it’s working by doing a Ansible ping:

```bash
$ ansible -i hosts all -m ping
master | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
worker2 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
worker1 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

Setting some variables (env_variables)

```env
kube_user: kube
adv_ip: 192.168.88.180
```

We’re now ready to run our first playbook. To do so:

```sh
ansible-playbook -i hosts setup_node_common.yml
ansible-playbook -i hosts setup_node_master.yml
ansible-playbook -i hosts setup_node_worker.yml
```

copy admin.conf in $HOME/.kube on master node to localmachine and run

```sh
export KUBECONFIG=.../config/config-dev
```
