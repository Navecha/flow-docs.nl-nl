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
ms.date: 05/09/2017
ms.author: barathb
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: aa5e0a7d143e0e1486533131f90d6b04c6fbc20c
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690003"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Microsoft Flow integreren met websites en apps
Sluit Microsoft Flow in uw app of website in om gebruikers een eenvoudige manier te bieden om hun persoonlijke of werktaken te automatiseren.

Voor het maken van stromen hebben gebruikers een **Microsoft-account** of een werk- of schoolaccount in **Azure Active Directory** nodig. Microsoft Flow biedt geen ondersteuning voor bijvoorbeeld whitelabeloplossingen die ondersteuning bieden voor willekeurige in uw systeem gebruikte identiteiten (tenzij deze oplossingen al gebruikmaken van Microsoft-accounts of AAD).

## <a name="prerequisites"></a>Vereisten
* [Bouw een aangepaste connector](register-custom-api.md) waarmee uw service wordt verbonden met Microsoft Flow.
* [Maak en publiceer een of meer sjablonen](../publish-a-template.md) die gebruikmaken van de API.

## <a name="show-templates-for-your-scenarios"></a>Sjablonen voor uw scenario's weergeven
Als u wilt starten, voegt u deze code toe om de stroomsjablonen rechtstreeks in uw website weer te geven:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

**Opmerking**: er is een regeleinde toegevoegd zodat de code beter op de pagina wordt weergegeven.

| Parameter | Beschrijving |
| --- | --- |
| landinstellingen |De uit vier letters bestaande land- en regiocode voor de sjabloonweergave. `en-us` staat bijvoorbeeld voor Amerikaans-Engels en `de-de` staat voor Duits. |
| zoekterm |De zoekterm voor de sjablonen die u in de weergave wilt weergeven. U kunt bijvoorbeeld zoeken naar `wunderlist` om sjablonen voor Wunderlist weer te geven. |
| aantal sjablonen |Het aantal sjablonen dat u in de weergave wilt weergeven. |
| doel |De pagina die wordt geopend wanneer gebruikers op de sjabloon klikken. Geef `details` op als u de details over de sjabloon wilt weergeven of geef `new` op om de Microsoft Flow-ontwerpfunctie te openen. |
| parameters.{naam} |Aanvullende context die aan de stroom moet worden doorgegeven. |

Als de parameter 'doel' is ingesteld op `new`, wordt Microsoft Flow geopend wanneer gebruikers op een sjabloon klikken, waarna zij een stroom kunnen maken met de ontwerpfunctie. Zie de volgende sectie als u vanuit de app met de volledige ervaring wilt werken.

### <a name="passing-additional-parameters-to-the-flow"></a>Aanvullende parameters aan de stroom doorgeven
Als de gebruiker zich in uw website of app in een bepaalde context bevindt, wilt u die context mogelijk aan de stroom doorgeven. Een gebruiker kan tijdens het bekijken van een bepaalde lijst in Wunderlist bijvoorbeeld een sjabloon openen voor *Melden wanneer een item wordt toegevoegd aan een lijst*. Als u de volgende stappen uitvoert, kunt u de lijst-id als een *parameter* aan de stroom doorgeven:

1. Definieer de parameter in de stroomsjabloon voordat u deze publiceert. Een parameter ziet eruit als `@{parameters('parameter_name')}`.
2. Geef de parameter door in de iframe-bron (src). Voeg bijvoorbeeld `&parameters.listName={the name of the list}` toe als u een parameter hebt met de naam **listName**.

### <a name="full-sample"></a>Volledig voorbeeld
Als u de eerste vier sjablonen over Wunderlist in het Duits wilt weergeven en **myCoolList** als eerste voor de gebruiker wilt weergeven:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="embed-the-management-of-flows"></a>Het beheer van stromen insluiten
Gebruik de geverifieerde Flow SDK om toe te staan dat gebruikers stromen rechtstreeks vanuit uw website of app kunnen maken en beheren (in plaats van naar de Microsoft Flow-portal te navigeren). U moet de gebruiker aanmelden bij Microsoft Account of Azure Active Directory om gebruik te kunnen maken van de geverifieerde SDK.

> [!NOTE]
> Alle gebruikers die in uw toepassing gebruikmaken van Microsoft Flow, worden Microsoft Flow-gebruikers. Het is niet mogelijk om de Microsoft-huisstijl te verbergen.
> 
> 

### <a name="include-the-javascript-for-the-authenticated-sdk"></a>JavaScript opnemen voor de geverifieerde SDK
U kunt de SDK in de HTML-code opnemen door dit voorbeeld te volgen. U kunt de SDK ook downloaden, minimaliseren en inpakken met uw product.

```javascript
<script src="https://flow.microsoft.com/content/msflowsdk-1.1.js" async defer></script>
```

### <a name="create-a-container-to-contain-the-view"></a>Een container met de weergave maken
Voeg een HTML-div toe:

```html
<div id="flowDiv" class="flowContainer"></div>
```

U wordt aangeraden deze container zo op te maken, dat deze met de juiste afmetingen in uw ervaring wordt weergegeven:

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

Houd er rekening mee dat het iframe niet correct wordt weergegeven als u een breedte van minder dan 320 pixels opgeeft en dat de inhoud niet wordt weergegeven als u een breedte van meer dan 1200 pixels opgeeft. U kunt een willekeurige hoogte opgeven.

### <a name="authentication-against-the-sdk"></a>Verificatie voor de SDK
Als u de stromen wilt weergeven die de gebruiker al heeft samengesteld en daarnaast stromen wilt maken op basis van sjablonen, geeft u een authToken van AAD op.

```javascript
<script>
    window.msFlowSdkLoaded = function() {
        var sdk = new MsFlowSdk({
            hostName:'https:/flow.microsoft.com'
        });
        var widget = sdk.renderWidget('flows', {
            container: 'flowDiv'
            environmentId: '[environmentId]'    // find environment id from browser URL when you 
                                                // click on 'my flows'
                                                //ex: https://flow.microsoft.com/manage/environments/[environmentId]/flows
        });
        widget.callbacks.GET_ACCESS_TOKEN = function(requestParam, widgetDoneCallback)
       {
            var authCallback = function(token) {
                widgetDoneCallback(null, {
                    token: token // Get AAD access token from your backend system
                });
            };
        }
    }
</script>
```

U vindt de `environmentId` door de volgende API-aanroep te maken die als resultaat de lijst met omgevingen retourneert waartoe de gebruiker toegang heeft:

```http
GET https://management.azure.com/providers/Microsoft.ProcessSimple/environments
?api-version=2016-11-01 
```

Hiermee wordt een JSON-antwoord geretourneerd dat bestaat uit een lijst met omgevingen, waaruit u om het even welke omgeving kunt kiezen. Als u de standaard gebruikersomgeving zoekt, kunt u die vinden door eigenschap `properties.isDefault=true` te onderzoeken.

In dit voorbeeld wordt `requestParam` gedefinieerd als:

```javascript
export interface IRpcRequestParam {
    callInfo: IRpcCallInfo,
    data?: any;
}
```

Vervolgens is `widgetDoneCallback` een retouraanroepfunctie die moet worden aangeroepen zodra de host het token heeft. Dit gebeurt omdat tokenovername waarschijnlijk een asynchroon proces is. De parameters die moeten worden doorgegeven bij het aanroepen van deze functie zijn `(errorResult: any, successResult: any)`. successResult is afhankelijk van het type retouraanroep. Voor `GetAccessToken` is het type:

```javascript
export interface IGetAccessTokenResult {
    token: string;
}
```
