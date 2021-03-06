Scenario 05  API Versioning


Problem:

APi versioning is a key functionality that needs to be addressed once the users used to expose a specific API for a long time and when they need to add, remove or change the API’ in future. When doing this there may be uses who are using the old API. Hence while introducing the new API Old API should also be supported for a specific time period. That time period is offered basically because to guide the uses and give a period for them to switch to the new API. 


Scenario:

Ability to retire old APIs and introduce new versions of APIs to enhance its functionality
Ensure that API updates don’t break when upgraded/versioned or moved between environments, geographies, data centers and the cloud
A/B testing with old vs new APIs
Ability to notify consumers of the old version about the availability of the new API version
Enforcing a grace period to upgrade to the new version of the API
Transferring contracts with app developers to newer versions.



Covered Automations:

Positive  

Management Console

Create Suscriber, Creator, Publisher users and roles from the APIM Management console and assign them with the relavent permissions
Set the subscribers email address from the subscriber profile
Update the registory resource file in the location /resource/_system/config/apimgt/applicationdata/tenant-conf.json to enable notification sending and to set the email template

API Publisher

Register and generate and token
Create API with Version 1.0.0
API Migration API Export
Change API state from Create to Publish for API Version 1.0.0
Change API Version 

API Subscriber


Obtain client Id and Secret
Generate  access token
Create application
Create subscription

API Publisher

Change new API state from create to publish

Terminate Tests
Unsubscribe Application
Delete Application
Remove users and roles
Delete old API
Delete new API

Configurations

Need to download Governance registry 5.4.0 and copy resource.war from G-Reg/repository/deployment/server/webapps to APIM-Home/repository/deployment/server/webapps. This is required to support Registry REST APIs by APIM
Need to Copy the downloaded api-import-export-2.1.0-v3.war file to the APIM_HOME/repository/deployment/server/webapps folder.
Need to configure API-M_HOME/repository/conf/output-event-adapters.xml file under the <adapterConfig type="email"> section as below

<property key="mail.smtp.from">dewmi123455@gmail.com</property>
       <property key="mail.smtp.user">dewmi123455</property>
       <property key="mail.smtp.password">password</property>
       <property key="mail.smtp.host">smtp.gmail.com</property>
       <property key="mail.smtp.port">587</property>


If you are using a Google mail account, note that Google has restricted third-party apps and less secure apps from sending emails by default. Therefore, you need to configure your account to disable this restriction.
