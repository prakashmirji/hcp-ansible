## hcp-ansible

### Introduction
This repo hosts the ansible playbooks to deploy and configure HPE Container Platform ( HPE CP)

### Use cases in mvp 1.0
  - I as a user wants to prepare the environment ( OS installation with right packages )
  - I as a user wants to have option to run pre-checks before I start installing the bits
  - I as a user wants to install/deploy HPE CP management software

          - controller node
          - gateway node
  - I as a k8s admin user wants to add and install k8s hosts
  - I as a k8s admin user wants do life cycle management (LCM) operations on my k8s cluster
  
          - create cluster
          - delete cluster
          - update cluster
          - add/remove hosts
  - I as a k8s admin wants to create and manage tenants
  - manage user roles
  - I as a MLOps user wants to add and install worker nodes
  
### Use cases in mvp 2.0
        TODO

### Pre-reqs
- Linux machine with ansible 2.9.x and python3.8.2 ( tested with these versions but might work with other versions too)
- minimun 5 nodes with centos 7.6 or up or RHEL ( not tested on SLES) ( nodes can be VMs or baremetal, see product spec for sizing)
- Following tools are downloaded by playbooks and placed under /usr/local/bin
        - epicctl
        - kubectl
        - kubectl-hpecp plugin
        - jq
- HPE CP bundle ( tested with pulling it from s3 bucket)

### How to setup your development env
        - Any linux machine line centos 7.6 with ansible 2.9.x and python3 ( tested with 3.8.2)
### How to test
        - rename group_vars/all/vars.sample to group_vars/all/vars.yml
        - update the values in vars.yml as per your environment
        - update hosts inventory file
        - then run below command ( note: you may edit site.yml before running playbooks)

        
        >ansible-playbooks -i hosts site.yml
        or
        >ansible-playbooks -i hosts playbooks/controller.yml
        
### Current staus

Following playbooks are working:

        - import_playbook: playbooks/prepare.yml
        - import_playbook: playbooks/uninstall-bds.yml
        - import_playbool: playbooks/download-tools.yml
        - import_playbook: playbooks/controller.yml
        - import_playbook: playbooks/gateway.yml
        - import_playbook: playbooks/k8s-hosts.yml
        - import_playbook: playbooks/k8s-cluster.yml
        - import_playbook: playbooks/k8s-tenant.yml
        - import_playbook: playbooks/epic-worker.yml

If you starting first time, you can start from download-tools.yml

### Troubleshooting
Following places can be looked at for the errors
[1] Too look for logs of epicctl : ~/.epicctl{{name}}
[2] Too look for platform logs /var/log/bluedata

If you are hitting this[1] k8s broken link issue, please run [2] before you start creatig  k8s cluster
[1]https://github.com/kubernetes/kubernetes/issues/92242

[2]ansible-playbook -i hosts playbooks/bug_fixes.yml

### Know issues
        TODO

### Contributions



