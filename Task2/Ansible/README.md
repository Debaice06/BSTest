**# Ansible Playbook Conf for Kubernetes using Ansbible Roles**

**First install ansible into control server**

**Configure password less communication in master nodes and worker nodes**

**From Master server run**

>  ssh-keygen
copy the content *id_rsa.pub* from ~/.ssh/
Go To the worker node and run *ssh-keygen*.
after that paste the content of public key of master server in worker nodes.
Go to ~/.ssh/ and create *authorized_keys* and paste there the contents.

Last time need to give password and after that it will be password less ssh login.

**Ansible conf and Playbook:** **Please go to *hosts* file from /etc/ansible & add the master and worker node in like below:**

> [kubernetes-master-nodes]

> 192.168.56.110

> [kubernetes-worker-nodes]

> 192.168.56.111

> 192.168.56.112

**Please check after adding if all nodes could be login by ansisble through below commands:**
> ansible -m ping all
it will give you success message

Now Run below ymls to configure Cluster:

**Before that you could check if your syntax is OK or not**
> ansible-playbook Kubernetes_Master.yml --syntax-check

> ansible-playbook Kubernetes_Worker.yml --syntax-check

**Run below yml for Installing Kubernetes into Master Server:**
> ansible-playbook Kubernetes_Master.yml

*It will installed each and everything including prerequisites,host file add, configure master, installing dashboard & metric server, service account creation etc.*


**After getting the master node ready need to prepare the Worker node:**
> ansible-playbook Kubernetes_Worker.yml

*It will installed each and everything including prerequisites,host file add, configure worker etc.*


