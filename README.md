# AS_Domain_Watchlist

Author: Arbala Security

For any technical questions, please contact info@arbalasystems.com   

This ARM template will create a Watchlist and a Logic App to work in tandem with one another. The Logic App is intended to be run from an Azure Sentinel alert. It will extract the domains from entities in an alert and add them to the watchlist. You will be able to view, edit, or repurpose the watchlist as you see fit.

#
To configure and deploy this playbook:
 
Open your browser and ensure you are logged into your Azure Sentinel workspace. In a separate tab, open the link to our ARM template on the Arbala Security GitHub Repository:

https://github.com/Arbala-Security/AS_Domain_Watchlist

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FArbala-Security%2FAS_Domain_Watchlist%2Fmain%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton""/>
</a>
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FArbala-Security%2FAS_Domain_Watchlist%2Fmain%2Fazuredeploy.json" target="_blank">
<img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.png"/>
</a>                                                 

From there, click the “Deploy to Azure” button at the bottom and it will bring you to the Custom Deployment Template.

In the first section:  

* Select the “**Subscription**” and “**Resource Group**” from the dropdown boxes you would like the playbook deployed to.  

In the **Parameters** section:   

**1) Playbook Name**: This can be left as “AS_Domain_Watchlist” or you may change it.  

**2) WorkspaceName**: Enter the name of the Azure Sentinel Workspace you are using for deployment.

**3) WatchlistName**: You may keep the default name or change it to something to better suit your use case.

**4) watchlistdescription**:  Enter a description for your watchlist. 

Towards the bottom, click on “Review + create”. 

![Template](Images/template1.png)

Once the resources have validated, click on "Create".

![Template](Images/template2.png)

The resources should take around a minute to deploy. Once the deployment is complete, you can expand the "Deployment details" section to view them.
Click the one corresponding to the Logic App.
                                                                                                                             
![Template](Images/template3.png)
                                                                                                                             
Click on the “Edit” button. This will bring us into the Logic Apps Designer.
                                                                                                                             
![logicappedit](Images/logicappedit.png)

Click on the bar labeled “Connections”.

Here you will select the connection with the same name as your Playbook.                                                                                                         
                                                                                                                             
![logicappconnections](Images/logicappconnections1.png)

Here you will select the connection with the same name as your Playbook. Click on the exclamation  icon.                          
                                                                                                                             
![logicappconnections](Images/logicappconnections2.png)                                                                                                                           
                                                                                                                             
You will be prompted to authorize the connection with your Azure account.
                                                                                                                             
![logicappconnections](Images/logicappconnections3.png) 
 
 Once the connection is set up, you will need to check the other connectors requiring an Azure Sentinel connection
                                                                                             
One of the two remaining connections is directly below the first. Check for the indicated display. You may need to unselect and then reselect the desired connection after authorizing the first for it to be recognized as valid.
                                                                                                                             
![Template](Images/logicappconnections4.png)                                                                                                                                     

The remaining connection is inside the For Loop as indicated. Repeat the same process here.                                       
                                                                                                                             
![Template](Images/logicappconnections5.png)                                                                                                                               
