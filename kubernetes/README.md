See [here](https://biscuit.ninja/posts/creating-a-kubernetes-cluster-using-keepalived-and-haproxy-with-ansible/) for an accompanying write up.


change vars value in env_variables
change host in hosts file in

Note:
- check default network interface of nodes before run install (must be interface of node ip)
- run version k8s , network version follow document which was be tested
- check firewall if any port can't access

for i in $(seq 1 2);do ssh-copy-id -f -i ~/.ssh/id_rsa.pub vagrant@192.168.88.18${i};done

for i in $(seq 1 2);do ssh-copy-id -f -i ~/.ssh/id_rsa.pub vagrant@192.168.88.19${i};done