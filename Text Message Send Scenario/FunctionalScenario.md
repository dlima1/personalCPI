https://help.sap.com/docs/SAP_MARKETING/0204678aad934e5da0ecf4d40ba38ca9/186c8256e63b763de10000000a4450e5.html?version=1909.YMKT&locale=en-US
Scope Item: Permission Marketing (1T1)
You can perform the following main integration activities for this scope item:
Marketing – Campaign Execution E-Mail Integration (SAP_COM_0016) integration scenario. For more information, see Setting Up Service Provider for Emails and Text Messages.

Service Provider and Available Features

Setting up sinch

In detail the following steps happen:
The marketing expert executes a text message campaign.
The system sends out marketing text messages.
A recipient is getting the text message on the mobile.
The recipient unsubscribes by sending the word STOP as reply to the received text message. Optionally, the recipient can send back the word STOP plus the campaign ID to unsubscribe from a specific campaign with a specific marketing area. Prerequisite is that the marketing area separation is active and the campaign ID is part of the sent text message, ideally using personalization attributes in the Content Studio.
At the end an interaction with type MKT_PERM_OPTOUT and with the marketing area of this campaign is created.
The mobile service provider sends the text message with the unsubscribe request to Sinch.
Sinch collects unsubscribe requests and bounces in a queue.
SAP pulls the unsubscribe requests and bounces, and creates interactions.
Based on the interactions the system updates marketing permissions
Generic Email and Text Message Integration
https://help.sap.com/docs/SAP_MARKETING_CLOUD/0f9408e4921e4ba3bb4a7a1f75f837a7/929b31776e0040dfbd1a553913c88756.html?locale=en-US

Text Message: Send
https://help.sap.com/docs/SAP_MARKETING_CLOUD/0f9408e4921e4ba3bb4a7a1f75f837a7/c2a5ddf39c14465fab2bc474370d848d.html?locale=en-US

Iflow implementation
https://blogs.sap.com/2018/07/23/sap-marketing-cloud-connect-any-text-message-service-provider-to-sap-marketing-cloud-chapter-1-send-sms/
