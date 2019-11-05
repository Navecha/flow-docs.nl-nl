---
title: Export aanvragen voor AVG-gegevens van Microsoft Flow | Microsoft Docs
description: Meer informatie over het gebruik van Microsoft Flow om te reageren op AVG betrokkenen-aanvragen voor het exporteren van gegevens.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 15eff70b8996e5ea130142a1c01699906e199642
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548204"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Reageren op AVG-aanvragen voor het exporteren van gegevens voor Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Als onderdeel van onze toezeg ging om u te helpen bij uw reis naar de AVG (AVG), hebben we documentatie ontwikkeld om u voor te bereiden. In de documentatie wordt niet alleen beschreven wat we doen om voor te bereiden op de AVG, maar zijn er ook voor beelden van stappen die u vandaag nog kunt uitvoeren met micro soft om AVG-naleving te ondersteunen bij gebruik van Microsoft Flow.

## <a name="manage-export-requests"></a>Export aanvragen beheren

Aan de *rechter kant van de draag baarheid van gegevens* kan een bijwerker een kopie van hun persoons gegevens in een elektronisch formaat aanvragen (dat is een gestructureerde, veelgebruikte, door de machine Lees bare indeling) die naar een andere gegevens controller kan worden verzonden.

Microsoft Flow biedt de volgende ervaringen om persoons gegevens voor een specifieke gebruiker te zoeken of exporteren:

* **Website toegang:** Meld u aan bij het [PowerApps-beheer centrum](https://admin.powerapps.com/)of het [Microsoft flow-beheer centrum](https://admin.flow.microsoft.com/).

* **Power shell-toegang:**  [PowerApps admin Power shell cmdlets](https://go.microsoft.com/fwlink/?linkid=871804).

|**Klant gegevens**|**Website toegang**|**Power shell-toegang**|
|-----------------|------------------|-------------------|
|Door het systeem gegenereerde logboeken|[Office 365 service Trust-Portal](https://servicetrust.microsoft.com/)|
|uitvoerings geschiedenis|Microsoft Flow Maker-Portal||
|Terugloop|Microsoft Flow Maker-Portal||
|Stroom machtigingen| Microsoft Flow Maker-Portal en Microsoft Flow-beheer centrum||
|Gebruikers Details||PowerApps-cmdlets|
|Inbel|Microsoft Flow Maker-Portal|PowerApps-cmdlets |
|Verbindings machtigingen|Microsoft Flow Maker-Portal|PowerApps-cmdlets |
|Aangepaste connectors|Microsoft Flow Maker-Portal|PowerApps-cmdlets |
|Machtigingen voor aangepaste connectors|Microsoft Flow Maker-Portal|PowerApps-cmdlets |
|#B0|Microsoft Flow Maker-Portal|Power shell-cmdlets voor on-premises gegevens gateway|
|Gateway machtigingen|Microsoft Flow Maker-Portal|Power shell-cmdlets voor on-premises gegevens gateway|

## <a name="export-a-flow"></a>Een stroom exporteren

Een eind gebruiker of beheerder, die zelf toegang tot de stroom heeft verleend, kan de stroom exporteren door de volgende stappen uit te voeren:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com/).

1. Selecteer de koppeling **mijn stromen** en selecteer vervolgens de stroom die u wilt exporteren.

1. Selecteren **... Meer**en selecteer vervolgens **exporteren**.

    ![Stroom exporteren](./media/gdpr-dsr-export/export-flow.png)

1. Selecteer **pakket (. zip)** .

Uw stroom is nu beschikbaar als zip-pakket. Zie het blog bericht over het [exporteren en importeren van een stroom](https://flow.microsoft.com/blog/import-export-bap-packages/)voor meer informatie.

## <a name="export-run-history"></a>Uitvoerings Geschiedenis exporteren

Uitvoerings geschiedenis bevat een lijst met alle uitvoeringen die hebben plaatsgevonden voor een stroom. Deze gegevens omvatten de status van de stroom, de begin tijd, de duur en de invoer-en uitvoer gegevens voor triggers en acties.

Een eind gebruiker of beheerder, die toegang tot de stroom via het Microsoft Flow-beheer centrum heeft gekregen, kan deze stappen volgen om deze gegevens te exporteren:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com/).
1. Selecteer de koppeling **mijn stromen** en selecteer vervolgens de stroom waarvoor u de uitvoerings geschiedenis wilt exporteren.
1. Selecteer in het deel venster **uitvoerings geschiedenis** de optie **alles weer geven**.

    ![uitvoerings geschiedenis](./media/gdpr-dsr-export/run-history.png)

1. Selecteer **CSV downloaden**.

    ![CSV downloaden](./media/gdpr-dsr-export/download-csv.png)

De uitvoerings geschiedenis wordt gedownload als een CSV-bestand, zodat u het kunt openen in micro soft Excel of een tekst editor en de resultaten verder wilt analyseren.

## <a name="export-a-users-activity-feed"></a>De activiteitsfeed van een gebruiker exporteren

In [Microsoft flow](https://flow.microsoft.com/)toont de activiteitsfeed de geschiedenis van activiteiten, fouten en meldingen van een gebruiker. Elke gebruiker kan de activiteitsfeed bekijken door de volgende stappen uit te voeren:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com/), selecteer het klok pictogram in de rechter bovenhoek en selecteer vervolgens **alle activiteiten weer geven**.

    ![Activiteitsfeed weer geven](./media/gdpr-dsr-export/show-activity-feed.png)

1. Kopieer de resultaten in het scherm **activiteit** en plak deze in een document editor, zoals micro soft Word.

    ![Activiteitsfeed weer geven](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>De verbindingen van een gebruiker exporteren

Verbindingen staan stromen toe om verbinding te maken met Api's, SaaS-toepassingen en andere systemen van derden. Volg deze stappen om uw verbindingen weer te geven:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com/), selecteer het tandwiel pictogram in de rechter bovenhoek en selecteer vervolgens **verbindingen**.

    ![Verbindingen weer geven](./media/gdpr-dsr-export/show-connections.png)
1. Kopieer de resultaten en plak deze in een document editor, zoals micro soft Word.

Power shell-cmdlets voor PowerApps-beheer

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Een lijst met de verbindings machtigingen van een gebruiker exporteren

Een gebruiker kan de toewijzingen van de verbindingsrol exporteren voor alle verbindingen waartoe ze toegang hebben via de Get-ConnectionRoleAssignment-functie in de [PowerApps Power shell cmdlets](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
Power shell-cmdlets voor PowerApps-beheer

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Aangepaste connectors van een gebruiker exporteren

Aangepaste connectors vormen een aanvulling op de out-of-Box connectors en bieden connectiviteit met andere Api's, SaaS en speciaal ontwikkelde systemen. U kunt het eigendom van een aangepaste connector overdragen of verwijderen.

Voer de volgende stappen uit om een lijst met klant connectors te exporteren:

1. Navigeer naar [Microsoft flow](https://flow.microsoft.com).
1. Selecteer het **tandwiel** pictogram voor de instellingen.
1. Selecteer **aangepaste connectors**.
1. Kopieer en plak de lijst met aangepaste connectors in een tekst editor, zoals micro soft Word.

    ![Aangepaste connectors exporteren](./media/gdpr-dsr-export/export-custom-connectors.png)

Naast de ervaring in Microsoft Flow kunt u de functie Get-connector van de [PowerApps Power shell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871804) gebruiken om alle aangepaste connectors te exporteren.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

Power shell-cmdlets voor PowerApps-beheer

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>De machtigingen voor de aangepaste connector van een gebruiker exporteren

Een gebruiker kan alle aangepaste connector machtigingen exporteren die ze hebben gemaakt via de Get-ConnectorRoleAssignment-functie in de [PowerApps Power shell cmdlets](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

Power shell-cmdlets voor PowerApps-beheer

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Goedkeurings Geschiedenis exporteren

Microsoft Flow goedkeurings historie legt een historisch overzicht vast van de goed keuringen die zijn ontvangen of verzonden voor een gebruiker. Elke gebruiker kan de goedkeurings geschiedenis weer geven op:

1. Aanmelden bij [Microsoft flow](https://flow.microsoft.com/), **goed keuringen**selecteren en vervolgens **geschiedenis**selecteren.

    ![Goedkeurings geschiedenis weer geven](./media/gdpr-dsr-export/view-approval-history.png)

1. In een lijst worden de goed keuringen weer gegeven die de gebruiker heeft ontvangen. De gebruikers kunnen goed keuringen weer geven die ze hebben verzonden door de pijl-omlaag naast **ontvangen** te selecteren en vervolgens **verzonden**te selecteren.

    ![Ontvangen goed keuringen weer geven](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Gebruikers gegevens exporteren
Gebruikers gegevens bieden een koppeling tussen een gebruiker en een specifieke Tenant. Een beheerder kan deze informatie exporteren door de cmdlet **Get-AdminFlowUserDetails** aan te roepen en de object-id voor de gebruiker door te geven.

Power shell-cmdlets voor PowerApps-beheer

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Gateway-instellingen exporteren
Reageren op aanvragen voor het exporteren van gegevens over on-premises gegevens gateways vindt u [hier](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

