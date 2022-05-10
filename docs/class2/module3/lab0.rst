.. role:: red
.. role:: bred

The Juiceshop Application
================================================================================

We will start by establishing an RDP session to the **Ubuntu 18.04 Client**.

-  Start an RDP session to the **Ubuntu 18.04 CLient** (Components > Ubuntu18.04 Client > ACCESS > XRDP)

   .. image:: ../images/udf-ubuntu-client-rdp.png
      :alt: UDF Ubuntu Client RDP 

-  When prompted, save the RDP file to your local machine and then open it to connect.
-  At the Ubuntu Login prompt, click on the **OK** button to continue.

   .. image:: ../images/udf-ubuntu-client-rdp2.png
      :alt: UDF Ubuntu XRDP


   .. tip:: If the RDP session times out, refer to the `User Credentials <https://github.com/Doctorwooo/f5-agility-labs-sslviz/blob/master/docs/class2/labinfo.rst>`_ for the **student** user password.

-  Open the **Firefox** browser
-  Click on the **Juiceshop** bookmark on the browser bar

   .. image:: ../images/juiceshop-bookmark.png

-  Accept the security risk by clicking **Advanced** and **Accept the Risk and Continue**. This is due to the BIGIP using a self-signed certificate.

   .. image:: ../images/certificate-risk.png

Here is the vulnerable Juiceshop application. Next, we will try a simple SQL injection attack that will illustrate why WAF protection is necessary.

  .. image:: ../images/juiceshop-rdp.png

-  Paste the following path in your browser's location bar after https://10.1.20.200/

  .. code-block:: none
   
    /rest/products/search?q=qwert%27%29%29%20UNION%20SELECT%20id%2C%20email%2C%20password%2C%20%274%27%2C%20%275%27%2C%20%276%27%2C%20%277%27%2C%20%278%27%2C%20%279%27%20FROM%20Users--

  






-   



-  If not already connected to the **SSL Orchestrator** TMUI, log into the TMUI *(Components > SSL Orchestrator > ACCESS > TMUI)*

      |credentials_link|


-  Select **SSL Orchestrator** from the left-hand menu and then click on **Configuration**. When the SSL Orchestrator dashboard finishes loading, the following deployment should already be present.

   .. image:: ../images/config-dashboard.png
      :alt: SSL Orchestrator Configuration Dashboard


-  Select **Security Policies** from the horizontal menu. You should now be presented with following screen:

   .. image:: ../images/security-policy-overview.png
      :alt: Security Policy Overview


-  Click on **ssloP\_f5labs\_explicit** and you will see the rules that are currently configured under this security policy.

   .. image:: ../images/updated-security-policy.png
      :alt: Security Policy Rules

-  Click on **Cancel** to return to the Topology list.



.. |credentials_link| raw:: html

      <a href="../labinfo.html#credentials" target="_blank"> Link to user credentials (opens in new browser tab) </a>
