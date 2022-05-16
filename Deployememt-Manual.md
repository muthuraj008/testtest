Manually Way of deployment.

Steps:
1. Create a virtual Machine(Any cloud Platform)
![image](https://raw.githubusercontent.com/muthuraj008/testtest/master/Images/testest.png)
3. Install IIS using below command
	a. Install-WindowsFeature -name Web-Server -IncludeManagementTools
	b. Install-WindowsFeature -Name Web-Mgmt-Service
3. Need to install Hosting Bundle for respective Target framework version(.NET 6.0). Use below link.
	url: https://dotnet.microsoft.com/en-us/download/dotnet
4. Install Web Deployment based on window bit version, Install it from MSI file and then enable all of the features(complete). Use below to download.
	url: https://www.microsoft.com/en-us/download/details.aspx?id=43717
5. Clone the project from the Git and open it through Visual Studio(If You dont install Visual Studio pls see the xxx.PPT in Gitbub)
	a. Open project in Visual studio, Right click on project(project_name) in solution explorer make sure you have selected release mode.(image :right_click_publish)
	b. Click on Add a Publish Profile and then select Folder in Publish Window. See the image(Image:Folder_publish)
	c. It will show the location where the binaries will be placed. Click finish to complete the publish process(Image: publish_path_local_machine).
	d. click Publish(image: Publish_folder). 
	e. After publish you will get publish succeeded on date.(Image: After_Publish)
	f. Goto the publish path shown in above step and zip the publish folder and push it to github.
	g. Goto to VM, pull the zip file from github and extract it.
6. Goto IIS, right click on Default Web Site and select Add Application(Image: Add_Applciation_iis)
7. Give any default name in Alias and make application pool as DefaultAppPool. provide the physical path where the source is present. 
8.  Next goto Appliation Pools and select and right click on defaultAppPool and select basic settings.(Image: Basic_settings)
9. Make sure in .Net CLR version: ".NET CLR version v4.0.30319" is selected and in Managed pipeline mode "Integrated" is selected.(Image: edit_app_pool)
10. Right click on newly created application in iss and GOTO manage Application and select browse. Application will opne in VM browser with localhost.(Image: verify_deployment)
11. Goto to any browser in local machine select the public ip of virtual machine with applcation name. example : "http://54.89.167.226/testsample".
