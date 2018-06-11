---
layout: post
title: WebSphere Application Server to API certificate based authentication
---
There are times, you wanted to authenticate to APIs from your application using SSL Certificate. Below the steps to achieve the same when you are using WebSphere as application server.

Logon to WebSphere Admin console. Under the Security select “SSL Certificate and Keystore management”
From the Right navigation, click on “Keystores and Certificates” link
From the list of Keystores and Trust stores, click on “Node Default Keystore”
Select “Personal certificates” from the right navigation
Click on import button, and give the certificate information
Select Key store file option
Enter the location of the client certificate with the file name
Type the password and click on “Get Key File Aliases”
Select the Certificate alias to import
Type user friendly alias name in Import Certificate alias and
Click on OK and save the configuration
Under the “Out bond” expand the “Nodes” and select the AppServer node
Under the Certificate alias select the Alias which is given to import the client certificate to keystore.
Click on OK and save the configurations.
Restart the app server.
