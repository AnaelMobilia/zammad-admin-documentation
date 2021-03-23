GitHub
======

The GitHub integration allows you to link issues to your Zammad tickets 
and keep track without switching sites.

.. figure:: /images/system/integrations/github/github-integration-page.png
   :alt: Integration page for GitHub
   :align: center
   :width: 90%

Configuration
-------------

Step 1: Create API-Key for Zammad
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

   .. note::

      API-Keys are bound to users. In this case it makes sense to use an admin 
      account which has access to all repositories in question. This especially 
      is relevant if you're working with private repositories.

      .. warning:: **🚧 If you're working with private repositories only... 🚧**

         Below permissions to not work with private repositories. 
         GitHub does not provide granular read only for those which is why 
         you have to use ``repo`` permission instead. We don't recommend that - 
         it provides a lot of additional access.

Go to your account settings and navigate to **Developer settings** → 
**Personal access tokens**. On this new site click on **Generate new token** to 
add a new API-Token. On the next screen provide a meaningful name 
(e.g. ``Zammad``) followed by ``public_repo`` permission. 

That's it, submit the form in order to receive the token.

.. figure:: /images/system/integrations/github/add-api-token-github.gif
   :alt: Screencast showing how to create a new API-Token
   :align: center
   :width: 90%

Step 2: Configure Zammad
^^^^^^^^^^^^^^^^^^^^^^^^

   .. hint:: 

      The default endpoint for GitHub is ``https://api.github.com/graphql``. 
      You only have to adjust this value if you're using 
      GitHub Enterprise Server.

Apart from that, you only have to submit your API-Token. 
Upon saving Zammad will verify the connection - this may take a moment. 
If everything is ready, just activate the integration and a new tab on the 
ticket settings will appear. 🎉

.. figure:: /images/system/integrations/github/configure-and-active-github-integration.gif
   :alt: Screencast showing how to configure Zammads GitHub integration
   :align: center
   :width: 90%

Limitations
-----------

The GitHub integration currently is limited to Issues only. 

Frequently Asked Questions
--------------------------

1. I entered the credentials, left the side and now the credentials are gone!:
   This is an indicator for Zammad still verifying your provided data. 
   It should be solved within minutes - if not, please see 2. below.

2. The token verification takes forever!
   Please ensure that your Zammad-Server can communicate to GitHub. 
   Depending on your systems load and connectivity the verification may take 
   quite some time.
