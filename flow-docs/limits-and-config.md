---
title: Limieten en configuratie | Microsoft Docs
description: Limieten en configuratie
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/30/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c6a9b3c344ac25afe90c607b4a665aeaab49321f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547379"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Limieten en configuratie in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Dit onderwerp bevat informatie over de huidige limieten en configuratie gegevens voor stromen.

## <a name="request-limits"></a>Aanvraag limieten
Dit zijn limieten voor één uitgaande aanvraag.

### <a name="timeout"></a>out

| Naam | Ondergrens |
| --- | --- |
| Time-out van aanvraag voor synchrone aanroepen |120 seconden |
| Time-out van aanvraag voor asynchrone aanroepen|Configureer bare. Maximum is 30 dagen. |

### <a name="message-size"></a>Bericht grootte

| Naam | Ondergrens | Noten |
| --- | --- | --- |
| Bericht grootte |100 MB |Niet alle Api's ondersteunen de volledige 100 MB. |
| Limiet voor expressie-evaluatie |131.072 tekens |`@concat()`, `@base64()`, `string` kan deze limiet niet overschrijden. |

### <a name="retry-policy"></a>Beleid voor opnieuw proberen

| Naam | Ondergrens |
| --- | --- |
| Nieuwe pogingen |90 | De standaard waarde is 4. De standaard instellingen voor het gebruik van de actie wijzigen | 
| Maximale vertraging voor opnieuw proberen |1 dag | |
| Minimale vertraging voor opnieuw proberen |5 seconden | |

## <a name="run-duration-and-retention"></a>Uitvoerings duur en-retentie
Dit zijn de limieten voor het uitvoeren van één stroom.

| Naam | Ondergrens | Noten |
| --- | --- | --- |
| Uitvoerings duur |30 dagen |Bevat werk stromen met stappen in behandeling, zoals goed keuringen. In afwachting van een time-out voor de stappen van 30 dagen. Goed keuringen voor time-outs worden verwijderd uit het goedkeurings centrum. Als iemand probeert een time-out aanvraag goed te keuren, wordt een fout bericht weer gegeven. |
| Opslag bewaren |30 dagen |Dit is vanaf de begin tijd van de uitvoering. |
| Min. terugkeer patroon |1 minuut | |
| Max. interval van terugkeer patroon |500 dagen | |
| Maximale retentie van uitvoerings geschiedenis |28 dagen, per AVG-regel. | |
|Minimale uitstel interval-gratis en licentie abonnement 1|5 seconden||
|Minimale uitstel interval-licentie van abonnement 2|1 seconde||

## <a name="looping-and-debatching-limits"></a>Limieten voor lussen en debatchering
Dit zijn limieten voor het uitvoeren van één stroom.

| Naam | Ondergrens | Noten |
| --- | --- | --- |
| Toep assen op elke items-gratis licentie|5\.000 |U kunt de filter actie gebruiken om een grotere matrix te filteren als dat nodig is. |
| Toep assen op elke items-licentie abonnement 1 en abonnement 2|100.000 |U kunt de filter actie gebruiken om een grotere matrix te filteren als dat nodig is. |
| Tot iteraties |5\.000 | |
| SplitOn-items-gratis licentie |5\.000 ||
| SplitOn items-abonnement 1 en licentie van abonnement 2 |100.000 ||
| Toep assen op elke parallellisme |50 |Lussen worden standaard uitgevoerd in volg orde (in wezen, parallellisme is 1). U kunt Maxi maal 50 parallel configureren. |
| Uitvoeringen van acties per 5 minuten-gratis, Office365, abonnement 1-licenties en proef abonnementen | 2\.000 | U kunt ook een werk belasting over meer dan één stroom distribueren als dat nodig is. |
|Uitvoeringen van acties per 5 minuten-licenties voor het betaalde abonnement 2|100.000|U kunt ook een werk belasting over meer dan één stroom distribueren als dat nodig is.|
|Uitvoeringen van acties per 5 minuten-licenties voor het betaalde abonnement 2|150.000|U kunt ook een werk belasting over meer dan één stroom distribueren als dat nodig is.|
| Acties gelijktijdige uitgaande aanroepen-gratis en abonnement 1-licentie | ~ 500 | Verminder het aantal gelijktijdige aanvragen of verklein de duur als dat nodig is. |
| Uitvoeringen van acties per 24 uur-gratis, Office365, abonnement 1-licenties en proef abonnementen | ~ 2.500 | Verminder het aantal gelijktijdige aanvragen of verklein de duur als dat nodig is. | 

## <a name="throughput-limits"></a>Doorvoer limieten

|Naam|Ondergrens|Noten|
|---|---|---|
|Runtime-eind punt: aantal lees aanvragen dat is toegestaan per 5 minuten-gratis en licentie van abonnement 1|6\.000||
|Runtime-eind punt: aantal lees aanvragen dat is toegestaan per 5 minuten-abonnement 2-licentie|60.000||
|Runtime-eind punt: aanroepen aanroepen per 5 minuten-gratis en licentie abonnement 1|4\.500||
|Runtime-eind punt: aantal invoke-aanroepen per 5 minuten-abonnement 2-licentie|45.000||
|Toegestane door Voer per 5 minuten-gratis en licentie abonnement 1|600 MB||
|Toegestane door Voer per 5 minuten-abonnement 2-licentie|6 GB||
|De hoeveelheid inhouds stromen mag worden geproduceerd (acties invoer/uitvoer) per uur-gratis, abonnement 1 en licentie abonnement 2|200 GB||


## <a name="definition-limits"></a>Definitie limieten
Dit zijn limieten voor één stroom.

| Naam | Ondergrens | Noten |
| --- | --- | --- |
| Acties per werk stroom |250 |U kunt geneste werk stromen toevoegen om dit zo nodig uit te breiden. |
| Diepte van toegestane actie nesten |achtste |U kunt geneste werk stromen toevoegen om dit zo nodig uit te breiden. |
| Maximum aantal tekens per expressie |8\.192 | |
| limiet voor `action`/`trigger`-naam |80 | |
| limiet voor `description` lengte |256 | |

## <a name="sharepoint-limits"></a>Share point-limieten
Er gelden [beperkingen](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) voor het gebruik van micro soft share point met Microsoft flow en PowerApps.

## <a name="ip-address-configuration"></a>IP-adres configuratie
Het IP-adres van waaruit Microsoft Flow aanvragen worden verzonden, is afhankelijk van de [regio](regions-overview.md) waarin de [omgeving](environments-overview-admin.md) met de stroom zich bevindt. Er zijn momenteel geen FQDN-mogelijkheden beschikbaar voor stroom scenario's.

>[!IMPORTANT]
> Sommige aanroepen van een stroom kunnen afkomstig zijn van IP-adressen die worden vermeld in de [Logic apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) -documentatie. Enkele voor beelden van deze aanroepen zijn HTTP of HTTP + OpenAPI.

### <a name="logic-apps"></a>Logic Apps
Aanroepen van een stroom worden direct uitgevoerd via de Azure Logic app-service. Enkele voor beelden van deze aanroepen zijn HTTP of HTTP + OpenAPI. Raadpleeg [de documentatie van Logic apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) voor meer informatie over de IP-adressen die door die service worden gebruikt.

### <a name="connectors"></a>Lijm
Aanroepen van een connector in een stroom (bijvoorbeeld de SQL-API of de share point-API) worden opgehaald van de IP-adressen die hier worden vermeld:

| Deel | Uitgaande IP |
| --- | --- |
| Azië en Stille Oceaan | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Australië  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Canada | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| Europa | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181 |
| India  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Japan | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| Zuid-Amerika | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Verenigd Koninkrijk | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Verenigde Staten | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49|
| Preview (Verenigde Staten)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

Als u bijvoorbeeld IP-adressen voor uw Azure-SQL database moet autoriseren, moet u deze adressen gebruiken.

### <a name="required-services"></a>Vereiste services
De volgende tabel geeft een lijst van de services waarmee Microsoft Flow verbinding maakt. Zorg ervoor dat geen van deze services in uw netwerk is geblokkeerd.

domeinen | Protocollen | Bestemmingen
--------|  ---------| -----
management.azure.com|https|Toegang tot de Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Toegang tot Active Directory Authentication Library (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|https|Toegang tot Azure AD Graph API-voor het ophalen van gebruikers gegevens, zoals een profiel foto.
*. azure-apim.net|https|Toegang tot de runtime voor connectors.
*. flow.microsoft.com|https|Toegang tot de Microsoft Flow-site.
*. powerapps.com|https|Toegang tot de PowerApps-site.
*. azureedge.net|https|Toegang tot de Microsoft Flow CDN.
nps.onyx.azure.net|https|Toegang tot NPS (net Promor Score).
