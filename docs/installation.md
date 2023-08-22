# NMS Installation<br>

### Remote Terminal Access<br>
`1.` Navigate to ubuntu, click on access vscode app via Ubuntu -> vscode<br>
<img width="400" alt="Access to vscode" src="https://github.com/donchai/nginx-103/assets/6828772/348600fe-e57d-4f76-83ed-4e1e8bb0903d"><br>

`2.` Launch a new terminal in vscode<br>
<img width="400" alt="Launch new terminal" src="https://github.com/donchai/nginx-103/assets/6828772/5eb59509-2747-4ef6-9bb2-37720cd22456"><br>

### Clone Github Repo<br>
`3.` Copy, paste, and enter following command into terminal to clone nms-demo-kit repo from Github<br>
```bash
git clone https://github.com/donchai/nms-demo-kit
```

### Begin Installation<br>
`4.` Copy, paste, and enter following command into terminal to change directory into nms-demo-kit<br>
```bash
cd nms-demo-kit
```
<img width="741" alt="Change directory to nms-demo-kit folder" src="https://github.com/donchai/nginx-103/assets/6828772/eb79ea89-dced-45b1-a583-bc2c63cc0a56"><br>

`5.` Copy, paste, and enter following command into terminal to set executable permission at *scripts* folder<br>
```bash
chmod 755 ./scripts/*
```

### NGINX Plus License File<br>
`6.` Download NGINX Plus trial license and put nginx-repo.crt and nginx-repo.key into nginx-plus folder<br>
`Obtain nginx-repo.crt and nginx-repo.key from Lab Facilitators`

### Build NMS Container<br>
`7.` Copy, paste, and enter following command into terminal to build the NMS (NGINX Instance Manager, API Connectivity Manager) container image, for steps , do refer to the prebuild shell script “buildNMS.sh”<br>
```bash
sudo ./scripts/buildNMS.sh -t nginx-nms -i -C nginx-plus/nginx-repo.crt -K nginx-plus/nginx-repo.key -A -W
```
<img width="955" alt="Build NMS" src="https://github.com/donchai/nginx-103/assets/6828772/d30086a5-da4d-4751-94ff-efa32bc2ba26"><br>

### Run NMS Container<br>
`8.` Copy, paste, and enter following command into terminal to deploy NMS into a container, we will be using a prebuild docker-compose manifest file<br>
```bash
sudo docker compose -f docker-compose.yaml up -d
```
<img width="906" alt="Deploy NMS" src="https://github.com/donchai/nginx-103/assets/6828772/07a93fa3-b5cc-4eb0-8b64-abe11cfa1aa2"><br>
