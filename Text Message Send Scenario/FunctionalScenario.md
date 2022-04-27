# SMS integration between MKT Cloud and Sinch
<ol>
  <li> [Functional Overview](#functionalOverview) </li>
</ol>
  
## <h1 id="functionalOverview">Functional Overview</h1> 
https://help.sap.com/docs/SAP_MARKETING/0204678aad934e5da0ecf4d40ba38ca9/186c8256e63b763de10000000a4450e5.html?version=1909.YMKT&locale=en-US
Scope Item: Permission Marketing (1T1)
You can perform the following main integration activities for this scope item:
Marketing – Campaign Execution E-Mail Integration (SAP_COM_0016) integration scenario. For more information, see Setting Up Service Provider for Emails and Text Messages.

<h2 id="serviceProviders">Service Provider and Available Features</h2>
Comparison between different service providers
https://answers.sap.com/questions/588831/sap-digital-interconnect-vs-amazon-ses-vs-3rd-part.html 


Sinch - Setting it up 

Note explaining how to configure mkt communication system and channel to connect with sinch provider
https://launchpad.support.sap.com/#/notes/3139793

In detail the following steps happen:
<ul>
  <li>The marketing expert executes a text message campaign.
  <li>The system sends out marketing text messages.
  <li>A recipient is getting the text message on the mobile.
  <li>The recipient unsubscribes by sending the word STOP as reply to the received text message. Optionally, the recipient can send back the word STOP plus the campaign ID to unsubscribe from a specific campaign with a specific marketing area. Prerequisite is that the marketing area separation is active and the campaign ID is part of the sent text message, ideally using personalization attributes in the Content Studio.
  <li>At the end an interaction with type MKT_PERM_OPTOUT and with the marketing area of this campaign is created.
  <li>The mobile service provider sends the text message with the unsubscribe request to Sinch.
  <li>Sinch collects unsubscribe requests and bounces in a queue.
  <li>SAP pulls the unsubscribe requests and bounces, and creates interactions.
  <li>Based on the interactions the system updates marketing permissions
<ul>
Generic Email and Text Message Integration
https://help.sap.com/docs/SAP_MARKETING_CLOUD/0f9408e4921e4ba3bb4a7a1f75f837a7/929b31776e0040dfbd1a553913c88756.html?locale=en-US

## <h1 id="technicalImplementation">Technical Implementation</h1> 

Text Message: Send
https://help.sap.com/docs/SAP_MARKETING_CLOUD/0f9408e4921e4ba3bb4a7a1f75f837a7/c2a5ddf39c14465fab2bc474370d848d.html?locale=en-US

Iflow implementation
https://blogs.sap.com/2018/07/23/sap-marketing-cloud-connect-any-text-message-service-provider-to-sap-marketing-cloud-chapter-1-send-sms/

sinch SMS api documentation
https://developers.sinch.com/docs/sms/ 

## <h1 id="componentes">Changed/Created Components</h1> 

| Objeto | Componente | Detalhes |
|---------|-----------|----------|
|Script|[BOEx_DocumentoVenta](github.com/vertracx/SquadSalesService/blob/main/Concha%20y%20Toro/Cloud%20for%20Customer/Melhorias%20Pedidos%20de%20Venda/%5BRN_PV25%5D%20Criar%20campo%20Regional/BOEx_DocumentoVenta.xbo)|Alteração de script para adicionar campo UUID Regional|
