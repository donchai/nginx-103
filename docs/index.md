# NGINX 103

Streamline Your App and API Management with NGINX Management Suite using NIM. This lab is an introduction to NGINX Management Suites (NMS) with various modules: API Connectivity Manager (ACM), Instance Manager (NIM), and Security Monitoring (SM). It includes the usage of NGINX Plus as a load balancer and API Gateway, as well as NGINX App Protect for API Security Protection.
<br>*Original Lab Author*: `Ewen Low`

**Lab Overview**

For the demonstration, we will build a demo setup consisting of 1 x LB fronting API gateway clusters that connect to the API endpoints (httpbin API).

<img width="600" alt="Lab Overview" src="https://github.com/donchai/nginx-103/assets/6828772/fa05f8f8-ff1f-49e7-acc7-c42ff16d95f5">

## NMS Install

`1.` Navigate to ubuntu, click on access vscode app via Ubuntu -> vscode<br>
<img width="400" alt="Access to vscode" src="https://github.com/donchai/nginx-103/assets/6828772/348600fe-e57d-4f76-83ed-4e1e8bb0903d"><br>

`2.` Launch a new terminal in vscode<br>
<img width="400" alt="Launch new terminal" src="https://github.com/donchai/nginx-103/assets/6828772/5eb59509-2747-4ef6-9bb2-37720cd22456"><br>

`3.` Copy, paste, and enter following command into terminal to clone nms-demo-kit repo from Github<br>
```bash
git clone https://github.com/donchai/nms-demo-kit
```

`4.` Copy, paste, and enter following command into terminal to change directory into nms-demo-kit<br>
```bash
cd nms-demo-kit
```
<img width="741" alt="Change directory to nms-demo-kit folder" src="https://github.com/donchai/nginx-103/assets/6828772/eb79ea89-dced-45b1-a583-bc2c63cc0a56"><br>

`5.` Copy, paste, and enter following command into terminal to set executable permission at *scripts* folder<br>
```bash
chmod 755 ./scripts/*
```

`6.` Download NGINX Plus trial license and put nginx-repo.crt and nginx-repo.key into nginx-plus folder
`Obtain nginx-repo.crt and nginx-repo.key from Lab Facilitators`

`7.` Copy, paste, and enter following command into terminal to build the NMS (NGINX Instance Manager, API Connectivity Manager) container image, for steps , do refer to the prebuild shell script “buildNMS.sh”<br>
```bash
sudo ./scripts/buildNMS.sh -t nginx-nms -i -C nginx-plus/nginx-repo.crt -K nginx-plus/nginx-repo.key -A -W
```
<img width="955" alt="Build NMS" src="https://github.com/donchai/nginx-103/assets/6828772/d30086a5-da4d-4751-94ff-efa32bc2ba26"><br>

`8.` Copy, paste, and enter following command into terminal to deploy NMS into a container, we will be using a prebuild docker-compose manifest file<br>
```bash
sudo docker compose -f docker-compose.yaml up -d
```
<img width="906" alt="Deploy NMS" src="https://github.com/donchai/nginx-103/assets/6828772/07a93fa3-b5cc-4eb0-8b64-abe11cfa1aa2"><br>

## Use

In your `conf.py` configuration file, add `sphinx_copybutton` to your
extensions list. E.g.:

```python
extensions = [
    ...
    'sphinx_copybutton'
    ...
]
```

When you build your site, your code blocks should now have little copy buttons
to their right. Clicking the button will copy the code inside!

See [](use.md) for more information about how to use `sphinx-copybutton`.

```{toctree}
:maxdepth: 2
use
contribute/index
reference/example
changelog
```

## Inspiration

The UI and design elements of `sphinx-copybutton` are heavily inspired by [GitHub's design choices](https://primer.style).
The icon we use is from [Tabler's icons set](https://tablericons.com/).
