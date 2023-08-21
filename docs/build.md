# NGINX Plus Installation
Refer to the pre-build shell script & “buildNPlusWithAgent.sh” for NGINX Plus installation detail.<br>

## Build NGINX Plus Image for API Gateway
`1.` Copy, paste, and enter following command into terminal to build NGINX Plus image with nginx-agent (the 10.1.1.6 the IP on the ubuntu host).<br>
The entire process will take around 2-3 minutes.<br>
```bash
sudo ./scripts/buildNPlusWithAgent.sh -t npluswithagent -n https://10.1.1.6
```
<img width="800" alt="Build NGINX Plus as API Gateway" src="https://github.com/donchai/nginx-103/assets/6828772/326b4afd-0350-4601-9f19-9e4d5713522d"><br>

## Build NGINX Plus Image for API Developer Portal
`2.` Copy, paste, and enter following command into terminal to build NGINX Plus (ACM Dev-Portal) image with nginx-agent (the 10.1.1.6 the IP on the ubuntu host).<br>
The entire process will take around 2-3 minutes.<br>
<img width="796" alt="Build NGINX Plus as API Developer Portal" src="https://github.com/donchai/nginx-103/assets/6828772/5e5ed597-c486-4bcd-bd8b-3e54e7bf8491"><br>
