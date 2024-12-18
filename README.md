# Retrospective
## :thinking: Problem Statement
#### Zombie Hosts in Ansible Inventories
- #### Current State
    - Currently EC2 hosts being registered into Ansible Inventories
        aren't being removed once EC2 has been terminated. This has 
        been causing issues with App deployments as well as EC2 
        Configuration.

- #### Pain Points
    - Teams are having to go through Inventories manually to remove
        any host that are no longer reachable. 
    - Delays in App development, App deployment
        and misconfigurations on some host.

## :mag_right: Solution Overview
- #### Proposed Architecture
    - Use AWS EventBridge and create an Event Rule that
        will trigger every time an EC2 is terminated.
    - Forward that event to a Custom Event Bus in a Hub Account,
        which will trigger a Lambda Function and call the Tower API
        to Trigger Clean up workflow.
- #### How it Solves the Problem
    - Frees up teams from having to manually maintain Ansible Inventories.
    - Workflow will go through Ansible Inventories and remove 
        that what would be Zombie Host.
    - Provides High Availability and will scale as the 
        organization grows and expands its AWS Account footprint.
    - Cost-effective, only triggering as needed.


![alt text](assets/TowerJob.png "Logo Title Text 1")
