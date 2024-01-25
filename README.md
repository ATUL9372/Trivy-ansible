# Trivy-Ansible 

This repository provides a solution for automating the vulnerability scanning of Docker images using Trivy. Instead of manually scanning images on individual servers, this Ansible-based solution allows you to seamlessly scan Docker images across multiple servers, consolidating the reports on your localhost for comprehensive analysis.

## Instructions

1. Install [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-ubuntu)

2. Install [vscode (optional)](https://code.visualstudio.com/download)
   
3. Install python3 python3-pip

         sudo apt install python3 python3-pip

4. Install sshpass

         sudo apt install sshpass


5. Modify/Add host IPs to `hosts` and configure the variables. Eg.

         [test]
         192.168.xx.xx
         13.57.xx.xx
         
         [test:vars]
         
         ansible_connection=ssh
         ansible_ssh_user=ENTER-USER-NAME
         ansible_ssh_pass=ENTER-PASSWORD


6. Run ansible playbook


         ansible-playbook -i hosts trivy_automation.yml 


7. Run ansible playbook with sudo password use -k and -K Eg.

         
         ansible-playbook -i hosts trivy_automation.yml -k
         
         ansible-playbook -i hosts trivy_automation.yml -K

