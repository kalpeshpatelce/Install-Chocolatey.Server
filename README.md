# Install-Chocolatey.Server
Install Chocolatey.Server
## Problem:
I want to Install Android Studio in 500 PCS. To install Android Studio in 500 PCs Traditional way is that you have go to each computer 
1) Login to PCs
2) download Software from Server Share
3) Install software it manually (like Click next & accept etc...)

So I googled to find some solution that automize all the above Process.
## Solution:
You have to Integrate Ansible with Chocolatey Server will solve the Problem. ii is similar to Install Software in Linux



# What is Chocolatey Server?
Chocolatey Server is a simple OData feed built on top of NuGet.Server. 
Basic Idea Behind the Chocolatey Server is that to Provide Software Repository for Windows Machine.
## Linux:
As we know that if we want to install some software in linux machine we can install it from shell with unattend mode. we do not need to interact with Software Gui. It will automatically installed as per unattended Command Parameter
## Windows:
But in Windows if you want to install software you have to interact with Software Gui Like Next button or OK Button so it is very Boring Process to install software in 500 PCS.
Now the Chocolatey server come in picture.chocolatey Server provide us Software Repository 
Two Type of Chocolatey Server
- Public Chocolatey Server (refer https://chocolatey.org/packages)
- Private Chocolatey Server (we have to Create it on premises)

# Install Chocolatey Server in On-Premises
Please Refer https://chocolatey.org/docs/how-to-set-up-chocolatey-server

To install and configure Chocolatey.Server using PowerShell run the following script in an elevated administrator session:
### Download Script from Below URL
https://github.com/kalpeshpatelce/Install-Chocolatey.Server/blob/master/InstallChocolateyServer-OnPremises.ps1

## Please check IIS Manager
![Image of IIS](https://media-exp1.licdn.com/dms/image/C4E12AQHf-HDtk-eTTw/article-inline_image-shrink_1500_2232/0?e=1603324800&v=beta&t=SHIAeXWC7dK9PlL9if4dT5xi1m_hhDlSf-zajIeM8sQ)

## Check Chocolatey Server Configured successfully By Enter URL http://localhost in Browser
![Image of IIS](https://media-exp1.licdn.com/dms/image/C4E12AQG092JYA3XbxA/article-inline_image-shrink_1500_2232/0?e=1603324800&v=beta&t=hJeEdNzupspa4_MBppSJfq487mdGXZcHrM0xhzMqnCc)

## Set APIKey For Your Chocolatey Server

Open Powershell run as administrator and type below command

```bash
choco setapikey -s="http://ServerIP/chocolatey " -k ="123456"
````
