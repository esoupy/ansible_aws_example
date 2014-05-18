ANSIBLE AWS PRIMER
==================

A collection of ansible playbook samples for AWS related tasks.

Requirements
------------
- Ansible 1.6+
- Boto 2.28+
- AWS account with the proper permissions
- AWS_ACCESS_KEY_ID & AWS_SECRET_ACCESS_KEY exported or ~/.boto config created

To install
----------
It is recommended to install in a virtualenv
::
    pip install boto
    pip install ansible


playbook_ec2_launch
-------------------
Template to create new ec2 instances within a VPC and apply a common role




