   ![image](https://user-images.githubusercontent.com/97246467/163365500-117d3cbd-40fc-4dae-9062-2cdbcd432df3.png)
# Introduction
I am currently working towards my AZ-900 exam and todays learning is all about configuring and deploying two virtual machines in a virtual network, The following will walk through the process required to undertake this task.

## Prerequisite

An Azure subscription and enough administrator permissions to deploy resource groups, virtual networks, and virtual machines.

## Create a virtual network (20 min)

In this walkthrough, we will create a virtual network, deploy two virtual machines onto that virtual network and then configure them to allow one virtual machine to ping the other within that virtual network.

## Task 1: Create a virtual network 

In this task, we will create a virtual network. 

Note: Before beginning the lab, disable both the public and private firewall in your virtual machine by opening the Start menu > Settings > Network and Internet > Locate Windows Firewall

1. Sign in to the Azure portal at <a href="https://portal.azure.com" target="_blank"><span style="color: #0066cc;" color="#0066cc">https://portal.azure.com</span></a>

2. From the **All services** blade, search for and select **Virtual networks**, and then click **+ Add, + Create, + New**. 

    ![select All services](https://user-images.githubusercontent.com/97246467/163356984-aafd6099-06bc-4e04-98f8-0e36c3029216.PNG)
    
    ![vn](https://user-images.githubusercontent.com/97246467/163358781-36066889-bc78-4230-aac9-0a4b4d61f916.png)
    
    ![2](https://user-images.githubusercontent.com/97246467/163358909-fa0e82cf-4214-4946-9c42-e2f49ab448de.PNG)

3. On the **Basics** tab, fill in the following information (leave the defaults for everything else):

    | Setting | Value | 
    | --- | --- |
    | Subscription | **Leave default provided** |
    | Resource Group | **Create new resource group** |
    | Name | **vnet1** |
    | Region | **(US) East US** |
    
    ![3](https://user-images.githubusercontent.com/97246467/163359215-1bcc2d72-e197-4d0d-9e6d-1cee202539ab.PNG)

#

4. Click the **Review + create** button. Ensure the validation passes. Then hit create to deploy the resource.


## Task 2: Create two virtual machines

In this task, we will create two virtual machines in the virtual network. 

1. From the **All services** blade, search for **Virtual machines** and then click **+ Add, + Create, + New**, from the drop down select **Virtual Machine**. 

    ![select All services](https://user-images.githubusercontent.com/97246467/163356984-aafd6099-06bc-4e04-98f8-0e36c3029216.PNG)
    
    ![vm](https://user-images.githubusercontent.com/97246467/163360304-51939186-fa4f-4645-afb2-da0196744480.png)

2. On the **Basics** tab, fill in the following information (leave the defaults for everything else):

   | Setting | Value | 
   | --- | --- |
   | Subscription | **Use default supplied** |
   | Resource group |  **Select default in drop down** |
   | Virtual machine name | **vm1**|
   | Region | **(US) East US** |
   | Image | **Windows Server 2019 Datacenter - Gen2** |
   | Username| **azureuser** |
   | Password| **Pa$$w0rd1234** |
   | Public inbound ports| Select **Allow selected ports**  |
   | Selected inbound ports| **RDP (3389)** |
   
    ![4](https://user-images.githubusercontent.com/97246467/163359720-4e6d6b39-1149-4a33-af01-55d0abac95e3.PNG)
    
    ![5](https://user-images.githubusercontent.com/97246467/163359767-8e17572e-e7d7-466f-9295-5c68f042d708.PNG)
    
    ![6](https://user-images.githubusercontent.com/97246467/163360180-f24dd7ba-c9e1-45db-aca4-719addaa31d0.PNG)

3. Select the **Networking** tab. Make sure the virtual machine is placed in the **vnet1** virtual network. Review the default settings, but do not make any other changes. 
    ![7](https://user-images.githubusercontent.com/97246467/163360482-80155723-474f-478e-8ca3-dd28d118b461.PNG)

4. Click **Review + create**. After the Validation passes, click **Create**. Deployment times can vary but it can generally take between three to six minutes to deploy.

5. Monitor your deployment, but continue on to the next step. 

6. Create a second virtual machine by repeating steps **2 to 4** above. Make sure you use a different virtual machine name, that the virtual machine is in the same virtual network, and is using a new public IP address:

    | Setting | Value |
    | --- | --- |
    | Resource group | **select default in dropdown (same as Task1-3 & Task2-2)** |
    | Virtual machine name |  **vm2** |
    | Virtual network | **vnet1** |
    | Public IP | **vm2-ip** |

7. Wait for both virtual machines to deploy and status says *running*.

## Task 3: Test the connection 

In this task, we will try to test whether the virtual machines can communicate (ping) each other. If not we will install a rule to allow an ICMP connection. Usually ICMP connections are automatically blocked.

1. From the **All resources** blade, search for **vm1**, open its **Overview** blade, and make sure its **Status** is **Running**. You may need to **Refresh** the page.

    ![1](https://user-images.githubusercontent.com/97246467/163362357-e40af252-13e6-477f-876f-297891d099bb.PNG)#
    
    ![2](https://user-images.githubusercontent.com/97246467/163362417-b5d2d1b9-ccd7-40b4-bbb6-3389550c401b.PNG)

2. On the **Overview** blade, select **Connect** and then select **RDP** from the drop down.

     ![3](https://user-images.githubusercontent.com/97246467/163362536-37e4bbdf-727c-4bb9-ada9-bc25e23e8118.PNG)
     
     
    ![4](https://user-images.githubusercontent.com/97246467/163362689-43e88f2b-838d-4276-a6a5-05bedee20685.PNG)

    **Note**: The following directions tell you how to connect to your VM from a Windows computer. 

3. On the **Connect with RDP** blade, keep the default options to connect by IP address over port 3389 and click **Download RDP File**.

4. Open the downloaded RDP file (located at the bottom left of you VM) and click **Connect** when prompted. 
5. 
    ![5](https://user-images.githubusercontent.com/97246467/163363673-ec5195e2-6a56-4bf7-beca-99a6db1cf4e7.PNG)

5. In the **Windows Security** window, type the username **azureuser** and password **Pa$$w0rd1234** and then click **OK**.

    ![6](https://user-images.githubusercontent.com/97246467/163363794-5b008dd3-af48-46a8-9212-10e0808b3426.PNG)

   ![12](https://user-images.githubusercontent.com/97246467/163364605-a716f2c5-8fea-44db-a539-641c8f1eb165.PNG)


6. You may receive a certificate warning during the sign-in process. Click **Yes** to create the connection and connect to your deployed VM. You should connect successfully. Close the Windows Server and Dashboard windows that pop up. You should see a Blue Windows background. You are now in your virtual machine.

    ![7](https://user-images.githubusercontent.com/97246467/163363804-c4b50e96-ed36-4df3-bbfb-e3b0a4d127b9.PNG)

7. In **both** newly created virtual machines, connect via RDP and disable both the public and private firewall by opening the Start menu > Settings > Network and Internet > Locate Windows Firewall. Or via the server manger > Local Server > Windows Defender Firewall.

    ![8](https://user-images.githubusercontent.com/97246467/163365344-4da906e9-e389-4ab9-8c75-2419291ee2d9.PNG)

    ![9](https://user-images.githubusercontent.com/97246467/163365346-b441a080-b030-4e3b-9303-6e189d834464.PNG)

8. Open up PowerShell on the virtual machine by clicking the **Start** button, and in Search type **PowerShell**, right click on **Windows PowerShell** to **Run as administrator**

9. In Powershell, try to ping vm2 by typing:

   ```PowerShell
   ping vm2
   ```
   ![10](https://user-images.githubusercontent.com/97246467/163364678-bb1baaaf-050e-4222-b2ae-bf96378201e7.PNG)


 10. You should be successful. You have pinged VM2 from VM1.

   ![11](https://user-images.githubusercontent.com/97246467/163364744-c1678423-e6db-4829-80b5-bbe14a19e9c1.PNG)

**Congratulations!** You have configured and deployed two virtual machines in a virtual network, and then you were able to connect them.
