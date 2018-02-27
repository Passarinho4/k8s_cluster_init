# k8s_cluster_init

This is my first serious try with automating setup of Kubernetes cluster. 

I assume that before launching anything you prepare proper machine. In my example it was virtual machine with 196GB RAM
and 32 cores. I decided to create 10 vms (using Vagrant) 16GB RAM and 2 cores per vm. Vagrantfile creates 1 master vm and 9 
workers. Then you need to run Ansible file which is located in ansible folder and configure K8s cluster. 
Unfortunatelly instalation is not easy and contains some hacks, but in the end you should get ready to use Kubernetes cluster 
with single master and 9 workers. 

vagrant/vagrant up
ansible/ansible-playbook -i hosts playbook.yml
ssh vagrant@192.168.77.10
kubectl get nodes - should display 10 Ready nodes.
NAME      STATUS    ROLES     AGE       VERSION
master    Ready     master    1m        v1.9.3
worker1   Ready     <none>    37s       v1.9.3
worker2   Ready     <none>    37s       v1.9.3
worker3   Ready     <none>    36s       v1.9.3
worker4   Ready     <none>    39s       v1.9.3
worker5   Ready     <none>    35s       v1.9.3
worker6   Ready     <none>    35s       v1.9.3
worker7   Ready     <none>    35s       v1.9.3
worker8   Ready     <none>    35s       v1.9.3
worker9   Ready     <none>    34s       v1.9.3

