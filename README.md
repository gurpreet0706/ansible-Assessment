# ansible-Assessment


1. Python 3
2. boto3 -- pip3 install boto3
3. ansible
4. Clone the anisble-assessment in /opt directory
5.  Open /etc/ansible/ansible.cfg file
    Find the [inventory] section and add the following line to enable the ec2 plugin.

        enable_plugins = aws_ec2

   It should look something like this.

     [inventory]
      enable_plugins = aws_ec2


6. Test the dynamic inventory configuration by listing the ec2 instances.

   ansible-inventory -i /opt/ansible-Assessment/inventory/aws_ec2.yaml --list 

7. If you want to use the dynamic inventory as a default Ansible inventory, edit the /etc/ansible/ansible.cfg file and search for inventory parameters under defaults. Change the inventory parameter value as shown below.

inventory      = /opt/ansible-Assessment/inventory/aws_ec2.yaml

8.  Use the following command to check the connectivity to ec2 instances

ansible all -m ping

9. run anisble playbook dockerapp.yaml to configure the ec2 instances with docker engine and run docker app.
