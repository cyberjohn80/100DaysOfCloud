**Add a cover photo like:**
![image](https://user-images.githubusercontent.com/97246467/163727263-2e3eef1e-29b7-47dc-a069-cfd3455c0d90.png)

# Introduction
I am currently working towards my AZ-900 exam and todays learning is all about in this walkthrough, we will creating a storage account, then work with blob storage files., The following will walk through the process required to undertake this task.

## Prerequisite

An Azure subscription and enough administrator permissions to deploy resource groups, virtual networks, and virtual machines.


# Task 1: Create a storage account 

In this task, we will create a new storage account. 

1. Sign in to the Azure portal at <a href="https://portal.azure.com" target="_blank"><span style="color: #0066cc;" color="#0066cc">https://portal.azure.com</span></a>

2. From the **All services** blade, search for and select **Storage accounts**, and then click **+ Add, + Create, + New**. 

  <img width="406" alt="image" src="https://user-images.githubusercontent.com/97246467/163727324-36203d74-3eed-45b7-8c12-145e9a69bf52.png">

  <img width="412" alt="image" src="https://user-images.githubusercontent.com/97246467/163727348-1506560a-61a1-474b-a1ca-7fb84b836bd2.png">

  <img width="515" alt="image" src="https://user-images.githubusercontent.com/97246467/163727386-733d79c9-929e-48f1-b6db-a4af57cce61a.png">

  <img width="465" alt="image" src="https://user-images.githubusercontent.com/97246467/163727419-756d5c9e-dd36-44bc-af9f-377d461a8fe1.png">

  <img width="486" alt="image" src="https://user-images.githubusercontent.com/97246467/163727508-89900f9b-14dc-4d5c-b23e-548709cdb0eb.png">

  <img width="454" alt="image" src="https://user-images.githubusercontent.com/97246467/163727534-a8b2cc43-81cd-4171-9d95-9c8b91ac26d8.png">

3. On the **Basics** tab of the **Create storage account** blade, fill in the following information (replace **xxxx** in the name of the storage account with letters and digits such that the name is globally unique). Leave the defaults for everything else.

    | Setting | Value | 
    | --- | --- |
    | Subscription | **Leave provided default** |
    | Resource group | **Create new resource group** |
    | Storage account name | **storageaccountxxxxx** |
    | Location | **(US) East US**  |
    | Performance | **Standard** |
    | Redundancy | **Locally redundant storage (LRS)** |
    
    **Note** - Remember to change the **xxxxx** so that it makes a unique **Storage account name**

5. Click **Review + Create** to review your storage account settings and allow Azure to validate the configuration. 

6. Once validated, click **Create**. Wait for the notification that the account was successfully created. 

7. From the Home page, search for and select **Storage accounts** and ensure your new storage account is listed.

  <img width="504" alt="image" src="https://user-images.githubusercontent.com/97246467/163727713-54418775-45ba-4688-86f6-9e2e885ad0bc.png">
  
  <img width="512" alt="image" src="https://user-images.githubusercontent.com/97246467/163727725-ab5b904d-b32d-49b2-825c-d0cac23af8a3.png">




# Task 2: Work with blob storage

In this task, we will create a Blob container and upload a blob file. 

1. Click the name of the new storage account, scroll to the **Data storage** section in the left menu, and then click **Containers**.

  <img width="484" alt="image" src="https://user-images.githubusercontent.com/97246467/163727769-d6140882-3f6c-4829-98f9-86009cdcdd63.png">

2. Click **+ Container** and complete the information. Use the Information icons to learn more. When done click **Create**.

  <img width="367" alt="image" src="https://user-images.githubusercontent.com/97246467/163727803-f72efac9-3a2e-4b98-8f62-12c150b01938.png">

    | Setting | Value |
    | --- | --- |
    | Name | **container1**  |
    | Public access level| **Private (no anonymous access)** |
  
  <img width="137" alt="image" src="https://user-images.githubusercontent.com/97246467/163727839-1431641e-132b-4393-9f57-0db03660a6ea.png">

  <img width="375" alt="image" src="https://user-images.githubusercontent.com/97246467/163727866-a432b256-6d4f-4381-ad9a-74573fcd9914.png">


4. Open a new browser window and search **Bing** for an image of a flower. Right click on the image and save it to your VM. 

6. Back in the Portal, click on **container1** , and then select **Upload**.

  <img width="509" alt="image" src="https://user-images.githubusercontent.com/97246467/163727896-f5da8986-19d0-4bac-af74-0e901b79cdb6.png">
  
 5. Browse for the image file you just saved on your local computer. Select it and then select upload.

  <img width="148" alt="image" src="https://user-images.githubusercontent.com/97246467/163727925-4f2fa608-4aa5-4652-8b2f-d38423035e5c.png">
   
6. Click the **Advanced** arrow, leave the default values but review the available options, and then click **Upload**.

  <img width="148" alt="image" src="https://user-images.githubusercontent.com/97246467/163727974-a09018f7-1531-4fce-aa69-76e941728ed3.png">


    **Note**: You can upload as many blobs as you like in this way. New blobs will be listed within the container.

7. Once the file is uploaded, right-click on the file and notice the options including View/edit, Download, Properties, and Delete. 

8. If you have time review the options for Files, Tables, and Queues.

# Task 3: Monitor the storage account

1. Return to the storage account blade and click **Diagnose and solve problems**. 

  <img width="505" alt="image" src="https://user-images.githubusercontent.com/97246467/163728042-3595e9ad-e964-4778-9e83-3b69b050f8c0.png">

2. Explore some of the most common storage problems. Notice there are multiple troubleshooters here.

3. On the storage account blade, scroll down to the **Monitoring** section and click **Insights**. Notice there is information on Failures, Performance, Availability, and Capacity. Your information will be different.

  <img width="508" alt="image" src="https://user-images.githubusercontent.com/97246467/163728070-4e4f1e41-754e-4d5e-8419-a46abb43a8fb.png">

  <img width="480" alt="image" src="https://user-images.githubusercontent.com/97246467/163728123-74b69c74-f66a-402b-91d0-5a9563852bfc.png">

Congratulations! You have created a storage account, then worked with storage blobs.

