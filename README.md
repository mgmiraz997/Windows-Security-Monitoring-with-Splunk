# Windows-Security-Monitoring-with-Splunk
# CSE 802 Lab | Name: Mahmudul Gony Miraz | Roll: 60041

# 1. Introduction:
In this project, we will discuss the complete guideline that how to analyze a machine if it faces the (5 different types of attacks) with the help of Splunk Enterprise, Sysmon, AtomicRedTeam and other necessary metarials to analyze the complete Offensive and Defensive security to analyze different attacks

In this project I will show how to:
i) Install all the Virtual Machines containg Kali Linux/Ubuntu, Windows Server 2019
ii) Splunk, Splunk Forwarder, AtomicRedTeam, Sysmon
iii) Other necessary softwares, extentions and commands
iv) Simulating the AtomicRed Team attack: T1053.005 { Persistence | Scheduled Task } , T1218.005 { Defense Evasion | MSHTA } , T1003.001 { Credential Access | LSASS Dumping } , T1059.001 { Execution | PowerShell Download } , T1112 { Defense Evasion | Registry Modification }

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

i) Now we need to Install AtomicRedTeam so that we can simulate different types of attacks in our Windows server 2019
<img width="1918" height="878" alt="Atomic Red team install(19)" src="https://github.com/user-attachments/assets/d14755b7-4bed-4619-bcb3-bbe8e859edf9" />
 
 ii) There are different types of attacks in here we will show specific 5 attacks in here (T1053.005, T1218.005, T1003.001, T1059.001, T1112)
 <img width="1918" height="878" alt="Atomic Red team Attack Techniques(20)" src="https://github.com/user-attachments/assets/40437aed-3829-4ac6-9076-715c27e13695" />

iii) Now we are all set to perform our all 5 attacks but before performing it, we need to know the 1. Hostname of my Windows Server 2019 and the Kali machine IP from our kali machine
<img width="1918" height="878" alt="Splunk attack simulation starting 2 (23)" src="https://github.com/user-attachments/assets/f6d537ca-cce1-44df-bdad-7757fd87ae26" />
<img width="1918" height="878" alt="Splunk attack simulation starting 1  (22)" src="https://github.com/user-attachments/assets/94e2f870-2832-4d15-a3fd-ffc1b5ab5643" />

iv) Here is a small demonstration of all the Splunk Dashboard logs of my Windows Server 2019
<img width="1918" height="878" alt="Splunk Dashboard logs of Windows Server (21)" src="https://github.com/user-attachments/assets/15a86a48-01f2-42eb-b5cc-44f4499028c7" />

v) Here you can see that I am testing to call all the logs of my windows server with the help of my windows machine hostname
<img width="1918" height="878" alt="Log Checking (24)" src="https://github.com/user-attachments/assets/3282e644-ac99-4e0f-a309-64fbfb68994a" />

# Part 4: Attack Simulation
---------------------------------

# Step 1:

i) First we will simulate the 1st attack which is { ATTACK 1 — Scheduled Task Persistence }. Here is the simulation of 1st attack:

ii) Attack code: Invoke-AtomicTest T1053.005
iii) Event ID 1

<img width="1918" height="878" alt="1st attack simulation 1 (25)" src="https://github.com/user-attachments/assets/289c3eac-7316-44a2-aece-520939b9212c" />
<img width="1918" height="878" alt="1st attack simulation 2 (26)" src="https://github.com/user-attachments/assets/fe2df0a8-4acf-42a4-9f8b-576390ca3a9c" />

iv) With the help of this query, we can see the logs and changes in the windows system
Query: 
index=* host="WIN-E58857279CK" EventCode=1 Image="*schtasks.exe"
| table _time Image CommandLine ParentImage User

<img width="1918" height="878" alt="1st Attack result 1 (27)" src="https://github.com/user-attachments/assets/624ee843-ffc8-4028-a0b2-091020570b95" />
<img width="1918" height="878" alt="1st Attack result 2 (28)" src="https://github.com/user-attachments/assets/7d8f5d2c-95d8-4551-9837-b57a225c97a1" />
<img width="1918" height="878" alt="1st Attack result 3 (29)" src="https://github.com/user-attachments/assets/07d15a25-4003-400a-b82f-94b54440ba4f" />
<img width="1918" height="878" alt="1st Attack result 4 (30)" src="https://github.com/user-attachments/assets/ec2ebc15-5e03-4fb7-b059-2aa8b977e130" />

# Step 2

i) Next we will simulate the 2nd attack which is { ATTACK 2 — MSHTA Execution }. Here is the simulation of 2nd attack:

ii) Attack code: Invoke-AtomicTest T1218.005
iii) Event ID 1

<img width="1920" height="1080" alt="2nd attack simulation 1 (31)" src="https://github.com/user-attachments/assets/1212f963-52e6-46ed-bbbe-ee274df3131b" />
<img width="1920" height="1080" alt="2nd attack simulation 2 (32)" src="https://github.com/user-attachments/assets/4e8bc7af-2d4f-4482-a46b-5fa9de367706" />

iv) With the help of this query, we can see the logs and changes in the windows system
Query:
index=* host="WIN-E58857279CK" EventCode=1 Image="*mshta.exe"
| table _time Image CommandLine ParentImage User

<img width="1920" height="1080" alt="2nd attack result 1 (33)" src="https://github.com/user-attachments/assets/3d4d0c73-caaa-48d1-ac27-9fc5dac4b7f1" />
<img width="1920" height="1080" alt="2nd attack result 2 (34)" src="https://github.com/user-attachments/assets/028820ed-b54c-495c-bfc5-0264af356e87" />

# Step 3

i) Next we will simulate the 3rd attack which is { ATTACK 3 — LSASS Dumping }. Here is the simulation of 3rd attack:

ii) Attack code: Invoke-AtomicTest T1003.001
iii) Event ID 10

<img width="1920" height="1080" alt="3rd attack simulation 1 (35)" src="https://github.com/user-attachments/assets/d10d4889-9e16-4985-a71e-d1f7737bc902" />
<img width="1920" height="1080" alt="3rd attack simulation 2 (36)" src="https://github.com/user-attachments/assets/43dd16f9-0be2-4e91-9b90-d3d16c0dbe94" />
<img width="1920" height="1080" alt="3rd attack simulation 3 (37)" src="https://github.com/user-attachments/assets/dd68cdaa-d0c0-4e3a-9a2e-a9d0fcec9dad" />
<img width="1920" height="1080" alt="3rd attack simulation 4 (38)" src="https://github.com/user-attachments/assets/02f864da-bfe6-443a-b959-9aae91269acc" />
<img width="1920" height="1080" alt="3rd attack simulation 5 (39)" src="https://github.com/user-attachments/assets/f8321fa6-3483-4d93-8de5-942a8e6546eb" />
<img width="1920" height="1080" alt="3rd attack simulation 6 (40)" src="https://github.com/user-attachments/assets/a40edd82-0429-4ec7-a81e-7ace3fadc552" />
<img width="1920" height="1080" alt="3rd attack simulation 7 (41)" src="https://github.com/user-attachments/assets/3d78822a-5583-4a55-a0e8-ec85d3042468" />

iv) With the help of this query, we can see the logs and changes in the windows system:
Query:
index=* host="WIN-E58857279CK" EventCode=10 TargetImage="*lsass.exe"
| table _time SourceImage TargetImage GrantedAccess User

<img width="1920" height="1080" alt="3rd attack result 1 (42)" src="https://github.com/user-attachments/assets/4efe380f-e83e-41f6-a99a-2a65c24d937f" />
<img width="1920" height="1080" alt="3rd attack result 2 (43)" src="https://github.com/user-attachments/assets/1a281818-1398-4a9c-aec1-f17624b2adf5" />
<img width="1920" height="1080" alt="3rd attack result 3 (44)" src="https://github.com/user-attachments/assets/403817c1-3fb3-401f-af7d-72b92c4a1448" />


# Step 4

i) Next we will simulate the 4th attack which is { ATTACK 4 — PowerShell Download Execution }. Here is the simulation of 4th attack:

ii) Attack code: Invoke-AtomicTest T1059.001
iii) Event ID 1

<img width="1920" height="1080" alt="4th attack simulation 1 (45)" src="https://github.com/user-attachments/assets/bb92e8e8-a862-46cf-a9c3-5a17c947c03c" />
<img width="1920" height="1080" alt="4th attack simulation 2 (46)" src="https://github.com/user-attachments/assets/6c171fa9-5f47-4aaa-9541-1d4e85c480e4" />
<img width="1920" height="1080" alt="4th attack simulation 3 (47)" src="https://github.com/user-attachments/assets/44b445b5-a64e-4d28-9f97-62db35a02d1e" />
<img width="1920" height="1080" alt="4th attack simulation 4 (48)" src="https://github.com/user-attachments/assets/aee4b533-6368-4448-b761-48ebcf3a6788" />
<img width="1920" height="1080" alt="4th attack simulation 5 (49)" src="https://github.com/user-attachments/assets/fe680950-7976-49ed-92d9-81e860081677" />
<img width="1920" height="1080" alt="4th attack simulation 6 (50)" src="https://github.com/user-attachments/assets/68056cb0-0ffe-4ceb-bb7e-6addc1308c6e" />
<img width="1920" height="1080" alt="4th attack simulation 7 (51)" src="https://github.com/user-attachments/assets/de351202-b109-42f5-9d72-46bca1820b76" />
<img width="1920" height="1080" alt="4th attack simulation 8 (52)" src="https://github.com/user-attachments/assets/8b9c37ac-6237-4962-9a0f-4b4e36a655d0" />
<img width="1920" height="1080" alt="4th attack simulation 9 (53)" src="https://github.com/user-attachments/assets/2d54309f-14a4-44ba-89fd-6bbdd4a3c480" />
<img width="1920" height="1080" alt="4th attack simulation 10 (54)" src="https://github.com/user-attachments/assets/f08bd6a6-7263-4b05-9f79-1ccaf3bbff10" />
<img width="1920" height="1080" alt="4th attack simulation 11 (55)" src="https://github.com/user-attachments/assets/9b6a7e0b-c48f-4547-a7f1-fbd141f97c8f" />
<img width="1920" height="1080" alt="4th attack simulation 12 (56)" src="https://github.com/user-attachments/assets/9c363f35-53f4-4f38-97bc-eee1b65230cc" />

iv) With the help of this query, we can see the logs and changes in the windows system:
Query:
index=* host="WIN-E58857279CK" EventCode=1 Image="*powershell.exe"
| search CommandLine="*DownloadString*"
| table _time Image CommandLine ParentImage User

<img width="1920" height="1080" alt="4rd attack result 1 (57)" src="https://github.com/user-attachments/assets/ade7cd82-340d-4192-968d-dc7cd898c810" />

# Step 5

i) Finally, we will simulate the 5th attack which is { ATTACK 5 — Registry Modification }. Here is the simulation of 5th attack:

ii) Attack code: Invoke-AtomicTest T1112
iii) Event ID 13

<img width="1920" height="1080" alt="5th attack simulation 1 (58)" src="https://github.com/user-attachments/assets/a18e1750-abfb-40d4-bd8a-88ee56991c9e" />
<img width="1920" height="1080" alt="5th attack simulation 2 (59)" src="https://github.com/user-attachments/assets/eb629eb1-a64c-4c76-8e65-14a491323e94" />
<img width="1920" height="1080" alt="5th attack simulation 3 (60)" src="https://github.com/user-attachments/assets/d2d7b822-f044-4cd7-a668-9b4f768db4a7" />
<img width="1920" height="1080" alt="5th attack simulation 4 (61)" src="https://github.com/user-attachments/assets/37db720e-7d36-46fc-8e31-f943135e675d" />

iv) With the help of this query, we can see the logs and changes in the windows system:
Query 1 ( For detecting every details ):
index=* host="WIN-E58857279CK" EventCode=13
| table _time Image TargetObject Details User

<img width="1920" height="1080" alt="5rd attack result 1 1 (62)" src="https://github.com/user-attachments/assets/dd40c2f0-a143-4244-938c-a91c0eddebab" />
<img width="1920" height="1080" alt="5rd attack result 1 2 (63)" src="https://github.com/user-attachments/assets/a481e589-9868-4fea-825c-482a5f22b62c" />
<img width="1920" height="1080" alt="5rd attack result 1 3 (64)" src="https://github.com/user-attachments/assets/7799bba8-f27e-4816-92b4-e0c556fd946a" />

query 2 ( For defender registry modifications )
index=* host="WIN-E58857279CK" EventCode=13 TargetObject="*Windows Defender*"
| table _time Image TargetObject Details

<img width="1920" height="1080" alt="5rd attack result 2 1 (65)" src="https://github.com/user-attachments/assets/87fc2922-5aeb-40bc-8f3f-b9b3c8757ba2" />
<img width="1920" height="1080" alt="5rd attack result 2 2 (66)" src="https://github.com/user-attachments/assets/94d12853-d02f-4c43-8c33-a09326f093dd" />
<img width="1920" height="1080" alt="5rd attack result 2 3 (67)" src="https://github.com/user-attachments/assets/5a110182-a99b-4702-a4ad-093f4e367115" />

# Part 5: Splunk Dashboard
----------------------------
Here is my Splunk Dashboard named: Windows Server Monitoring containing all the active logs from the Windows Server 2019

<img width="1920" height="1080" alt="Splunk Dashboard 1 (68)" src="https://github.com/user-attachments/assets/68878825-424f-4fd0-b8f7-7c8e30848a0c" />
<img width="1920" height="1080" alt="Splunk Dashboard 2 (69)" src="https://github.com/user-attachments/assets/fce0ab15-5805-490b-99a4-0470a0f98630" />
<img width="1920" height="1080" alt="Splunk Dashboard 3 (70)" src="https://github.com/user-attachments/assets/608bb410-5e58-44d0-bd89-4ebde7f88169" />
<img width="1920" height="1080" alt="Splunk Dashboard 4 (71)" src="https://github.com/user-attachments/assets/b82ddb22-b65c-4699-8947-6d89d12eb559" />
<img width="1920" height="1080" alt="Splunk Dashboard 5 (72)" src="https://github.com/user-attachments/assets/548d962d-76bc-4e5d-8e7e-e15d26c0bb7a" />
<img width="1920" height="1080" alt="Splunk Dashboard 6 (73)" src="https://github.com/user-attachments/assets/22a94d90-3556-4c20-be69-4c1ad2522dc0" />
<img width="1920" height="1080" alt="Splunk Dashboard 7 (74)" src="https://github.com/user-attachments/assets/65c156f6-31a8-446a-ae87-3ff345d85f23" />
<img width="1920" height="1080" alt="Splunk Dashboard 8 (75)" src="https://github.com/user-attachments/assets/e4702f24-949e-45f3-80e7-aae88723beaf" />
<img width="1920" height="1080" alt="Splunk Dashboard 9 (76)" src="https://github.com/user-attachments/assets/570ae8da-b329-4311-84a3-418e3a45c5b8" />
<img width="1920" height="1080" alt="Splunk Dashboard 10 (77)" src="https://github.com/user-attachments/assets/7176cf83-ad76-46c5-b00c-ed7c672e96f5" />
<img width="1920" height="1080" alt="Splunk Dashboard 11 (78)" src="https://github.com/user-attachments/assets/581b5181-9f97-4afc-b217-a00d4e236fa3" />
<img width="1920" height="1080" alt="Splunk Dashboard 12 (79)" src="https://github.com/user-attachments/assets/6f09acff-4927-41ab-af9f-8cae6626a472" />
<img width="1920" height="1080" alt="Splunk Dashboard 13 (80)" src="https://github.com/user-attachments/assets/b5e1a102-9b4f-4d62-a713-bb81c2553c2f" />
<img width="1920" height="1080" alt="Splunk Dashboard 14 (81)" src="https://github.com/user-attachments/assets/223b290c-5a29-4a13-9093-7a8c0a952e1f" />
<img width="1920" height="1080" alt="Splunk Dashboard 15 (82)" src="https://github.com/user-attachments/assets/90a1a75a-6cff-45f0-ab2c-44a0bd23254e" />
<img width="1920" height="1080" alt="Splunk Dashboard 16 (83)" src="https://github.com/user-attachments/assets/945c45d3-7620-424a-ab95-a22656a796fe" />
<img width="1920" height="1080" alt="Splunk Dashboard 17 (84)" src="https://github.com/user-attachments/assets/8ccf9cad-7c8e-4b6b-b75d-7b2ad60011b6" />
<img width="1920" height="1080" alt="Splunk Dashboard 18 (85)" src="https://github.com/user-attachments/assets/253e0aa8-76f7-4687-bf4b-e46dc0de67c8" />
<img width="1920" height="1080" alt="Splunk Dashboard 19 (86)" src="https://github.com/user-attachments/assets/86faca1d-f0c0-4ffe-a6db-63a2b0d8def7" />
<img width="1920" height="1080" alt="Splunk Dashboard 20 (87)" src="https://github.com/user-attachments/assets/c41d9298-a495-4c84-9133-0d144a837a4d" />
<img width="1920" height="1080" alt="Splunk Dashboard 21 (88)" src="https://github.com/user-attachments/assets/47b3af13-7073-48c3-9416-3c8202f87bba" />
<img width="1920" height="1080" alt="Splunk Dashboard 22 (89)" src="https://github.com/user-attachments/assets/6233271f-ea7a-490f-9f1d-7bdaf09a01e4" />
<img width="1920" height="1080" alt="Splunk Dashboard 23 (90)" src="https://github.com/user-attachments/assets/9141ad84-60a9-4586-89e7-9032279af8ec" />
<img width="1920" height="1080" alt="Splunk Dashboard 24 (91)" src="https://github.com/user-attachments/assets/e5556ee4-f0ae-418f-9a4c-4a2a05089229" />
<img width="1920" height="1080" alt="Splunk Dashboard 25 (92)" src="https://github.com/user-attachments/assets/8ecb87b5-8a05-4017-a0ff-c494ced75744" />
<img width="1920" height="1080" alt="Splunk Dashboard 26 (93)" src="https://github.com/user-attachments/assets/011114a1-9768-4ac5-bea3-73e97949b537" />
<img width="1920" height="1080" alt="Splunk Dashboard 27 (94)" src="https://github.com/user-attachments/assets/6724c06e-2311-4d36-b044-dbccabdadf41" />
<img width="1920" height="1080" alt="Splunk Dashboard 28 (95)" src="https://github.com/user-attachments/assets/7e95e103-6725-470c-b42a-75ab4af3456f" />
<img width="1920" height="1080" alt="Splunk Dashboard 29 (96)" src="https://github.com/user-attachments/assets/672fa8ff-3614-4afc-8c6c-d4ed72e1e08e" />
<img width="1920" height="1080" alt="Splunk Dashboard 30 (97)" src="https://github.com/user-attachments/assets/2f95d56b-1f9a-4a5b-aa2f-9a4394e0a54b" />

# Part 6: Final Thoughts
--------------------------
From my entire project, the most helpful Sysmon Event IDs for each detection of attacks were:

1) T1053.005 – Scheduled Task/Job:

i) Most Helpful Event ID: Sysmon Event ID 1 (Process Creation)
ii) Reason:
Event ID 1 was the most useful for detecting scheduled task abuse because it records the execution of schtasks.exe and PowerShell scheduled task commands. The event provides important details such as the process name, command line arguments, parent process, user account, and timestamp.

2) T1218.005 – Mshta

i) Most Helpful Event ID: Sysmon Event ID 1 (Process Creation)
ii) Reason:
Event ID 1 captures the execution of mshta.exe, including the command line used to launch the process. This allows analysts to identify suspicious script execution through the Microsoft HTML Application Host.

3) T1003.001 – LSASS Credential Dumping

i) Most Helpful Event ID: Sysmon Event ID 10 (Process Access)
ii) Reason:
Event ID 10 records when a process attempts to access another process. It is particularly useful for detecting credential dumping because it logs attempts to access lsass.exe, a common target used by tools such as Mimikatz.

4) T1059.001 – PowerShell

i) Most Helpful Event ID: Sysmon Event ID 1 (Process Creation)
ii) Reason:
Event ID 1 captures PowerShell execution, including command-line arguments, encoded commands, parent-child process relationships, and execution context. This makes it one of the most valuable events for detecting malicious PowerShell activity.

5) T1112 – Modify Registry

i) Most Helpful Event ID: Sysmon Event ID 13 (Registry Value Set)
ii) Reason:
Event ID 13 records registry value modifications and provides details about the modified registry key, the new value, and the process responsible for the change. This event is highly effective for detecting registry-based persistence and configuration changes.

# Summary:
During the attack simulations, Sysmon Event IDs 1, 10, and 13 were the most valuable telemetry sources. Event ID 1 provided visibility into process execution, Event ID 10 helped identify credential access attempts against LSASS, and Event ID 13 captured registry modifications used for persistence. Together, these events enabled effective detection and analysis of the Atomic Red Team attack scenarios within the Splunk monitoring environment.

























