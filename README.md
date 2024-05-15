## SRE homework

This readme is applicable to **Linux Mint 21 or Ubuntu** and will provide all the information required for using the files located in this particular folder

### Steps to prepare and run:
Since Mint 21 already has Python 3 preinstalled, no additional actions required here

1. Install docker carefully following the instructions from [here](https://www.linuxtechi.com/how-to-install-docker-on-linux-mint/)
2. Install ansible by ```sudo apt-get install ansible```
3. Install ansible-lint by ```pip3 install ansible-lint```
4. This step is ***optional*** however it's much better to have it:
    * Install VSCode
        * Install Red Hat Ansible Extension
    * Add homework folder to VSCode workspace and allow VSCode to detect all the installations and create the new Python venv
5. In VSCode, open new terminal 
6. In order to set **docker-compose** logging rotation:
    * ```ls /etc/docker/```
        * ***If*** the output has no **daemon.json** listed:
            * ```sudo cp daemon.json /etc/docker/```
7. Run ```docker compose up -d``` and wait until all services are up and running. Kibana dashboard should be accessible after that on ***localhost:5601***
8. In order to verify the validity of ***.yml*** files, run: ```ansible-lint``` and it should give no errors or warnings
9. Run ```ansible-playbook playbook-create-space.yml```
    * After that open ***localhost:5601*** and verify that ***new***
    Kibana space has been created
10. Run ```ansible-playbook playbook-delete-space.yml```
    * After that open ***localhost:5601*** and verify that ***new*** Kibana space has been deleted
11. To stop the docker containers run ```docker-compose down --remove-orphans```