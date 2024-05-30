# IP3 Project
 
## Using Docker compose
To run the project using docker compose follow the instructions detailed in the [README](https://github.com/mzazakeith/yolo/blob/master/README.md).

## Ansible
To run the containerized app through playbooks follow the following steps

### Steps

1. Create the required files and directory
    * `ansible.cfg`
    * `Vagrantfile`
    * `hosts`
    * `playbook.yml`
    * `vars`
   
2. Initialize roles using ansible galaxy
    ```
    ansible-galaxy init <roleName>
    ```
   You will need to create 3 roles:
   1. `git_install` - Installs Git 
   2. `docker_install` - Installs Docker and Docker Compose 
   3. `docker_run` - Starts the project using Docker Compose

3. Running the Playbook with Vagrant

   - Start the Vagrant Environment:
   ```
   vagrant up
   ```
   - This command will bring up the Vagrant environment and automatically provision it according to the settings in your Vagrantfile.

   - Provision the Vagrant Environment (if needed):
     ```
     vagrant provision
     ```
   - Use this command to re-run the provisioning process if the Vagrant environment is already up and you need to apply changes made to the provisioning scripts or playbook.

4. After the play runs to completion, you can access the project through [http://localhost:3000](http://localhost:3000)
   This is made possible by the forwarded ports added in Vagrantfile

---
