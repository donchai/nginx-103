# NGINX Plus Configuration
Configure NGINX LB using NGINX Instance Manager.<br>

### Add Configuration
`1.` In Instance Manager secLon, Instances tab, click on *nginx-lb* and Edit Config, add a new file as */etc/nginx/conf.d/nplusapi.conf* You may copy the content from folder *misc/nplusapi.conf*.<br>
<img width="1221" alt="Add NGINX Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/7d4fc1e5-0f79-408c-9ae9-eed0fc2e6182"><br>

`2.` Click in the plus + sign to add new file.<br>
<img width="1216" alt="Click Add NGINX Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/ca0d581f-36bb-435d-a60b-399ac3c543e9"><br>

### Copy Configuration
`3.` Copy, and paste following text as path value into `File name` field, click `Create` button once ready.<br>
```bash
etc/nginx/conf.d/nplusapi.conf
```
<img width="600" alt="Create New NGINX Configuration File" src="https://github.com/donchai/nginx-103/assets/6828772/5ee28db5-4a36-445f-9670-2b5fa01e5c3e"><br>

`4.` Navigate to VS code, under *the nms-demo-kit*, *misc* folder. Find *nplusapi.conf*, copy the code.<br>
<img width="600" alt="Copy NGINX Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/8a3533df-0679-4fae-8202-555985dd4465"><br>
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
`5.` Navigate back to the NMS portal, paste the code into the new file blank body.<br>
<img width="1224" alt="Paste NGINX Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/ba225918-e8d0-42ab-9904-516d15665d20"><br>

