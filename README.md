I have installed Ansible on one server A using the below cmd.
yum install ansible -y
Then I created /etc/ansible/ansible_data directory
mkdir /etc/ansible/ansible_data
Inside that directory, I have created an inventory file as ip and given permission as chmod 755
Then I created another server B where I wanted to install Grafana and Prometheus.
So for connecting the two servers I have used ssh-keygen on server A and copied id_rsa.pub in server B .ssh/authrized_keys
Now we have the connectivity from server A to B.
I have created the playbook and inserted all the required commands in the 

