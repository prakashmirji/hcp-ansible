## hcp-ansible

### Introduction
This repo hosts the ansible playbooks to deploy and configure HPE Container Platform

Note: This repo has basic framework to get started, we will be adding more functionality as we move forward

### Use cases
  - I as a user wants to prepare the environment ( OS installation with right packages )
  - I as a user wants have option to run pre-checks before I start installing the bits
  - I as a user wants to install/deploy HPE container platform bits with playbooks ( configure controller and gateway )
  
          - with HPE best practices
          - with consistent behavior
  - I as a k8s admin user wants to create k8s cluster
  - I as a k8s admin user wants do life cycle management (LCM) operations on my k8s cluster
  
          - create cluster
          - delete cluster
          - update cluster
          - add/remove hosts
  - I as a user wants to build my environment with desired state
  - I as a user wants to automate the provision and decommission of the HPE container platform with playbooks
  - I as a system admin wants to update the hosts/nodes and configure them consistently

### Pre-reqs
        - Linux machine with ansible 2.9.x and python3.8.2
        - 5 nodes with centos 7.6 or up
### How to setup your development env

### How to test
```
rename group_vars/all/vars.sample to group_vars/all/vars.yml
update the values in vars.yml
then run below command
ansible-playbooks -i hosts site.yml
or
ansible-playbooks -i hosts playbooks/prepare.yml
```

### Troubleshooting

### Know issues


### Contributions



