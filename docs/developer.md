# Developer Portal Configuration
In the previously created *API Connectivity Manager*-> *Infrastructure*-> *Workspace*-> *Environment*. Inside the environment (*nonprod*), Create Developer Portal Cluster.<br>

### Create Configuration
`1.` The name of the Dev Portal Clusters must be same with the instance group (refer to the *Instance Manager*-> *Instance Group*) name you specify in this case "*devportal*".<br>
<img width="800" alt="Create Developer Portal Configuration" src="https://github.com/donchai/nginx-103/assets/6828772/f4efb420-bd97-43a4-9627-a7a0454eaa6a"><br>
<br>Enter *devportal* into `Name` field, and enter *nginx-devportal* into `Hostname` field. Click `Create` button to create.<br>
<img width="400" alt="Enter Developer Portal Configuration Detail" src="https://github.com/donchai/nginx-103/assets/6828772/e29e334f-bf95-4e53-a3b2-332ea1794815"><br>

`2.` Once done, go to *Services*-> select the *httpbin-api* API proxy, Click *Edit Proxy*. Under *Configuration*, Look for *Developer Portal*, Tick the checkbox “*Also publish API to developer portal*”, and provide a portal proxy hostname value (*nginx-devportal*), Click `Save & Publish` button to complete.<br>
<img width="800" alt="Create Developer Portal" src="https://github.com/donchai/nginx-103/assets/6828772/61b6a097-81a5-4ef7-87ca-4b8fec1d15c7"><br>
