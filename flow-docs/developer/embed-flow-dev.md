---
title: Microsoft Flow integreren met websites en apps | Microsoft Docs
description: Sluit de Microsoft Flow-ervaring in uw website of app in.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: cf2f14826670cf221411fa2204ee9b2c5581222e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547710"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Microsoft Flow integreren met websites en apps
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Sluit Microsoft Flow in uw app of website in met behulp van *flow widgets* om uw gebruikers een eenvoudige manier te bieden om hun persoonlijke of professionele taken te automatiseren.

Flow widgets zijn iframes die zich in een host-document bevinden. Dit document verwijst naar een pagina in de ontwerp functie van Microsoft Flow. Deze widgets integreren specifieke Microsoft Flow functionaliteit in de toepassing van derden.

Widgets kunnen eenvoudig zijn. Bijvoorbeeld een widget waarmee een lijst sjablonen wordt weer gegeven zonder communicatie tussen de host en IFRAME. Widgets kunnen ook complex zijn. Bijvoorbeeld een widget die een stroom van een sjabloon inricht en vervolgens de stroom activeert via twee richtings communicatie tussen de host en de widget.

## <a name="prerequisites"></a>Vereisten

- Een **micro soft-account** of
- Een werk-of school account

## <a name="use-the-unauthenticated-widget"></a>De niet-geverifieerde widget gebruiken
Als u het object niet-geverifieerde sjablonen wilt gebruiken, sluit u het rechtstreeks in de hosttoepassing in met behulp van een IFRAME. U hebt de JS-SDK of een toegangs token niet nodig. 

### <a name="show-templates-for-your-scenarios"></a>Sjablonen voor uw scenario's weer geven
Als u wilt beginnen, voegt u deze code toe om de Microsoft Flow sjablonen op uw website weer te geven:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}&category={category}"></iframe>
```

| Bepaalde | Beschrijvingen |
| --- | --- |
| instelling |De taal-en regio code van vier letters voor de sjabloon weergave. `en-us` bijvoorbeeld vertegenwoordigt Amerikaans-Engels en `de-de` vertegenwoordigt Duits. |
| Zoek term |De zoek term voor de sjablonen die u in de weer gave wilt weer geven. Zoek bijvoorbeeld `wunderlist` om sjablonen voor Wunderlist weer te geven. |
| aantal sjablonen |Het aantal sjablonen dat u in de weer gave wilt weer geven. |
| Beoogde |De pagina die wordt geopend wanneer gebruikers de sjabloon selecteren. Voer `details` in om de details van de sjabloon weer te geven, of voer `new` in om de Microsoft Flow Designer te openen. |
| rubriek |Hiermee wordt gefilterd op de opgegeven sjabloon categorie. | 
| instellen. naam |Aanvullende context voor het door geven van de stroom. |


Als de bestemmings parameter is `new`, wordt de Microsoft Flow Designer geopend wanneer gebruikers een sjabloon selecteren. Gebruikers kunnen vervolgens een stroom maken in de ontwerp functie. Zie de volgende sectie als u de volledige ervaring van de widget wilt hebben.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Aanvullende para meters door geven aan de stroom sjabloon

Als de gebruiker zich in een specifieke context in uw website of app bevindt, kunt u deze context door geven aan de stroom. Een gebruiker kan bijvoorbeeld een sjabloon openen om mij op de *hoogte te stellen wanneer een item wordt toegevoegd aan een lijst* en een bepaalde lijst in Wunderlist bekijkt. Volg deze stappen om de lijst-ID als een *para meter* aan de stroom door te geven:

1. Definieer de para meter in de stroom sjabloon voordat u deze publiceert. Een para meter ziet eruit als `@{parameters('parameter_name')}`.
1. Geef de para meter door in de query reeks van de bron-IFRAME. Voeg bijvoorbeeld `&parameters.listName={the name of the list}` toe als u een para meter met de naam **noemer**hebt.

### <a name="full-sample"></a>Volledig voor beeld

Gebruik de volgende code om de vier sjablonen van de Wunderlist in het Duits weer te geven en om de gebruiker te starten met **myCoolList**:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>De geverifieerde stroom widgets gebruiken

In de volgende tabel ziet u de lijst met Microsoft Flow widgets die de volledige ervaring in de widget ondersteunen met behulp van toegangs token voor gebruikers verificatie. U moet de Java script Software Developer Kit (JS-SDK) van Microsoft Flow gebruiken om de widgets in te sluiten en het vereiste token voor gebruikers toegang te bieden.

| Type widget    | Ondersteunde functie                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| Terugloop          | Toont een lijst met stromen op een tabblad voor persoonlijke en gedeelde stromen. Bewerk een bestaande stroom of maak een nieuwe stroom op basis van een sjabloon of leeg. | 
| flowCreation   | Hiermee maakt u een stroom op basis van een sjabloon-id die de hosttoepassing levert.                                                                | 
| gezamenlijke        | Hiermee activeert u een hand matige of hybride trigger stroom die de hosttoepassing levert.                                                        | 
| approvalCenter | Hiermee worden goedkeurings aanvragen en verzonden goed keuringen Inge sloten.                                                                                        | 
| Sjablonen      | Hiermee wordt een lijst met sjablonen weer gegeven. De gebruiker kiest één om een nieuwe stroom te maken.                                                                         | 

Gebruik de geauthenticeerde flow-SDK om gebruikers toe te staan om stromen rechtstreeks te maken en te beheren vanuit uw website of app (in plaats van naar Microsoft Flow). U moet de gebruiker ondertekenen met hun micro soft-account of Azure Active Directory om de geverifieerde SDK te gebruiken.

> [!NOTE]
> Het is niet mogelijk om de Microsoft Flow huis stijl te verbergen wanneer u widgets gebruikt.

## <a name="widget-architecture"></a>architectuur van widget

Microsoft Flow widgets werk door een IFRAME in te sluiten dat verwijst naar Microsoft Flow naar een host-toepassing. De host biedt het toegangs token dat vereist is voor de widget Microsoft Flow. Met de JS SDK van Microsoft Flow kan de hosttoepassing de levens cyclus van de widget initialiseren en beheren.

![architectuur van widget](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>JS-SDK-Details

Het Microsoft Flow-team biedt de JS-SDK om stroom widgets te kunnen integreren in toepassingen van derden. De flow JS SDK is beschikbaar als een open bare koppeling in de flow-service. Hiermee kan de hosttoepassing gebeurtenissen van de widget afhandelen en met de stroom toepassing communiceren door acties naar de widget te verzenden. Widget-gebeurtenissen en-acties zijn specifiek voor het type widget.

### <a name="widget-initialization"></a>Widget initialisatie

De flow JS SDK-verwijzing moet worden toegevoegd aan de hosttoepassing voordat de widget kan worden geïnitialiseerd.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Maak een JS SDK-exemplaar door optionele hostNamen en land instellingen in een JSON-object door te geven.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US'
}); 
```

| Naam     | Vereist/optioneel | Beschrijvingen                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Beschrijving          | Microsoft Flow hostnaam, bijvoorbeeld https://flow.microsoft.com        | 
| `locale`   | Beschrijving          | Land instellingen van de client voor de widget (de standaard waarde is `en-Us` als deze niet is opgegeven) | 


Zodra de JS SDK-instantie is gemaakt, kunt u een Microsoft Flow-widget initialiseren en insluiten in een bovenliggend element in de hosttoepassing. Als u dit wilt doen, voegt u een HTML-DIV toe:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Initialiseer vervolgens de Microsoft Flow-widget met de JS-SDK-`renderWidget()` methode. Zorg ervoor dat u het type widget en de bijbehorende instellingen opgeeft.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flowDiv',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {}
});
```

Hier volgt een voorbeeld stijl voor de container die u kunt aanpassen, zodat deze overeenkomt met de dimensies van de hosttoepassing.

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

Dit zijn de para meters voor `renderWidget()`: 

| Bepaalde        | Vereist/optioneel | Beschrijvingen                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Vereist          | Id van een DIV-element op de hostpagina waar de widget wordt Inge sloten.                   | 
| `environmentId`    | Beschrijving          | Voor widgets is een omgevings-ID vereist. Als u geen id opgeeft, wordt er een standaard omgeving gebruikt. | 
| `flowsSettings`    | Beschrijving          | Microsoft Flow-instellingen object                                                                        | 
| `templateSettings` | Beschrijving          | Sjabloon instellingen object                                                                    | 
| `approvalSettings` | Beschrijving          | Goedkeurings instellingen object                                                                    | 

### <a name="access-tokens"></a>Toegangs tokens

Nadat de JS-SDK `renderWidget()` uitgevoerd, initialiseert de JS-SDK een IFRAME dat verwijst naar de URL van de Microsoft Flow-widget. Deze URL bevat alle instellingen in de query reeks parameters. De hosttoepassing moet een Microsoft Flow toegangs Token ophalen voor de gebruiker (Azure Active Directory JWT-token met de doel groep https://service.flow.microsoft.com) voordat de widget wordt geïnitialiseerd. De widget genereert een `GET_ACCESS_TOKEN` gebeurtenis om een toegangs token aan te vragen bij de host. De host moet de gebeurtenis afhandelen en het token door geven aan de widget:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

De hosttoepassing is verantwoordelijk voor het onderhouden van het token en geeft dit door met een geldige verval datum naar de widget wanneer daarom wordt gevraagd. Als de widget langer dan een periode is geopend, moet de host controleren of het token is verlopen en het token vernieuwen als dit nodig is voordat het aan de widget wordt door gegeven.

### <a name="detecting-if-the-widget-is-ready"></a>Detecteren of de widget gereed is

Nadat de initialisatie is voltooid, wordt een gebeurtenis door de widget gegenereerd om te melden dat de widget gereed is. De host kan Luis teren naar de `WIDGET_READY` gebeurtenis en eventuele extra hostcode uitvoeren.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Widget instellingen

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings kan worden gebruikt om de functionaliteit van de widget Microsoft Flow aan te passen.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Bepaalde | Vereist/optioneel | Beschrijvingen | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Vereist | Gebruik de GUID van de sjabloon wanneer de gebruiker de knop **maken van lege** in de flow-widget selecteert. | 
| `flowsFilter` | Beschrijving | De Microsoft Flow-widget past het gegeven filter toe wanneer er stromen worden vermeld. Bijvoorbeeld stromen weer geven die verwijzen naar een specifieke share point-site. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Beschrijving | Het actieve tabblad wordt standaard weer gegeven in de widget Microsoft Flow. <br /> Bijvoorbeeld: <br /> ```tab:'sharedFlows' ``` wordt het tabblad team weer gegeven<br /> en ``` tab:'myFlows' ``` wordt het tabblad mijn stromen weer gegeven. |   

### <a name="templatessettings"></a>TemplatesSettings 

Dit geldt voor alle widgets waarmee u stromen kunt maken op basis van een sjabloon, met inbegrip van stromen, FlowCreation en sjabloon widgets.

```javascript
templatesSettings?: {
    defaultParams?: any;
    destination?: string;
    pageSize?: number;
    searchTerm?: string;
    templateCategory?: string;
    useServerSideProvisioning?: boolean;
    enableDietDesigner?: boolean;
};
 ```

| Bepaalde |Vereist/optioneel | Beschrijvingen                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Beschrijving          | Ontwerp tijd parameters die moeten worden gebruikt bij het maken van een stroom op basis van een sjabloon, bijvoorbeeld: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Beschrijving          | Geldige waarden zijn ' New ' en ' Details '. Als u deze waarde instelt op ' Details ', wordt een detail pagina weer gegeven wanneer u een stroom maakt op basis van een sjabloon.     |
| `pageSize` | Beschrijving          | Aantal sjablonen dat moet worden weer gegeven. Standaard grootte = 6 | 
| `searchTerm` | Beschrijving          | Sjablonen weer geven die overeenkomen met de opgegeven zoek term| 
| `templateCategory` | Beschrijving          | Sjablonen in een specifieke categorie weer geven| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

Is van toepassing op ApprovalCenter widgets.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Bepaalde | Vereist/optioneel | Beschrijvingen | 
|------------|-------------------|--------------| 
| `hideLink`| Beschrijving | Als deze functie is ingesteld op `true`, worden in de widget de koppelingen ontvangen en verzonden goed keuring verborgen | 
| `autoNavigateToDetails`| Beschrijving | Wanneer de widget is ingesteld op `true`, worden de goedkeurings gegevens automatisch geopend wanneer er slechts één goed keuring bestaat | 
| `approvalsFilter`| Beschrijving | Met de widget goed keuring wordt het opgegeven goedkeurings filter toegepast wanneer de goed keuringen worden weer gegeven, bijvoorbeeld: de widget goed keuring past het opgegeven goedkeurings filter toe bij het weer geven van de goed keuringen, bijvoorbeeld: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Beschrijving | Standaard actief tabblad dat in de flow-widget moet worden weer gegeven. <br/> Geldige waarden: ' receivedApprovals ', ' sentApprovals ' | 
| `showSimpleEmptyPage`| Beschrijving | Hiermee wordt een lege pagina weer gegeven wanneer er geen goed keuringen zijn | 
| `hideInfoPaneCloseButton` | Beschrijving | Hiermee wordt de knop voor het sluiten van het gegevens venster verborgen (of de host heeft al een knop Sluiten) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Widget gebeurtenissen

De widget Microsoft Flow ondersteunt gebeurtenissen waarmee de host naar levens cyclus gebeurtenissen van de widget kan Luis teren. De widget Microsoft Flow ondersteunt twee typen gebeurtenissen: eenrichtings meldings gebeurtenissen (bijvoorbeeld widget\_Ready) en gebeurtenissen die zijn gegenereerd door de widget om gegevens op te halen van de host (toegang verkrijgen tot\_\_-token). De host moet de methode widget. listen () gebruiken om te Luis teren naar specifieke gebeurtenissen die van de widget worden gegenereerd.

### <a name="usage"></a>Belasting

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Ondersteunde gebeurtenissen per type widget

| Widget gebeurtenis      | Nadere                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | De widget is geladen                                      | 
| `WIDGET_RENDERED`   | De weer gave van de widget is geladen en de gebruikers interface is voltooid                      | 
| `GET_ACCESS_TOKEN`  | Widget Aanvraag voor gebruikers toegangs token insluiten                      | 
| `GET_STRINGS`       | Hiermee kan host een set UI-teken reeksen negeren die in de widget worden weer gegeven | 

### <a name="runtime-widget"></a>Runtime-widget

| Widget gebeurtenis                    | Nadere                                     | gegevens                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Geactiveerd en de stroom uitvoering is gestart      |           | 
| `RUN_FLOW_COMPLETED`              | De stroom uitvoering is geactiveerd             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | Door de gebruiker geselecteerde knop voor het uitvoeren van de stroom       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | Door gebruiker geselecteerde annulerings knop bij uitvoering van stroom     |           | 
| `FLOW_CREATION_SUCCEEDED`         | De stroom is gemaakt           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Wordt geactiveerd wanneer de host de widget moet sluiten. |       | 

### <a name="flow-creation-widget"></a>Widget stroom maken

| Widget gebeurtenis             | Nadere                                  | gegevens  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | Het maken van de stroom is mislukt                     |       | 
| `WIDGET_CLOSE`             | Wordt geactiveerd wanneer de widget moet worden gesloten door de host  |       | 
| `TEMPLATE_LOAD_FAILED`     | Kan de sjabloon niet laden              |       | 
| `FLOW_CREATION_SUCCEEDED`  | De stroom is gemaakt        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widget goed keuring

| Widget gebeurtenis                      | Nadere                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | De ontvangen goedkeurings status is gewijzigd  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Goedkeurings status verzonden is gewijzigd      | 

Met de gebeurtenis **\_strings ophalen** kunt u tekst aanpassen voor een aantal van de UI-elementen die in de widget worden weer gegeven. De volgende teken reeksen kunnen worden aangepast:

| Teken reeks sleutel                     | Gebruiken in de widget                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Tekst die wordt weer gegeven op de knop stroom maken in zowel stroom maken als runtime-widget                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | De aanvankelijke waarde die moet worden gebruikt voor de naam van de stroom in de widget stroom maken. Wordt alleen gebruikt wanneer de instelling allowCustomFlowName is ingeschakeld. | 
| `FLOW_CREATION_HEADER`           | De header die moet worden gebruikt bij het maken van een stroom in zowel de stroom maken als de runtime-widget                                                    | 
| `INVOKE_FLOW_HEADER`             | De header die moet worden gebruikt bij het aanroepen van een stroom in de runtime-widget                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Tekst die wordt weer gegeven op de knop die wordt gebruikt om een stroom in de runtime-widget aan te roepen/uit te voeren                                                       | 

### <a name="example"></a>Hierbij

Roep `widgetDoneCallback` het door geven van een JSON-object met sleutel-waardeparen van teken reeks sleutel en tekst om de standaard waarde te overschrijven.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Widget acties

De host gebruikt widget acties om een specifieke actie of een bericht naar de widget te verzenden. De widget JS SDK biedt de `notify()` methode om een bericht of een JSON-nettolading naar de widget te verzenden. Elke widget actie ondersteunt een specifieke Payload-hand tekening.

### <a name="usage"></a>Belasting

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Hierbij 

Een stroom aanroepen door de volgende opdracht naar een runtime-widget te verzenden 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Runtime-widget

| Widget actie                               | Nadere                                                      | Parameter interface  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Hiermee wordt een stroom uitvoering geactiveerd                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Hiermee wordt een stroom uitgevoerd op basis van een sjabloon                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Hiermee wordt het trigger schema voor een stroom opgehaald                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Hiermee wordt alle activiteiten die in behandeling zijn, geannuleerd en wordt er een WIDGET_CLOSE-gebeurtenis gegenereerd |                      | 

### <a name="flow-creation-widget"></a>Widget stroom maken

| Widget actie                               | Nadere                                                      | Parameter interface  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Hiermee maakt u een stroom voor de geselecteerde sjabloon                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Hiermee maakt u een stroom voor de geselecteerde sjabloon definitie          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Hiermee wordt alle activiteiten die in behandeling zijn, geannuleerd en wordt er een WIDGET_CLOSE-gebeurtenis gegenereerd |                      | 

### <a name="approval-widget"></a>Widget goed keuring

| Widget actie  | Nadere                                           | Parameter interface  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Hiermee sluit u het deel venster info-Details van goed keuring  | n.v.t.                  | 

## <a name="configuring-your-client-application"></a>Uw client toepassing configureren

U moet uw client toepassing configureren met Flow-service scopes (gedelegeerde machtigingen). Als de Azure Active Directorye (AAD)-app die wordt gebruikt voor de integratie van de widget gebruikmaakt van een autorisatie stroom ' code Grant ', moet de AAD-app vooraf worden geconfigureerd met gedelegeerde machtigingen die door Microsoft Flow worden ondersteund. Dit biedt gedelegeerde machtigingen waarmee de toepassing:

-   Goed keuringen beheren
-   Goed keuringen lezen
-   Activiteiten lezen
-   Stromen beheren
-   Stromen lezen

Volg deze stappen om een of meer gedelegeerde machtigingen te selecteren:

1.  Ga naar https://portal.azure.com 
2.  Selecteer **Azure Active Directory**.
3.  Selecteer **app-registraties** onder **beheren**.
4.  Voer de toepassing van derden in die moet worden geconfigureerd voor flow service-bereiken.
5.  **Instellingen**selecteren.
      architectuur van ![-widget](../media/embed-flow-dev/AAD-App-Settings.png)
6. Selecteer de **vereiste machtigingen** onder **API-toegang**/
7. Selecteer **toevoegen**.
8. Kies **een API selecteren**.
      architectuur van ![-widget](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Zoek naar **Microsoft flow-service** en selecteer deze. Opmerking: voordat u Microsoft Flow service kunt zien, moet uw Tenant ten minste één AAD-gebruiker hebben aangemeld bij de flow-Portal (<https://flow.microsoft.com>)
10. Kies de vereiste stroom bereiken voor uw toepassing en selecteer vervolgens **Opslaan**.
      architectuur van ![-widget](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

Uw toepassing krijgt nu een stroom service token dat gedelegeerde machtigingen bevat in de claim van de \'-SCP in het JWT-token.

## <a name="sample-application-embedding-flow-widgets"></a>Voor beeld van stroom widgets voor het insluiten van toepassingen 

Een voor beeld van een Java script-toepassing met één pagina (SPA) vindt u in de sectie Resources, zodat u kunt experimenteren met het insluiten van stroom widgets op een hostpagina. Als u de voorbeeld toepassing gebruikt, moet u een AAD-toepassing registreren waarvoor impliciete toekennings stroom is ingeschakeld.

### <a name="registering-an-aad-app"></a>Een AAD-app registreren

1.  Meld u aan bij de [Azure Portal](https://portal.azure.com/).
2.  Selecteer in het navigatie deel venster links de optie **Azure Active Directory**en selecteer vervolgens **app-registraties** (preview) \> nieuwe registratie.
3.  Wanneer de pagina **een toepassing registreren** wordt weer gegeven, voert u een naam in voor uw toepassing.
4.  Onder **ondersteunde account typen**selecteert u **accounts** in elke organisatie Directory.
5.  Selecteer in de sectie **omleidings-URL** het webplatform en stel de waarde in op de URL van de toepassing\'s op basis van uw webserver.  Stel deze waarde in op http://localhost:30662/ om de voor beeld-app uit te voeren.
6.  Selecteer **registreren**.
7.  Noteer de waarde van de toepassing (client) op de pagina app- **overzicht** .
8.  Voor het voor beeld moet [impliciete toekennings stroom](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) zijn ingeschakeld. Selecteer in het navigatie deel venster aan de linkerkant van de geregistreerde toepassing **verificatie**.
9.  Schakel in **Geavanceerde instellingen**onder **impliciete toekenning**de selectie vakjes **id-tokens** en **toegangs tokens** in. ID-tokens en toegangs tokens zijn vereist omdat deze app zich moet aanmelden bij gebruikers en de flow-API aanroept.
10. Selecteer **Opslaan**.

### <a name="running-the-sample"></a>Het voor beeld uitvoeren
<!-- todo where should I download from? -->
1.  Down load het voor beeld en kopieer het naar een lokale map op het apparaat.
2.  Open het bestand index. html in de map FlowSDKSample en wijzig de `applicationConfig` om de `clientID` bij te werken naar de toepassings-ID die u eerder hebt geregistreerd.
    architectuur van ![-widget](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  De voor beeld-app is geconfigureerd voor het gebruik van stroom bereik **stromen. Read. all** en **flow. Manage. all.** U kunt aanvullende bereiken configureren door de eigenschap **flowScopes** in het object **applicationConfig** bij te werken.
4.  Voer deze opdrachten uit om de afhankelijkheid te installeren en de voor beeld-app uit te voeren:
    > \> NPM installeren \> knooppunt server. js
5. Open de browser en voer http://localhost:30662
6. Selecteer de knop **Aanmelden** om te verifiëren bij Aad en een stroom toegangs token op te halen.
7. Het tekstvak **toegangs token** bevat het toegangs token.
    architectuur van ![-widget](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Selecteer de widget **stroom laden** of de **widget sjablonen laden** om de bijbehorende widgets in te sluiten.
    architectuur van ![-widget](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

Voorbeeld koppeling voor het [downloaden](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip)van toepassingen.

## <a name="resources"></a>Resources

### <a name="widget-test-pages"></a>Test pagina's voor widget

Meer informatie over de integratie van de widget en instellingen:

- Widget sjablonen: <[https://flow.microsoft.com/test/templateswidget/](https://flow.microsoft.com/test/templateswidget/)>
- FlowCreation-widget: <[https://flow.microsoft.com/test/flowcreationwidget/](https://flow.microsoft.com/test/flowcreationwidget/)>
- Runtime-widget: <[https://flow.microsoft.com/test/runtimewidget/](https://flow.microsoft.com/test/runtimewidget/)>
- Object goed keuringen centrum: <[https://flow.microsoft.com/test/approvalcenterwidget/](https://flow.microsoft.com/test/approvalcenterwidget/)>
- Widget stromen: <[https://flow.microsoft.com/test/managewidget/](https://flow.microsoft.com/test/managewidget/)>

### <a name="supported-widget-locales"></a>Ondersteunde land instellingen voor de widget

Als de geïnitialiseerde land instelling niet wordt weer gegeven, wordt de stroom standaard ingesteld op de dichtstbijzijnde ondersteunde land instelling.

| instelling     | Japanse                   | 
|------------|----------------------------| 
| bg-bg      | Bulgaars (Bulgarije)       | 
| CA-es      | Catalaans (Spanje)            | 
| cs-cz      | Tsjechisch (Tsjechische Republiek)     | 
| da-dk      | Deens (Denemarken)           | 
| de-de      | Duits (Duitsland)           | 
| el-gr      | Grieks (Grieken land)             | 
| en-US      | Engels (Verenigde Staten)    | 
| es-es      | Spaans (Castilië)        | 
| et-ee      | Estisch (Estland)         | 
| EU-es      | Baskisch (Spanje)             | 
| fi-fi      | Fins (Finland)          | 
| fr-FR      | Frans (Frank rijk)            | 
| gl-es      | Galicisch (Spanje)           | 
| High-HU      | Hong aars (Hongarije)        | 
| hi-in      | Hindi (India)              | 
| HR-HR      | Kroatisch (Kroatië)         | 
| id-id      | Indonesisch (Indonesië)     | 
| it-it      | Italiaans (Italië)            | 
| JP-JP      | Japans (Japan)           | 
| kk-kz      | Kazachstaans (Kazachstan)        | 
| ko-KR      | Koreaans (Korea)             | 
| lt-LT      | Litouws (Litouwen)     | 
| LV-LV      | Lets (Letland)           | 
| MS-mijn      | Maleis (Maleisië)           | 
| nb-no      | Noors (Bokmål)         | 
| nl-nl      | Nederlands (Nederland)        | 
| pl-pl      | Pools (Polen)            | 
| pt-br      | Portugees (Brazilië)        | 
| pt-pt      | Portugees (Portugal)      | 
| ro-ro      | Roemeens (Roemenië)         | 
| ru-ru      | Russisch (Rusland)           | 
| sk-SK      | Slowaaks (Slowakije)          | 
| sl-si      | Sloveens (Slovenië)       | 
| SR-Cyrl-RS | Servisch (Cyrillisch, Servië) | 
| sr-Latn-RS | Servisch (Latijns, Servië)    | 
| sv-se      | Zweeds (Zweden)           | 
| th      | Thais (Thai land)            | 
| tr-tr      | Turks (Turkije)           | 
| UK-ua      | Oekraïens (Oekraïne)        | 
| VI-VN      | Vietnamees (Vietnam)      |
