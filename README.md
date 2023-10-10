# NeoRed: la biblioteca C# para la API REST de NeoRed

Esta API se basa en la arquitectura REST API, lo que permite al usuario administrar fácilmente sus datos con este enfoque basado en recursos.

Cada llamada API se establece en qué tipo de solicitud específica (GET, POST, PUT, DELETE) se utilizará.

La API tiene un límite de 20 conexiones simultáneas y un tiempo de espera de 600 segundos por solicitud.

Para comenzar a utilizar esta API, necesitará su token de acceso(disponible [aqui](https://panel.neosmtp.com/api/)). Recuerde guardar esto muy bien. Los niveles de acceso requeridos se enumeran en la descripción de la solicitud dada.

Todos los repositorios de nuestra libreria son descargables se pueden encontrar en nuestro repositorio de Github [aqui](https://github.com/SoporteNeored/)

Este SDK de C# lo genera automáticamente el proyecto [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 4.0.0
- SDK version: 4.0.22
- Build package: org.openapitools.codegen.languages.CSharpNetCoreClientCodegen

<a name="frameworks-supported"></a>
## Frameworks supported
- .NET Core >=1.0
- .NET Framework >=4.6
- Mono/Xamarin >=vNext

<a name="dependencies"></a>
## Dependencies

- [RestSharp](https://www.nuget.org/packages/RestSharp) - 106.13.0 or later
- [Json.NET](https://www.nuget.org/packages/Newtonsoft.Json/) - 13.0.2 or later
- [JsonSubTypes](https://www.nuget.org/packages/JsonSubTypes/) - 1.8.0 or later
- [System.ComponentModel.Annotations](https://www.nuget.org/packages/System.ComponentModel.Annotations) - 5.0.0 or later

Es posible que las DLL incluidas en el paquete no sean la última versión. Recomendamos usar [NuGet](https://docs.nuget.org/consume/installing-nuget) para obtener la ultima version de los packages:
```
Install-Package RestSharp
Install-Package Newtonsoft.Json
Install-Package JsonSubTypes
Install-Package System.ComponentModel.Annotations
```

NOTA: Las versiones de RestSharp superiores a 105.1.0 tienen un error que provoca que falle la carga de archivos. Consulte [RestSharp#742](https://github.com/restsharp/RestSharp/issues/742).
NOTA: RestSharp para .Net Core crea un nuevo socket para cada llamada a la API, lo que puede provocar un problema de agotamiento del socket. Consulte [RestSharp#1406](https://github.com/restsharp/RestSharp/issues/1406).

<a name="installation"></a>
## Installation
Generate the DLL using your preferred tool (e.g. `dotnet build`)

Luego incluya la DLL (en la carpeta `bin`) en el proyecto C# y use los espacios de nombres:
```csharp
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;
```
<a name="usage"></a>
## Usage

Para utilizar el cliente API con un proxy HTTP, configure un `System.Net.WebProxy`
```csharp
Configuration c = new Configuration();
System.Net.WebProxy webProxy = new System.Net.WebProxy("http://myProxyUrl:80/");
webProxy.Credentials = System.Net.CredentialCache.DefaultCredentials;
c.Proxy = webProxy;
```

<a name="getting-started"></a>
## Getting Started

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class Example
    {
        public static void Main()
        {

            Configuration config = new Configuration();
            config.BasePath = "https://api.NeoRed.com/v4";
            // Configurar la autorización de la clave API: apikey
            config.ApiKey.Add("X-NeoRed-ApiKey", "YOUR_API_KEY");
            // Descomentar a continuación para configurar el prefijo (por ejemplo, portador) para la clave API, si es necesario
             // config.ApiKeyPrefix.Add("X-NeoRed-ApiKey", "Portador");

            var apiInstance = new CampaignsApi(config);
            var name = "name_example";  // string | Nombre de la campaña a eliminar

            try
            {
                // Delete Campaign
                apiInstance.CampaignsByNameDelete(name);
            }
            catch (ApiException e)
            {
                Debug.Print("Excepción al llamar a CampaignsApi.CampaignsByNameDelete: " + e.Message );
                Debug.Print("Status Code: "+ e.ErrorCode);
                Debug.Print(e.StackTrace);
            }

        }
    }
}
```

<a name="documentation-for-api-endpoints"></a>


Todos los URI son relativos

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*CampaignsApi* | [**CampaignsByNameDelete**]([Docs/CampaignsApi.md#CampaignsByNameDelete)) | **DELETE** /campaigns/{name} | Delete Campaign
*CampaignsApi* | [**CampaignsByNameGet**](Docs/CampaignsApi.md#campaignsbynameget) | **GET** /campaigns/{name} | Load Campaign
*CampaignsApi* | [**CampaignsByNamePut**](Docs/CampaignsApi.md#campaignsbynameput) | **PUT** /campaigns/{name} | Update Campaign
*CampaignsApi* | [**CampaignsGet**](Docs/CampaignsApi.md#campaignsget) | **GET** /campaigns | Load Campaigns
*CampaignsApi* | [**CampaignsPost**](Docs/CampaignsApi.md#campaignspost) | **POST** /campaigns | Add Campaign
*ContactsApi* | [**ContactsByEmailDelete**](Docs/ContactsApi.md#contactsbyemaildelete) | **DELETE** /contacts/{email} | Delete Contact
*ContactsApi* | [**ContactsByEmailGet**](Docs/ContactsApi.md#contactsbyemailget) | **GET** /contacts/{email} | Load Contact
*ContactsApi* | [**ContactsByEmailPut**](Docs/ContactsApi.md#contactsbyemailput) | **PUT** /contacts/{email} | Update Contact
*ContactsApi* | [**ContactsDeletePost**](Docs/ContactsApi.md#contactsdeletepost) | **POST** /contacts/delete | Delete Contacts Bulk
*ContactsApi* | [**ContactsExportByIdStatusGet**](Docs/ContactsApi.md#contactsexportbyidstatusget) | **GET** /contacts/export/{id}/status | Check Export Status
*ContactsApi* | [**ContactsExportPost**](Docs/ContactsApi.md#contactsexportpost) | **POST** /contacts/export | Export Contacts
*ContactsApi* | [**ContactsGet**](Docs/ContactsApi.md#contactsget) | **GET** /contacts | Load Contacts
*ContactsApi* | [**ContactsImportPost**](Docs/ContactsApi.md#contactsimportpost) | **POST** /contacts/import | Upload Contacts
*ContactsApi* | [**ContactsPost**](Docs/ContactsApi.md#contactspost) | **POST** /contacts | Add Contact
*EmailsApi* | [**EmailsByMsgidViewGet**](Docs/EmailsApi.md#emailsbymsgidviewget) | **GET** /emails/{msgid}/view | View Email
*EmailsApi* | [**EmailsMergefilePost**](Docs/EmailsApi.md#emailsmergefilepost) | **POST** /emails/mergefile | Send Bulk Emails CSV
*EmailsApi* | [**EmailsPost**](Docs/EmailsApi.md#emailspost) | **POST** /emails | Send Bulk Emails
*EmailsApi* | [**EmailsTransactionalPost**](Docs/EmailsApi.md#emailstransactionalpost) | **POST** /emails/transactional | Send Transactional Email
*EventsApi* | [**EventsByTransactionidGet**](Docs/EventsApi.md#eventsbytransactionidget) | **GET** /events/{transactionid} | Load Email Events
*EventsApi* | [**EventsChannelsByNameExportPost**](Docs/EventsApi.md#eventschannelsbynameexportpost) | **POST** /events/channels/{name}/export | Export Channel Events
*EventsApi* | [**EventsChannelsByNameGet**](Docs/EventsApi.md#eventschannelsbynameget) | **GET** /events/channels/{name} | Load Channel Events
*EventsApi* | [**EventsChannelsExportByIdStatusGet**](Docs/EventsApi.md#eventschannelsexportbyidstatusget) | **GET** /events/channels/export/{id}/status | Check Channel Export Status
*EventsApi* | [**EventsExportByIdStatusGet**](Docs/EventsApi.md#eventsexportbyidstatusget) | **GET** /events/export/{id}/status | Check Export Status
*EventsApi* | [**EventsExportPost**](Docs/EventsApi.md#eventsexportpost) | **POST** /events/export | Export Events
*EventsApi* | [**EventsGet**](Docs/EventsApi.md#eventsget) | **GET** /events | Load Events
*FilesApi* | [**FilesByNameDelete**](Docs/FilesApi.md#filesbynamedelete) | **DELETE** /files/{name} | Delete File
*FilesApi* | [**FilesByNameGet**](Docs/FilesApi.md#filesbynameget) | **GET** /files/{name} | Download File
*FilesApi* | [**FilesByNameInfoGet**](Docs/FilesApi.md#filesbynameinfoget) | **GET** /files/{name}/info | Load File Details
*FilesApi* | [**FilesGet**](Docs/FilesApi.md#filesget) | **GET** /files | List Files
*FilesApi* | [**FilesPost**](Docs/FilesApi.md#filespost) | **POST** /files | Upload File
*InboundRouteApi* | [**InboundrouteByIdDelete**](Docs/InboundRouteApi.md#inboundroutebyiddelete) | **DELETE** /inboundroute/{id} | Delete Route
*InboundRouteApi* | [**InboundrouteByIdGet**](Docs/InboundRouteApi.md#inboundroutebyidget) | **GET** /inboundroute/{id} | Get Route
*InboundRouteApi* | [**InboundrouteByIdPut**](Docs/InboundRouteApi.md#inboundroutebyidput) | **PUT** /inboundroute/{id} | Update Route
*InboundRouteApi* | [**InboundrouteGet**](Docs/InboundRouteApi.md#inboundrouteget) | **GET** /inboundroute | Get Routes
*InboundRouteApi* | [**InboundrouteOrderPut**](Docs/InboundRouteApi.md#inboundrouteorderput) | **PUT** /inboundroute/order | Update Sorting
*InboundRouteApi* | [**InboundroutePost**](Docs/InboundRouteApi.md#inboundroutepost) | **POST** /inboundroute | Create Route
*ListsApi* | [**ListsByNameContactsPost**](Docs/ListsApi.md#listsbynamecontactspost) | **POST** /lists/{name}/contacts | Add Contacts to List
*ListsApi* | [**ListsByNameContactsRemovePost**](Docs/ListsApi.md#listsbynamecontactsremovepost) | **POST** /lists/{name}/contacts/remove | Remove Contacts from List
*ListsApi* | [**ListsByNameDelete**](Docs/ListsApi.md#listsbynamedelete) | **DELETE** /lists/{name} | Delete List
*ListsApi* | [**ListsByNameGet**](Docs/ListsApi.md#listsbynameget) | **GET** /lists/{name} | Load List
*ListsApi* | [**ListsByNamePut**](Docs/ListsApi.md#listsbynameput) | **PUT** /lists/{name} | Update List
*ListsApi* | [**ListsGet**](Docs/ListsApi.md#listsget) | **GET** /lists | Load Lists
*ListsApi* | [**ListsPost**](Docs/ListsApi.md#listspost) | **POST** /lists | Add List
*SecurityApi* | [**SecurityApikeysByNameDelete**](Docs/SecurityApi.md#securityapikeysbynamedelete) | **DELETE** /security/apikeys/{name} | Delete ApiKey
*SecurityApi* | [**SecurityApikeysByNameGet**](Docs/SecurityApi.md#securityapikeysbynameget) | **GET** /security/apikeys/{name} | Load ApiKey
*SecurityApi* | [**SecurityApikeysByNamePut**](Docs/SecurityApi.md#securityapikeysbynameput) | **PUT** /security/apikeys/{name} | Update ApiKey
*SecurityApi* | [**SecurityApikeysGet**](Docs/SecurityApi.md#securityapikeysget) | **GET** /security/apikeys | List ApiKeys
*SecurityApi* | [**SecurityApikeysPost**](Docs/SecurityApi.md#securityapikeyspost) | **POST** /security/apikeys | Add ApiKey
*SecurityApi* | [**SecuritySmtpByNameDelete**](Docs/SecurityApi.md#securitysmtpbynamedelete) | **DELETE** /security/smtp/{name} | Delete SMTP Credential
*SecurityApi* | [**SecuritySmtpByNameGet**](Docs/SecurityApi.md#securitysmtpbynameget) | **GET** /security/smtp/{name} | Load SMTP Credential
*SecurityApi* | [**SecuritySmtpByNamePut**](Docs/SecurityApi.md#securitysmtpbynameput) | **PUT** /security/smtp/{name} | Update SMTP Credential
*SecurityApi* | [**SecuritySmtpGet**](Docs/SecurityApi.md#securitysmtpget) | **GET** /security/smtp | List SMTP Credentials
*SecurityApi* | [**SecuritySmtpPost**](Docs/SecurityApi.md#securitysmtppost) | **POST** /security/smtp | Add SMTP Credential
*SegmentsApi* | [**SegmentsByNameDelete**](Docs/SegmentsApi.md#segmentsbynamedelete) | **DELETE** /segments/{name} | Delete Segment
*SegmentsApi* | [**SegmentsByNameGet**](Docs/SegmentsApi.md#segmentsbynameget) | **GET** /segments/{name} | Load Segment
*SegmentsApi* | [**SegmentsByNamePut**](Docs/SegmentsApi.md#segmentsbynameput) | **PUT** /segments/{name} | Update Segment
*SegmentsApi* | [**SegmentsGet**](Docs/SegmentsApi.md#segmentsget) | **GET** /segments | Load Segments
*SegmentsApi* | [**SegmentsPost**](Docs/SegmentsApi.md#segmentspost) | **POST** /segments | Add Segment
*StatisticsApi* | [**StatisticsCampaignsByNameGet**](Docs/StatisticsApi.md#statisticscampaignsbynameget) | **GET** /statistics/campaigns/{name} | Load Campaign Stats
*StatisticsApi* | [**StatisticsCampaignsGet**](Docs/StatisticsApi.md#statisticscampaignsget) | **GET** /statistics/campaigns | Load Campaigns Stats
*StatisticsApi* | [**StatisticsChannelsByNameGet**](Docs/StatisticsApi.md#statisticschannelsbynameget) | **GET** /statistics/channels/{name} | Load Channel Stats
*StatisticsApi* | [**StatisticsChannelsGet**](Docs/StatisticsApi.md#statisticschannelsget) | **GET** /statistics/channels | Load Channels Stats
*StatisticsApi* | [**StatisticsGet**](Docs/StatisticsApi.md#statisticsget) | **GET** /statistics | Load Statistics
*SubAccountsApi* | [**SubaccountsByEmailCreditsPatch**](Docs/SubAccountsApi.md#subaccountsbyemailcreditspatch) | **PATCH** /subaccounts/{email}/credits | Add, Subtract Email Credits
*SubAccountsApi* | [**SubaccountsByEmailDelete**](Docs/SubAccountsApi.md#subaccountsbyemaildelete) | **DELETE** /subaccounts/{email} | Delete SubAccount
*SubAccountsApi* | [**SubaccountsByEmailGet**](Docs/SubAccountsApi.md#subaccountsbyemailget) | **GET** /subaccounts/{email} | Load SubAccount
*SubAccountsApi* | [**SubaccountsByEmailSettingsEmailPut**](Docs/SubAccountsApi.md#subaccountsbyemailsettingsemailput) | **PUT** /subaccounts/{email}/settings/email | Update SubAccount Email Settings
*SubAccountsApi* | [**SubaccountsGet**](Docs/SubAccountsApi.md#subaccountsget) | **GET** /subaccounts | Load SubAccounts
*SubAccountsApi* | [**SubaccountsPost**](Docs/SubAccountsApi.md#subaccountspost) | **POST** /subaccounts | Add SubAccount
*SuppressionsApi* | [**SuppressionsBouncesGet**](Docs/SuppressionsApi.md#suppressionsbouncesget) | **GET** /suppressions/bounces | Get Bounce List
*SuppressionsApi* | [**SuppressionsBouncesImportPost**](Docs/SuppressionsApi.md#suppressionsbouncesimportpost) | **POST** /suppressions/bounces/import | Add Bounces Async
*SuppressionsApi* | [**SuppressionsBouncesPost**](Docs/SuppressionsApi.md#suppressionsbouncespost) | **POST** /suppressions/bounces | Add Bounces
*SuppressionsApi* | [**SuppressionsByEmailDelete**](Docs/SuppressionsApi.md#suppressionsbyemaildelete) | **DELETE** /suppressions/{email} | Delete Suppression
*SuppressionsApi* | [**SuppressionsByEmailGet**](Docs/SuppressionsApi.md#suppressionsbyemailget) | **GET** /suppressions/{email} | Get Suppression
*SuppressionsApi* | [**SuppressionsComplaintsGet**](Docs/SuppressionsApi.md#suppressionscomplaintsget) | **GET** /suppressions/complaints | Get Complaints List
*SuppressionsApi* | [**SuppressionsComplaintsImportPost**](Docs/SuppressionsApi.md#suppressionscomplaintsimportpost) | **POST** /suppressions/complaints/import | Add Complaints Async
*SuppressionsApi* | [**SuppressionsComplaintsPost**](Docs/SuppressionsApi.md#suppressionscomplaintspost) | **POST** /suppressions/complaints | Add Complaints
*SuppressionsApi* | [**SuppressionsGet**](Docs/SuppressionsApi.md#suppressionsget) | **GET** /suppressions | Get Suppressions
*SuppressionsApi* | [**SuppressionsUnsubscribesGet**](Docs/SuppressionsApi.md#suppressionsunsubscribesget) | **GET** /suppressions/unsubscribes | Get Unsubscribes List
*SuppressionsApi* | [**SuppressionsUnsubscribesImportPost**](Docs/SuppressionsApi.md#suppressionsunsubscribesimportpost) | **POST** /suppressions/unsubscribes/import | Add Unsubscribes Async
*SuppressionsApi* | [**SuppressionsUnsubscribesPost**](Docs/SuppressionsApi.md#suppressionsunsubscribespost) | **POST** /suppressions/unsubscribes | Add Unsubscribes
*TemplatesApi* | [**TemplatesByNameDelete**](Docs/TemplatesApi.md#templatesbynamedelete) | **DELETE** /templates/{name} | Delete Template
*TemplatesApi* | [**TemplatesByNameGet**](Docs/TemplatesApi.md#templatesbynameget) | **GET** /templates/{name} | Load Template
*TemplatesApi* | [**TemplatesByNamePut**](Docs/TemplatesApi.md#templatesbynameput) | **PUT** /templates/{name} | Update Template
*TemplatesApi* | [**TemplatesGet**](Docs/TemplatesApi.md#templatesget) | **GET** /templates | Load Templates
*TemplatesApi* | [**TemplatesPost**](Docs/TemplatesApi.md#templatespost) | **POST** /templates | Add Template
*VerificationsApi* | [**VerificationsByEmailDelete**](Docs/VerificationsApi.md#verificationsbyemaildelete) | **DELETE** /verifications/{email} | Delete Email Verification Result
*VerificationsApi* | [**VerificationsByEmailGet**](Docs/VerificationsApi.md#verificationsbyemailget) | **GET** /verifications/{email} | Get Email Verification Result
*VerificationsApi* | [**VerificationsByEmailPost**](Docs/VerificationsApi.md#verificationsbyemailpost) | **POST** /verifications/{email} | Verify Email
*VerificationsApi* | [**VerificationsFilesByIdDelete**](Docs/VerificationsApi.md#verificationsfilesbyiddelete) | **DELETE** /verifications/files/{id} | Delete File Verification Result
*VerificationsApi* | [**VerificationsFilesByIdResultDownloadGet**](Docs/VerificationsApi.md#verificationsfilesbyidresultdownloadget) | **GET** /verifications/files/{id}/result/download | Download File Verification Result
*VerificationsApi* | [**VerificationsFilesByIdResultGet**](Docs/VerificationsApi.md#verificationsfilesbyidresultget) | **GET** /verifications/files/{id}/result | Get Detailed File Verification Result
*VerificationsApi* | [**VerificationsFilesByIdVerificationPost**](Docs/VerificationsApi.md#verificationsfilesbyidverificationpost) | **POST** /verifications/files/{id}/verification | Start verification
*VerificationsApi* | [**VerificationsFilesPost**](Docs/VerificationsApi.md#verificationsfilespost) | **POST** /verifications/files | Upload File with Emails
*VerificationsApi* | [**VerificationsFilesResultGet**](Docs/VerificationsApi.md#verificationsfilesresultget) | **GET** /verifications/files/result | Get Files Verification Results
*VerificationsApi* | [**VerificationsGet**](Docs/VerificationsApi.md#verificationsget) | **GET** /verifications | Get Emails Verification Results


<a name="documentation-for-models"></a>
## Documentation for Models

 - [Model.AccessLevel](Docs/AccessLevel.md)
 - [Model.AccountStatusEnum](Docs/AccountStatusEnum.md)
 - [Model.ApiKey](Docs/ApiKey.md)
 - [Model.ApiKeyPayload](Docs/ApiKeyPayload.md)
 - [Model.BodyContentType](Docs/BodyContentType.md)
 - [Model.BodyPart](Docs/BodyPart.md)
 - [Model.Campaign](Docs/Campaign.md)
 - [Model.CampaignOptions](Docs/CampaignOptions.md)
 - [Model.CampaignRecipient](Docs/CampaignRecipient.md)
 - [Model.CampaignStatus](Docs/CampaignStatus.md)
 - [Model.CampaignTemplate](Docs/CampaignTemplate.md)
 - [Model.ChannelLogStatusSummary](Docs/ChannelLogStatusSummary.md)
 - [Model.CompressionFormat](Docs/CompressionFormat.md)
 - [Model.ConsentData](Docs/ConsentData.md)
 - [Model.ConsentTracking](Docs/ConsentTracking.md)
 - [Model.Contact](Docs/Contact.md)
 - [Model.ContactActivity](Docs/ContactActivity.md)
 - [Model.ContactPayload](Docs/ContactPayload.md)
 - [Model.ContactSource](Docs/ContactSource.md)
 - [Model.ContactStatus](Docs/ContactStatus.md)
 - [Model.ContactUpdatePayload](Docs/ContactUpdatePayload.md)
 - [Model.ContactsList](Docs/ContactsList.md)
 - [Model.DeliveryOptimizationType](Docs/DeliveryOptimizationType.md)
 - [Model.EmailContent](Docs/EmailContent.md)
 - [Model.EmailData](Docs/EmailData.md)
 - [Model.EmailMessageData](Docs/EmailMessageData.md)
 - [Model.EmailPredictedValidationStatus](Docs/EmailPredictedValidationStatus.md)
 - [Model.EmailRecipient](Docs/EmailRecipient.md)
 - [Model.EmailSend](Docs/EmailSend.md)
 - [Model.EmailStatus](Docs/EmailStatus.md)
 - [Model.EmailTransactionalMessageData](Docs/EmailTransactionalMessageData.md)
 - [Model.EmailValidationResult](Docs/EmailValidationResult.md)
 - [Model.EmailValidationStatus](Docs/EmailValidationStatus.md)
 - [Model.EmailView](Docs/EmailView.md)
 - [Model.EmailsPayload](Docs/EmailsPayload.md)
 - [Model.EncodingType](Docs/EncodingType.md)
 - [Model.EventType](Docs/EventType.md)
 - [Model.EventsOrderBy](Docs/EventsOrderBy.md)
 - [Model.ExportFileFormats](Docs/ExportFileFormats.md)
 - [Model.ExportLink](Docs/ExportLink.md)
 - [Model.ExportStatus](Docs/ExportStatus.md)
 - [Model.FileInfo](Docs/FileInfo.md)
 - [Model.FilePayload](Docs/FilePayload.md)
 - [Model.FileUploadResult](Docs/FileUploadResult.md)
 - [Model.InboundPayload](Docs/InboundPayload.md)
 - [Model.InboundRoute](Docs/InboundRoute.md)
 - [Model.InboundRouteActionType](Docs/InboundRouteActionType.md)
 - [Model.InboundRouteFilterType](Docs/InboundRouteFilterType.md)
 - [Model.ListPayload](Docs/ListPayload.md)
 - [Model.ListUpdatePayload](Docs/ListUpdatePayload.md)
 - [Model.LogJobStatus](Docs/LogJobStatus.md)
 - [Model.LogStatusSummary](Docs/LogStatusSummary.md)
 - [Model.MergeEmailPayload](Docs/MergeEmailPayload.md)
 - [Model.MessageAttachment](Docs/MessageAttachment.md)
 - [Model.MessageCategory](Docs/MessageCategory.md)
 - [Model.NewApiKey](Docs/NewApiKey.md)
 - [Model.NewSmtpCredentials](Docs/NewSmtpCredentials.md)
 - [Model.Options](Docs/Options.md)
 - [Model.RecipientEvent](Docs/RecipientEvent.md)
 - [Model.Segment](Docs/Segment.md)
 - [Model.SegmentPayload](Docs/SegmentPayload.md)
 - [Model.SmtpCredentials](Docs/SmtpCredentials.md)
 - [Model.SmtpCredentialsPayload](Docs/SmtpCredentialsPayload.md)
 - [Model.SortOrderItem](Docs/SortOrderItem.md)
 - [Model.SplitOptimizationType](Docs/SplitOptimizationType.md)
 - [Model.SplitOptions](Docs/SplitOptions.md)
 - [Model.SubAccountInfo](Docs/SubAccountInfo.md)
 - [Model.SubaccountEmailCreditsPayload](Docs/SubaccountEmailCreditsPayload.md)
 - [Model.SubaccountEmailSettings](Docs/SubaccountEmailSettings.md)
 - [Model.SubaccountEmailSettingsPayload](Docs/SubaccountEmailSettingsPayload.md)
 - [Model.SubaccountPayload](Docs/SubaccountPayload.md)
 - [Model.SubaccountSettingsInfo](Docs/SubaccountSettingsInfo.md)
 - [Model.SubaccountSettingsInfoPayload](Docs/SubaccountSettingsInfoPayload.md)
 - [Model.Suppression](Docs/Suppression.md)
 - [Model.Template](Docs/Template.md)
 - [Model.TemplatePayload](Docs/TemplatePayload.md)
 - [Model.TemplateScope](Docs/TemplateScope.md)
 - [Model.TemplateType](Docs/TemplateType.md)
 - [Model.TransactionalRecipient](Docs/TransactionalRecipient.md)
 - [Model.Utm](Docs/Utm.md)
 - [Model.VerificationFileResult](Docs/VerificationFileResult.md)
 - [Model.VerificationFileResultDetails](Docs/VerificationFileResultDetails.md)
 - [Model.VerificationStatus](Docs/VerificationStatus.md)


<a name="documentation-for-authorization"></a>
## Documentación para autorización

<a name="apikey"></a>
### apikey

- **Type**: API key
- **API key parameter name**: X-NeoRed-ApiKey
- **Location**: HTTP header

