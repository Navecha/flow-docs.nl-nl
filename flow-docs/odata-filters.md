---
title: "Gegevens filteren en kopiëren | Microsoft Docs"
description: "Informatie over het filteren en kopiëren van gegevens van een bron naar een doel met Microsoft Flow"
services: 
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/21/2017
ms.author: deonhe
ms.openlocfilehash: 37b53fa50afdc6865c5ba905957405f0e4b67520
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="filter-and-copy-data-with-microsoft-flow"></a>Gegevens filteren en kopiëren met Microsoft Flow
In deze procedure ziet u hoe u een stroom kunt maken waarmee een bron wordt gecontroleerd op nieuwe of gewijzigde items en deze wijzigingen naar een doel worden gekopieerd. U kunt een dergelijke stroom maken als uw gebruikers gegevens op één locatie invoeren, maar uw team deze nodig hebben op een andere locatie of in een andere indeling.

In deze procedure worden gegevens gekopieerd van een Microsoft SharePoint-[lijst](https://support.office.com/en-us/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) (bron) naar een [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview)-tabel (doel), maar u kunt gegevens kopiëren tussen de meer dan [150 services](https://flow.microsoft.com/connectors/) die Microsoft Flow ondersteunt.

> [!IMPORTANT]
> Wijzigingen die u in het doel aanbrengt, worden niet gekopieerd naar de bron omdat synchronisatie in twee richtingen niet wordt ondersteund. Als u toch synchronisatie in twee richtingen instelt, maakt u een oneindige lus waarin wijzigingen eindeloos worden verzonden tussen de bron en het doel.
> 
> 

## <a name="prerequisites"></a>Vereisten
* Toegang tot een gegevensbron en een doel. Deze procedure bevat geen stappen voor het maken van de bron en het doel.
* U moet toegang hebben tot [Microsoft Flow](https://flow.microsoft.com).
* Basiskennis van hoe uw gegevens worden opgeslagen.
* Bekendheid met de basisprincipes van het maken van stromen. U kunt nalezen hoe u [acties, triggers](multi-step-logic-flow.md#add-another-action) en [voorwaarden](add-a-condition.md) maakt. In de volgende stappen wordt ervan uitgegaan dat u weet hoe u deze acties uitvoert.

> [!TIP]
> Niet alle kolomnamen in de bron en het doel hoeven overeen te komen, maar u moet gegevens opgeven voor alle *vereiste* kolommen wanneer u een item invoegt of bijwerkt. In Microsoft Flow worden de vereiste velden voor u geïdentificeerd.
> 
> 

## <a name="quick-overview-of-the-steps"></a>Snel overzicht van de stappen
Als u vertrouwd bent met Microsoft Flow, gebruikt u deze stappen om gegevens te kopiëren van de ene gegevensbron naar de andere:

1. Identificeer de bron die u wilt bewaken en het doel waarnaar u gewijzigde gegevens kopieert. Controleer of u toegang tot beide hebt.
2. Geef ten minste één kolom aan die een unieke identificatie van de items bevat in de bron en het doel. In het volgende voorbeeld gebruiken we de kolom **Titel**, maar u kunt elke gewenste kolom gebruiken.
3. Stel een trigger in waarmee de bron wordt gecontroleerd op wijzigingen.
4. Doorzoek het doel om te bepalen of het gewijzigde item bestaat.
5. Gebruik een **voorwaarde** zoals deze:
   * Als het nieuwe of gewijzigde item niet in het doel bestaat, moet dit worden gemaakt.
   * Als het nieuwe of gewijzigde item wel in het doel bestaat, moet dit worden bijgewerkt.
6. Activeer de stroom en bevestig dat nieuwe of gewijzigde items worden gekopieerd van de bron naar het doel.

> [!NOTE]
> Als u nog niet eerder een verbinding met SharePoint of Azure SQL Database hebt gemaakt, volgt u de instructies wanneer u wordt gevraagd u aan te melden.
> 
> 

Hier volgen de gedetailleerde stappen voor het maken van de stroom.

## <a name="monitor-the-source-for-changes"></a>De bron controleren op wijzigingen
1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com) en selecteer **Mijn stromen** > **Leeg item maken**.
2. Zoek naar **SharePoint** > selecteer de trigger **SharePoint: wanneer een item is gemaakt of gewijzigd** in de lijst met triggers.
3. Voer het **Siteadres** in en selecteer de **Lijstnaam** op de kaart **Wanneer een item is gemaakt of gewijzigd**.
   
    Geef het **Siteadres** en de **Lijstnaam** op van de SharePoint-lijst die door uw stroom wordt gecontroleerd op nieuwe of bijgewerkte items.
   
    ![sharepoint-trigger configureren](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>Het doel doorzoeken op het nieuwe of gewijzigde item
We gebruiken de actie **SQL Server - Rijen ophalen** om in het doel te zoeken naar het nieuwe of gewijzigde item.

1. Selecteer **Nieuwe stap** > **Een actie toevoegen**.
2. Zoek naar **Rijen ophalen**, selecteer **SQL Server - Rijen ophalen** en selecteer de tabel die u wilt controleren in de lijst **Tabelnaam**.
3. Selecteer **Geavanceerde opties weergeven**.
4. Typ **Titel eq '** in het vak **Filterquery**, selecteer het token **Titel** in de lijst met dynamische inhoud en typ **'**.
   
    In de vorige stap wordt ervan uitgegaan dat u zoekt op de titels van de rijen in de bron en het doel.
   
    De kaart **Rijen ophalen** moet er nu uitzien als deze afbeelding:
   
    ![het item ophalen uit de doeldatabase](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>Controleren of het nieuwe of gewijzigde item is gevonden
Selecteer **Nieuwe stap** > **Een voorwaarde toevoegen** om de kaart **Voorwaarde** te openen.

Op de voorwaardekaart:

1. Selecteer het vak aan de linkerkant.
   
    De lijst **Voeg dynamische inhoud toe van de apps en connectors in deze stroom** wordt geopend.
2. Selecteer **waarde** in de categorie **Rijen ophalen**.
   
   > [!TIP]
   > Bevestig dat u **waarde** hebt geselecteerd in de categorie **Rijen ophalen**. Selecteer **waarde** niet in de categorie **Wanneer een item is gemaakt of gewijzigd**.
   > 
   > 
3. Selecteer **is gelijk aan** in de lijst in het middelste vak.
4. Typ **0** (nul) in het vak aan de rechterkant.
   
    De **Voorwaarde**-kaart lijkt nu op deze afbeelding:
   
    ![een voorwaarde configureren](media/odata-filters/configure-condition.png)
5. Selecteer **Bewerken in geavanceerde modus**.
   
    Wanneer de geavanceerde modus wordt geopend, ziet u de expressie **@equals(body('Get_rows')?['value'], 0)** in het vak. Bewerk deze expressie door **length()** toe te voegen rond de functie **body('Get_items')?['value']**. De hele expressie ziet er nu als volgt uit: **@equals(length(body('Get_rows')?['value']), 0)**
   
    De **Voorwaarde**-kaart lijkt nu op deze afbeelding:
   
    ![een voorwaarde configureren](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > Door de functie **length()** toe te voegen, kan de lijst **waarde** worden gecontroleerd via de stroom en kan worden bepaald of deze items bevat.
   > 
   > 

Wanneer via uw stroom items worden 'opgehaald' van het doel, zijn er twee mogelijke resultaten.

| Resultaat | Volgende stap |
| --- | --- |
| Het item bestaat |[Werk het item bij](odata-filters.md#update-the-item-in-the-destination) |
| Het item bestaat niet |[Maak een nieuw item](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> De afbeeldingen van de kaarten **Rij invoegen** en **Rij bijwerken** die u hierna ziet, kunnen afwijken van uw kaarten omdat deze kaarten de namen bevatten van de kolommen in de Azure SQL Database-tabel die in de stroom wordt gebruikt.
> 
> 

## <a name="create-the-item-in-the-destination"></a>Het item maken in het doel
Als het item niet bestaat in het doel, maakt u dit met de actie **SQL Server - Rij invoegen**.

Op de vertakking**Zo ja** van de **Voorwaarde**:

1. Selecteer **Een actie toevoegen**, zoek naar **rij invoegen** en selecteer **SQL Server - Rij invoegen**.
   
    De kaart **Rij invoegen** wordt geopend.
2. Selecteer in de lijst **Tabelnaam** de tabel waarin het nieuwe item wordt ingevoegd.
   
    De kaart **Rij invoegen** wordt uitgevouwen, zodat u alle velden in de geselecteerde tabel kunt zien. Velden met een sterretje (*) zijn vereist en moeten worden ingevuld om een geldige rij te maken.
3. Selecteer elk veld dat u wilt vullen en voer de gegevens in.
   
    U kunt gegevens handmatig invoeren, een of meer tokens selecteren bij **Dynamische inhoud** of een combinatie van tekst en tokens in de velden gebruiken.
   
    De kaart **Rij invoegen** lijkt nu op deze afbeelding:
   
    ![een voorwaarde configureren](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>Het item bijwerken in het doel
Als het item in het doel bestaat, werkt u dit bij met de wijzigingen.

1. Voeg de actie **SQL Server - Rij bijwerken** toe aan de vertakking **Zo nee** van de **Voorwaarde**.
2. Volg de stappen in de sectie [Het item maken](odata-filters.md#create-the-item-in-the-destination) van dit document om de velden van de tabel te vullen.
   
    ![omgevingen weergeven](media/odata-filters/update-row.png)
3. Typ bovenaan de pagina een naam voor de stroom in het vak **Stroomnaam** en selecteer **Stroom maken** om deze op te slaan.
   
    ![uw stroom een naam geven](media/odata-filters/give-the-flow-a-name.png)

Wanneer er nu een item wordt gewijzigd in uw SharePoint-lijst (bron), wordt de stroom geactiveerd en wordt er een nieuw item ingevoegd of wordt een bestaand item in de Azure SQL Database (doel) bijgewerkt.

> [!NOTE]
> De stroom wordt niet geactiveerd wanneer een item wordt verwijderd uit de bron. Als dit een belangrijk scenario is, kunt u een afzonderlijke kolom toevoegen waarin wordt aangegeven wanneer een item niet meer nodig is.
> 
> 

## <a name="learn-more"></a>Meer informatie
Gebruik [gegevensbewerkingen](data-operations.md) in uw stromen.

