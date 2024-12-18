# Retrospective
## :thinking: Problem Statement
### Zombie Host in Ansible Inventories
- #### Current 
- Currently EC2 hosts being registered into Ansible Inventories
    aren't being removed once EC2 has been terminated. This has 
    been causing issues with App deployments as well as EC2 
    Configuration.

- #### Pain Points
    - Teams are having to go through Inventories manually to remove
        any host that are no longer reachable. 
    - Delays in App development
        and misconfigurations on some host.

## :mag_right: Solution Overview


![alt text](assets/TowerJob.png "Logo Title Text 1")
