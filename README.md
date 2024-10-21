 <h1>Virtual-Machines-In-Azure</h1>

<h2>Description</h2>
Brief set up of a Windows Server 2019 VM and Windows 10 VM in Microsoft Azure. 


<h2>Environments Used </h2>
- <b>Microsoft Azure Cloud</b>
- <b>Windows Server 2019</b>
- <b>Windows 10 Pro</b>



<h2>Project walk-through:</h2>

After creating an account in Azure, we proceed with the following:

Click on Virtual Machines under the Azure services heading.

![Screenshot 2024-10-10 230309](https://github.com/user-attachments/assets/35d0ba4f-4215-430c-9d7e-f7eb6bdb92b5)


We will create a resource group named HomeLab. Both of the virtual machines will be under this resource group.

The first VM we create will be Server2019 picked from the drop down.

The region that allows us to have the features we want in our VM is West US2.

Security is set as standard.

We will not use redundancies in Availibility Options in this lab.

In this lab, we select a VM with 4-core CPUs 

![Screenshot 2024-10-10 233210](https://github.com/user-attachments/assets/768d26c3-52a4-485c-9c31-8908446129c7)

The Administration Account name chosen for this lab is helpdesk and a password is created.

For purposes of this lab we will be using RDP so we select the public inbound port for RDP.

Then select review + create.


![Screenshot 2024-10-10 233340](https://github.com/user-attachments/assets/35479f6f-5b7b-42ca-8d5b-1626ff2bd762)


In the summary page we can see that the validation for our VM has passed. Clicking create will deploy the Windows Server2019
VM.

![Screenshot 2024-10-10 233502](https://github.com/user-attachments/assets/de1a2db3-6df0-4fba-80cc-d7247eac46ec)

Now that we have our server2019 VM, we navigate to the VM (overview) and click connect

![Screenshot 2024-10-12 232133](https://github.com/user-attachments/assets/2aae82c7-41f5-43e1-91c3-baaa0d61e5b2)

Download the RDP File and click on the file.

Fill in the Admin sign in credentials. In our case for helpdesk and the VM will boot up.


![Screenshot 2024-10-12 232231](https://github.com/user-attachments/assets/914acef5-bb52-4fca-83b3-97d0899e8497)


![Screenshot 2024-10-12 232444](https://github.com/user-attachments/assets/64975471-953e-4808-a622-4406a9e41ad7)


![Screenshot 2024-10-12 232505](https://github.com/user-attachments/assets/78418615-86ec-4f21-9d68-492cf64232a3)



<img src= https://github.com/user-attachments/assets/9337405e-0171-48a0-bc6e-15f60fa3496c width="700" height="400" />



___________________________________________________________________________________________________________________________________________________________

