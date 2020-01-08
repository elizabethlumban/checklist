Prerequisites:

1. Create an [IBM Public Cloud account](https://cloud.ibm.com/registration).
2. You have an existing Github account and repository and project set up.
3. We will create a toolchain based on this sample [application](https://github.com/elizabethlumban/front-end-app).


### Deploying the code to IBM Cloud

1. Login to your IBM Cloud Account.
2. In the Dashboard, select DevOps and in the DevOps Toolchain click  ``` Create ToolChain```
3. Then, in the next page select ``` Develop a Cloud Foundry App ```
4. Specify the 'Toolchain' name, 'Select Region' set to  ' Dallas' (this depends on your account), just set 'default' in 'Select a resource group' in the 'Select a source provider' select 'Github'.
5. Under Tool Integrations> Github Tab.  GitHub Server: Github, Repository Type: Existing, Repository URL: https://github.com/ichabondcrane/front-end-app

6. In the Delivery Pipeline tab, specify an App Name and Create the IBM Cloud API Key. Click on the New button next to the
IBM Cloud API Key field. A dialog box will be opened that will guide you on the API Key, take note the API Key and click
``` Create ```.  For the rest of the fields, I set it to the following values (this changes depending on your cloud account)
and then click Create button on top of the form.

Region : Dallas
Organization: IBM Singapore Garage
Space: dev

Note: If this is your first time to set up Github in your IBM Cloud account, you will need to authorize IBM Cloud Toolchain to authorize your repository .

7. After that, the toolchain will be created and you will need to allow IBM Cloud Toolchain to access your github repository. Please refer to this  [link](https://console.bluemix.net/docs/services/ContinuousDelivery/ts_index.html#ts_cd) for more information.

8. Next, is to configure the Delivery Pipeline, click on the Delivery Pipeline Box. In the Build Stage, click on the configure, go to Jobs tab and then in the build script, use the following script and click on ``` Save ```. 

![Build Input](https://raw.github.com/elizabethlumban/checklist/master/03%20-%20Dev_Ops/buildinput.png?raw=true "Build Input")
![Build Jobs](https://raw.github.com/elizabethlumban/checklist/master/03%20-%20Dev_Ops/buildjobs.png?raw=true "Build Jobs")


13. Then,in the Production Box, click Configure and in the Jobs tab, go to Deploy script and paste  ```node server.js ``` at the last line and click on ` Save `.

14. To test if the toolchain works, make a change in your local copy, push the code to your repository and wait for the toolchain to deploy it.

15. Once the application is up, go back to IBM Cloud Dashboard and go to Resources List and then select your app and open it. In the ``` Connect ``` Box, click on ```Create Connection ``` and then select the DB2 service you created earlier by clicking on the ``` Connect ``` button next to it. Once done, the application will be restaged.

16. In order to display the data correctly, the following files in the local repository needs to be modified, depending on the columns you want to display, make the change accordingly and push the code.

``` text
env.json (for your local testing only)
app.component.ts
app.component.html
```

17. Once the toolchain finished the deploy, go back to the toolchain dashboard and click on ``` Visit App URL ``` to view the app.


###  Useful links:
1. [Creating IBM Toolchains](https://cloud.ibm.com/docs/services/ContinuousDelivery?topic=ContinuousDelivery-toolchains_getting_started#toolchains_getting_started)
2. [IBM DB2 on Cloud](https://www.ibm.com/sg-en/cloud/db2-on-cloud)
