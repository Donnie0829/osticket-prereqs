<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Install/ Enable Internet and Information Services (IIS) with CGI and common HTTP features
- Download and install PHP Manager for IIS
- Download and install the Rewrite Module
- Download PHP 7.3.8
- Download and install VC_redist.x86.exe
- Download and install MySQL 5.5.62
- Install osTicket v1.15.8
- Download and Install HeidiSQL
- Configured permissions and installed osTicket

<h2>Installation Steps</h2>

Step 1: Create a resource group in Azure

![image](https://github.com/user-attachments/assets/1f53cbee-c9d3-40d9-8229-d3f2a167dfd0)



Step 2: Create a Windows 10 Pro Virtual Machine (VM)

- Select the Resource group that was created
- VM name: VM-osTciket
- Select US East or US West region
- For availability options, select 'No infrastructure redundancy required'
- For security type select 'Standard'
- Image: Windows 10 Pro
- Size: 2 or 4 Virtual CPUs (vcpus)
- Choose your usernamde and password
- Check the box for Licensing
- Click Review + Create
  
![image](https://github.com/user-attachments/assets/5b6126b2-dc43-4e4d-af80-605e96b41655)
![image](https://github.com/user-attachments/assets/efbcccbd-609c-4cda-b022-9c6b627d42f7)
![image](https://github.com/user-attachments/assets/f39c69a2-9e55-4df3-8074-ea2b4bf4b4d8)



Step 3: Open Remote Desktop Connection App

-Copy and paste the Public IP Address into the Remote Desktop Connection (Wait until the VM finished deploying)
-Click 'Connect'
-Log in with the credentials created during the virtual machine configuration process.
-Select 'Yes' to connect to your VM

![image](https://github.com/user-attachments/assets/33151caa-a7bc-4e1e-a39c-eabffc2aa50c)

![image](https://github.com/user-attachments/assets/54367482-5d1e-4e72-b545-b28426df0109)



Step 4: Install/Enable IIS in Windows with CGI and Common HTTP features

- Right click on the "start/windows" icon, click run, and enter "control"
- Click on 'Programs'
- Click the blue hyperlink that says "Turn Windows features on or off"
- Select Internet Information Services (IIS) -> World Wide Web Services -> Application Development Features (click the plus sign to [x] CGI) -> Common HTTP Features (click the plus sign to [x] all.)
- Click 'Ok'

![image](https://github.com/user-attachments/assets/a480d6b3-9d71-4ead-95cb-48c57020c3f7)



Step 5: Open the Installation files page 

- Download and install PHP Manager for IIS
- Download and install Rewrite Module
- Download and install PHP 7.3.8
- Download and install VC_redist.x86.exe.
- Download and install MySQL 5.5.62

![image](https://github.com/user-attachments/assets/3b398afe-916d-4731-b670-a3ca73cf1fbe)


Note: When PHP 7.3.8 is finished downloading, create a folder on Windows (C:) and name it 'PHP'-> right click the PHP 7.3.8 file -> Extract all -> Browse -> This PC -> Windows (C:) -> PHP -> Select Folder -> Extract

![image](https://github.com/user-attachments/assets/6c57d332-8ee3-494f-a0de-89805b3d8b99)


Note: When downloading MySQL, choose 'Typical' as your set up type -> continue installation and set up credentials -> select 'Standard Configuration' -> select next -> choose your password (the username will automatically be 'root') -> Execute and finish 

![image](https://github.com/user-attachments/assets/a65ac180-23a9-470d-92c9-84530390d99a)



Step 6: Open IIS as a Admin

- Click start and type in IIS in the search bar -> right click on IIS app and click 'Run as administrator'
- Register PHP from within the IIS app
- Click on PHP Manager
- Select blue hyperlink that says 'Register new PHP version'
- Click on PHP mANAGER -> Register new PHP version -> This PC -> PHP -> php-cgi -> open -> click 'Ok'
- Go back to the home page in the IIS app and click "Restart"

  ![image](https://github.com/user-attachments/assets/a2711dce-9062-461f-8253-5944b80e02c1)

  ![image](https://github.com/user-attachments/assets/e46b4733-cc20-4007-81a8-218b27f23f84)

  ![image](https://github.com/user-attachments/assets/f74207f1-7bed-4e26-9de7-66270ec61b46)



  Step 7: Download and Install osTicket v1.15.8

  - When the osTicket file has downloaded, open the osTicket file
  - Once inside the folder, open another File Explorer (the yellow folderon the taskbar) and go to This PC -> Windows (C;) -> inetpub -> wwwroot
  - Once inside the wwwroot folder, drag the "upload" folder within the 'wwwroot' folder
  - Right click the 'upload' within the wwwroot folder and rename it 'osTicket'
 
    ![image](https://github.com/user-attachments/assets/56ce4003-eceb-4b4b-a46b-dd9d5b2bc085)



Step 8: Go back to IIS app

- Click 'Restart'
- Go to Sites (left margin) -> Default Websites -> osTicket -> click "Browse *:80" (blue hyperlink on in the right margin)
- Webpage to osTicket should open

  ![image](https://github.com/user-attachments/assets/0fa35efe-3baa-4eca-adc8-35ba4100c03a)

  ![image](https://github.com/user-attachments/assets/2af7faea-eaf2-4d0f-97ff-ded3309b7ebf)


Note: If the webpage gives you an error, something is incorrect



Step 9: Enable extensions

- Go back to IIS app -> Sites -> Default Websites -. osTicket
- Double click on PHP Manager
- Click the blue hyperlink that says 'Enable or Disable an extension'
- Enable (right click each to enable); php_imap.dll, php_intl.dll, and php_opcache.dll
- Refresh osTicket webpage in order to review the enabled extentions


![image](https://github.com/user-attachments/assets/4d14ae91-15ff-47be-9237-d6b2353fcb3b)

![image](https://github.com/user-attachments/assets/8c11d930-2e88-48d8-a3c2-5d617448623c)

![image](https://github.com/user-attachments/assets/9ca88748-8338-4f1a-8e1c-196dcb0f0265)

![image](https://github.com/user-attachments/assets/7ba3fbd4-62b5-48d5-9c52-cb46895d96f0)



Step 10; Rename ost-sampleconfig.php

- Go to the wwwroot folder in the File Explorer
- Click osTicket -> include -> scroll to find 'ost-sampleconfig.php' and rename it 'ost-config.php' (simply remove the word 'sample')
- Right click ost-config.php -> click Properties -> click Security (tab at the top
- 0 -> click Advanced -> click Disable inheritance -> click pop up hyperlink that says 'Remove all inherited permissions-> click Add -> Select Principle -> type 'Everyone' in the object name field -> click Ok -> click 'Full Control' -> click ok -> click Apply and then Ok


![image](https://github.com/user-attachments/assets/20cacd3e-b483-4b29-9285-3510c6c30882)



Step 11: Continue Setting up OsTicket (click 'Continue' at the bottom

- Help Desk Name: Donnie's Help Desk
- Email: donniehall0412@gmail.com (Receives email from customers)
- Name; Donnie
- Last name: Hall
- Email address: me@donniehall.tech (can be any email address)
- Username: adminuser
- Password: Choose your own
- Download and install HeidiSQL
- Open HeidiSQL will
- Click 'New' at the bottom left,
- Enetr root password that was created when we downloaded MySQL
- Connect to the session
- Create a database called 'osTicket' in Heidi SQL -> right click where it says 'Unnamed' in bold -> Create New -> Datbase -> type 'osTicket' in the Name field
- Continue on to the Database Settings on the osTicket webpage:
   - MySQL Database: enter 'osTicket' (databse we just created in HeidiSQL)
   - MySQL Username: root
   - MySQL Password: Password that was created when we downloaded MySQL
   - Click 'Install Now!'
 
  ![image](https://github.com/user-attachments/assets/6d40caab-3f9f-4abf-8783-f04073c13c76)

  ![image](https://github.com/user-attachments/assets/6112a3f8-29d2-4fb2-9f98-32b463209bed)

  ![image](https://github.com/user-attachments/assets/65c62e6a-2eb8-40a5-b434-9d3660ac21ef)

  ![image](https://github.com/user-attachments/assets/60712b61-c55f-4623-8f06-bb553ab549e6)



  Congratulations, osTicket has been installed successfully!


  ![image](https://github.com/user-attachments/assets/95ddba7b-08aa-4757-a7c9-7263f8f08920)




  Step 12; Clean up

  - Go to Files Explorer
  - Go to Windows (C) -> inetpub -> wwwroot -> osTicket -> setup (right click and delete)
  - Set Permissions to 'Read' only: Go to Windows (C) -> inetpub -> wwwroot -> osTicket -> include -> os-config.php -> right click and go to Properties -> Security -> Advanced -> Double click 'Everyone' -> deselect 'Full control' , 'Modify' , and 'Write' -> and Apply
 



Step 13: Test your osTicket log in credentials

- Click on http://localhost/osTicket/scp under 'Your Staff Control Panel'
- Enetr log in credentials
- Congrats, you have successfully logged into osTicket













  








<br />
