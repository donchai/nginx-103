# API Gateway Configuration
For this lab, we will use the the script to automate API Connectivity Manager (ACM) configuration. However, you are encouraged to manually execute the steps below to be familiar with the ACM workflow.<br>

### Add Configuration
`1.` Copy, paste, and enter below command into VS code terminal to invoke API call creating ACM configuration.<br>
```bash
sh misc/end2end_deploy.sh
```
<img width="800" alt="Invoke ACM Configuration API Call" src="https://github.com/donchai/nginx-103/assets/6828772/b6c4cfb8-1aaa-4c9f-94b7-a17a139023e5"><br>

### Enable API Gateway Cluster
`2.` In *API Connectivity Manager*, *Infrastructure*, create a *Workspace*, an *Environment*. In the *Environment* tab, add *API Gateways* Cluster. You may fill in any mock details, but the Name of the API Gateway Clusters must be same with the instance group name you specify for the *nginx-gw* in docker-compose file, in this case "*gwcluster*".<br>
<img width="800" alt="ACM Configuration Overview" src="https://github.com/donchai/nginx-103/assets/6828772/6b0e210a-331f-4098-9145-998d5d136766"><br>

### Scaling API Gateway Cluster
`3.` By scaling the *nginx-gw* instances, the newly spin up instance will auto register as part of the API Gateway Cluster instance group. You will notice additional instance in the Instances section.<br>
<br>Before Scaling, verify total ACM Gateway Instance count on NMS portal.<br>
<img width="800" alt="ACM Before Scaling" src="https://github.com/donchai/nginx-103/assets/6828772/55d8859e-e787-44aa-9c78-adff090001f3"><br>
<br>First, in VS code, edit docker-compose file, under *nginx-gw* section, change the replicas value to 3. Close the file once done.<br>
<img width="800" alt="Edit ACM Gateway Instance Count Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/64ad9be6-8e7d-46fb-bbf6-7a37b5511af9"><br>
<br>Copy, paste, and enter below command into VS code terminal to scale API Gateway Cluster instance.<br>
```bash
sudo docker compose -f docker-compose.yaml up -d
```
<br>After Scaled, verify total ACM Gateway Instance count on NMS portal.<br>
<img width="800" alt="Scaled ACM Gateway" src="https://github.com/donchai/nginx-103/assets/6828772/8ece6021-eb52-4edf-9cb6-5d154df471c8"><br>

### Test API Gateway
`4.` Spend 5 minutes to explore the ACM UI and configuration. Copy, paste, and enter below command in VS code terminal to test ACM setting.<br>
```bash
curl -v localhost/get

curl -v localhost/headers

curl -v localhost/ip

curl -v localhost/delay/4

```
You may refer to the *misc/httpbin-oas.yml* for other possible httpbin API endpoints.<br>
