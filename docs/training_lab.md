---
layout: default
title: Training Labs
nav_order: 2
---

# How to set-up training labs
Last modified: **June 6th, 2021**

**Note:** This documentation is for Dynatrace India ACE Services team. Please don't read if you are a non-dynatrace person. This document shows how to setup lab in Azure DevTestLabs.

In this document you can find how to set-up labs for training and also it classified into 2 types, 
1. Admin Training
2. Power User Training

Please check the contents for navigating through the document. It contains several sections and step by step guide to create lab resources for training purposes. For creating labs, using Azure or GCP is recommended.

## Pre-requisites
1. Access to Azure tenant of Dynatrace (At least one subscription access is required)
2. Admin access to Transform Lab (https://lab.dt-transform.com)
3. Dynatrace Email ID
4. Participants email address for sending all the instructions later on. 

## Steps needs to be followed
- Collect the participants details ```(Name, Email)```.
- Create GitHub issue to notify the activity or to track each changes. 
- Create atleast 2 VMs for each participant.
- Create Dynatrace Environments for users (depends on the type of user).
- Email the resource details to each participant from the list you have collected from the customer. 

### Creating GitHub Issue
Before doing any changes it is the best practice to create a GitHub issue with the details of the change. Please follow that to keep track of your work and also help us to improve. In future there will be an automation included for these issues. In the same repository, you need to create 2 issues one is regarding Access request for Dynatrace Environment and another is for creating VMs in Azure.

- Login to [GitHub](https://github.com).
- Visit out lab repository [here](https://github.com/Dynatrace-India/DT-Transform-Managed-Lab/).
- Go to issues and click on ```New issue``` as shown below.

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/5.png)

- Use the predefined templates to create an issue. Note: Use **Access Request** teamplate for Environment access and **Resource request ** template for creating virtual Machines.

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/6.png)

- Follow the instructions in the template and create issues 

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/7.png)

### Creating Virual Machines
#### Creating Azure DevTestLabs Lab
- Navigate to [Azure DevTestLabs](https://portal.azure.com/#blade/HubsExtension/BrowseResource/resourceType/Microsoft.DevTestLab%2Flabs) and login using your Dynatrace account (If you don't have access to Azure account, please contact gotc@dynatrace.com for the access).
- Click on ```Add``` at the top left panel and ```Create Devtest Lab``` blade will open. 
- Fill the ****Basic details** with the details as shown in the below screenshot. (You can fill up your own details for e.g. instead of ```BT-Training``` you can fill any other name of the customer).

    ![Create Devtest Lab - Basic Settings](../../assets/docs/training-lab/1.png)

- Go to next step **Auto-shutdown** by clicking on ```Next: Auto-shutdown``` on **Basic deatils** page (Please don't click on ```Review + create``` as this will directly take you with preconfigured settings.). In this page leave the default settings and let Auto-shutdown to off as shown in screenshot. 

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/2.png)

- Click on ```Next: Networking``` and this will take you to **Networking** step. Please select ```indiaservices_transform_lab-vnet``` from the drop down of **Virtual Network**. Keep **Subnet** to default. In **Network Isolation** you can wither Isolate lab instances or go with non-isolation. Foe more details about Network isolation in DevTest Labs, please visit this [documentation](https://docs.microsoft.com/en-us/azure/devtest-labs/network-isolation#steps-to-follow-post-lab-creation).

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/3.png)

- Go to **Tags** and enter the tags as shown in the below screenshot. In github-issue tag, please specify the issue number created [here](https://github.com/Dynatrace-India/DT-Transform-Managed-Lab/issues) before creating lab.

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/4.png)

- Once tags are added, please click on ```Review + create``` that will take you to the summary page. Click on ```Create```.

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/4a.png)

- Your lab will be created in 5-10 minutes. You can track the progress in **deployment overview** page. Once it is created, it will give you success message and a button to navigate to the resource. 

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/4b.png)

#### Creating Virual Machine in Azure DevTestLabs
- Make sure you know the confuiguration of VMs that you need along . with the OS of it. As you might have specified in the GiHub issue earlier.
- Go to [Azure DevTestLabs](https://portal.azure.com/#blade/HubsExtension/BrowseResource/resourceType/Microsoft.DevTestLab%2Flabs) and see that lab name you created in previous section. Click on the lab to open it's **Overview** page.

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/8.png)

- Click on ```Add```, Base selectotr page will open and here as per the requirement, search for the Windows 10 Pro. 

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/8a.png)

- Selet the latest build release of Windows 10 Pro. In this case, we need to select **Windows 10 Pro, Version 21H1**.
- Once you select the option, it will take you to the VM creation page where you need to enter the name of the VM and an admin user name where all other VMs canbe accessed through that credentials. Please use ```D4s_v3``` size and after selecting the size please sue **Standard SSD** instead of **Standard HDD**.

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/8b.png)

- You can go to ```Advanced settings``` and leave **Virtual network** and **Subnet selector** as it is. If you want to make virtual machine publicly accessible, you need to select ```Public``` IP address. Selecty the **Expiration date** to next 15 days and enter the number of instances it should create, In our case it is 20 so I am using 20 as the number. 

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/8c.png)

- Go back to Basic Settings and click on ```Create```. 
- This will create 20 VMs for us to use it for training. It will take around 15 to 20 minutes to create all the machines. So, sit back and relax for sometime. 

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/8d.png)

- Now if you see the screenshot above, all VMs that are created with the rule of ```Auto-shutdown``` enabled. If we leave this enabled, it will turn off VM every day at 19:00 Hours. To disable that, got o ```Configyuration & policies```> ```Auto shutdown policy``` > select ```User has no control over the schedule set by lab administrator``` and save it.

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/8e.png)

- Above step will ensure that you can set Auto shutdowm policy to all the VM at once. Thus, got to ```Auto-shutdown``` and turn it off in all VMs in the lab as shown in the screenshot below. 
    
    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/8f.png)

- Finally, All VMs are created and now they are ready to start working and do out task. But, all machines are having the same credentials which we gave at the start. So, if you want to create specific user credentials for each machine we need to go into each VM and create a user with the participant name and password. 

- As shown in above screenshot, navigate to [Virtual Machines](https://portal.azure.com/#blade/HubsExtension/BrowseResource/resourceType/Microsoft.Compute%2FVirtualMachines) and select the each virtual machine and select reset password option that is available in options blade of the VM.

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/8g.png)

- Once passwords are reset or users are created for each VM, download the RDP files of each VM and store it in a folder. Mail the RDP files and user credentials to user's individual emails. 

**Note:** Assign 2 VMs with same credentials because we are providing 2 VMs for every user. 

### Create Dynatrace Environments for users
- Create New Environements
- Create User Group
- Create User account

#### Create New Environements
- When you collect the naem of the users/participants based on the please procees to login to [Tansform Lab](https://lab.dt-transform.com)
- Make sure you have the access to cluster management console.
- Once toy login, navigate to ```Environements``` > ```Add another environment``` > Name the environment in this format, BT - <FirstNaem>. 

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/9.png)

- Create environment for each user.

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/9a.png)

#### Create User Group
- To create user group in CMC, go to ```User authentication``` from navigation menu and go to ```User groups```
- Click on ```Add new group``` and add group to have all access to their respective environments. 
- Create one group to each user and assign that group permission to have admin access to the environemnts that you have created above. 

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/9b.png)

- Create group for each user and assign their dedicated environment to them. 

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/9c.png)

#### Create User account
- Go to CMC, in ```User authentication``` > ```User accounts``` > ```Add new user```.
- Fill up details regarding the account such as First Name, Last Name, Email and Username.

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/10.png)

- Save the details and in next page, make sure you assign the user groupt ot he the user. If not, user will not be able to access the environment. 

    ![Create Devtest Lab - Auto-shutdown](../../assets/docs/training-lab/10a.png)



### Email the resources you have created to individual users
After creating VMs and Dynatrace environments to the users, please email those RDP files and passwords that you have created along with usernames. Meanwhile, if you need any help feel free to contact vishruth.harithsa@dynatrace.com at any time. 