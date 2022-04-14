![image](https://user-images.githubusercontent.com/97246467/163352852-a74ad9d1-f61f-482d-bc0c-a19291e9880e.png)

# Introduction
I am currently working towards my AZ-900 exam and todays learning is all about creating, configuring, and deploying a container by using Azure Container Instances (ACI) in the Azure Portal, The following will walk through the process required to undertake this task.

## Prerequisite

An Azure subscription and enough administrator permissions to deploy resource groups, virtual networks, and virtual machines.

##Deploy Azure Container Instances (10 min)

In this walkthrough we create, configure, and deploy a container by using Azure Container Instances (ACI) in the Azure Portal. The container is a Welcome to ACI web application that displays a static HTML page. 

##Task 1: Create a container instance 

In this task, we will create a new container instance for the web application.  

1. Sign in to the [Azure portal](https://portal.azure.com).

2. From the **All services** blade, search for and select **Container instances** and then click **+ Add, + Create, + New**. 

	![screenshot All services](https://user-images.githubusercontent.com/97246467/163351061-50d8f641-5f09-4535-9609-e0b8289670b1.PNG)


	![![screenshot Container instances](https://user-images.githubusercontent.com/97246467/163350789-bd9081af-c4b9-4d06-927c-12e360669034.PNG)


	![screenshot create](https://user-images.githubusercontent.com/97246467/163351310-d0ca3283-755a-4dee-aa92-9d36e0600971.PNG)



3. Provide the following Basic details for the new container instance  (leave the defaults for everything else)): 

	| Setting| Value|
	|----|----|
	| Subscription | ***Use default supplied*** |
	| Resource group | **Create new resource group** |
	| Container name| **mycontainer**|
	| Region | **(US) East US** |
	| Image source| **Docker Hub or other registry**|
	| Image type| **Public**|
	| Image| **mcr.microsoft.com/azuredocs/aci-helloworld**|
	| OS type| **Linux** |
	| Size| ***Leave at the default***|
	
	
![screenshot seetings One](https://user-images.githubusercontent.com/97246467/163351426-0c7e84c8-799a-4d6b-8ec2-8aa41266abc3.PNG)

![screenshot seetings Two](https://user-images.githubusercontent.com/97246467/163351473-907228a7-f140-46e1-93cd-9269a802149b.PNG)

4. Configure the Networking tab (replace **xxxxx** with letters and digits such that the name is globally unique). Leave all other settings at their default values.

	| Setting| Value|
	|--|--|
	| DNS name label| **mycontainerdnsxxxxx** |

	![screenshot seetings Network](https://user-images.githubusercontent.com/97246467/163351523-177fcb28-a481-49d6-b588-20a6b8658f21.PNG)

	**Note**: Your container will be publicly reachable at dns-name-label.region.azurecontainer.io. If you receive a **DNS name label not available** error message following the deployment, specify a different DNS name label (replacing the xxxxx) and re-deploy. 

5. Click **Review and Create** to start the automatic validation process.

6. Click **Create** to create the container instance. 

7. Monitor the deployment page and the **Notifications** page. 


## Task 2: Verify deployment of the container instance

In this task, we verify that the container instance is running by ensuring that the welcome page displays.

1. After the deployment is complete, click the **Go to resource** link the deployment blade or the link to the resource in the Notification area.

2. On the **Overview** blade of **mycontainer**, ensure your container **Status** is **Running**. 

3. Locate the Fully Qualified Domain Name (FQDN).
	![Screenshot of the overview pane for the newly created container in Azure portal, with the FQDN highlighted. ](https://user-images.githubusercontent.com/97246467/163352240-018ea7b3-97bc-413e-a13c-218cb0597ff5.PNG)


2. Copy the container's FQDN into a new web browser tab and press **Enter**. The Welcome page should display. 

	![Screenshot of the ACI welcome message shown in a web browser.](https://user-images.githubusercontent.com/97246467/163352146-d65683d6-c835-47d7-aa3c-799e47c901a5.PNG)


**Congratulations!** You have used Azure Portal to successfully deploy an application to a container in Azure Container Instances.

## Social Proof

[Twitter](https://twitter.com/cyberjohn80/status/1514531907509305346)
