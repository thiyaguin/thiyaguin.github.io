---
title: "Configure IIS and Apache Webserver to prevent Clickjacking"
tags:
  - Apache
  - clickjack
  - clickjacking
  - header
  - HTTPD
  - IIS
  - SameOrigin
  - security
  - X-Frame
---
lickjacking, also known as a “UI redress attack”, is when an attacker uses multiple transparent to trick a user into clicking on a button or link on another page when they were intending to click on the the top level page. Thus, the attacker is “hijacking” clicks meant for their page and routing them to another page, most likely owned by another application, domain, or both.

To prevent clickjacking, configure the below in your web server.

To configure IIS:

1. Open Internet Information Services (IIS) Manager.
2. In the Connections pane on the left side, expand the Sites folder and select the site that you want to protect
          ![IIS HomePage SS](https://thiyaguin.github.io/assets/IIS_Home.png)
3. Double-click the HTTP Response Headers icon in the feature list in the middle.
4. In the Actions pane on the right side, click Add.
5. In the dialog box that appears, type X-Frame-Options in the Name field and type SAMEORIGIN in the Value field
          ![IIS XFram SS](https://thiyaguin.github.io/assets/xframe.png)          
6. Click OK to save your changes.
7. Restart the IIS

To configure Apache:

1. Add the following lines to the httpd.conf file:

        <IfModule !headers_module>
          # If the HEADERS module has NOT already been loaded, load it
          LoadModule headers_module modules/mod_headers.so
        </IfModule>

        Header always append X-Frame-Options SAMEORIGIN
        <IfModule !headers_module>
          # If the HEADERS module has NOT already been loaded, load it
          LoadModule headers_module modules/mod_headers.so
        </IfModule>

        Header always append X-Frame-Options SAMEORIGIN
        
2. Save the conf file
3. Restart the Apache
