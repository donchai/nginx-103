# Developer Portal Configuration
In the previously created *API Connectivity Manager*-> *Infrastructure*-> *Workspace*-> *Environment*. Inside the environment (*nonprod*), Create Developer Portal Cluster.<br>

### Create Configuration
`1.` The name of the Dev Portal Clusters must be same with the instance group (refer to the *Instance Manager*-> *Instance Group*) name you specify in this case "*devportal*".<br>
<img width="800" alt="Create Developer Portal Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/f4efb420-bd97-43a4-9627-a7a0454eaa6a"><br>
<br>Enter *devportal* into `Name` field, and enter *nginx-devportal* into `Hostname` field. Click `Create` button to create Developer Portal.<br>
<img width="400" alt="Enter Developer Portal Configuration Detail" src="https://github.com/donchai/nginx-103/assets/6828772/e29e334f-bf95-4e53-a3b2-332ea1794815"><br>

`2.` Once done, go to *Services*-> select the *httpbin-api* API proxy, Click *Edit Proxy*. Under *Configuration*, Look for *Developer Portal*, Tick the checkbox “*Also publish API to developer portal*”, and provide a portal proxy hostname value (*nginx-devportal*), Click `Save & Publish` button to complete.<br>
<img width="800" alt="Create Developer Portal" src="https://github.com/donchai/nginx-103/assets/6828772/61b6a097-81a5-4ef7-87ca-4b8fec1d15c7"><br>

### Enable Access
`3.` Go to your UDF lab portal, create additional access method under ubuntu server for port 90.<br>
Enter *HTTP-90* into `Label` field, select *HTTPS* on `Protocol` dropdown, select *10.1.1.6* on `Instance Address` dropdown, and enter *90* into `Instance Port` field, click Save button to complete.<br>
<img width="800" alt="Enable Developer Portal Access" src="https://github.com/donchai/nginx-103/assets/6828772/56fb7d95-5022-4862-9c20-8579c3ef82a8"><br>
<br>Once done, locate the newly added access method with port 90 and click `Access` to browse Developer Portal.<br>

### Explore Developer Portal
`4.` Spend 2-3 minutes to explore Developer Portal. Look for various endpoints and possible API calls.<br>
<img width="1074" alt="Explore Developer Portal" src="https://github.com/donchai/nginx-103/assets/6828772/1d613470-76cf-4a1b-81db-3556d7ab3e54"><br>

### The End
Thank you for your time for NGINX Super User 2.0 Lab 103, untill the next time, have a good one!<br>
<img alt="NGINX Super User 2.0" src="./_static/NGINX-Super-User.png"><br>
