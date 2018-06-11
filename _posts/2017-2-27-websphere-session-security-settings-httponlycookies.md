---
title: WebSphere Session Security Settings – HTTPOnlyCookies
---

1. Go to the server’s detail properties page, and select Session Management option under Container Settings.
2. Click on Under General properties, click Enable cookies. Do not clear this option. Click the label only    
        ![WebSphere Console SS](https://thiyaguin.github.io/assets/cookie_timeout.png)
3. Check the Restrict cookie to HTTPS sessions check bok and click on Apply. Then save the changes to master configuration.  
4. Go back to the server detail properties page and select Web Container Settings -> Web Container under Container
5. In web container page, under Additional properties menu, select Custom properties and create a new one as follows
    Name – com.ibm.ws.webcontainer.HTTPOnlyCookies
    Value – *
    Description – HTTPOnlyCookies
6. Click on Apply and save the Master configuration.
