![image](https://user-images.githubusercontent.com/97246467/163008185-110ef96e-d645-4355-843c-f9b778b8b338.png)

## Introduction
I am currently working towards my AZ-900 exam and todays learning is all about creating a Web App, The following will walk through the process required to undertake this task.

## Prerequisite

An Azure subscription and enough administrator permissions to deploy resource groups, virtual networks, and virtual machines.

## Steps to create a web app
In this walkthrough, we will create a web app that runs a Docker container. The Docker container contains a Welcome message.

Azure App Service are actually a collection of four services, all of which are built to help you host and run web applications. The four services (Web Apps, Mobile Apps, API Apps, and Logic Apps) look different, but in the end they all operate in very similar ways. Web Apps are the most commonly used of the four services, and this is the service that we will be using in this lab 


# Task 1: Create a Web App 

In this task, you will create an Azure App Service Web App. 

1. Sign-in to the [Azure portal](http://portal.azure.com/). 

2. From the **All services** blade, search for and select **App Services**,and click **+ Add, + Create, + New**

![image](https://user-images.githubusercontent.com/97246467/163011567-50e5eb56-08aa-4b28-8c00-04a4ab91e012.png)

![image](https://user-images.githubusercontent.com/97246467/163011651-b5d7a3d0-7202-4136-a3c4-f9baaeb74545.png)

![image](https://user-images.githubusercontent.com/97246467/163011882-85086c3c-9fdb-4e2a-a1e4-a01198512141.png)

3. On the **Basics** tab of the **Web App** blade, specify the following settings (replace **xxxx** in the name of the web app with letters and digits such that the name is globally unique). Leave the defaults for everything else, including the App Service Plan. 

    | Setting | Value |
    | -- | -- |
    | Subscription | **Use default supplied** |
    | Resource Group | **Create new resource group**|
    | Name | **myDockerWebAppxxxx** |
    | Publish | **Docker Container** |
    | Operating System | **Linux** |
    | Region | **UK West** |
    
     
  ![image](https://user-images.githubusercontent.com/97246467/163011984-c8315f07-690b-4d9e-8e18-2729ffec53a9.png)
    
  ![image](https://user-images.githubusercontent.com/97246467/163012063-5cfc2fd0-fd78-401b-9c55-edc52faaba26.png)

    
    **Note:** Remember to change the **xxxx** so that your Web App name is unique.

4. Click **Next > Docker** and configure the container information.  

    | Setting | Value |
    | -- | -- |
    | Options | **Single container** |
    | Image Source | **Docker Hub** |
    | Access Type | **Public** |
    | Image and tag | **mcr.microsoft.com/azuredocs/aci-helloworld** |
   
![image](https://user-images.githubusercontent.com/97246467/163012286-d1634800-33ff-43cd-8519-3f35a58296c2.png)

 **Note:** The startup command is optional and not needed in this exercise.

5. Click **Review + create**, and then click **Create**. 

# Task 2: Test the Web App

In this task, we will test the web app.

1. Wait for the Web App to deploy.

2. From **Notifications** click **Go to resource**. 

![image](https://user-images.githubusercontent.com/97246467/163012652-bbd0fadd-02a3-4f43-9722-ebd6fc6f05a8.png)

3. On the **Overview** blade, locate the **URL**. Copy the URL to the clipboard.

![image](https://user-images.githubusercontent.com/97246467/163012918-06f0632a-b201-444e-b70c-59a47c731f6f.png)

4. In a new browser window, paste the URl and press enter. The Welcome to Azure Container Instances! welcome message will be displayed.

 ![image](https://user-images.githubusercontent.com/97246467/163013214-3529d1f7-dd69-495c-821d-9c5f44157e04.png)

5. Switch back to the **Overview** blade of your web app and scroll down. You will notice several charts tracking Data In/Out and Requests. If you repeat step 4 a few times, you should be able to see corresponding telemetry being displayed in these charts. This includes number of requests and average response time. 

![image](https://user-images.githubusercontent.com/97246467/163013350-9fe25d59-4ca7-4a06-b23e-4c6ed734fbb1.png)

Congratulations you successfully created an Azure App Service.

## Social Proof

[Twitter](https://twitter.com/cyberjohn80/status/1513583374987837442)
