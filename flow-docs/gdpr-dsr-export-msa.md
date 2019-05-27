---
title: Exportverzoeken van betrokkenen in het kader van de AVG met Microsoft Flow voor Microsoft-accounts (MSA) | Microsoft Docs
description: Ontdek hoe u Microsoft Flow kunt gebruiken om te reageren op exportverzoeken van betrokkenen in het kader van de AVG voor Microsoft-accounts.
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
ms.date: 5/25/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 6f181a66453573c2f636cbe5130b7fc003a3b151
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035011"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Reageren op exportverzoeken van betrokkenen in het kader van de AVG met Microsoft Flow

In het kader van onze inzet om met u samen te werken nu de Algemene verordening gegevensbescherming (AVG) eraan komt, hebben we documentatie ontwikkeld om u daarop voor te bereiden. In deze documentatie wordt niet alleen beschreven wat we doen als voorbereiding op de AVG, maar laten we ook voorbeelden zien van hoe u vandaag al samen met Microsoft AVG-naleving kunt ondersteunen bij gebruik van Microsoft Flow.

## <a name="manage-export-requests"></a>Exportverzoeken beheren

De *rechts overdraagbaarheid van gegevens* kunnen betrokkenen om aan te vragen van hun persoonsgegevens in elektronische vorm (dat wil zeggen een 'gestructureerde, gangbare machine leesbare en interoperabele indeling') die kan worden overgedragen aan een andere verwerkingsverantwoordelijke.

Gebruik het [Microsoft-privacydashboard](https://account.microsoft.com/privacy/) of [Microsoft Flow](https://flow.microsoft.com/) om persoonsgegevens voor een specifieke gebruiker te zoeken of te exporteren.

|Persoonsgegevens|Locatie|
|-----------------|-------------------|
|Activiteit van producten en services|Privacydashboard van Microsoft|
|Stromen|Microsoft Flow Maker Portal|
|Uitvoeringsgeschiedenis|Microsoft Flow Maker Portal|
|Activiteitsfeed|Microsoft Flow Maker Portal|
|Verbindingen|Microsoft Flow Maker Portal|

## <a name="export-product-and-service-activity"></a>Product- en serviceactiviteit exporteren

1. Meld u aan bij het [Microsoft-privacydashboard](https://account.microsoft.com/privacy/) met uw Microsoft-account (MSA).
1. Selecteer **Activiteitenoverzicht**.

    ![Activiteitengeschiedenis](./media/gdpr-dsr-export-msa/activityhistory.png): u kunt door uw activiteitengeschiedenis bladeren voor de verschillende Microsoft-toepassingen en -services die u gebruikt.
1. Als u gegevens over uw **product- en serviceactiviteit** wilt exporteren, selecteert u **Uw gegevens downloaden** en vervolgens **NIEUW ARCHIEF MAKEN**.

    ![Uw gegevens downloaden](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Selecteer **App- en servicegebruik** en vervolgens **Archief maken**.

    ![Uw gegevens downloaden](./media/gdpr-dsr-export-msa/create-archive.png)
1. Er wordt een nieuw archief gemaakt. Selecteer **Downloaden** om de geëxporteerde gegevens over uw product- en serviceactiviteit op te halen.

    ![Downloaden](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Een stroom exporteren

Een eindgebruiker die toegang heeft tot een stroom, kan de stroom exporteren door deze stappen te volgen:

1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com/).

1. Selecteer **Mijn stromen** en selecteer vervolgens de stroom die u wilt exporteren.

1. Selecteer **... Meer** en selecteer **Exporteren**.

    ![Stroom exporteren](./media/gdpr-dsr-export/export-flow.png)

1. Selecteer **Pakket (.zip)**.

De stroom is nu beschikbaar als zip-pakket. Zie voor meer informatie het blogbericht over [exporteren en importeren van een stroom](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Uitvoeringsgeschiedenis exporteren

De uitvoeringsgeschiedenis bevat een lijst met alle uitvoeringen voor een stroom. Deze gegevens omvatten de status, begintijd en duur van de stroom en de invoer-/uitvoergegevens voor triggers en acties.

Een eindgebruiker die toegang heeft tot een stroom, kan zijn of haar gegevens exporteren door deze stappen te volgen:

1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com/).
1. Selecteer de koppeling **Mijn stromen** en selecteer de stroom waarvoor u de uitvoeringsgeschiedenis wilt exporteren.
1. Selecteer in het deelvenster **Uitvoeringsgeschiedenis** de optie **Alles weergeven**.

    ![Uitvoeringsgeschiedenis](./media/gdpr-dsr-export/run-history.png)

1. Selecteer **CSV-bestand downloaden**.

    ![CSV-bestand downloaden](./media/gdpr-dsr-export/download-csv.png)

De uitvoeringsgeschiedenis wordt gedownload als een CSV-bestand zodat u het kunt openen in Microsoft Excel of een teksteditor om de resultaten te analyseren.

## <a name="export-a-users-activity-feed"></a>De activiteitsfeed van een gebruiker exporteren

In [Microsoft Flow](https://flow.microsoft.com/) geeft de activiteitsfeed de geschiedenis van activiteiten, fouten en meldingen van een gebruiker weer. Gebruikers kunnen bekijken eigen activiteitsfeed door de volgende stappen:

1. Meld u aan bij [Microsoft Flow](http://flow.microsoft.com/), selecteer het belpictogram rechtsboven en selecteer vervolgens **Alle activiteiten weergeven**.

    ![Activiteitsfeed weergeven](./media/gdpr-dsr-export/show-activity-feed.png)

1. Kopieer in het scherm **Activiteit** de resultaten en plak deze in een teksteditor, zoals Microsoft Word.

    ![Activiteitsfeed weergeven](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>De verbindingen van een gebruiker exporteren

Met verbindingen kunnen stromen verbinding maken met API's, SaaS-toepassingen en andere systemen van derden. Volg deze stappen om uw verbindingen weer te geven:

1. Meld u aan bij [Microsoft Flow](http://flow.microsoft.com/), selecteer het tandwielpictogram rechtsboven en selecteer vervolgens **Verbindingen**.

    ![Verbindingen weergeven](./media/gdpr-dsr-export/show-connections.png)
1. Kopieer de resultaten en plak deze in een teksteditor, zoals Microsoft Word.
