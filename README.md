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
# Step 1:
i) First we need to install both Kali/ Ubuntu OS and Windows server 2019
ii) Both should be an ISO file so that we can install it in our Virtual Machine
iii) Kali linux: https://www.kali.org/get-kali/#kali-installer-images | windows server 2019: https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019  |  VMWare: https://getintopc.com/softwares/virtualization/vmware-workstation-pro-2023-free-download/
iv) After installation, we need to cofigure our both machines. below I am giving the minimum requiremes to set for both of the machines

kali machine
---------------
<img width="1920" height="1080" alt="Screenshot (182)" src="https://github.com/user-attachments/assets/5c353c9f-69fd-4c47-b791-33ef99e723b9" />

Windows server 2019
------------------------
<img width="1920" height="1080" alt="Screenshot (183)" src="https://github.com/user-attachments/assets/7c410ffc-fcf5-49ae-8922-c8a11f684e64" />






















