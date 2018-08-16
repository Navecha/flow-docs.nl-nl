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
ms.date: 01/31/2018
ms.author: stepsic
ms.openlocfilehash: 0595fa9113d85c6517392149f510a3a11df36061
ms.sourcegitcommit: cd3cdcff3accb9a54f002fdc33d33935b4276249
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/06/2018
ms.locfileid: "39519865"
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
| Nieuwe pogingen |4 |

## <a name="run-duration-and-retention"></a>Uitvoeringsduur en bewaarperiode
Dit zijn de limieten voor het uitvoeren van één stroom.

| Naam | Limiet | Opmerkingen |
| --- | --- | --- |
| Uitvoeringsduur |30 dagen |Inclusief werkstromen met stappen in behandeling, zoals goedkeuringen. Na 30 dagen zijn alle stappen in behandeling verlopen. Verlopen goedkeuringen worden verwijderd uit het goedkeuringscentrum. Als iemand een verlopen aanvraag probeert goed te keuren, wordt er een foutbericht verzonden. |
| Bewaarperiode |30 dagen |Dit is vanaf de begintijd van het uitvoeren. |
| Minimaal terugkeerpatroon |1 minuut | |
| Maximaal terugkeerpatroon |500 dagen | |
| Maximale bewaarperiode voor uitvoeringsgeschiedenis |28 dagen, volgens de AVG-regels. | |

## <a name="looping-and-debatching-limits"></a>Limieten voor lussen en debatching
Dit zijn limieten voor het uitvoeren van één stroom.

| Naam | Limiet | Opmerkingen |
| --- | --- | --- |
| ForEach-items |5000 |Met de filteractie kunt u naar behoefte grotere matrices filteren. |
| Until-iteraties |5000 | |
| SplitOn-items |5000 | |
| Parallelle uitvoering ForEach |1 | |

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

### <a name="logic-app-service"></a>Service Logische app
Aanroepen die vanuit een stroom worden gedaan, verlopen direct via de service Logische app van Azure. Enkele voorbeelden van deze aanroepen zijn HTTP of HTTP + OpenAPI. Deze aanroepen zijn afkomstig van de volgende IP-adressen:

| Regio | Uitgaande IP |
| --- | --- |
| Azië |168.63.200.173, 13.75.89.159, 23.97.68.172, 13.75.94.173, 40.83.127.19, 52.175.33.254, 52.163.93.214, 52.187.65.81, 52.187.65.155, 13.76.133.155, 52.163.228.93, 52.163.230.166 |
| Australië |13.75.153.66, 104.210.89.222, 104.210.89.244, 13.75.149.4, 104.210.91.55, 104.210.90.241, 13.73.115.153, 40.115.78.70, 40.115.78.237, 13.73.114.207, 13.77.3.139, 13.70.159.205 |
| Canada |52.233.29.92, 52.228.39.241, 52.228.39.244, 52.232.128.155, 52.229.120.45, 52.229.126.25 |
| Europa |13.79.173.49, 52.169.218.253, 52.169.220.174, 40.113.12.95, 52.178.165.215, 52.178.166.21, 13.95.155.53, 52.174.54.218, 52.174.49.6, 40.68.222.65, 40.68.209.23, 13.95.147.65 |
| India |52.172.157.194, 52.172.184.192, 52.172.191.194, 52.172.154.168, 52.172.186.159, 52.172.185.79, 52.172.9.47, 52.172.49.43, 52.172.51.140, 52.172.50.24, 52.172.55.231, 52.172.52.0 |
| Japan |13.71.146.140, 13.78.84.187, 13.78.62.130, 13.71.158.3, 13.73.4.207, 13.71.158.120, 40.74.140.173, 40.74.81.13, 40.74.85.215, 40.74.140.4, 104.214.137.243, 138.91.26.45 |
| Verenigde Staten |137.135.106.54, 40.117.99.79, 40.117.100.228, 13.92.98.111, 40.121.91.41, 40.114.82.191, 52.160.90.237, 138.91.188.137, 13.91.252.184, 52.160.92.112, 40.118.244.241, 40.118.241.243 |

### <a name="services"></a>Services

> [!IMPORTANT]
>   Als u bestaande configuraties hebt, moet u deze zo snel mogelijk voor 1 september 2018 bijwerken, zodat deze de IP-adressen bevatten in deze lijst voor de regio's waar uw stromen bestaan.

Aanroepen van een API (bijvoorbeeld de SQL API of de SharePoint API) waarmee via een stroom verbinding is gemaakt, zijn afkomstig van het hieronder vermelde IP-adres:

| Regio | Uitgaande IP |
| --- | --- |
| Azië |13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19, 52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 52.187.53.78, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124, 23.97.72.250 |
| Australië |13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174, 13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.188.38, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35, 13.70.88.23 |
| Brazilië |191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Canada |13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152, 52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56, 52.229.123.161, 52.233.27.68 |
| Europa |13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 52.178.37.42, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254, 52.164.249.26, 137.117.161.181 |
| India |104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218, 52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.49.180, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245, 52.172.153.107 |
| Japan |13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248, 104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 104.214.151.229, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229, 13.78.121.151 |
| Verenigd Koninkrijk |51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Verenigde Staten |13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49, 104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 40.78.144.221, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 13.93.159.171, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191, 23.96.11.216 |
| Verenigde Staten (als eerste toegang) |13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157, 52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 52.161.31.35, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29, 13.66.208.24 |

Als u bijvoorbeeld IP-adressen moet goedkeuren voor uw Azure SQL-database, moet u deze adressen gebruiken.

De volgende tabel vermeldt de services waarmee Microsoft Flow verbinding maakt. Zorg ervoor dat geen van deze services in uw netwerk wordt geblokkeerd.

Domeinen | Protocollen | Gebruikt
--------|  ---------| -----
management.azure.com|https|Toegang tot Azure Resource Manager
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Toegang tot Active Directory Authentication Library (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|https|Toegang tot Microsoft Azure Active Directory Graph API - voor het ophalen van gebruikersgegevens, zoals een profielfoto.
*.azure-apim.net|https|Toegang tot de Runtime for Connectors.
*.flow.microsoft.com|https|Toegang tot de Microsoft Flow-website.
*.powerapps.com|https|Toegang tot de website PowerApps.
psux.azureedge.net|https|Toegang tot het Microsoft Flow-CDN.
NPS.onyx.Azure.NET|https|Toegang tot NPS (Net Promoter Score).

