---
comments: true
---
# Configuring Geo Binding

Geo Binding helps ISA administrators to restrict the ISA User Agent connection to specific countries, thus further securing remote access to corporate resources. Geo Binding can be configured per user and per user group. More than one country can be selected as the source of the User Agent connection. 

For the purpose of this article, the end-user device shown is a Windows PC.

- Log into the ISA web console using administrator credentials 
- Navigate to the USERS & GROUPS > Users page.

![](../static/ISA/ConfiguringGeoBinding/ConfiguringGeoBinding1.png)

- Click on the name of a user

![](../static/ISA/ConfiguringGeoBinding/ConfiguringGeoBinding2.png)

- Alternatively, click on the name of a user group on the User Groups page.

- In the user window, click Edit

![](../static/ISA/ConfiguringGeoBinding/ConfiguringGeoBinding3.png)

- Alternatively, in the Group details window, click Edit.

![](../static/ISA/ConfiguringGeoBinding/ConfiguringGeoBinding4.png)

- Scroll Down

![](../static/ISA/ConfiguringGeoBinding/ConfiguringGeoBinding5.png)

- Turn on the Geo Binding toggle.

![](../static/ISA/ConfiguringGeoBinding/ConfiguringGeoBinding6.png)

- Click inside the Select countries box.

![](../static/ISA/ConfiguringGeoBinding/ConfiguringGeoBinding7.png)

- Select the countries you want to allow the user or the user group to connect from. 

![](../static/ISA/ConfiguringGeoBinding/ConfiguringGeoBinding7.png)

- Click Update to save the change.

![](../static/ISA/ConfiguringGeoBinding/ConfiguringGeoBinding8.png)

**Conclusion**

Geo Binding adds one more layer of security to the ISA User Agent connection process by restricting users to connect from certain allowed countries. If a user attempts to connect from a country not configured under Geo Binding, the connection is refused.
