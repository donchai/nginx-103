# NGINX Plus Installation
Refer to the pre-build shell script & “buildNPlusWithAgent.sh” for NGINX Plus installation detail.<br>

### Build Image for API Gateway
`1.` Copy, paste, and enter following command into terminal to build NGINX Plus image with nginx-agent (the 10.1.1.6 the IP on the ubuntu host).<br>
The entire process will take around 2-3 minutes.<br>
```bash
sudo ./scripts/buildNPlusWithAgent.sh -t npluswithagent -n https://10.1.1.6
```
<img width="800" alt="Build NGINX Plus as API Gateway" src="https://github.com/donchai/nginx-103/assets/6828772/326b4afd-0350-4601-9f19-9e4d5713522d"><br>

### Build Image for API Developer Portal
`2.` Copy, paste, and enter following command into terminal to build NGINX Plus (ACM Dev-Portal) image with nginx-agent (the 10.1.1.6 the IP on the ubuntu host).<br>
The entire process will take around 2-3 minutes.<br>
```bash
sudo ./scripts/buildNPlusWithAgent.sh -t npluswithagent:devportal -D -n https://10.1.1.6
```
<img width="794" alt="Build NGINX Plus as API Developer Portal" src="https://github.com/donchai/nginx-103/assets/6828772/d73d9c7e-420a-486e-9da9-ba4a8294b53a"><br>

### Edit Docker Configuration File
`3.` Navigate to the nms-demo-kit folder at vs code, click on the docker-compose.yaml manifest file.<br>
<img width="468" alt="Edit docker-compose.yaml File" src="https://github.com/donchai/nginx-103/assets/6828772/d8fa6b74-81ba-431e-9a79-8f170de516b5"><br>

`4.` Uncomment out the *nginx-lb*, *nginx-gw*, *httpbin-app*, *acm.nginx-devportal* sections in docker-compose.yaml section.<br>
Before<br>
<img width="800" alt="Before Uncomment docker-compose.yaml File" src="https://github.com/donchai/nginx-103/assets/6828772/e661d2ef-2991-4afe-a4ae-cc74ffd62b7e"><br>
After (Highlight from line 32 to line 65) and press the below shortcut keys<br>
• Shortcut keys for Mac = Command + /)<br>
• Shortcut keys for Windows = Control + K or Control + C or Control + U<br>
<img width="800" alt="After Uncomment docker-compose.yaml File" src="https://github.com/donchai/nginx-103/assets/6828772/65472789-8299-4c8d-88d2-580d5fd8a18d"><br>
Close the docker-compose.yaml file after successfully uncommented the sections mentioned-above.<br>

### Deploy and Run NGINX Plus Instances
`5.` Copy, paste, and enter following command into terminal to deploy your N+ instances using docker compose.<br>
The entire process will take around 2-3 minutes.<br>
```bash
sudo docker compose -f docker-compose.yaml up -d
```
<img width="800" alt="Deploy NGINX Plus Instances" src="https://github.com/donchai/nginx-103/assets/6828772/7760fb56-f039-41eb-93ad-e169a3aaa1ec"><br>

### Verify Running State using Docker Command
`6.` Copy, paste, and enter following command into terminal to verify the NGINX Plus Instances deployment status.<br>
```bash
sudo docker ps
```
<img width="800" alt="Verify NGINX Plus Instances Deployment Status using Docker" src="https://github.com/donchai/nginx-103/assets/6828772/8a762d91-c286-41f7-bef5-e31e74081c89"><br>

### Verify Running State using NMS Portal
`7.` Navigate back to your NMS portal, click on Instance manager modules. On the overview page of the NMS Instance Manager dashboard, you should see the below instances.<br>
<img width="800" alt="Verify NGINX Plus Instances Deployment Status using NMS" src="https://github.com/donchai/nginx-103/assets/6828772/f4ac8e69-32aa-4796-8e6d-4d2fa66e641e"><br>

