# Windows-Security-Monitoring-with-Splunk
CSE 802 Lab | Roll: 60041

# 1. Introduction:
In this project, we will discuss the complete guideline that how to analyze a machine if it faces the (5 different types of attacks) with the help of Splunk Enterprise, Sysmon, AtomicRedTeam and other necessary metarials to analyze the complete Offensive and Defensive security to analyze different attacks

In this project I will show how to:
i) Install all the Virtual Machines containg Kali Linux/Ubuntu, Windows Server 2019
ii) Splunk, Splunk Forwarder, AtomicRedTeam, Sysmon
iii) Other necessary softwares, extentions and commands

The project will contain different parts adn each part will contain different steps which help us to go further step by step setup to analyzing different attacks

# 2. Complete Blueprint

<img width="1536" height="1024" alt="Complete Blueprint" src="https://github.com/user-attachments/assets/ffc02f0b-049e-47ea-9544-fe3311d9828b" />

Details:
i) From here as we can see that the after successful installation of Splunk in kali machine and installation of AtomicredTeam, Splunk, Splunk Forwarder and Sysmon we are forwarding all the logs and any kind of alerts to our Blue Team machine (Kali machine) to analyze different types of logs
ii) From the Windows server 2019(Red Team), the AtomicRedTeam automeically generation differnet types of attacks with the help of commands and these attacks were forwarding with the help of Splunk Forwarder. These attacked logs were forward to kali machine and with the help of different queries, we were able to analyze different attacks and storing all the results in the Splunk Dashboards

# 3. Configuration

# Part 1: Istalling necessary OSs
-----------------------------------

# Step 1:
i) First we need to install both Kali/ Ubuntu OS and Windows server 2019
ii) Both should be an ISO file so that we can install it in our Virtual Machine
iii) Kali linux: https://www.kali.org/get-kali/#kali-installer-images | windows server 2019: https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019  |  VMWare: https://getintopc.com/softwares/virtualization/vmware-workstation-pro-2023-free-download/
iv) After installation, we need to cofigure our both machines. below I am giving the minimum requiremes to set for both of the machines

# Part 2: Kali Machine Configuration
-----------------------------------------

# Step 1
kali machine:

<img width="1920" height="1080" alt="Screenshot (182)" src="https://github.com/user-attachments/assets/5c353c9f-69fd-4c47-b791-33ef99e723b9" />

Windows server 2019:

<img width="1920" height="1080" alt="Screenshot (183)" src="https://github.com/user-attachments/assets/7c410ffc-fcf5-49ae-8922-c8a11f684e64" />

# Stpe 2:

i) After installation of OS we need to check the IP Address of the Kali machine
<img width="1918" height="878" alt="kali ip (1)" src="https://github.com/user-attachments/assets/2171b89c-3872-4a73-a537-40d990108a7f" />

ii) Then we need to install and set up the Spllunk in our kali machine
<img width="1918" height="878" alt="kali splunk install 1 (2)" src="https://github.com/user-attachments/assets/863662b0-12cf-4ca5-8db2-4ba56019fa1e" />
<img width="1918" height="878" alt="kali splunk install 1 (3)" src="https://github.com/user-attachments/assets/b68a1803-5dd1-4bde-ae1b-7023877b6cd8" />
<img width="1918" height="878" alt="kali splunk install 1 (4)" src="https://github.com/user-attachments/assets/b9d802fe-bdf9-4e96-a130-4252e2101016" />

iii) Now we need to setup the Splunk in our kali machine
<img width="1918" height="878" alt="starting splunk (5)" src="https://github.com/user-attachments/assets/9581a754-1155-4f3f-b881-ad312b2140dd" />
<img width="1918" height="878" alt="auto start splunk (6)" src="https://github.com/user-attachments/assets/5892dfa5-5aec-4a11-a996-1ec0dd4f231e" />

iv) Now we are ready to log in to our Splunk Enterprise to analyze all the attacks happens in our windows server 2019
<img width="1918" height="878" alt="accessing splunk (7)" src="https://github.com/user-attachments/assets/0ac84c11-fee7-4a92-99f8-a104e89dd75f" />

v) After login, we will see this type of interface
<img width="1918" height="878" alt="splunk interface (8)" src="https://github.com/user-attachments/assets/820892cc-458a-4379-aa7d-7a62bcad9eba" />

vi) Now we need to import the port 9997 so that our Kali machine can commuicate with the winsows server
<img width="1918" height="878" alt="enabling port 9997 (9)" src="https://github.com/user-attachments/assets/c5c31358-11dd-4061-86d1-939093cc2661" />
<img width="1918" height="878" alt="enabling port 9997 2 (10)" src="https://github.com/user-attachments/assets/2463b57e-4849-4cf5-aaad-a56be6db9199" />
<img width="1918" height="878" alt="enabling port 9997 2 (11)" src="https://github.com/user-attachments/assets/011c0551-4ded-4437-9cb3-18f0e4f1741e" />

# Part 3: Windows Server 2019 Configuration
---------------------------------------------

# Step 1: 

i) After configuring our kali machine, we need to configure our windows server 2019
<img width="1920" height="1080" alt="Setting up windows server (12)" src="https://github.com/user-attachments/assets/c6aae756-ee8c-4b8b-8d2d-b086ca8790dc" />

ii) In the windows server, we need to install the Sysmon
<img width="1920" height="1080" alt="Sysmon install  1 (13)" src="https://github.com/user-attachments/assets/b3c4268e-5e1c-449a-9e1f-4d8fee09f809" />
<img width="1920" height="1080" alt="Sysmon install  2 (14)" src="https://github.com/user-attachments/assets/8e174783-1cc5-4b34-8d0a-cdaa0397b9a8" />

iii) To cross check the Sysmon has been actually installed or not, we need to check it in: Services and Windows Event Viewer
<img width="1920" height="1080" alt="Sysmon install  3 (15)" src="https://github.com/user-attachments/assets/6e828023-8beb-429d-ab48-a5a003ece9e9" />
<img width="1920" height="1080" alt="Sysmon install  4 (16)" src="https://github.com/user-attachments/assets/440b6d66-b78c-4da3-88f6-97993e0498bd" />

# Step 2:

i) Next we need to install the Splunk Forwarder so that the Windows server can forward the logs to the kali machine
<img width="1920" height="1080" alt="Splunk Forwarding install (18 1)" src="https://github.com/user-attachments/assets/0011a617-984a-4720-baf0-95da3752ea71" />
<img width="1920" height="1080" alt="Splunk Forwarding install (18 2)" src="https://github.com/user-attachments/assets/91a02963-ad92-44ee-ab73-8e20ac3522ee" />
<img width="1920" height="1080" alt="Splunk Forwarding install (18 3)" src="https://github.com/user-attachments/assets/a657d41e-7e7b-42b1-a282-cfaeffcb8f08" />

iv) Here we need to select the (Local System) instead of (Virtual Account)
<img width="1920" height="1080" alt="Splunk Forwarding install (18 4)" src="https://github.com/user-attachments/assets/a0523c9e-430c-4c04-9238-28bfefb96f17" />
<img width="1920" height="1080" alt="Splunk Forwarding install (18 5)" src="https://github.com/user-attachments/assets/4a92d924-799d-486d-a8b1-1b25d77bfd3a" />
<img width="1920" height="1080" alt="Splunk Forwarding install (18 6)" src="https://github.com/user-attachments/assets/3ebd2bef-987c-45d2-a88c-f22f5d02ae3d" />

v) Now we need to provide the username and password
<img width="1920" height="1080" alt="Splunk Forwarding install (18 7)" src="https://github.com/user-attachments/assets/6af74f6f-9301-46f4-989e-1b5d03cfcc7c" />

vi) After that we need to insert the Deployment server: IP + Port and Receiving indexer: IP + Port
<img width="1920" height="1080" alt="Splunk Forwarding install (18 8)" src="https://github.com/user-attachments/assets/09257db2-915c-4be6-a70f-8d3a2f64b403" />
<img width="1920" height="1080" alt="Splunk Forwarding install (18 9)" src="https://github.com/user-attachments/assets/ef5aee37-fb0b-469a-b0a9-4762b82f2554" />

vii) Now just install the Splunk Forwarder
<img width="1920" height="1080" alt="Splunk Forwarding install (18 10)" src="https://github.com/user-attachments/assets/90d04284-224e-4f55-a991-5af68296de7c" />

viii) For Corss checking the Splunk forwarder has been successfully installed or not we will check it from: Windows Services
<img width="1920" height="1080" alt="Splunk Forwarding receiving index2 (18)" src="https://github.com/user-attachments/assets/bcf9cab2-3d7d-4065-9901-3cafeb34eaaf" />

ix) Here we can see the active forwarding ports and IPs
<img width="1920" height="1080" alt="Splunk Forwarding receiving index(17)" src="https://github.com/user-attachments/assets/94ec0e60-8547-4aac-86cd-8a2dbe37ccc1" />

# Step 3

i) 

















