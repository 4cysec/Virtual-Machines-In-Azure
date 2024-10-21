 <h1>Virtual-Machines-In-Azure</h1>

<h2>Description</h2>
Vulnerability scans are executed on a Windows 10 virtual machine using Tenable's Nessus Essentials tool. The Windows 10 machine is set up with a few different configurations to analyze the differences in scan results. 

<h2>Languages and Utilities Used</h2>

- <b>Nessus Essentials 10.8.1</b> 


<h2>Environments Used </h2>

- <b>VMWare Workstation Pro 17</b>
- <b>Windows 10 Pro</b>



<h2>Project walk-through:</h2>

After Setting Up Windows 10 Pro VM Machine and registering Nessus Essentials we can begin our scans!

We will start with a non credentialed basic network scan.

-->Click New Scan then -->Click Basic Network Scan

<img src= https://github.com/user-attachments/assets/c63188de-5a19-426d-bb16-72ac6876f552 width="600" height="400" />


<img src= https://github.com/user-attachments/assets/2f1de274-ba8a-4633-81b5-16110fb18fd5 width="700" height="500" />



We enter a name for the scan and the IP address of our Windows 10 machine --> Click Save.

<img src= https://github.com/user-attachments/assets/1bdb94f3-94a9-405a-b742-30ed2f7a7294 width="700" height="400" />


In the "My Scans" page, -->Click Launch button to start the created scan.


<img src= https://github.com/user-attachments/assets/d39240ac-85ca-4cbe-b402-cc15ceeec10f width="800" height="300" />


Clicking on the row with the labeled scan opens the page with the scan results.

<img src= https://github.com/user-attachments/assets/78d5a7e3-e88f-426d-b137-5692cdd2e1fc width="800" height="300" />


Vulnerabilities are shown in categories of risk levels.

<img src= https://github.com/user-attachments/assets/9337405e-0171-48a0-bc6e-15f60fa3496c width="700" height="400" />


Clicking on the row will open the page listing the vulnerabilities by their risk levels.

Clicking each vulnerability provides more information such as the description of the vulnerability, the solution for
remediation and an Output message with some information.



<img src= https://github.com/user-attachments/assets/58e65f47-335c-4498-9e6b-5f5add38aff2 width="700" height="400" />


<img src= https://github.com/user-attachments/assets/244576f4-85d8-4a3c-a889-722a0f8cb5ad width="700" height="500" />


Note that the vulnerabilities listed under "Info" are not given risk value but provide some information about the network.

___________________________________________________________________________________________________________________________________________________________

Credentialed Scans

In order to run credentialed scans on the VM we will configure the Windows 10 VM. This done since our machine
is not connected to a domain.

Entering Services.msc in the search bar we will enable remote registry allowing the scan to find any risky configurations.

<img src= https://github.com/user-attachments/assets/c770cd48-4f32-4e0e-a167-f5c5554028ab width="700" height="500" />


Next, we navigate to User Account Control Settings and change the setting to Never notify for experimental purposes.

<img src= https://github.com/user-attachments/assets/9e520667-e960-46a0-831d-1e5b8577d4f9 width="600" height="400" />


We will further disable account controls by navigating to the registry(regedit) and editing a registry key.

Navigate to HKLM-->Software-->Microsoft-->Windows-->CurrentVersion-->Policies-->System

Within System we add D-Word labed "LocalAccountTokenFilterPolicy" and set the value to 1.

<img src= https://github.com/user-attachments/assets/a505ff50-aa6d-4734-97c4-a9af116d3289 width="600" height="400" />


In Nessus, we checkmark our previous scan. The More Tab appears. --> Select Configure in the drop down.

<img src= https://github.com/user-attachments/assets/db371c04-09c9-4d53-94a4-9bbd791e4211 width="900" height="300" />


After changing the scan's name in the settings tab, we click the Credentials tab then Windows to fill in our credentials.
These are our log in credentials into the Windows VM. --> Save

<img src= https://github.com/user-attachments/assets/5e13d2e7-947c-479c-b054-bcb4b85cf533 width="900" height="300" />



Once the credentialed scan is launched we can see that the vulnerability levels have increased.

<img src= https://github.com/user-attachments/assets/068d356e-d06c-4917-b995-38dd30cc5226 width="900" height="300" />


Running a credentialed scan detected far greater vulnerabilties than the non credentialed scan. 

Let's take a look at the critical vulnerability and what we would need to do to remediate it.

We Click on Mixed then Critical to find the descripion and solution.

<img src= https://github.com/user-attachments/assets/33e4387f-ba95-4d04-99fb-3d2d0b9c6a23 width="600" height="400" />

<img src= https://github.com/user-attachments/assets/d6f77e09-0b59-46a5-ac98-1e2c877ba030 width="600" height="400" />


The vulnerability is a remote code execution vulnerability within the Microsoft 365 Office app version.

<img src= https://github.com/user-attachments/assets/9488450b-3840-4658-b12c-697b74da4537 width="600" height="400" />


We can resolve the issue by updating the version of the app or uninstalling it.

Let's remove the app and launch the scan again and see if the critical vulnerability shows up in the results.

<img src= https://github.com/user-attachments/assets/5627d43e-5d3d-4c76-b003-fe87fb04339b width="600" height="400" />


As we can see from the results above, the critical vulnerability has been resolved.

Let's see what happens when we install Windows 10 Updates.

<img src= https://github.com/user-attachments/assets/6cbe7cbc-e815-4a83-8808-db0accfd3cb2 width="600" height="400" />


Navigating to the History Tab, we can compare our scans. We can see that we have one less vulnerability in our post
windows update scan.

<img src= https://github.com/user-attachments/assets/ec1e382b-ba09-4cb1-8946-c930755da8f3 width="600" height="400" />

<img src= https://github.com/user-attachments/assets/a3023c50-b58c-4f24-8e64-e37fac69bfdd width="600" height="400" />
