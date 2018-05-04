---
title: 'Microsoft Flow: AVG-verzoeken van betrokkenen - export | Microsoft Docs'
description: Ontdek hoe u Microsoft Flow kunt gebruiken om te reageren op exportverzoeken van betrokkenen in het kader van de AVG.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: 1e1fe346ba6ffb264985da0115714246a621ef5a
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Reageren op exportverzoeken van betrokkenen in het kader van de AVG met Microsoft Flow

In het kader van onze inzet om met u samen te werken nu de Algemene verordening gegevensbescherming (AVG) eraan komt, hebben we documentatie ontwikkeld om u daarop voor te bereiden. In deze documentatie wordt niet alleen beschreven wat we doen als voorbereiding op de AVG, maar laten we ook voorbeelden zien van hoe u vandaag al samen met Microsoft AVG-naleving kunt ondersteunen bij gebruik van Microsoft Flow.

## <a name="manage-export-requests"></a>Exportverzoeken beheren

Met het *recht op dataportabiliteit* kunnen betrokkenen een verzoek indienen voor een kopie van hun persoonsgegevens in digitale vorm (dat wil zeggen een 'gestructureerde, gangbare, door een machine leesbare en interoperabele indeling') die kan worden overgedragen aan een andere verwerkingsverantwoordelijke.

Microsoft Flow biedt de volgende mogelijkheden voor het zoeken of exporteren van persoonsgegevens voor een specifieke gebruiker:

* **Webtoegang:** meld u aan bij het [PowerApps-beheercentrum](https://admin.powerapps.com/) of het [Microsoft Flow-beheercentrum](https://admin.flow.microsoft.com/).

* **PowerShell-toegang:**  [PowerApps Admin PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871804).

|**Klantgegevens**|**Websitetoegang**|**PowerShell-toegang**|
|-----------------|------------------|-------------------|
|Door het systeem gegenereerde logboeken|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|
|Uitvoeringsgeschiedenis|Microsoft Flow Maker Portal||
|Gebruikerstaken|| |
|Stromen|Microsoft Flow Maker Portal||
|Stroommachtigingen| Microsoft Flow Maker Portal en Microsoft Flow-beheercentrum||
|Gebruikersdetails|| |
|Verbindingen|Microsoft Flow Maker Portal| |
|Verbindingsmachtigingen|Microsoft Flow Maker Portal| |
|Aangepaste connectors|Microsoft Flow Maker Portal| |
|Machtigingen voor aangepaste connectors|Microsoft Flow Maker Portal| |
|Gateway|Microsoft Flow Maker Portal|PowerShell-cmdlets on-premises gateway|
|Gatewaymachtigingen|Microsoft Flow Maker Portal|

## <a name="export-a-flow"></a>Een stroom exporteren

Een eindgebruiker of beheerder, die zichzelf toegang tot de stroom heeft verleend, kan de stroom exporteren met behulp van de volgende stappen:

1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com/).

1. Selecteer de koppeling **Mijn stromen** en selecteer de stroom die u wilt exporteren.

1. Selecteer **... Meer** en selecteer **Exporteren**.

    ![Stroom exporteren](./media/gdpr-dsr-export/export-flow.png)

1. Selecteer **Pakket (.zip)**.

De stroom is nu beschikbaar als zip-pakket. Zie voor meer informatie het blogbericht over [exporteren en importeren van een stroom](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Uitvoeringsgeschiedenis exporteren

Uitvoeringsgeschiedenis bevat een lijst met alle uitvoeringen die voor een stroom hebben plaatsgevonden. Deze gegevens omvatten de status, begintijd en duur van de stroom en de invoer-/uitvoergegevens voor triggers en acties.

Een gebruiker of beheerder, die toegang tot de stroom via het Microsoft Flow-beheercentrum heeft, kan deze stappen volgen om deze gegevens exporteren:

1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com/).
1. Selecteer de koppeling **Mijn stromen** en selecteer de stroom waarvoor u de uitvoeringsgeschiedenis wilt exporteren.
1. Selecteer in het deelvenster **Uitvoeringsgeschiedenis** de optie **Alles weergeven**.

    ![Uitvoeringsgeschiedenis](./media/gdpr-dsr-export/run-history.png)

1. Selecteer **CSV-bestand downloaden**.

    ![CSV-bestand downloaden](./media/gdpr-dsr-export/download-csv.png)

De uitvoeringsgeschiedenis wordt gedownload als een CSV-bestand zodat u het kunt openen in Microsoft Excel of een teksteditor om de resultaten nader te analyseren.

## <a name="export-a-users-activity-feed"></a>De activiteitsfeed van een gebruiker exporteren

In [Microsoft Flow](https://flow.microsoft.com/) geeft de activiteitsfeed de geschiedenis van activiteiten, fouten en meldingen van een gebruiker weer. Elke gebruiker kan zijn eigen activiteitsfeed zien door de volgende stappen uit te voeren:

1. Meld u aan bij [Microsoft Flow](http://flow.microsoft.com/), selecteer het belpictogram rechtsboven en selecteer vervolgens **Alle activiteiten weergeven**.

    ![Activiteitsfeed weergeven](./media/gdpr-dsr-export/show-activity-feed.png)

1. Kopieer in het scherm **Activiteit** de resultaten en plak deze in een documenteditor, zoals Microsoft Word.

    ![Activiteitsfeed weergeven](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>De verbindingen van een gebruiker exporteren

Met verbindingen kunnen stromen verbinding maken met API's, SaaS-toepassingen en andere systemen van derden. Volg deze stappen om uw verbindingen weer te geven:

1. Meld u aan bij [Microsoft Flow](http://flow.microsoft.com/), selecteer het tandwielpictogram rechtsboven en selecteer vervolgens **Verbindingen**.

    ![Verbindingen weergeven](./media/gdpr-dsr-export/show-connections.png)
1. Kopieer de resultaten en plak deze in een documenteditor, zoals Microsoft Word.

## <a name="export-a-list-of-a-users-connection-permissions"></a>Een lijst met verbindingsmachtigingen van een gebruiker exporteren

Een gebruiker kan de toewijzingen voor verbindingsrollen exporteren voor alle verbindingen waartoe de gebruiker toegang heeft via de functie Get-ConnectionRoleAssignment in de [PowerApps PowerShell-cdmlets](https://go.microsoft.com/fwlink/?linkid=871804).
![Verbindingsmachtigingen exporteren](./media/gdpr-dsr-export/export-connection-permissions.png)

## <a name="export-a-users-custom-connectors"></a>Aangepaste connectors van een gebruiker exporteren

Aangepaste connectors vormen een aanvulling op de meegeleverde connectors en maken verbinding mogelijk met andere API's, SaaS-toepassingen en speciaal ontwikkelde systemen. U kunt het eigendom van een aangepaste connector overdragen of deze verwijderen.

Volg deze stappen om een lijst met aangepaste connectors te exporteren:

1. Navigeer naar [Microsoft Flow](https://flow.microsoft.com).
1. Selecteer het **tandwiel**pictogram.
1. Selecteer **Aangepaste connectors**.
1. Kopieer en plak de lijst met aangepaste connectors in een teksteditor, zoals Microsoft Word.

    ![Aangepaste connectors exporteren](./media/gdpr-dsr-export/export-custom-connectors.png)

Naast de mogelijkheden die Microsoft Flow biedt, kunt u de functie Get-Connector uit de [PowerApps PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871804) gebruiken om alle aangepaste connectors te exporteren.

![Aangepaste connectors exporteren met PowerShell](./media/gdpr-dsr-export/export-custom-connectors-powershell.png)

## <a name="export-a-users-custom-connector-permissions"></a>De machtigingen voor aangepaste connectors van een gebruiker exporteren

Een gebruiker kan alle machtigingen voor aangepaste connectors exporteren die hij heeft gemaakt via de functie Get-ConnectorRoleAssignment in de [PowerApps PowerShell-cdmlets](https://go.microsoft.com/fwlink/?linkid=871804).

![De machtigingen voor aangepaste connectors exporteren met PowerShell](./media/gdpr-dsr-export/export-connector-permissions.png)

## <a name="export-approval-history"></a>Goedkeuringsgeschiedenis exporteren

Microsoft Flow Approvals History legt een historisch overzicht vast van goedkeuringen die voor een gebruiker zijn ontvangen of verzonden. Elke gebruiker kan de eigen goedkeuringsgeschiedenis als volgt bekijken:

1. Meld u aan bij [Microsoft Flow](http://flow.microsoft.com/), selecteer **Goedkeuringen** en selecteer **Geschiedenis**.

    ![Goedkeuringsgeschiedenis weergeven](./media/gdpr-dsr-export/view-approval-history.png)

1. Een lijst geeft goedkeuringen weer die de gebruiker heeft ontvangen. De gebruikers kunnen goedkeuringen bekijken die ze hebben verzonden door de pijl-omlaag naast **Ontvangen** te selecteren en vervolgens **Verzonden** te selecteren.

    ![Ontvangen goedkeuringen weergeven](./media/gdpr-dsr-export/view-received-approvals.png)
