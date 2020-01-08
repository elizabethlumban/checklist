Prerequisites:

1. Create an [IBM Public Cloud account](https://cloud.ibm.com/registration).
2. You have an existing Github account and repository and project set up.
3. We will create a toolchain based on this sample [application](https://github.com/elizabethlumban/front-end-app).


### Deploying the code to IBM Cloud

1. Login to your IBM Cloud Account.
2. In the Dashboard, select DevOps and in the DevOps Toolchain click  ``` Create ToolChain```
3. Then, in the next page select ``` Develop a Cloud Foundry App ```
4. Specify the ``` Toolchain ``` name,  ``` Select Region ``` set to  ' Dallas' (this depends on your account), just set 'default' in ``` Select a resource group ``` in the   ``` Select a source provider ``` select 'Github'.
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

8. Next, is to configure the ``` Delivery Pipeline ```, click on the Delivery Pipeline Box. In the Build Stage, click on the Configure Stage, go to Input tab and just follow the values in the screenshot below. In this stage, we are specifying Github repository 
as the source of input for this stage and in this stage, the job will be automatically triggered when  a commit is pushed in the GIT repository. Then in the Jobs stage, we set the Builder type as npm and in the build script, we install the necessary modules and build it. This job will stop running if the install and the build fails.

![Build Input](https://raw.github.com/elizabethlumban/checklist/master/03%20-%20Dev_Ops/buildinput.png?raw=true "Build Input")
![Build Jobs](https://raw.github.com/elizabethlumban/checklist/master/03%20-%20Dev_Ops/buildjobs.png?raw=true "Build Jobs")

9. Next, is the Test Stage, click on the Configure Stage and just follow the values in the screenshot, in the Input tab, it will take its input from the previous stage, the Build Stage, and then in the Jobs tab, for this particular project we will need to install a few modules first and then it will execute the automated test.

![Test Input](https://raw.github.com/elizabethlumban/checklist/master/03%20-%20Dev_Ops/testinput.png?raw=true "Test Input")
![Test Jobs](https://raw.github.com/elizabethlumban/checklist/master/03%20-%20Dev_Ops/testjobs.png?raw=true "Test Jobs")

10. Then,in the Deploy Stage, click Configure Stage and in the Input tab, just follow the screenshot below and then in the Jobs tab, all the fields should have been auto populated with these values from the screenshot except for the deploy script. The deploy script varies depending on what kind of application you are trying to deploy.

![Deploy Input](https://raw.github.com/elizabethlumban/checklist/master/03%20-%20Dev_Ops/deployinput.png?raw=true "Deploy Input")
![Deploy Jobs](https://raw.github.com/elizabethlumban/checklist/master/03%20-%20Dev_Ops/deployjobs.png?raw=true "Deploy Jobs")

11. We should be all set after this, and to test if the toolchain works, make a change at your local repository and then push it to github, it should trigger the Build stage.

![Toolchain](https://raw.github.com/elizabethlumban/checklist/master/03%20-%20Dev_Ops/toolchain.png?raw=true "Toolchain")

12. Once Deploy Stage is finished and passed, go to the Deploy Stage box and under the ``` Last Execution Result ```, click on View Console under the application name, you will be routed to the application page itself (see screenshot) and from there click
on ``` Visit App URL ``` link. 

![Deploy Stage](https://raw.github.com/elizabethlumban/checklist/master/03%20-%20Dev_Ops/deploystage.png?raw=true "Deploy Stage")
![Toolchain Visit URL](https://raw.github.com/elizabethlumban/checklist/master/03%20-%20Dev_Ops/visiturl.png?raw=true "Visit URL")




###  Reference:
1. [Creating IBM Toolchains](https://cloud.ibm.com/docs/services/ContinuousDelivery?topic=ContinuousDelivery-toolchains_getting_started#toolchains_getting_started)
