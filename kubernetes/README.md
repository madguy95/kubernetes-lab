See [here](https://biscuit.ninja/posts/creating-a-kubernetes-cluster-using-keepalived-and-haproxy-with-ansible/) for an accompanying write up.

for i in $(seq 1 2);do ssh-copy-id -f -i ~/.ssh/id_rsa.pub vagrant@192.168.88.18${i};done

for i in $(seq 1 2);do ssh-copy-id -f -i ~/.ssh/id_rsa.pub vagrant@192.168.88.19${i};done