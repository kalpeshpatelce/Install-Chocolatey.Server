# Install-Chocolatey.Server
Install Chocolatey.Server
- Problem:
⋅⋅⋅i want to install Android Studio in 500 PCS. so to install android Studio in 500 PCs Traditional way is that you have go to each computer 
1) Login to PCs
2) download Software from Server Share
3) Install software it manually (like Click next & accept etc...)

⋅⋅⋅so I googled to find some solution that automize all the above Process.
- Solution:
you have to integrate Ansible with Chocolatey Server will solve my Problem. ii is similar to Install Software in Linux



# What is Chocolatey Server?
Chocolatey Server is a simple OData feed built on top of NuGet.Server. 
Basic Idea Behind the Chocolatey Server is that to Provide Software Repository for Windows Machine.
- Linux:
As we know that if we want to install some software in linux machine we can install it from shell with unattend mode. we do not need to interact with Software Gui. It will automatically installed as per unattended Command Parameter
- Windows:
but in Windows if you want to install software you have to interact with Software Gui Like Next button or OK Button so it is very Boring Process to install software in 500 PCS.
Now the Chocolatey server come in picture.chocolatey Server provide us Software Repository 
Two Type of Chocolatey Server
- Public Chocolatey Server (refer https://chocolatey.org/packages)
- Private Chocolatey Server (we have to Create it on premises)

# Install Chocolatey Server in On-Premises
Please Refer https://chocolatey.org/docs/how-to-set-up-chocolatey-server

```bash
Setup Manually
If your Windows updates are not up to date, there are two required Windows updates you are going to need (heads up they take awhile)
Install KB2919355 - choco install KB2919355 -y - this one or the other Windows update takes a very long time to install, just be patient
Restart your machine.
Install KB2919442 - choco install KB2919442 -y (IIRC this is the one that takes forever...) -
Reboot that machine again
You need at least .NET Framework 4.6. If you don't have that or newer, then run choco install dotnet4.6.1 -y
Reboot one more time, thanks Windows!!
Install or upgrade the package - choco upgrade chocolatey.server -y
Ensure IIS is installed. You can try choco install IIS-WebServer --source windowsfeatures
Ensure that ASP.NET is installed. Try choco install IIS-ASPNET45 --source windowsfeatures (Windows Server 2012). Use IIS-ASPNET for Windows Server 2008, possibly IIS-ASPNET46 for Windows Server 2016.
Disable or remove the Default website
Set up an app pool for Chocolatey.Server. Ensure 32-bit is enabled and the managed runtime version is v4.0 (or some version of 4). Ensure it is "Integrated" and not "Classic".
Set up an IIS website pointed to the install location and set it to use the app pool.
Go to explorer and right click on c:\tools\chocolatey.server and add the following permissions:
IIS_IUSRS - Read
IUSR - Read
IIS APPPOOL\<app pool name> - Read
Right click on the App_Data subfolder and add the following permissions:
IIS_IUSRS - Modify
IIS APPPOOL\<app pool name> - Modify

````
