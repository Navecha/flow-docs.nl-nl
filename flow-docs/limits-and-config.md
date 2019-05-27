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
ms.date: 12/04/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 615d13adaee8b5db302065b3c21a488504f39398
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64906402"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Limieten en configuratie in Microsoft Flow
Dit onderwerp bevat informatie over de huidige limieten en configuratiegegevens voor stromen.

## <a name="request-limits"></a>Aanvraaglimieten
Er gelden limieten voor één uitgaande aanvraag.

### <a name="timeout"></a>Time-out

| Naam | Limiet |
| --- | --- |
| Time-out aanvragen voor synchrone aanroepen |120 seconden |
| Time-out aanvragen voor a-synchrone aanroepen|Kunnen worden geconfigureerd. Maximum is 30 dagen. |

### <a name="message-size"></a>Berichtgrootte

| Naam | Limiet | Opmerkingen |
| --- | --- | --- |
| Berichtgrootte |100 MB |Niet alle API's ondersteunen de volledige 100 MB. |
| Limiet voor evaluatie van expressie |131.072 tekens |`@concat()`, `@base64()`, `string` mogen deze limiet niet overschrijden. |

### <a name="retry-policy"></a>Beleid voor opnieuw proberen

| Naam | Limiet |
| --- | --- |
| Nieuwe pogingen |90 | De standaard is 4. Om de standaard gebruikte actie-instellingen te wijzigen | 
| Maximale vertraging nieuwe poging |1 dag | |
| Minimale vertraging nieuwe poging |5 seconden | |

## <a name="run-duration-and-retention"></a>Uitvoeringsduur en bewaarperiode
Dit zijn de limieten voor het uitvoeren van één stroom.

| Naam | Limiet | Opmerkingen |
| --- | --- | --- |
| Uitvoeringsduur |30 dagen |Inclusief werkstromen met stappen in behandeling, zoals goedkeuringen. Na 30 dagen zijn alle stappen in behandeling verlopen. Verlopen goedkeuringen worden verwijderd uit het goedkeuringscentrum. Als iemand een verlopen aanvraag probeert goed te keuren, wordt er een foutbericht verzonden. |
| Bewaarperiode |30 dagen |Dit is vanaf de begintijd van het uitvoeren. |
| Minimaal terugkeerpatroon |1 minuut | |
| Maximaal terugkeerpatroon |500 dagen | |
| Maximale bewaarperiode voor uitvoeringsgeschiedenis |28 dagen, volgens de AVG-regels. | |
|Minimale postone interval - vrij en plannen van 1-licentie|5 seconden||
|Minimaal interval - abonnement 2-licentie uitstellen|1 seconde||

## <a name="looping-and-debatching-limits"></a>Limieten voor lussen en debatching
Dit zijn limieten voor het uitvoeren van één stroom.

| Naam | Limiet | Opmerkingen |
| --- | --- | --- |
| Toepassen op elke items - gratis licentie|5000 |Met de filteractie kunt u naar behoefte grotere matrices filteren. |
| Toepassen op elke items - abonnement 1 en abonnement 2-licentie|100.000 |Met de filteractie kunt u naar behoefte grotere matrices filteren. |
| Until-iteraties |5000 | |
| SplitOn-items: gratis licentie |5000 ||
| SplitOn-items - abonnement 1 en abonnement 2-licentie |100.000 ||
| Op alle parallelle uitvoeringen toepassen |50 |Standaard worden lussen opeenvolgend uitgevoerd (parallelle uitvoering is in wezen 1) U kunt er maximaal 50 parallel configureren |
| Acties uitvoeringen per vijf minuten: gratis en licentie-abonnement 1 | 2,000 | Naar behoefte kunt u ook een werkbelasting over meer dan één stroom verdelen. |
|Uitvoeringen van acties per vijf minuten - abonnement 2-licentie|100.000|Naar behoefte kunt u ook een werkbelasting over meer dan één stroom verdelen.|
| Acties gelijktijdige uitgaande gesprekken - vrij en plannen van 1-licentie | ~500 | Naar behoefte kunt u het aantal gelijktijdige aanvragen verminderen of de duur verkorten. |
| Acties gelijktijdige uitgaande gesprekken - vrij en plannen van 1-licentie | ~2500 | Naar behoefte kunt u het aantal gelijktijdige aanvragen verminderen of de duur verkorten. | 

## <a name="throughput-limits"></a>Doorvoerlimieten

|Naam|Limiet|Opmerkingen|
|---|---|---|
|Eindpunt van de runtime - aantal gelezen aanroepen toegestaan per vijf minuten: gratis en licentie-abonnement 1|6,000||
|Eindpunt van de runtime - lezen toegestane aantal aanvragen per vijf minuten - abonnement 2-licentie|60,000||
|Runtime-eindpunt: Invoke-aanroepen per vijf minuten: gratis en licentie-abonnement 1|4,500||
|Runtime-eindpunt: Aantal invoke-aanroepen per vijf minuten - abonnement 2-licentie|45,000||
|Hoeveelheid doorvoer toegestaan per vijf minuten: gratis en licentie-abonnement 1|600 MB||
|Hoeveelheid doorvoer toegestaan per vijf minuten - abonnement 2-licentie|6 GB||
|Hoeveelheid inhoud stromen kunnen produceren (acties invoer/uitvoer) per uur: gratis, abonnement 1 en abonnement 2-licentie|200 GB||


## <a name="definition-limits"></a>Definitielimieten
Dit zijn limieten voor één stroom.

| Naam | Limiet | Opmerkingen |
| --- | --- | --- |
| Acties per werkstroom |250 |U kunt naar behoefte geneste werkstromen toevoegen om dit uit te breiden. |
| Toegestane nestdiepte voor acties |5 |U kunt naar behoefte geneste werkstromen toevoegen om dit uit te breiden. |
| Maximum aantal tekens per expressie |8192 | |
| `action`/`trigger`, limiet voor de naam |80 | |
| `description`, limiet voor de lengte |256 | |

## <a name="sharepoint-limits"></a>SharePoint-limieten
Er gelden [beperkingen](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) voor het gebruik van Microsoft SharePoint met Microsoft Flow en PowerApps.

## <a name="ip-address-configuration"></a>IP-adresconfiguratie
Het IP-adres dat wordt gebruikt om Microsoft Flow-aanvragen te verzenden, is afhankelijk van de [regio](regions-overview.md) waarin de [omgeving](environments-overview-admin.md) die de stroom bevat zich bevindt. Er worden momenteel geen FQDN's gepubliceerd die beschikbaar zijn voor stroomscenario's.

>[!IMPORTANT]
> Aantal aanroepen van een stroom maakt afkomstig van IP zijn kunnen-adressen die worden vermeld in de [Logic apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) documentatie. Enkele voorbeelden van deze aanroepen zijn HTTP of HTTP + OpenAPI.

### <a name="logic-apps"></a>Logic Apps
Aanroepen die vanuit een stroom worden gedaan, verlopen direct via de service Logische app van Azure. Enkele voorbeelden van deze aanroepen zijn HTTP of HTTP + OpenAPI. Raadpleeg [de documentatie voor Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) voor de IP-adressen die door deze service worden gebruikt.

### <a name="connectors"></a>Connectors
Aanroepen vanuit een connector in een stroom (bijvoorbeeld de SQL-API of de SharePoint-API) zijn afkomstig van de hier weergegeven IP-adressen:

| Regio | Uitgaande IP |
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

Als u bijvoorbeeld IP-adressen moet goedkeuren voor uw Azure SQL-database, moet u deze adressen gebruiken.

### <a name="required-services"></a>Vereiste services
De volgende tabel vermeldt de services waarmee Microsoft Flow verbinding maakt. Zorg ervoor dat geen van deze services in uw netwerk wordt geblokkeerd.

Domeinen | Protocollen | Gebruikt
--------|  ---------| -----
management.azure.com|https|Toegang tot Azure Resource Manager
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Toegang tot Active Directory Authentication Library (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|https|Toegang tot Microsoft Azure Active Directory Graph API - voor het ophalen van gebruikersgegevens, zoals een profielfoto.
*.azure-apim.net|https|Toegang tot de Runtime for Connectors.
*.flow.microsoft.com|https|Toegang tot de Microsoft Flow-website.
*.powerapps.com|https|Toegang tot de website PowerApps.
*.azureedge.net|https|Toegang tot het Microsoft Flow-CDN.
NPS.onyx.Azure.NET|https|Toegang tot NPS (Net Promoter Score).
