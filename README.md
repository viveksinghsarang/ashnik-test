I have installed Ansible on one server A using the below cmd.  
yum install ansible -y  
Then I created /etc/ansible/ansible_data directory  
mkdir /etc/ansible/ansible_data  
Inside that directory, I have created an inventory file as ip and given permission as chmod 755  
Then I created another server B where I wanted to install Grafana and Prometheus.  
So for connecting the two servers I have used ssh-keygen on server A and copied id_rsa.pub in server B .ssh/authrized_keys  
Now we have the connectivity from server A to B.  
I have created the playbook and inserted all the required commands in the deploy_Prom_and_Grafana.yml file.  
For the configurations of Grafana and Prometheus, we have to create two files grafana.ini.j2 and prometheus.yml.j2 that will be copied from server A to B.  
The playbook will also create a systemd file for Prometheus, so it will copy the file prometheus.service.j2.  
To run the playbook we will use the below cmd  
ansible-playbook -i ip deploy_Prom_and_Grafana.yml  
On server B to send vm matric to Prometheus I have installed Node exporter and created a systemd file for it.  
For creating the dashboard we can import pre-created dashboards from the grafana.com.  
Either we can import dashboards as a JSON or we can provide a dashboard ID in the Grafana console.  
For monitoring the application we can use black-box exporter.


