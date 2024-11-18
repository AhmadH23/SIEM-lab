# SIEM-lab

## Description

The purpose of this project is to gain hands-on experience with Elastic Cloud, which is used to detect and respond to threats by unifying SIEM, cloud security, and endpoint security, and learn how to remediate vulnerabilities. 

The project focuses on two crucial steps in the Vulnerability Management Lifecycle. By using Elastic Cloud, I will use Linux to connect to Elastic Cloud locally and run some scans on Linux like Nmap, then creating a dashboard on Elastic Cloud which will allow me to see what scans were done on Linux. I will then create an alert for a specific scan, so for example the alert will be whenever Nmap is run, then it will send an alert to the admin via email.

Feel free to follow along!

## Utilities Used

Elastic Cloud

## Environments Used
- Virtual Box
- Linux

## Links
- **Virtual Box**: [https://www.vmware.com/products/workstation-player/workstation-player-evaluation.html](https://www.virtualbox.org/)
- **Linux**: https://www.kali.org/get-kali/#kali-platforms
- **Elastic Cloud**: https://www.elastic.co/cloud

<h1 align="center">
Program Walk-through
</h1>

 <p align="center"> <b>First I downloaded and installed Virtual Box so that I can run Linux through a virtual machine.</b></p>
 
![Screenshot 2024-11-11 at 22 10 34](https://github.com/user-attachments/assets/2bfeda9e-ddb2-45f9-8f29-292af46f1ffa)

<p align="center"><b> Once downloaded, install it and run the application, once opened it will look like this:</b></p>

![virtualbox-main-empty](https://github.com/user-attachments/assets/5606b1e2-9fd8-4755-891a-e8143365ef5e)

<p align="center"><b>  Then I installed Kali Linux. First I will go to the Kali website:  https://www.kali.org/get-kali/#kali-platforms  
and click on Installer Images.</b></p>
<p></p>



![Screenshot 2024-11-12 at 22 25 33](https://github.com/user-attachments/assets/3ab97ccb-674b-4028-86c4-70f24af64f20)

<p align="center"><b>It took take me to this page, I selected the appropriate install based on my operating system.</b></p>

![Screenshot 2024-11-12 at 22 30 01](https://github.com/user-attachments/assets/12062e15-54cf-4b60-a31d-4ff061d0934e)

<p align="center"> <b>Once I have installed the correct package, I then opened Virtual Box and created a new machine using the Kali Linux OS I just installed. Click on the New button on virtual box to start the process.</b> </p>

![Screenshot 2024-11-13 at 20 43 16](https://github.com/user-attachments/assets/eb173614-326c-41f0-9447-f33fa441d30c)

<p align="center"><b>To start I chose a name for my operating system, I went with Kali Linux. For the ISO image this will be the Kali Linux install that I installed earlier on, once I have selected the ISO image hit the next button.</b></p>


![Screenshot 2024-11-13 at 21 24 21](https://github.com/user-attachments/assets/b1cac207-2e13-4199-835a-1f2e0cb4361a)


<p align="center"><b>Then I selected the amount of memory and processing power I want to use, it is recommended to use 25% of your base memory for RAM so if you have 8GB RAM you will allocate 2GB for Linux, as for processors I have left it at 1 CPU.</b></p>


![Screenshot 2024-11-13 at 21 33 25](https://github.com/user-attachments/assets/83d3a1a7-0188-4684-a204-ea6ac22f1b7c)

<p align="center"> <b> Then I created a virtual hard disk and then hit next.</b></p>

![Screenshot 2024-11-13 at 21 49 07](https://github.com/user-attachments/assets/7bd7991c-bb29-4e3a-8723-cf2e97c27777)


<p align="center"> <b> Once I have done that I will hit finish. </b></p>

![Screenshot 2024-11-13 at 22 00 51](https://github.com/user-attachments/assets/4c32c777-8071-4771-85dd-2c48df4cd349)

<p align="center"> <b> As you can see the Kali Linux OS that I have installed showing on the Virtual Box showing as powered off, hit the green start button at the top to finish setting up Linux.</b></p>

![Screenshot 2024-11-13 at 22 02 26](https://github.com/user-attachments/assets/1f7c72eb-8446-4105-b341-22149efcf3ab)

<p align="center"> <b> Select Graphic Install:</b></p>

![Screenshot 2024-11-15 at 15 24 32](https://github.com/user-attachments/assets/d16cb66c-3f06-4f5f-9fe1-496d97cd4778)

<p align="center"> <b> I then finished setting up Kali Linux. Make sure that you select the language you are most comfortable working in and then click Continue. Next, I selected location, clicked Continue once again, and then selected the keyboard layout. VirtualBox will then go through a process of detecting your hardware and network adapters. Just wait patiently as it does so. Eventually, I was greeted by a screen asking me to configure your network, I left mine as kali but you can name it whatever you wish and hit Continue.</b></p>

![Screenshot 2024-11-15 at 15 28 24](https://github.com/user-attachments/assets/64ccabfb-9c68-4a4b-81e1-21cf872e4a8f)

<p align="center"> <b> Then I was asked to enter a domain name, I left that blank and hit Continue once again. Then I was taken to a new screen in which I will be setting up my username and password, you can name these whatever you like just make sure to remember them.</b></p>

<p align="center"> <b> Then on this screen, I will select Guided - use entire disk and hit Continue.</b></p>

![Screenshot 2024-11-15 at 15 32 42](https://github.com/user-attachments/assets/1025f7a7-e766-46e6-b147-cfb31b824a2e)

<p align="center"> <b> Here I selected All files in one partition then hit Continue again. </b></p>

![Screenshot 2024-11-15 at 15 33 51](https://github.com/user-attachments/assets/2cef214f-5133-4649-8884-e84bec235dea)


<p align="center"> <b> Then select Finish partitioning and write changes to disk and click Continue.</b></p>

![Screenshot 2024-11-15 at 15 34 56](https://github.com/user-attachments/assets/91ba704b-bf25-498f-a267-ad789d326a18)

<p align="center"> <b> Here I selected Yes then Continue once again.</b></p>

![Screenshot 2024-11-15 at 15 36 38](https://github.com/user-attachments/assets/4e7b4da2-c565-45ee-877d-7079ea4e4f05)

<p align="center"> <b> Then Kali will ask if there is any additional software I want to install, I left it as the default one. </b></p>

![Screenshot 2024-11-15 at 15 39 48](https://github.com/user-attachments/assets/44b5cf7b-9d16-4fd9-b721-1e1d85c1b4fd)

<p align="center"> <b> Once the install has finished it took me to this page, select Yes then Continue.</b></p>

![Screenshot 2024-11-15 at 16 14 14](https://github.com/user-attachments/assets/cc1486b2-2ae9-434d-8ff5-1870a34eec76)


<p align="center"> <b> Then select enter device manually and hit Continue, select the drive where the GRUB bootloader should be installed and it will likely be something like /dev/sda. Click through to the next screen, which should tell you that the installation is complete. </b></p>

![Screenshot 2024-11-15 at 16 16 29](https://github.com/user-attachments/assets/a4e0e294-f973-4d4a-ac56-24963cbacec5)


<p align="center"> <b> Now that the installation is complete I can now log in using the username and password I set earlier.</b></p>

![Screenshot 2024-11-16 at 14 12 02](https://github.com/user-attachments/assets/097f7183-5767-46e9-8604-6ebfdb7b119b)

<p align="center"> <b> And we're in!! This is the longest part but we have got through it, now to move on to the next stage.</b></p>

![Screenshot 2024-11-16 at 14 14 49](https://github.com/user-attachments/assets/3f105bf1-9f64-4113-be3a-d6529dfcafb3)


<h1 align="center">
Elastic Cloud
</h1>

<p align="center"> <b> First I will head over to the Elastic Cloud website and create a free account. [https://www.elastic.co/cloud](https://cloud.elastic.co/login?redirectTo=%2Fhome) </b></p>

![Screenshot 2024-11-16 at 14 51 49](https://github.com/user-attachments/assets/bd81c971-bf42-4f04-9491-0043af895a4f)


<p align="center"> <b> Once you I logged in, head to the top of the page and search for Integrations and click on it.</b></p>


![Screenshot 2024-11-16 at 15 23 34](https://github.com/user-attachments/assets/31ba1312-0844-483e-b762-a2f19576efcd)


<p align="center"> <b> Search for Elastic Defend and click on it, once I have clicked on it there will be a blue button on the side labelled Add Elastic Defend click on that. </b></p>

![Screenshot 2024-11-16 at 15 24 47](https://github.com/user-attachments/assets/a4b5b175-93dc-4ff6-8615-58a59b4b658d)

![Screenshot 2024-11-16 at 15 26 27](https://github.com/user-attachments/assets/84974b8b-58ba-4446-bf53-91b2331e4289)

<p align="center"> <b> I will then be taken to the following page, at the bottom it will say Install Elastic Agent, click on it.</b></p>

![Screenshot 2024-11-16 at 15 29 04](https://github.com/user-attachments/assets/262cf421-1ff6-48f4-8a18-ca392fb78651)

<p align="center"> <b> I will then be taken to the following page, copy the command and pasted in into the Linux terminal and hit enter.</b></p>

![Screenshot 2024-11-16 at 15 30 52](https://github.com/user-attachments/assets/2cd592d8-b492-4df5-8fa2-493590f8a095)

![Screenshot 2024-11-16 at 17 03 15](https://github.com/user-attachments/assets/59d415c3-b005-42e6-93f2-24dec45dccb0)

<p align="center"> <b> It will go through the process of installing the agent to the host and now the agent has been enrolled onto my host (Linux) </b></p>


![Screenshot 2024-11-16 at 17 05 19](https://github.com/user-attachments/assets/3dc07bdd-efb2-44b1-8eb9-6e2a75d49222)

![Screenshot 2024-11-16 at 17 06 11](https://github.com/user-attachments/assets/8e1bca2a-1ddf-420f-9b8f-b521d1975cbd)

<p align="center"> <b> Now that the Agent is now enrolled I will run some nmap scans on Linux like so. </b></p>

![Screenshot 2024-11-17 at 12 28 31](https://github.com/user-attachments/assets/bbb88024-56b0-43e2-87c7-8a4d8b2671cd)



<p align="center"> <b> On the top left side of the screen I clicked on the hamburger icon then selected Logs underneath observability.</b></p>

![Screenshot 2024-11-17 at 12 44 24](https://github.com/user-attachments/assets/cf35c870-7977-4503-b62e-ace5c6fd31af)



![Screenshot 2024-11-17 at 12 45 06](https://github.com/user-attachments/assets/99ae7f94-036a-4cfd-a240-fe13e70267a9)

<p align="center"> <b> In the search bar I entered a search query to filter the logs. I wanted to search for all logs related to Nmap scans, enter the query: event.action: “nmap_scan” or process.args: nmap. Here you can see all the logs in which I have done nmap scans. </b></p>

![Screenshot 2024-11-17 at 12 55 13](https://github.com/user-attachments/assets/072c0173-4cee-4f4c-a765-e7d728bbbc5e)

<p align="center"> <b> What I am going to do next is create a dashboard to visualise the events. I will first head over to the hamburger icon on the top left on the page and click on it like I done a few steps ago and underneath the Analytics section click on Dashboards.</b></p>

![Screenshot 2024-11-17 at 13 27 35](https://github.com/user-attachments/assets/3bc051c0-58a9-48b2-902b-c38145658435)


<p align="center"> <b> Once that page loads up Clicked on Create dashboard then Create visualisation and implemented the following settings:</b></p>

![Screenshot 2024-11-17 at 13 30 42](https://github.com/user-attachments/assets/e83a4376-bc66-47a3-a4df-4c78ec74dec1)


<p align="center"> <b> On this dropbox I selected Area.</b></p>

![Screenshot 2024-11-17 at 13 34 46](https://github.com/user-attachments/assets/1f610f55-bfdf-454e-a1bc-a82e2714601c)

<p align="center"> <b> Then I implemented the following settings:</b></p>

![Screenshot 2024-11-17 at 13 38 17](https://github.com/user-attachments/assets/8a28aebd-f50d-4dd8-97f4-38be79ff8ff9)

<p align="center"> <b> Once that is done I can now see the dashboard showing on the page like so: </b></p>


![Screenshot 2024-11-17 at 13 39 19](https://github.com/user-attachments/assets/adc96d2f-4acb-4f77-ad14-004832c33d4a)

<p align="center"> <b> On the top right corner I clicked on Save and return which then brings me to the next step. I will create an alert, alerts are created based on predefined rules or custom queries, and can be configured to trigger specific actions when certain conditions are met. I will go through the steps of creating an alert in the Elastic SIEM instance to detect Nmap scans.</b></p>

<p align="center"> <b> Using the same hamburger icon I used to navigate to create a dashboard, in that navigation section under Security there will be a section labelled Alerts, click on that which will take me to the following page:</b></p>


![Screenshot 2024-11-17 at 13 44 24](https://github.com/user-attachments/assets/2d989397-4804-4aee-98a5-8c72526cd862)


<p align="center"> <b> On the top right there is a blue button labelled Manage rules, after clicking on that it will take me to the following page in which I will click on Create new rule button on the top right corner:</b></p>

![Screenshot 2024-11-17 at 13 45 48](https://github.com/user-attachments/assets/f8c2be22-3e9c-4b81-89d3-d9624d492680)

<p align="center"> <b> Under the Define rule section, I selected the Custom query option from the dropdown menu. Under Custom query, set the conditions for the rule, I set the following rules: </b></p>

![Screenshot 2024-11-17 at 13 49 15](https://github.com/user-attachments/assets/3e5fb90e-f128-4401-a5dc-4878c369d8f3)

<p align="center"> <b> This query will match all events with the action “nmap.” Then I clicked Continue. Then, under the About rule section, I gave my rule a name and a description something like: Nmap Scan Detection.
Then I set the severity level for the alert, which can help me prioritise alerts based on their importance. I kept all the other default settings under Schedule rule and clicked Continue.</b></p>


![Screenshot 2024-11-17 at 13 53 39](https://github.com/user-attachments/assets/67769e0e-d61d-457a-bcd4-29254c8bd48b)

<p align="center"> <b> Then I created an email alert, I done this by selecting Email under the Rule Actions section and entering the email address in which I want the alert going to.</b></p>

![Screenshot 2024-11-17 at 13 54 15](https://github.com/user-attachments/assets/fd938fbb-9290-460c-b011-b223091143c8)

![Screenshot 2024-11-17 at 13 55 34](https://github.com/user-attachments/assets/6487faae-9380-4e42-a774-c8fa599143dd)

<p align="center"> <b> Then I clicked on Create & enable rule, now I went back to my Kali vm and done a Nmap scan.</b></p>

![Screenshot 2024-11-17 at 14 05 49](https://github.com/user-attachments/assets/a8007afe-ce32-4552-84b0-c4d2b3cdd8bc)

<p align="center"> <b> After doing that I have recieved an alert to my email alerting me that a Nmap scan was done:</b></p>


![Screenshot 2024-11-17 at 14 06 34](https://github.com/user-attachments/assets/8ffd0a48-e90c-4207-ac02-e95d595a5edb)

<p align="center"><b>And this is how we can set up a simple SIEM lab using Elastic Cloud and Kali Linux, and create alerts for specific commands and have an alert be sent out to your email address.</b></p>


<h1 align="center">
Conclusion
</h1>


<p align = "center"><b>  In this project, I have set up a home lab using Elastic SIEM and a Kali VM. I forwarded data from the Kali VM to the SIEM using the Elastic Cloud agent, generated security events on the Kali VM using Nmap, and queried and analysed the logs in the SIEM using the Elastic web interface. I also created a dashboard to visualise security events and then created an alert to detect security events. </b></p>

<p align = "center"><b> This home lab provides a valuable environment for learning and practicing the skills necessary for effective security monitoring and incident response using Elastic SIEM. By following these steps, you too can gain hands-on experience with using a SIEM and improve your security monitoring skills to help you become a successful security analyst or engineer. </b></p>


