![image](https://user-images.githubusercontent.com/97246467/163008185-110ef96e-d645-4355-843c-f9b778b8b338.png)

## Introduction
I am currently working towards my AZ-900 exam and todays learning is all about creating, configuring, and deploying a container by using Azure Container Instances (ACI) in the Azure Portal, The following will walk through the process required to undertake this task.

## Prerequisite

An Azure subscription and enough administrator permissions to deploy resource groups, virtual networks, and virtual machines.

## Steps To Deploy Azure Container Instances
In this walkthrough, we will create a web app that runs a Docker container. The Docker container contains a Welcome message.

Azure App Service are actually a collection of four services, all of which are built to help you host and run web applications. The four services (Web Apps, Mobile Apps, API Apps, and Logic Apps) look different, but in the end they all operate in very similar ways. Web Apps are the most commonly used of the four services, and this is the service that we will be using in this lab 


#Deploy Azure Container Instances (10 min)

In this walkthrough we create, configure, and deploy a container by using Azure Container Instances (ACI) in the Azure Portal. The container is a Welcome to ACI web application that displays a static HTML page. 

# Task 1: Create a container instance 

In this task, we will create a new container instance for the web application.  

1. Sign in to the [Azure portal](https://portal.azure.com).

2. From the **All services** blade, search for and select **Container instances** and then click **+ Add, + Create, + New**. 

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


4. Configure the Networking tab (replace **xxxxx** with letters and digits such that the name is globally unique). Leave all other settings at their default values.

	| Setting| Value|
	|--|--|
	| DNS name label| **mycontainerdnsxxxxx** |

	
	**Note**: Your container will be publicly reachable at dns-name-label.region.azurecontainer.io. If you receive a **DNS name label not available** error message following the deployment, specify a different DNS name label (replacing the xxxxx) and re-deploy. 

5. Click **Review and Create** to start the automatic validation process.

6. Click **Create** to create the container instance. 

7. Monitor the deployment page and the **Notifications** page. 


# Task 2: Verify deployment of the container instance

In this task, we verify that the container instance is running by ensuring that the welcome page displays.

1. After the deployment is complete, click the **Go to resource** link the deployment blade or the link to the resource in the Notification area.

2. On the **Overview** blade of **mycontainer**, ensure your container **Status** is **Running**. 

3. Locate the Fully Qualified Domain Name (FQDN).

	![Screenshot of the overview pane for the newly created container in Azure portal, with the FQDN highlighted. ](../images/0202.png)

2. Copy the container's FQDN into a new web browser tab and press **Enter**. The Welcome page should display. 

	![Screenshot of the ACI welcome message shown in a web browser.](../images/0203.png)


**Congratulations!** You have used Azure Portal to successfully deploy an application to a container in Azure Container Instances.

**Note**: To avoid additional costs, you can optionally remove this resource group. Search for resource groups, click your resource group, and then click **Delete resource group**. Verify the name of the resource group and then click **Delete**. Monitor the **Notifications** to see how the delete is proceeding.
