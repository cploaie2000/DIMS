"# DIMS" 
# DIMS
DIMS - Database Independent Management Software

Reason

	1. Possible substitute for specific activities DBAs are doing  while using SQL Server Management Studio, Excel, Power BI, Powershell ISE or other third party applications they might use to perform those activities
	2. Suitable for working with metadata meaning result sets of under  5000 rows or 2 000 rows in case we have more than 20 - 30 columns

Heads Up

	1. The application main value is its source code which for the time being is not shared because the main goal is to sell the source code together with the application in order for people  to continue its development as they see fit.
	2. Those being said you need to be aware that the application has between 150 to more than 300 different achievable end results end some of those were developped and tested only to some extent hence prepare yourself for a bumby but hope fun ride while using the application.
	3. Whatever the application might loose because of its appearance is trying to win back by the amout of features or operations provided
	4. Application went through a series of modifications throughout time hence consistency of the application was hard to keep which is why you might see some things which might not look linear from the actions point of view. For example some selections might look strange although a second time the selection was made it looks like it should
	5. Some of the features and scripts might require information present only in the database tables I used to develop the application hence ignore the message and continue using the features which are working.
	6. Some of the features are incomplete, an example is Execution Plan or better say the graphical display of execution plan
	7. Some features requires specifc dbatools version which shipped the functions in specific folder but new versions are deployed differently

Whishes

	1. I would like for whomever downloads and uses the application to understand that I am not looking into bug hunting contest or something along these lines. I am fully aware of some all of the application shortcomings. 
	2. I would like for whomever uses the application to understand that some of the things were hard coded and some of them were proof of concepts

Recommendations

Preferably use the application on your local computer and against SQL Servers which don't require encryption. 
Due to:
	- obfuscating the code your antivirus might complain about the executable - it happened when using the application on one of my working laptops
	- by default the application connection string when connecting to SQL Server is not using Encrypt and TrustServerCertificate  options test it against sql server which don't require encryption. I am thinking how to implement the addition of those parameters in case the target SQL Server requires encryption. 

Presentation videos / linkedin posts throughout the years
	- https://www.youtube.com/@catalinploaiecataploaie4862
	- https://www.linkedin.com/in/catalin-ploaie-537a3a22/recent-activity/all/

Installation 

There is no installation wizard, the application is composed by 2 files, the executable and the license file. Both of them needs to be found in the same folder in order for the application to launch successfully.

Prerequisites

The application requires SQL Server installed and running on the server where you are planning to use the application. At launch is checking for local sql server instances and is choosing default instance  as the default instance to be used by the application.
It is recommended to have administrator privilegies on the local computer in order to avoid any of the issues caused by missing the required privilegies during the application launch.
Friendly advice - It is recommended to watch this video created a few time back about the application before starting playing with the application. The video tried to compress ( video is speeded up ) enough information about the application as it was 20 months ago. I believe is beneficial and might answer questions you might have about why and for whom.

DIMS   October 2024   Presentation Final V3




First steps

Once the application is launched you will be asked about the instance and database on the local computer that the application will use for different features of the application. 
Depending on the chosen database name and which objects having specific name are present inside that database the application will provide you an initial overview of the current state. 
This wizard or selections made here have no impact on the current state of the application until you choose to create specific objects for specific features in the selected database on the selected instance
As you can see the only button for changing whaterver is displayed currently in the interface is the one labeled - display objects to be created - . This is to let user know that by cheking unchecking features on the left sidepressing that button will generate the create statement only for the objects for the checked features which were not discovered yet.


<img width="792" height="650" alt="wizard" src="https://github.com/user-attachments/assets/25992673-f44f-4fb7-8202-89aafa3c5f86" />

Checking / unchecking any options as showin in the picture below will display the objects that needs to be created in the database for those features.
Pressing the green button will start executing the scripts for creating those objects using sqlcmd which is important to have SQL Server Instance installed on the local computer.

<img width="1883" height="647" alt="wizardandcreateobj" src="https://github.com/user-attachments/assets/23f7feb0-21a0-44c5-87b0-b6a15d4bb64d" />


Closing the wizard window allows the launching process to go to the next step which is asking the user if wants to start the application using a specific domain account, different than the user he is currently logged. Providing account information here allows the application to connect to remote sql servers part from that domain using that credential. 

<img width="772" height="629" alt="netonly" src="https://github.com/user-attachments/assets/61f52862-9c96-4606-bf30-3e914d1eaa83" />

Regardless of the option chosen, OK or Cancel the application will ask user to choose which data collections he wants to be enabled and started once the application launch process is finishing
Frienldy advice - It is recommended to not check / enable any options here for the time being since is better to use the application in the ad hoc mode meaning nothing is running in the background which collects data and inserts it to some of the tables for some of the features you might have installed.

<img width="692" height="503" alt="enabledisabledr" src="https://github.com/user-attachments/assets/0a94e673-8b5a-4dcb-aeed-7ca5c9956672" />

Pressing ok or cancel shows a window displaying the outcom of your actions in the image above. In case Cancel or OK without any checks the message will be as below.

<img width="705" height="413" alt="okwindow" src="https://github.com/user-attachments/assets/6448cd74-fc82-4b54-9a6a-428f654ecb86" />

Once you press OK, the application will start connecting to different tables in order to select informaton that is used for initial configuration of the interface. These error messages are informational only and they will disappear once you start installing the metadata for all the features application exposes.

