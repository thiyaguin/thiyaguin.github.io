---
title: WebSphere Application Server to API certificate based authentication
---
There are times, you wanted to authenticate to APIs from your application using SSL Certificate. Below the steps to achieve the same when you are using WebSphere as application server.

1. Logon to WebSphere Admin console. Under the Security select “SSL Certificate and Keystore management”
2. From the Right navigation, click on “Keystores and Certificates” link
3. From the list of Keystores and Trust stores, click on “Node Default Keystore”
4. Select “Personal certificates” from the right navigation
5. Click on import button, and give the certificate information
6. Select Key store file option
7. Enter the location of the client certificate with the file name
8. Type the password and click on “Get Key File Aliases”
9. Select the Certificate alias to import
10. Type user friendly alias name in Import Certificate alias and
11. Click on OK and save the configuration
12. Under the “Out bond” expand the “Nodes” and select the AppServer node
13. Under the Certificate alias select the Alias which is given to import the client certificate to keystore.
14. Click on OK and save the configurations.
15. Restart the app server.
