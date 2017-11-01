Setup Postman
=============

For this automation setup we will use the Google REST API client "Postman"

Task0 - download and install Postman
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Visit https://getpostman.com and download and install Postman for you OS.

Task 1 - Import the Postman Collection & Environment
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

One feature of Postman is the grouping of REST API calls called "Collections."
Collections can deploy in an automated fashion with another feature called
"Collection Runner." A user can create a Collection, and to deploy it to
different destination environments.
The challenge is that API calls must adapt to the environment. For example, the
Destination IP of the Call has to change for each destination. Postman has
introduced a feature called "Environments" to simplify the portability of
Collections. Within the collection, a user can create a variable, which
references a key-value pair within an Environment file. Once the Collection REST
API call deploys, Postman will replace the variable with the value in the
Environment file.

In this task you will Import a Postman Collection & Environment.
Perform the following steps to complete this task:

#. Open the Postman tool.

#. By default, the Postman client requires verification of SSL/TLS Certificates
   to a public Root Certificate Authority.  However, by default, BIG-IP and many
   other devices use a self-signed certificate for SSL/TLS connections. To allow
   connections with self-signed certificates we need to modify the default
   settings of Postman.

   - Open the Postman Settings windows by clicking `File --> Settings`:

   - Verify your client is configured to allow self-signed certificates by
     setting ``SSL certificate verification`` to ``OFF``

   - Close the Settings window

#. Import a Postman collection.
   To import a Postman Collection, click the `Import` button in the top left of
   the Postman window

#. Click the `Import from Link` tab.  Paste the following URL into the
   text box and click send.

   https://raw.githubusercontent.com/vbojko/F5_Service_POP/master/Architectures/Usecase1/v12.1/Postman/DNS-LTM-POP_v12.1.postman_collection.json

#. You should now see a collection named ``DNS-LTM-POP_v12.1`` in your Postman
   Collections sidebar. Postman automatically resizes its GUI depending on its
   window size. It might be necessary to use the short ``Ctrl + \`` (on Windows)
   or click the show sidebar icon at the bottom left corner of postman if you do
   not see the sidebar.

#. Import the Environment file by clicking `Import --> Import from Link` and
   pasting the following URL and clicking `Import`:

   https://raw.githubusercontent.com/vbojko/F5_Service_POP/master/Architectures/Usecase1/v12.1/Postman/DNS-LTM-POP_Environment_Setup.postman_environment.json

#. Set your environment to
   ``DNS-LTM-POP_Environment_Setup`` by using the menu at the top right
   of your Postman window:

#. Install ``F5-postman-workflows``.
   The Collection we installed above **REQUIRES** this framework for testing and
   polling functionality.

   **You must install this framework into Postman by importing another
   collection**.

    - Import the collection file by clicking: `Import --> Import from Link` and
      pasting the following URL and clicking `Import`in the field:

      ``https://raw.githubusercontent.com/0xHiteshPatel/f5-postman-workflows/master/F5_Postman_Workflows.postman_collection.json``

    - click the 'Import' button
    - Navigate to your Postman Collections
    - Expand the ‘F5_Postman_Workflows’ collection
    - Expand the ‘Install’ folder
    - Click the ‘Install/Upgrade f5-postman-workflows’ items
    - Click the ‘Send’ button
    - Verify the installation was successful by:
    - Examine the response tests and ensure the ‘Install Successful’ test passed
      - Examine your Postman Global Environment and look for a _f5_workflow_functions item populated with JavaScript code
