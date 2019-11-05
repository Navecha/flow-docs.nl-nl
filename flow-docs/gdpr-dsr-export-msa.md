---
title: Export aanvragen voor AVG-gegevens voor micro soft-accounts (MSA) Microsoft Flow Microsoft Docs
description: Meer informatie over het gebruik van Microsoft Flow om te reageren op AVG betrokkenen-aanvragen voor het exporteren van gegevens van micro soft-accounts.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: Deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 253d6785228fb28b5c78d0cae629a237a2e176da
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548155"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Reageren op AVG-aanvragen voor het exporteren van gegevens voor Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Als onderdeel van onze toezeg ging om u te helpen bij uw reis naar de AVG (AVG), hebben we documentatie ontwikkeld om u voor te bereiden. In de documentatie wordt niet alleen beschreven wat we doen om voor te bereiden op de AVG, maar zijn er ook voor beelden van stappen die u vandaag nog kunt uitvoeren met micro soft om AVG-naleving te ondersteunen bij gebruik van Microsoft Flow.

## <a name="manage-export-requests"></a>Export aanvragen beheren

Aan de *rechter kant van gegevens portabiliteit* kunnen gegevens houders een kopie van hun persoons gegevens in een elektronisch formaat aanvragen (dat is een gestructureerde, veelgebruikte, door de machine Lees bare indeling) die kan worden overgedragen naar een andere gegevens controller.

Gebruik het [micro soft-privacybeleid](https://account.microsoft.com/privacy/)of [Microsoft flow](https://flow.microsoft.com/) om persoonlijke gegevens voor een specifieke gebruiker te zoeken of te exporteren.

|Persoons gegevens|Locatie|
|-----------------|-------------------|
|Product-en service activiteit|Micro soft-privacybeleid|
|Terugloop|Microsoft Flow Maker-Portal|
|uitvoerings geschiedenis|Microsoft Flow Maker-Portal|
|Activiteitsfeed|Microsoft Flow Maker-Portal|
|Inbel|Microsoft Flow Maker-Portal|

## <a name="export-product-and-service-activity"></a>Product-en service activiteit exporteren

1. Meld u aan bij het [micro soft-privacy-dash board](https://account.microsoft.com/privacy/) met uw micro soft-account (MSA).
1. Selecteer de **activiteiten geschiedenis**.

    ![activiteiten geschiedenis](./media/gdpr-dsr-export-msa/activityhistory.png) u kunt door de activiteiten geschiedenis bladeren voor de verschillende micro soft-toepassingen en-services die u gebruikt.
1. Als u de gegevens van **product-en service activiteit** wilt exporteren, selecteert u **uw gegevens downloaden**en selecteert u **nieuw archief maken**.

    ![Uw gegevens downloaden](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Selecteer **app-& service gebruik**en selecteer vervolgens **archief maken**.

    ![Uw gegevens downloaden](./media/gdpr-dsr-export-msa/create-archive.png)
1. Er wordt een nieuw archief gemaakt. Selecteer **downloaden** om de gegevens van uw geëxporteerde product-en service-activiteit te verkrijgen.

    ![Update](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Een stroom exporteren

Een eind gebruiker die toegang heeft tot een stroom, kan de stroom exporteren door de volgende stappen uit te voeren:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com/).

1. Selecteer **mijn stromen**en selecteer vervolgens de stroom die u wilt exporteren.

1. Selecteren **... Meer**en selecteer vervolgens **exporteren**.

    ![Stroom exporteren](./media/gdpr-dsr-export/export-flow.png)

1. Selecteer **pakket (. zip)** .

Uw stroom is nu beschikbaar als zip-pakket. Zie het blog bericht over het [exporteren en importeren van een stroom](https://flow.microsoft.com/blog/import-export-bap-packages/)voor meer informatie.

## <a name="export-run-history"></a>Uitvoerings Geschiedenis exporteren

Uitvoerings geschiedenis bevat een lijst met alle uitvoeringen voor een stroom. Deze gegevens omvatten de status van de stroom, de begin tijd, de duur en de invoer-en uitvoer gegevens voor triggers en acties.

Een eind gebruiker die toegang heeft tot de stroom kan deze stappen volgen om deze gegevens te exporteren:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com/).
1. Selecteer de koppeling **mijn stromen** en selecteer vervolgens de stroom waarvoor u de uitvoerings geschiedenis wilt exporteren.
1. Selecteer in het deel venster **uitvoerings geschiedenis** de optie **alles weer geven**.

    ![uitvoerings geschiedenis](./media/gdpr-dsr-export/run-history.png)

1. Selecteer **CSV downloaden**.

    ![CSV downloaden](./media/gdpr-dsr-export/download-csv.png)

De uitvoerings geschiedenis wordt gedownload als een CSV-bestand, zodat u het kunt openen in micro soft Excel of een tekst editor om de resultaten te analyseren.

## <a name="export-a-users-activity-feed"></a>De activiteitsfeed van een gebruiker exporteren

In [Microsoft flow](https://flow.microsoft.com/)toont de activiteitsfeed de geschiedenis van activiteiten, fouten en meldingen van een gebruiker. Gebruikers kunnen hun activiteitsfeed bekijken door de volgende stappen uit te voeren:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com/), selecteer het klok pictogram in de rechter bovenhoek en selecteer vervolgens **alle activiteiten weer geven**.

    ![Activiteitsfeed weer geven](./media/gdpr-dsr-export/show-activity-feed.png)

1. Kopieer de resultaten in het scherm **activiteit** en plak ze in een tekst editor, zoals micro soft Word.

    ![Activiteitsfeed weer geven](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>De verbindingen van een gebruiker exporteren

Verbindingen staan stromen toe om verbinding te maken met Api's, SaaS-toepassingen en andere systemen van derden. Volg deze stappen om uw verbindingen weer te geven:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com/), selecteer het tandwiel pictogram in de rechter bovenhoek en selecteer vervolgens **verbindingen**.

    ![Verbindingen weer geven](./media/gdpr-dsr-export/show-connections.png)
1. Kopieer de resultaten en plak deze in een tekst editor, zoals micro soft Word.
