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

# IP 4 

## Orchestration with Kubernetes

1. We begin by creating our `manifests` directory
2. We create the needed manifest files placing them in their specific directories 

> `config-maps` <br>
> `deployments` <br>
> `persistent-volumes` <br>
> `services` <br>
> `stateful-sets` <br>

- We populate the files as needed. You can use mine for guidance [manifests](https://github.com/mzazakeith/yolo/tree/master/manifests).

3. We then clone our repo in the Google cloud shell

```bash
git clone https://github.com/mzazakeith/yolo
```

4. Now ensure that you have enabled billing and the container api so that you can create clusters.

5. Create a new cluster with the following command

```bash
   gcloud container clusters create-auto yolo --region us-central1
```
6. Apply your manifest files. Remember to `cd` into the correct directories or reference the directories correctly in your commands 
```bash
kubectl apply -f mongo-config.yaml
kubectl apply -f backend-config.yaml

kubectl apply -f pvc.yaml
kubectl apply -f mongo-stateful-set.yaml

kubectl apply -f backend-deployment.yaml
kubectl apply -f client-deployment.yaml

kubectl apply -f mongo-service.yaml
kubectl apply -f backend-service.yaml
kubectl apply -f client-service.yaml

```
7. Run the following command to check if the deployments were successful
```bash
kubectl get pods
```
8. Use the following [link](https://34.71.139.167:3000/) to access our deployed application
```
[https://34.71.139.167:3000/](http://34.170.6.187:3000/)
```

![](/Users/mzaza/Documents/Practice Projects/yolo/running.png)
