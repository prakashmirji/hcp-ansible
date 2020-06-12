## hcp-ansible

### Introduction
This repo hosts the ansible playbooks to deploy and configure HPE Container Platform

### Use cases ( mvp 1.0 )
  - I as a user wants to prepare the environment ( OS installation with right packages )
  - I as a user wants to have option to run pre-checks before I start installing the bits
  - I as a user wants to install/deploy HPE container platform bits with playbooks ( configure controller and gateway )

          - with HPE best practices
          - with consistent behavior
  - I as a k8s admin user wants to add and install k8s hosts
  - I as a k8s admin user wants do life cycle management (LCM) operations on my k8s cluster
  
          - create cluster
          - delete cluster
          - update cluster
          - add/remove hosts
  - I as a user wants to automate the LCM of the HPE container platform with playbooks
  - I as a k8s admin wants to create and manage tenants

### Pre-reqs
        - Linux machine with ansible 2.9.x and python3.8.2
        - 5 nodes with centos 7.6 or up or RHEL
        - epicctl tool
### How to setup your development env
        - TODO
### How to test
        - rename group_vars/all/vars.sample to group_vars/all/vars.yml
        - update the values in vars.yml as per your environment
        - update hosts inventory file
        - then run below command ( note: you may edit site.yml before running playbooks)
        ```
        ansible-playbooks -i hosts site.yml
        or
        ansible-playbooks -i hosts playbooks/controller.yml
        ```
### Current staus

Following playbooks are working:

        - import_playbook: playbooks/pre-checks-hcp.yml
        - import_playbook: playbooks/prepare.yml
        - import_playbook: playbooks/uninstall-bds.yml
        - import_playbook: playbooks/controller.yml
        - import_playbook: playbooks/gateway.yml
        - import_playbook: playbooks/k8s-hosts.yml
        - import_playbook: playbooks/k8s-cluster-lcm.yml
        - import_playbook: playbooks/k8s-cluster-delete.yml

### Troubleshooting
        TODO
### Know issues
        TODO

### Contributions



