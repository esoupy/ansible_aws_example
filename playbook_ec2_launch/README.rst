playbook_ec2_launch
===================

Template to create new ec2 instances within a VPC and apply a common role

Required Existing Setup and Info
--------------------------------
- AWS VPC created
- AWS Region
- VPC subnets and a target subnet ID
- routes created with Internet access (IGW or NAT)
- security groups create and group ID(s)
- EC2 keypair generated and name

The host running the ansible playbook must ssh access to instances in the target VPC subnet.
After EC2 instances are created within a VPC, the ansible playbook server will then apply any
roles and tasks over ssh.

Flow
----
1. Ansible Host  --->  use boto locally to create AWS instances
2. Ansible Host  --->  connect to newly created AWS instances over Private IP
3. Ansible Host  --->  apply role tasks to new AWS instances over ssh


Setup
-----
Update the vars/aws_vars.yml file with the correct AWS resource IDs

Launch a single ec2 instance:
::
    ansible-playbook -i hosts play_ec2_launch.yml


To Launch more than 1 at a time, you can specify the count from the CLI
::
    ansible-playbook -i hosts play_ec2_launch.yml --extra-vars="count=5"


