<h1>Cybersecurity systems administration</h1>

<h2>Description</h2>
Within this project, I used a virtual machine, created new users in the Windows OS and assigned them limited rights, an essential aspect for cybersecurity, then I managed folders and access permissions for them, which helps limit access to sensitive information.<br />
The next step was to enable the event logging, to observe how data can identify possible security threats followed by creating and running automated tasks, useful for regular monitoring and protecting the system <br />

<h2>Languages and Utilities Used</h2>

- <b>[Oracle Virtual Box](https://www.virtualbox.org/)</b> 

<h2>Environments Used </h2>

- <b>[Windows 10](https://www.microsoft.com/en-us/software-download/windows10)</b> 

<h2>Project walk-through:</h2>

<p>
<b><h3>1. Creating a new user</h3></b>

- In this chapter I created a new user named "TestUser" with "TestPassword123" password and granting limited rights;<br/>
- In the CLI terminal I used "net user TestUser TestPassword213 /add" command;
  ![image](https://github.com/user-attachments/assets/9eaa5387-843c-4f2f-bbf2-010d4302d637)<br/>
- In the GUI window you can find the created account - the next step is to select the desired user;
![image](https://github.com/user-attachments/assets/e3ea352b-3b38-438d-870e-6a1d3593ac31)<br/>
- To view the user's rights, select the option indicated below;
![image](https://github.com/user-attachments/assets/845b49f0-a7e9-42f5-8f1e-25bff9500dd1)
- It is noted that the "TestUser" user has limited rights by default.
![image](https://github.com/user-attachments/assets/0597d39d-ca13-4224-ae26-4ec2f4070b37)

<b><h3>2. Creating a folder and granting read-only access:</h3></b>

- To create a folder on the desktop, I performed the following steps: right click on the Desktop->New>Folder option and named it TestUser;<br/>
![image](https://github.com/user-attachments/assets/0043d1d6-b2a6-4bbf-949a-06cc92522c73)
- The next steps for granting reading rules to the user “TestUser” are:<br/>
  o Right click on the folder->Properties->Security<br/>
  ![image](https://github.com/user-attachments/assets/3906d3a5-ca2e-4fd6-b6f9-386371a1bff2)<br/>
  o In the list of users I did not find the newly created one, so I added it using the option Edit->Add->Object Types (Users)->Advance->Find Now-> Select the User “TestUser”->close the windows with the option Ok. Later from the list of “rights” I selected only Read. Later Apply and ok.<br/>
  ![image](https://github.com/user-attachments/assets/e0c1c73b-6e7b-42e0-b8be-fae759f34dd5)<br/>
  ![image](https://github.com/user-attachments/assets/6a7576f6-d39b-451c-b679-e37668c785a5)<br/>
  ![image](https://github.com/user-attachments/assets/9b597720-632d-44ad-9304-83692fa956f0)<br/>
  ![image](https://github.com/user-attachments/assets/c8905d23-62cd-40ec-84be-98cf0a146b6f)<br/>
  
<b><h3>3. Changing login settings.:</h3></b>

- Here I enabled event logging for failed login attempts and checked the logs to confirm that logging was successfully enabled.<br/>
- To record events related to failed login attempts, I followed the next steps:</br>
    o Windows+R-> gpedit.msc</br>
    o In the opened window I accessed:</br>
    ![image](https://github.com/user-attachments/assets/55a9f2eb-22d1-491e-ad11-237859327cc5)</br>
    o In the "Audit account logon event" box, I checked the options for successful or failed login, then Ok.</br>
    ![image](https://github.com/user-attachments/assets/6bad2416-4a9d-4598-bde2-92f87b3f1597)</br>
    o For the test user, we created two successive failed logs to test the attempts. They can be viewed in the “Event Viewer” in Windows Administrative Tools.</br>
    ![image](https://github.com/user-attachments/assets/55109bd3-fa9e-4e0d-8b77-67f07deccfe6)
    o Considering that failed events have a specific ID number, namely 4625, we used a filter to find them faster.</br>
    ![image](https://github.com/user-attachments/assets/e8d07407-9e75-412c-8b27-9f3a71df9775)</br>
    ![image](https://github.com/user-attachments/assets/78abaac2-9010-4ab5-9944-28cbff789808)</br>
    ![image](https://github.com/user-attachments/assets/3c18147a-044e-4ab2-85c7-5f4227cdbbeb)</br>
    
<b><h3>4. Creating a scheduled task:</h3></b>

- In this step, I created a scheduled task that would run every hour and display a random message in the command window:</br>
  o I used the Windows+R key combination to open the “Run” window, followed by the command “taskschd.msc” for the Task Scheduler tool.
  ![image](https://github.com/user-attachments/assets/7f1b30db-c1d6-4914-80cb-5f1e92fd5199)</br>
  o Then I selected - Action->Create Task-> where I configured the "scheduled task": task name, task description.</br>
  ![image](https://github.com/user-attachments/assets/aea1b636-df4b-4f1c-bb1e-8ffccc73a3a1)</br>
  o In the Actions tab, I selected the action that needs to be performed:</br>
    o Action: Start a program;</br>
    o Program/script: CMD;</br>
    o Add arguments: /C TITLE Hello &ECHO.&ECHO.&ECHO Perform updates &ECHO.&ECHO.&TIMEOUT [-1];</br>
    o Ok.;</br>
![image](https://github.com/user-attachments/assets/9980d0ca-b2a1-4fff-aef2-0556aff8b90c)</br>
  o In the Triggers tab, I selected when to perform the above action, starting from the moment the task was created, then I checked the option to repeat every hour, followed by Ok.</br>
  ![image](https://github.com/user-attachments/assets/9f99b81a-5afd-43fc-8778-672a7e111a39)</br>
  o Testing- right panel Run:</br>
  ![image](https://github.com/user-attachments/assets/3ac9dd15-0856-45d9-ae51-26fa29190886)</br>
  ![image](https://github.com/user-attachments/assets/e61d755b-bea4-46de-957c-feed8c9407f5)</br>

📌 Conclusion
This project demonstrates the practical application of fundamental Windows system administration tasks, using both the graphical user interface and the command line. The following objectives were successfully implemented:

- Creating a user account with limited privileges;
- Configuring folder access permissions;
- Enabling and verifying audit logging for failed login attempts;
- Scheduling a recurring task using Task Scheduler.

Each step was clearly documented, and the testing confirmed that all configurations were applied correctly.



  

    





