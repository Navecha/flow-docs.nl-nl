---
title: Gegevens filteren en kopiëren | Microsoft Docs
description: Meer informatie over het filteren en kopiëren van gegevens van een bron naar een doel met Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: be5863c51e17bdba32d79891725a81b386ec2e90
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548933"
---
# <a name="filter-and-copy-data-with-microsoft-flow"></a>Gegevens filteren en kopiëren met Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
In dit scenario ziet u hoe u een stroom maakt waarmee een bron wordt gecontroleerd op nieuwe of gewijzigde items en die wijzigingen vervolgens naar een doel worden gekopieerd. U kunt een stroom zoals deze maken als uw gebruikers gegevens invoeren op één locatie, maar uw team dit op een andere locatie of in een andere indeling nodig heeft.

Hoewel in dit overzicht gegevens worden gekopieerd van een micro soft share point- [lijst](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) (de bron) naar een [Azure SQL database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview) tabel (de bestemming), kunt u gegevens kopiëren tussen de meer dan [150 Services](https://flow.microsoft.com/connectors/) die Microsoft flow ondersteunt.

> [!IMPORTANT]
> Wijzigingen die u in de bestemming aanbrengt, worden niet gekopieerd naar de bron omdat synchronisatie in twee richtingen niet wordt ondersteund. Als u een synchronisatie in twee richtingen probeert in te stellen, maakt u een oneindige lus waar wijzigingen oneindig tussen de bron en de bestemming worden verzonden.
> 
> 

## <a name="prerequisites"></a>Vereisten
* Toegang tot een gegevens bron en een bestemming. Dit scenario bevat geen stappen voor het maken van de bron en het doel.
* Toegang tot [Microsoft flow](https://flow.microsoft.com).
* Basis informatie over hoe uw gegevens worden opgeslagen.
* Vertrouwd met de basis beginselen van het maken van stromen. U kunt controleren hoe [acties, triggers](multi-step-logic-flow.md#add-another-action)en [voor waarden](add-condition.md)worden toegevoegd. Bij de volgende stappen wordt ervan uitgegaan dat u weet hoe u deze acties moet uitvoeren.

> [!TIP]
> Elke kolom naam in de bron-en doel locatie hoeft niet overeen te komen, maar u moet gegevens opgeven voor alle *vereiste* kolommen wanneer u een item invoegt of bijwerkt. Microsoft Flow de vereiste velden voor u worden geïdentificeerd.
> 
> 

## <a name="quick-overview-of-the-steps"></a>Snel overzicht van de stappen
Als u vertrouwd bent met Microsoft Flow, kunt u deze snelle stappen gebruiken om gegevens te kopiëren van de ene gegevens bron naar de andere:

1. Identificeer de bron die u wilt bewaken en het doel waarnaar u de gewijzigde gegevens wilt kopiëren. Controleer of u toegang hebt tot beide.
2. Identificeer ten minste één kolom waarmee items in de bron en bestemming uniek worden geïdentificeerd. In het volgende voor beeld gebruiken we de kolom **title** , maar u kunt elke gewenste kolom (men) gebruiken.
3. Stel een trigger in waarmee de bron wordt gecontroleerd op wijzigingen.
4. Zoek het doel om te bepalen of het gewijzigde item bestaat.
5. Gebruik een **voor waarde** zoals deze:
   * Als het nieuwe of gewijzigde item niet bestaat in het doel, maakt u het.
   * Als het nieuwe of gewijzigde item zich in het doel bevindt, werkt u het bij.
6. Activeer uw stroom en bevestig dat er nieuwe of gewijzigde items van de bron naar het doel worden gekopieerd.

> [!NOTE]
> Als u nog geen verbinding met share point of Azure SQL Database hebt gemaakt, volgt u de instructies wanneer u wordt gevraagd om u aan te melden.
> 
> 

Hier volgen de gedetailleerde stappen voor het maken van de stroom.

## <a name="monitor-the-source-for-changes"></a>De bron controleren op wijzigingen
1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com), selecteer **mijn stromen** > **leeg maken**.
2. Zoek naar **share point** > Selecteer de trigger **share point-wanneer een item is gemaakt of gewijzigd** in de lijst met triggers.
3. Voer het **site adres** in en selecteer de **lijst naam** op de kaart **Wanneer een item is gemaakt of gewijzigd** .
   
    Geef het **site adres** en de **lijst naam** op voor de share point-lijst die wordt bewaakt door de stroom voor nieuwe of bijgewerkte items.
   
    ![share point-trigger configureren](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>De bestemming voor het nieuwe of gewijzigde item zoeken
We gebruiken SQL Server de actie **rijen ophalen** om de bestemming voor het nieuwe of gewijzigde item te zoeken.

1. Selecteer **nieuwe stap** > **een actie toe te voegen**.
2. Zoek naar **rijen ophalen**, selecteer **SQL Server-rijen ophalen**en selecteer vervolgens in de lijst **tabel naam** de tabel die u wilt bewaken.
3. Selecteer **Geavanceerde opties weer geven**.
4. Voer in het vak **filter query** de **titel EQ**in, selecteer het token **titel** in de lijst met dynamische inhoud en voer vervolgens **'** in.
   
    In de vorige stap wordt ervan uitgegaan dat u de titels van de rijen in de bron en het doel gebruikt.
   
    De kaart **rijen ophalen** moet er nu uitzien als de volgende afbeelding:
   
    ![Probeer het item op te halen uit de doel database](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>Controleren of het nieuwe of gewijzigde item is gevonden
Selecteer **nieuwe stap** > **een voor waarde toe te voegen** om de kaart **voor waarde** te openen.

Op de kaart voor waarde:

1. Selecteer het vak aan de linkerkant.
   
    De **dynamische inhoud toevoegen van de apps en connectors die in deze stroom lijst worden gebruikt,** wordt geopend.
2. Selecteer de **waarde** in de categorie **rijen ophalen** .
   
   > [!TIP]
   > Bevestig dat u de **waarde** hebt geselecteerd in de categorie **rijen ophalen** . Selecteer geen **waarde** in de categorie **Wanneer een item is gemaakt of gewijzigd** .
   > 
   > 
3. Selecteer **is gelijk aan** in de lijst in het middelste vak.
4. Geef **0** (nul) op in het vak aan de rechter kant.
   
    De **voorwaarde** kaart lijkt nu op deze afbeelding:
   
    ![een voor waarde configureren](media/odata-filters/configure-condition.png)
5. Selecteer **bewerken in geavanceerde modus**.
   
    Wanneer de geavanceerde modus wordt geopend, ziet u **\@gelijk is aan (Body (' Get_rows ')? [' waarde '], 0)** in het vak. Bewerk deze expressie door **Length ()** toe te voegen rondom de **hoofd tekst (' Get_items ')? [' Value ']** -functie. De volledige expressie ziet er nu als volgt uit: **@equals(length (hoofd tekst (' Get_rows ')? [' waarde ']), 0)**
   
    De **voorwaarde** kaart lijkt nu op deze afbeelding:
   
    ![een voor waarde configureren](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > Als u de functie **Length ()** toevoegt, kan de stroom de lijst met **waarden** controleren en bepalen of deze items bevat.
   > 
   > 

Wanneer de stroom items van de bestemming haalt, zijn er twee mogelijke resultaten.

| Daarvan | Volgende stap |
| --- | --- |
| Het item bestaat |[Het item bijwerken](odata-filters.md#update-the-item-in-the-destination) |
| Het item bestaat niet |[Een nieuw item maken](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> De afbeeldingen in de **rij invoegen** en **rij bijwerken** die hieronder worden weer gegeven, kunnen afwijken van u omdat deze kaarten de namen van de kolommen in de Azure SQL database tabel weer geven die in de stroom worden gebruikt.
> 
> 

## <a name="create-the-item-in-the-destination"></a>Het item maken in de doel locatie
Als het item zich niet in de doel locatie bevinden, maakt u dit met behulp van de actie voor het invoegen van een **rij SQL Server** .

Op de vertakking **Indien ja** van de **voor waarde**:

1. Selecteer **een actie toevoegen**, zoek naar **rij invoegen**en selecteer vervolgens **SQL Server-invoegrij**.
   
    De kaart **rij invoegen** wordt geopend.
2. Selecteer in de lijst **tabel naam** de tabel waarin het nieuwe item moet worden ingevoegd.
   
    De kaart **rij invoegen** wordt uitgebreid en alle velden in de geselecteerde tabel worden weer gegeven. Velden met een asterisk (*) zijn vereist en moeten worden ingevuld om de rij geldig te maken.
3. Selecteer elk veld dat u wilt vullen en voer de gegevens in.
   
    U kunt de gegevens hand matig invoeren, een of meer tokens uit de **dynamische inhoud**selecteren of een wille keurige combi natie van tekst en tokens in de velden invoeren.
   
    De kaart voor het **invoegen van rijen** lijkt nu op deze afbeelding:
   
    ![een voor waarde configureren](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>Het item in het doel bijwerken
Als het item zich in het doel bevindt, moet u het bijwerken met de wijzigingen.

1. Voeg de actie voor het bijwerken van de **rij SQL Server** toe aan de vertakking **if no** van de **voor waarde**.
2. Volg de stappen in de sectie [het item maken](odata-filters.md#create-the-item-in-the-destination) van dit document om de velden van de tabel in te vullen.
   
    ![omgevingen weer geven](media/odata-filters/update-row.png)
3. Voer boven aan de pagina een naam in voor de stroom in het vak **stroom naam** en selecteer **stroom maken** om deze op te slaan.
   
    ![uw stroom een naam gegeven](media/odata-filters/give-the-flow-a-name.png)

Wanneer een item in uw share point-lijst (bron) wordt gewijzigd, wordt de stroom nu geactiveerd en wordt een nieuw item ingevoegd of een bestaand item in uw Azure SQL Database (bestemming) bijgewerkt.

> [!NOTE]
> Uw stroom wordt niet geactiveerd wanneer een item uit de bron wordt verwijderd. Als dit een belang rijk scenario is, kunt u overwegen een afzonderlijke kolom toe te voegen die aangeeft wanneer een item niet meer nodig is.
> 
> 

## <a name="learn-more"></a>Meer informatie
Gebruik [gegevens bewerkingen](data-operations.md) in uw stromen.

