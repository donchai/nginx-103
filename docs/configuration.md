# NGINX Plus Configuration
Configure NGINX LB using NGINX Instance Manager.<br>

### Add Configuration
`1.` In Instance Manager section, Instances tab, click on *nginx-lb* and Edit Config, add a new file as */etc/nginx/conf.d/nplusapi.conf* You may copy the content from folder *misc/nplusapi.conf*.<br>
<img width="800" alt="Add NGINX Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/7d4fc1e5-0f79-408c-9ae9-eed0fc2e6182"><br>

`2.` Click in the plus + sign to add new file.<br>
<img width="800" alt="Click Add NGINX Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/ca0d581f-36bb-435d-a60b-399ac3c543e9"><br>

### Copy Configuration
`3.` Copy, and paste following text as path value into `File name` field, click `Create` button once ready.<br>
```bash
etc/nginx/conf.d/nplusapi.conf
```
<img width="400" alt="Create New NGINX Configuration File" src="https://github.com/donchai/nginx-103/assets/6828772/5ee28db5-4a36-445f-9670-2b5fa01e5c3e"><br>

`4.` Navigate to VS code, under *the nms-demo-kit*, *misc* folder. Find *nplusapi.conf*, copy the code.<br>
<img width="800" alt="Copy NGINX Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/8a3533df-0679-4fae-8202-555985dd4465"><br>
<br>Alternatively, copy the code below.<br>
```bash
server {

    listen       8080;

        location /api {
        api write=on;
        allow all;
    }

    location / {
    root /usr/share/nginx/html;
    index   dashboard.html;
    }
}
```

### Paste Configuration
`5.` Navigate back to the NMS portal, paste the code into the new file blank body. Click `Publish` button twice to save the new NGINX configuration file.<br>
<img width="800" alt="Paste NGINX Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/ba225918-e8d0-42ab-9904-516d15665d20"><br>

### Modify Default Configuration
`6.` From the drop down list, select */etc/nginx/conf.d/default.conf* option.<br>
<img width="800" alt="Edit Default NGINX Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/c400ce74-2e6c-494c-9272-8a57c53603d2"><br>

`7.` Navigate back to VS code, under the *nms-demo-kit*, *misc* folder. Find *lb.conf*, copy the code.<br>
<img width="800" alt="Copy New Default NGINX LB Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/c38eae92-e658-4b06-bcb8-b8c2096661a8"><br>
<br>Alternatively, copy the code below.<br>
```bash
resolver 127.0.0.11 valid=10s status_zone=httpresolver;

upstream backend_gw {
    zone backend_gw 64k;
    server nginx-gw:80 resolve;
}

server {
    listen 80;
    status_zone main_server;
    location / {
        status_zone main_location;
        add_header backend $upstream_addr;
        proxy_pass http://backend_gw;
    }
}
```

`8.` Paste the code under the */etc/nginx/conf.d/default.conf* existing modify file content body (overwrite all). Click `Publish` button twice to save the modified NGINX default configuration file.<br>
<img width="800" alt="Replace Default NGINX Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/d52cb029-50a7-44cd-a75a-bfb0f8218b97"><br>

### Verify Applied Configuration
`9.` Test the LB setting, navigate back to VS code terminal and copy, paste, and enter command below twice.<br>
```bash
curl -I http://localhost/
```
<img width="600" alt="Test LB Setting" src="https://github.com/donchai/nginx-103/assets/6828772/486cf304-b57d-44a5-a59a-ca1f12699cf1"><br>

### Verify Container IP Address
We have configured NGINX load balancer to return backend server's IP address. There are mulLple backend server (NGINX Gateway), the NGINX load balancer will round robin to different backend server and return respecLve IP addresses. Your containers IP addresses might be different from what is shown below.<br>
<br>First, copy, paste, and enter below command to find out `<container id>` value.<br>
```bash
sudo docker ps
```
Second, to check IP address in docker container, copy, paste, and enter below command twice. Remember to replace `<container id>` with actual value.<br>
```bash
sudo docker inspect <container id> | grep "IPAddress"
```
<img width="1301" alt="Get Docker IP Address" src="https://github.com/donchai/nginx-103/assets/6828772/db317d1e-9792-46a4-9d19-fa210ff6dc5f"><br>
<br>Alternatively, go to the NMS portal to check on the IP for the NGINX-GW Cluster Instance 1 and Instance 2.<br>
<img width="800" alt="Replace Default NGINX Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/76befac4-c601-445a-8972-2f8b80d68161"><br>

