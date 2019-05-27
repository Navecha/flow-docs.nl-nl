---
title: Microsoft Flow integreren met websites en apps | Microsoft Docs
description: Microsoft Flow-ervaringen insluiten in uw website of app
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: barathb
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 47d44b2c97275add492153d85138b7d11b554530
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64457105"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Microsoft Flow integreren met websites en apps

Sluit Microsoft Flow in uw app of website in met *Flow-widgets* om gebruikers een eenvoudige manier te bieden om hun persoonlijke of werktaken te automatiseren.

Flow-widgets zijn iframes die zich in een hostdocument bevinden. Dit document verwijst naar een pagina in de ontwerpfunctie voor Microsoft Flow. Deze widgets integreren specifieke functionaliteit van Microsoft Flow in de toepassing van derden.

Widgets kunnen eenvoudig zijn. Bijvoorbeeld, een widget die een lijst met sjablonen weergeeft zonder communicatie tussen de host en de iframe. Widgets kunnen ook complex zijn. Bijvoorbeeld, een widget die een stroom inricht vanuit een sjabloon en vervolgens de stroom activeert via communicatie in twee richtingen tussen de host en de widget.

## <a name="prerequisites"></a>Vereisten

- Een **Microsoft-account** of
- Een werk- of schoolaccount

## <a name="use-the-unauthenticated-widget"></a>De niet-geverifieerde widget gebruiken
Als u een niet-geverifieerde sjabloon wilt gebruiken, moet u deze rechtstreeks in de hosttoepassing in een iframe insluiten. U hebt geen JS SDK of toegangstoken nodig. 

### <a name="show-templates-for-your-scenarios"></a>Sjablonen voor uw scenario's weergeven
Als u wilt starten, voegt u deze code toe om de Microsoft Flow-sjablonen op uw website weer te geven:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

| Parameter | Beschrijving |
| --- | --- |
| landinstellingen |De uit vier letters bestaande land- en regiocode voor de sjabloonweergave. `en-us` staat bijvoorbeeld voor Amerikaans-Engels en `de-de` staat voor Duits. |
| zoekterm |De zoekterm voor de sjablonen die u in de weergave wilt weergeven. U kunt bijvoorbeeld zoeken naar `wunderlist` om sjablonen voor Wunderlist weer te geven. |
| aantal sjablonen |Het aantal sjablonen dat u in de weergave wilt weergeven. |
| doel |De pagina die wordt geopend wanneer gebruikers de sjabloon selecteren. Voer `details` in als u de details over de sjabloon wilt weergeven of voer `new` in om de Microsoft Flow-ontwerpfunctie te openen. |
| parameters.{naam} |Aanvullende context die aan de stroom moet worden doorgegeven. |
| templateCategory | Filters voor de opgegeven sjablooncategorie                     | 

Als de doelparameter `new` is, wordt de Microsoft Flow-ontwerpfunctie geopend wanneer gebruikers een sjabloon selecteren. Gebruikers kunnen vervolgens een stroom maken in de ontwerpfunctie. Zie de volgende sectie als u vanuit de widget de volledige ervaring wilt gebruiken.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Aanvullende parameters aan de stroomsjabloon doorgeven

Als de gebruiker zich in uw website of app in een specifieke context bevindt, wilt u die context mogelijk aan de stroom doorgeven. Een gebruiker kan tijdens het bekijken van een bepaalde lijst in Wunderlist bijvoorbeeld een sjabloon openen voor *Melden wanneer een item wordt toegevoegd aan een lijst*. Voer de volgende stappen uit om de lijst-id als een *parameter* aan de stroom door te geven:

1. Definieer de parameter in de stroomsjabloon voordat u deze publiceert. Een parameter ziet eruit als `@{parameters('parameter_name')}`.
1. Geef de parameter door in de iframe-bron (src). Voeg bijvoorbeeld `&parameters.listName={the name of the list}` toe als u een parameter hebt met de naam **listName**.

### <a name="full-sample"></a>Volledig voorbeeld

Als u de eerste vier Wunderlist-sjablonen in het Duits wilt weergeven en **myCoolList** als eerste voor de gebruiker wilt weergeven, gebruikt u deze code:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>De geverifieerde stroomwidgets gebruiken

De volgende tabel bevat een lijst met Microsoft Flow-widgets die ondersteuning bieden voor de volledige ervaring in de widget met het toegangstoken voor gebruikersverificatie. U moet de Javascript Software Developer Kit (JS SDK) van Microsoft Flow gebruiken om de widgets in te sluiten en het vereiste token voor gebruikerstoegang op te geven.

| Widgettype    | Ondersteunde functie                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| Stromen          | Hiermee wordt een lijst met stromen op een tabblad voor persoonlijke en gedeelde stromen weergegeven. Een bestaande stroom bewerken of een nieuwe stroom maken vanuit een sjabloon of een geheel nieuwe stroom maken. | 
| FlowCreation   | Hiermee wordt een stroom van een sjabloon-id gemaakt die de hosttoepassing levert.                                                                | 
| Runtime        | Hiermee wordt een handmatige of hybride-triggerstroom geactiveerd die de hosttoepassing levert.                                                        | 
| ApprovalCenter | Hiermee worden goedkeuringsaanvragen en verzonden goedkeuringen ingesloten.                                                                                        | 
| Sjablonen      | Hiermee wordt een lijst met sjablonen weergegeven. De gebruiker kiest er een om een nieuwe stroom te maken.                                                                         | 

Gebruik de geverifieerde Flow SDK om toe te staan dat gebruikers stromen rechtstreeks vanuit uw website of app kunnen maken en beheren (in plaats van naar Microsoft Flow te navigeren). U moet de gebruiker aanmelden met zijn Microsoft-account of Azure Active Directory om gebruik te kunnen maken van de geverifieerde SDK.

> [!NOTE]
> Het is niet mogelijk om de Microsoft Flow-huisstijl te verbergen wanneer u widgets gebruikt.

## <a name="widget-architecture"></a>Widgetarchitectuur

Microsoft Flow-widgets werken door een iframe dat verwijst naar Microsoft Flow in te sluiten in een hosttoepassing. De host levert het toegangstoken dat wordt vereist door de Microsoft Flow-widget. Met de JS SDK van Microsoft Flow kan de hosttoepassing de levenscyclus van de widget initialiseren en beheren.

![widgetarchitectuur](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>Details van de JS SDK

Het team van Microsoft Flow levert de JS SDK zodat Flow-widgets kunnen worden geïntegreerd in toepassingen van derden. De Flow JS SDK is beschikbaar als openbare koppeling in de Flow-service. Hiermee kan de hosttoepassing gebeurtenissen van de widget verwerken en communiceren met de Flow-toepassing door acties te sturen naar de widget. Widgetgebeurtenissen en -acties zijn specifiek voor het widgettype.

### <a name="widget-initialization"></a>Widgetinitialisatie

De verwijzing naar de Flow JS SDK moet worden toegevoegd aan de hosttoepassing voordat de widget wordt geïnitialiseerd.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Maak een JS SDK-instantie door optionele waarden voor hostName en de landinstellingen op te geven in een JSON-object.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US',
}); 
```

| Naam     | Vereist/optioneel | Beschrijving                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Optioneel          | Microsoft Flow-hostnaam, bijvoorbeeld: https://flow.microsoft.com        | 
| `locale`   | Optioneel          | Clientlandinstellingen voor de widget (standaard ingesteld op `en-Us` indien niet opgegeven) | 


Wanneer de JS SDK-instantie is gemaakt, kunt u een Microsoft Flow-widget initialiseren en insluiten in een bovenliggend element in de hosttoepassing . Voeg een HTML-div toe om dit te doen:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Initialiseer vervolgens de Microsoft Flow-widget met de renderWidget()-methode van de JS SDK. Zorg ervoor dat u het widgettype en de bijbehorende instellingen opgeeft.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flow-div',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {},
});
```

Hier volgt een stijlvoorbeeld voor de container die u kunt wijzigen zodat deze overeenkomt met de afmetingen van de hosttoepassing.

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

Dit zijn de parameters voor `renderWidget()`: 

| Parameter        | Vereist/optioneel | Beschrijving                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Vereist          | Id van een DIV-element op de hostpagina waar de widget wordt ingesloten                      | 
| `environmentId`    | Optioneel          | Widgets moeten een omgevings-id hebben. Als u geen id opgeeft, wordt een standaardomgeving gebruikt. | 
| `flowsSettings`    | Optioneel          | Object voor Microsoft Flow-instellingen                                                                        | 
| `templateSettings` | Optioneel          | Object voor sjablooninstellingen                                                                    | 
| `approvalSettings` | Optioneel          | Object voor goedkeuringsinstellingen                                                                    | 

### <a name="access-tokens"></a>Toegangstokens

Na de JS SDK `renderWidget()` is uitgevoerd, wordt met de JS SDK een iframe geïnitialiseerd dat verwijst naar de URL van de Microsoft Flow-widget. Deze URL bevat de alle instellingen in de queryreeksparameters. De hosttoepassing moet een Microsoft Flow-toegangstoken verkrijgen voor de gebruiker (Azure Active Directory JWT-token met de doelgroep https://service.flow.microsoft.com) voordat de widget wordt geïnitialiseerd. De widget opent een `GET_ACCESS_TOKEN`-gebeurtenis om een toegangstoken aan te vragen bij de host. De host moet de gebeurtenis verwerken en het token doorgeven aan de widget:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

De hosttoepassing is verantwoordelijk voor het onderhoud van het token en moet het token aan de widget doorgeven met een geldige vervaldatum als dit wordt gevraagd. Als de widget langere tijd is geopend, moet door de host worden gecontroleerd of het token is verlopen en het token vernieuwen als dit nodig is voordat het wordt doorgegeven aan de widget.

### <a name="detecting-if-the-widget-is-ready"></a>Detecteren of de widget klaar is

Nadat de initialisatie is geslaagd, activeert de widget een gebeurtenis om te waarschuwen dat de widget klaar is. De host kan luisteren naar de `WIDGET_READY`-gebeurtenis en eventuele extra hostcode uitvoeren.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Widgetinstellingen

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings kan worden gebruikt om de functionaliteit van de Microsoft Flow-widget aan te passen.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Parameter | Vereist/optioneel | Beschrijving | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Vereist | GUID van de sjabloon gebruiken wanneer de gebruiker de knop **Nieuwe maken** selecteert in de Flow-widget | 
| `flowsFilter` | Optioneel | De Microsoft Flow-widget past het opgegeven filter toe bij het weergeven van stromen. Bijvoorbeeld stromen weergeven die verwijzen naar een specifieke SharePoint-site. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Optioneel | Het actieve tabblad wordt ingesteld als standaard voor weergave in de Microsoft Flow-widget. <br /> Bijvoorbeeld: <br /> ```tab:'sharedFlows' ``` geeft het tabblad Team weer<br /> en ``` tab:'myFlows' ``` geeft het tabblad Mijn stromen weer. |   

### <a name="templatessettings"></a>TemplatesSettings 

Dit geldt voor alle widgets die waarmee u stromen kunt maken vanuit een sjabloon, inclusief Flows-, FlowCreation- en Templates-widgets.

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

| Parameter |Vereist/optioneel | Beschrijving                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Optioneel          | Ontwerptijdparameters die moeten worden gebruikt bij het maken van een stroom vanuit een sjabloon, bijvoorbeeld: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Optioneel          | Geldige waarden zijn 'nieuw' of 'details'. Als de waarde is ingesteld op 'details', wordt een detailpagina weergegeven bij het maken van een stroom vanuit een sjabloon.     |
| `pageSize` | Optioneel          | Aantal sjablonen om weer te geven. Standaardgrootte = 6 | 
| `searchTerm` | Optioneel          | Sjablonen weergeven die overeenkomen met de opgegeven zoekterm| 
| `templateCategory` | Optioneel          | Sjablonen weergeven in een specifieke categorie| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

Is van toepassing op ApprovalCenter-widgets.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Parameter | Vereist/optioneel | Beschrijving | 
|------------|-------------------|--------------| 
| `hideLink`| Optioneel | Indien ingesteld op `true`, worden in de widget de ontvangen en verzonden goedkeuringskoppelingen verborgen | 
| `autoNavigateToDetails`| Optioneel | Indien ingesteld op `true`, worden in de widget de goedkeuringsdetails automatisch geopend al er slechts één goedkeuring is | 
| `approvalsFilter`| Optioneel | In de goedkeuringswidget wordt het opgegeven goedkeuringsfilter toegepast wanneer de goedkeuringen worden vermeld, bijvoorbeeld:    In de goedkeuringswidget wordt het opgegeven goedkeuringsfilter toegepast wanneer de goedkeuringen worden vermeld, bijvoorbeeld: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Optioneel | Het standaard actieve tabblad om weer te geven in de Flow-widget. <br/> Geldige waarden: 'receivedApprovals', 'sentApprovals' | 
| `showSimpleEmptyPage`| Optioneel | Er wordt een lege pagina weergegeven wanneer er geen goedkeuringen zijn | 
| `hideInfoPaneCloseButton` | Optioneel | Hiermee wordt de knop Sluiten van het info-deelvenster verborgen (of de host heeft al een knop Sluiten) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Widgetgebeurtenissen

De Microsoft Flow-widget ondersteunt gebeurtenissen waarmee de host kan luisteren naar levenscyclusgebeurtenissen van de widget. De Microsoft Flow-flow ondersteunt twee soorten gebeurtenissen: meldingsgebeurtenissen in één richting (bijvoorbeeld Widget\_Ready) en gebeurtenissen die worden gegenereerd vanuit de widget om gegevens op te halen van de host (Get\_Access\_Token). De host moet de widget.listen()-methode gebruiken om te luisteren naar specifieke gebeurtenissen die worden gegenereerd door de widget.

### <a name="usage"></a>Gebruik

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Ondersteunde gebeurtenissen per widgettype

| Widgetgebeurtenis      | Details                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | Widget geladen                                      | 
| `WIDGET_RENDERED`   | Widget geladen en rendering van de gebruikersinterface is voltooid                      | 
| `GET_ACCESS_TOKEN`  | Widgetaanvraag voor token voor gebruikerstoegang insluiten                      | 
| `GET_STRINGS`       | Host toestaan om een set met UI-tekenreeksen te overschrijven die wordt weergegeven in de widget | 

### <a name="runtime-widget"></a>Runtime-widget

| Widgetgebeurtenis                    | Details                                     | Gegevens                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Geactiveerd en de stroomuitvoering is gestart      |           | 
| `RUN_FLOW_COMPLETED`              | Stroomuitvoering geactiveerd             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | Gebruiker heeft de knop Gereed geselecteerd in de stroomuitvoering       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | Gebruiker heeft de knop Annuleren geselecteerd in de stroomuitvoering     |           | 
| `FLOW_CREATION_SUCCEEDED`         | De stroom is gemaakt           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Geactiveerd wanneer de host de widget moet sluiten |       | 

### <a name="flow-creation-widget"></a>Widget voor stroom maken.

| Widgetgebeurtenis             | Details                                  | Gegevens  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | Stroom maken is mislukt                     |       | 
| `WIDGET_CLOSE`             | Geactiveerd wanneer de host de widget moet sluiten  |       | 
| `TEMPLATE_LOAD_FAILED`     | Kan de sjabloon niet laden              |       | 
| `FLOW_CREATION_SUCCEEDED`  | De stroom is gemaakt        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widget voor goedkeuring

| Widgetgebeurtenis                      | Details                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | Goedkeuringsstatus gewijzigd ontvangen  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Goedkeuringsstatus gewijzigd verzonden      | 

Met de gebeurtenis **GET\_STRINGS** kunt u tekst aanpassen voor enkele van de UI-elementen die in de widget worden weergegeven. De volgende tekenreeksen kunnen worden aangepast:

| Tekenreekssleutel                     | Gebruiken in de widget                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Tekst die wordt weergegeven op de knop voor stroom maken in zowel de widget voor stromen maken als de runtimewidget                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | De aanvankelijke waarde die moet worden gebruikt voor de stroomnaam in de widget voor stromen maken. Alleen gebruikt wanneer de instelling allowCustomFlowName is ingeschakeld. | 
| `FLOW_CREATION_HEADER`           | Koptekst die moet worden gebruikt bij het maken van een stroom in de widget voor stromen maken en de runtimewidget                                                    | 
| `INVOKE_FLOW_HEADER`             | Koptekst die moet worden gebruikt bij het aanroepen van een stroom in de runtimewidget                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Tekst die wordt weergegeven op de knop waarmee een stroom in de runtimewidget wordt aangeroepen/uitgevoerd                                                       | 

### <a name="example"></a>Voorbeeld

Roep `widgetDoneCallback` aan waarmee een JSON-object wordt doorgegeven met sleutel-waardeparen van de tekenreekssleutel en de tekst om de standaardwaarde te overschrijven.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Widgetacties

De host gebruikt widgetacties om een specifieke actie of een specifiek bericht te verzenden naar de widget. De JS SDK van de widget biedt de `notify()`-methode om een bericht of een JSON-nettolading naar de widget te verzenden. Elke widgetactie biedt ondersteuning voor de handtekening van een specifieke nettolading.

### <a name="usage"></a>Gebruik

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Voorbeeld 

Een stroom aanroepen door de volgende opdracht te verzenden naar een runtimewidget 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Runtime-widget

| Widgetactie                               | Details                                                      | Parameterinterface  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Hiermee wordt een stroomuitvoering geactiveerd                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Hiermee wordt een stroomuitvoering door op sjabloon geactiveerd                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Hiermee wordt een activeringsschema voor een stroom opgehaald                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Hiermee worden lopende activiteiten geannuleerd en wordt een WIDGET_CLOSE-gebeurtenis gegenereerd |                      | 

### <a name="flow-creation-widget"></a>Widget voor stroom maken.

| Widgetactie                               | Details                                                      | Parameterinterface  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Hiermee wordt een stroom gemaakt voor de geselecteerde sjabloon                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Hiermee wordt een stroom gemaakt voor de geselecteerde sjabloondefinitie          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Hiermee worden lopende activiteiten geannuleerd en wordt een WIDGET_CLOSE-gebeurtenis gegenereerd |                      | 

### <a name="approval-widget"></a>Widget voor goedkeuring

| Widgetactie  | Details                                           | Parameterinterface  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Hiermee wordt het info-deelvenster met de goedkeuringsdetails gesloten  | N.v.t.                  | 

## <a name="configuring-your-client-application"></a>Uw clienttoepassing configureren

U moet uw clienttoepassing configureren met Flow-servicebereiken (gedelegeerde machtigingen). Als de Azure Active Directory-app (AAD) die wordt gebruikt voor de widgetintegratie een autorisatiestroom 'code verlenen' gebruikt, moet de AAD-app vooraf worden geconfigureerd met gedelegeerde machtigingen die worden ondersteund door Microsoft Flow. Dit voorziet in gedelegeerde machtigingen waarmee de toepassing het volgende kan:

-   Goedkeuringen beheren
-   Goedkeuringen lezen
-   Activiteiten lezen
-   Stromen beheren
-   Stromen lezen

Volg deze stappen om een of meer gedelegeerde machtigingen te selecteren:

1.  Ga naar https://portal.azure.com 
2.  Selecteer **Azure Active Directory**.
3.  Selecteer **App-registraties** onder **Beheren**.
4.  Voer de toepassing van derden in die moet worden geconfigureerd voor Flow-servicebereiken.
5.  Selecteer **Instellingen**.
      ![widgetarchitectuur](../media/embed-flow-dev/AAD-App-Settings.png)
6. Selecteer **Vereiste machtigingen** onder **API-toegang**/
7. Selecteer **Toevoegen**.
8. Kies **Een API selecteren**.
      ![widgetarchitectuur](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Zoek naar **Microsoft Flow-service** en selecteer deze. Opmerking: Voordat u een Microsoft Flow-service kunt zien, moet er voor uw tenant ten minste één AAD-gebruiker zijn aangemeld bij de Flow-portal (<https://flow.microsoft.com>)
10. Kies de vereiste Flow-bereiken voor uw toepassing en selecteer vervolgens **Opslaan**.
      ![widgetarchitectuur](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

Uw toepassing krijgt nu een Flow-servicetoken dat gedelegeerde machtigingen bevat in de \'scp'-claim in het JWT-token.

## <a name="sample-application-embedding-flow-widgets"></a>Voorbeeldtoepassing met ingesloten stroomwidgets 

Een voorbeeld van een JavaScript SPA (Single Page Application) is beschikbaar in de resourcessectie, zodat u kunt experimenteren met het insluiten van stroomwidgets in een hostpagina. Als u de voorbeeldtoepassing wilt gebruiken moet u een AAD-toepassing registreren met de stroom van de impliciete toekenning ingeschakeld.

### <a name="registering-an-aad-app"></a>Een AAD-app registreren

1.  Meld u aan bij [Azure Portal](https://portal.azure.com/).
2.  Selecteer in het linkernavigatiedeelvenster de optie **Azure Active Directory** en selecteer vervolgens **App-registraties** (preview-versie) \> Nieuwe registratie.
3.  Wanneer de pagina **Een toepassing registreren** wordt weergegeven, voert u een naam in voor uw toepassing.
4.  Selecteer onder **Ondersteunde accounttypen** de optie **Accounts** in een organisatiemap.
5.  Selecteer onder de sectie **Omleidings-URL** het webplatform en stel de waarde in op de URL van de toepassing, gebaseerd op uw webserver.  Stel deze waarde in op http://localhost:30662/ om de voorbeeld-app uit te voeren.
6.  Selecteer **Registreren**.
7.  Let op de pagina **Overzicht** van de app op de toepassings-id (client).
8.  Voor het voorbeeld moet [impliciete toewijzingsstroom](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) zijn ingeschakeld. Selecteer in het linkernavigatievenster van de geregistreerde toepassing de optie **Verificatie**.
9.  Schakel in **Geavanceerde instellingen** onder **Impliciete toewijzing** de selectievakjes **Id-tokens** en **Toegangstokens** in. Id-tokens en toegangstokens zijn vereist, omdat met deze app gebruikers moeten worden aangemeld en de Flow API moet worden aangeroepen.
10. Selecteer **Opslaan**.

### <a name="running-the-sample"></a>Het voorbeeld uitvoeren
<!-- todo where should I download from? -->
<!-- todo is this a misspelling: applicaionConfig -->
1.  Downloaden het voorbeeld en kopieert het naar een lokale map op uw apparaat.
2.  Open het bestand index.html in de map FlowSDKSample en wijzig de `applicaionConfig` om de `clientID` bij te werken naar de toepassings-id die u eerder hebt geregistreerd.
    ![widgetarchitectuur](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  De voorbeeld-app is geconfigureerd voor het gebruik van Flow-bereiken **Flows.Read.All** en **Flow.Manage.All.** U kunt extra bereiken configureren door de eigenschap **flowScopes** in het object **applicationConfig** bij te werken.
4.  Voer deze opdrachten uit om de afhankelijkheid te installeren en de voorbeeld-app uit te voeren:
    > \> npm install \> node server.js
5. Open de browser en voer http://localhost:30662 in
6. Selecteer de knop **Aanmelden** om te worden geverifieerd bij AAD en een stroomtoegangstoken te verkrijgen.
7. Het tekstvak **Toegangstoken** bevat het toegangstoken.
    ![widgetarchitectuur](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Selecteer **Load Flow-widget** of **Load Templates-widget** om de bijbehorende widgets in te sluiten.
    ![widgetarchitectuur](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

Voorbeeldtoepassing [downloadkoppeling](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip).

## <a name="resources"></a>Resources

### <a name="widget-test-pages"></a>Testpagina's voor widgets

Meer informatie over de integratie en instellingen van widgets:

- Widget voor sjablonen: <[https://flow.microsoft.com/en-us/test/templateswidget/](https://flow.microsoft.com/en-us/test/templateswidget/)>
- Widget voor FlowCreation: <[https://flow.microsoft.com/en-us/test/flowcreationwidget/](https://flow.microsoft.com/en-us/test/flowcreationwidget/)>
- Widget voor runtime: <[https://flow.microsoft.com/en-us/test/runtimewidget/](https://flow.microsoft.com/en-us/test/runtimewidget/)>
- Widget voor Goedkeuringscentrum: <[https://flow.microsoft.com/en-us/test/approvalcenterwidget/](https://flow.microsoft.com/en-us/test/approvalcenterwidget/)>
- Widget voor stromen: <[https://flow.microsoft.com/en-us/test/managewidget/](https://flow.microsoft.com/en-us/test/managewidget/)>

### <a name="supported-widget-locales"></a>Ondersteunden widgettalen

Als de geïnitialiseerde landinstellingen niet worden weergegeven, wordt standaard de dichtstbijzijnde ondersteunde landinstelling gebruikt door Flow.

| Landinstellingen     | Taal                   | 
|------------|----------------------------| 
| bg-bg      | Bulgaars (Bulgarije)       | 
| ca-es      | Catalaans (Spanje)            | 
| cs-cz      | Tsjechisch (Tsjechische Republiek)     | 
| da-dk      | Deens (Denemarken)           | 
| de-de      | Duits (Duitsland)           | 
| el-gr      | Grieks (Griekenland)             | 
| en-Us      | Engels (Verenigde Staten)    | 
| es-es      | Spaans (Castilië)        | 
| et-ee      | Estisch (Estland)         | 
| eu-es      | Baskisch (Spanje)             | 
| fi-fi      | Fins (Finland)          | 
| fr-fr      | Frans (Frankrijk)            | 
| gl-es      | Galicisch (Spanje)           | 
| hi-HU      | Hongaars (Hongarije)        | 
| hi-in      | Hindi (India)              | 
| hr-hr      | Kroatisch (Kroatië)         | 
| id-Id      | Indonesisch (Indonesië)     | 
| it-It      | Italiaans (Italië)            | 
| jp-Jp      | Japans (Japan)           | 
| kk-kz      | Kazachs (Kazachstan)        | 
| ko-kr      | Koreaans (Korea)             | 
| lt-LT      | Litouws (Litouwen)     | 
| lv-lv      | Lets (Letland)           | 
| ms-my      | Maleis (Maleisië)           | 
| nb-no      | Norwegian (Bokmål)         | 
| nl-nl      | Nederlands (Nederland)        | 
| pl-pl      | Pools (Polen)            | 
| pt-br      | Portugees (Brazilië)        | 
| pt-pt      | Portugees (Portugal)      | 
| ro-ro      | Roemeens (Roemenië)         | 
| ru-ru      | Russisch (Rusland)           | 
| sk-sk      | Slowaaks (Slowakije)          | 
| sl-si      | Sloveens (Slovenië)       | 
| sr-cyrl-rs | Servisch (Cyrillisch, Servië) | 
| sr-latn-rs | Servisch (Latijns, Servië)    | 
| sv-se      | Zweeds (Zweden)           | 
| th-th      | Thai (Thailand)            | 
| tr-tr      | Turks (Turkije)           | 
| uk-ua      | Oekraïens (Oekraïne)        | 
| vi-vn      | Vietnamees (Vietnam)      |
