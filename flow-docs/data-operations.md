---
title: Informatie over gegevens bewerkingen | Microsoft Docs
description: Meer informatie over het uitvoeren van bewerkingen, zoals het maken van een HTML-tabel, het maken van een CSV-tabel, het samen stellen, samen voegen, selecteren en filteren van matrices met Microsoft Flow.
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
ms.date: 08/02/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 87d805fb7de5ee9688e9e89c201be00fda8fb319
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547773"
---
# <a name="use-data-operations-with-microsoft-flow"></a>Gegevens bewerkingen met Microsoft Flow gebruiken
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
In dit overzicht vindt u meer informatie over enkele van de Microsoft Flow populaire gegevens bewerkingen, zoals opstellen, samen voegen, selecteren, matrix filteren, tabel maken en JSON parseren die beschikbaar zijn voor het bewerken van gegevens wanneer u stromen maakt.

## <a name="prerequisites"></a>Vereisten
* Toegang tot Microsoft Flow.
* Een hulp programma zoals [postman](https://www.getpostman.com/postman) om HTTP Post-aanvragen met een JSON-matrix naar uw stroom te verzenden.

## <a name="use-the-compose-action"></a>De actie opstellen gebruiken
Gebruik de actie **gegevens bewerkingen-opstellen** (samen stellen) om te voor komen dat u meerdere keren identieke gegevens hoeft in te voeren wanneer u een stroom ontwerpt. Als u bijvoorbeeld een matrix met cijfers moet invoeren: ````[0,1,2,3,4,5,6,7,8,9]```` verschillende keren tijdens het ontwerpen van uw stroom, kunt u de actie opstellen gebruiken om de matrix als volgt op te slaan:

1. Zoek naar **opstellen**en selecteer vervolgens de actie **gegevens bewerkingen-opstellen** (samen stellen).
   
    ![Zoek en selecteer de actie opstellen](./media/data-operations/search-select-compose.png)
2. Voer in het vak **invoer** de matrix in die u later wilt raadplegen:
   
    ![de actie opstellen configureren](./media/data-operations/add-array-compose.png)

> [!TIP]
> Voor eenvoudige Naslag informatie kunt u de naam van de kaart **opstellen** wijzigen door te klikken op de tekst ' opstellen ' op de titel balk van de kaart **opstellen** .
> 
> 

Wanneer u de inhoud van de actie opstellen wilt openen, voert u de volgende stappen uit via het **uitvoer** token van de **apps en connectors die in deze stroom lijst worden gebruikt** :

1. Een actie toevoegen, zoals **gegevens bewerkingen – samen voegen**.
2. Selecteer het besturings element waaraan u de inhoud wilt toevoegen die u hebt opgeslagen in de actie opstellen.
   
    De **dynamische inhoud toevoegen van de apps en connectors die in deze stroom worden gebruikt,** wordt geopend.
3. Selecteer op de pagina **dynamische inhoud toevoegen uit de apps en connectors die in deze stroom worden gebruikt**, het **uitvoer** token dat wordt weer gegeven onder de categorie **opstellen** van het tabblad **dynamische inhoud** .
   
    ![uitvoer van de actie opstellen gebruiken](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>De actie toevoegen gebruiken
Gebruik de actie **gegevens bewerkingen-lid** worden (lid worden) om een matrix te scheiden met een scheidings teken voor uw keuze. Stel dat uw stroom een webaanvraag ontvangt die de volgende matrix met e-mail adressen bevat: ````["d@example.com", "k@example.com", "dal@example.com"]````. Uw e-mail programma vereist echter adressen als één teken reeks, gescheiden door punt komma's. Als u dit wilt doen, gebruikt u de actie **gegevens bewerkingen-samen voegen** (samen voegen) om het komma scheidings teken te wijzigen in een punt komma '; ' door de volgende stappen te volgen:

1. Voeg een nieuwe actie toe, zoek naar **toevoegen**en selecteer vervolgens **gegevens bewerkingen-lid** worden (lid worden).
   
    ![Zoek en selecteer de actie toevoegen](./media/data-operations/search-select-join.png)
2. Voer de matrix in het vak **van** in en voer het nieuwe scheidings teken in dat u wilt gebruiken in het vak **samen voegen met** .
   
    Hier heb ik de punt komma (;) Als het nieuwe scheidings teken.
   
    ![de actie voor samen voegen configureren](./media/data-operations/add-array-join.png)
3. Sla de stroom op en voer deze uit.
4. Nadat de stroom is uitgevoerd, wordt de uitvoer van de actie **gegevens bewerkingen – samen voegen** :
   
    ![uitvoer samen voegen](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>De actie selecteren gebruiken
Gebruik de **gegevens bewerkingen – selecteren** (selecteren) om de vorm van de objecten in een matrix te transformeren. U kunt bijvoorbeeld elementen in elk object in een matrix toevoegen, verwijderen of een andere naam geven.

> [!NOTE]
> Hoewel u elementen kunt toevoegen of verwijderen met de actie selecteren, kunt u het aantal objecten in de matrix niet wijzigen.
> 
> 

U kunt bijvoorbeeld de actie selecteren gebruiken als gegevens uw stroom via een webaanvraag in deze indeling worden ingevoerd:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

en u de vorm van de binnenkomende gegevens wilt wijzigen door de naam ' First ' op ' FirstName ', Last to ' LastName ' aan te noemen en een nieuw lid met de naam ' Familynaam ' toe te voegen waarin ' First ' en ' last ' worden gecombineerd (gescheiden door een spatie):

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Ga als volgt te werk:

1. Voeg de actie **aanvraag/antwoord – antwoord** (aanvraag) toe aan de stroom.
2. Selecteer **voor beeld van nettolading gebruiken om schema te genereren** op de **aanvraag** kaart.
3. Plak in het vak dat wordt weer gegeven een voor beeld van de matrix met bron gegevens en selecteer vervolgens de knop **gereed** .
4. Voeg de actie **gegevens bewerkingen – selecteren** (selecteren) toe en configureer deze zoals in de volgende afbeelding.
   
    ![de actie selecteren configureren](./media/data-operations/select-card.png)
   
   > [!TIP]
   > De uitvoer van de actie Select is een matrix die de zojuist gevormde objecten bevat. U kunt deze matrix vervolgens gebruiken in elke andere actie, zoals **opstellen**, die eerder is besproken.
   > 
   > 

## <a name="use-the-filter-array-action"></a>De actie filter matrix gebruiken
Gebruik **gegevens bewerkingen-filter matrix** (filter matrix) om het aantal objecten in een matrix te beperken tot een subset die overeenkomt met de criteria die u opgeeft.

> [!NOTE]
> U kunt geen filter matrix gebruiken om de vorm van de objecten in een matrix te wijzigen. Het is ook mogelijk dat de tekst waarop u filtert hoofdletter gevoelig is.
> 
> 

U kunt bijvoorbeeld filter matrix gebruiken op deze matrix:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

voor het maken van een nieuwe matrix die alleen objecten bevat waarin *eerste* is ingesteld op ' Deon '.

Laten we dit doen.

1. Zoek de actie **gegevens bewerkingen-filter matrix** (filter matrix) en voeg deze toe aan uw stroom.
2. Configureer de actie voor de filter matrix, zoals in de volgende afbeelding.
   
    ![actie filter matrix configureren](./media/data-operations/add-configure-filter-array.png)
3. Sla de stroom op en voer deze uit.
   
    U kunt [postman](https://www.getpostman.com/postman) gebruiken om een webaanvraag te genereren die een JSON-matrix naar uw stroom verzendt.
4. Als uw stroom wordt uitgevoerd, ervan uitgaande dat de JSON-invoer eruitziet als deze matrix:
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    de uitvoer ziet er als volgt uit (u ziet dat alleen objecten waarin het *eerst* is ingesteld op ' Deon ' zijn opgenomen in de uitvoer van de actie):
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>Gebruik de actie CSV-tabel maken
Gebruik de **gegevens bewerkingen-CSV-tabel maken** (CSV-tabel maken) om een invoer van een JSON-matrix te wijzigen in een tabel met door komma's gescheiden waarden (CSV). U kunt de kopteksten ook zichtbaar laten in de CSV-uitvoer. U kunt bijvoorbeeld de volgende matrix omzetten in een CSV-tabel met behulp van de actie **CSV-tabel maken** :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. Zoek, voeg en configureer de actie **gegevens bewerkingen-CSV-tabel maken** die lijkt op de volgende afbeelding.
   
    ![de actie CSV-tabel maken configureren](./media/data-operations/create-csv-table.png)
   
    Opmerking: het token van de **hoofd tekst** in deze afbeelding is afkomstig van een actie **aanvraag/antwoord-antwoord** . u kunt echter wel de invoer voor de actie **CSV-tabel maken** ophalen uit de uitvoer van een eerdere actie in uw stroom, of rechtstreeks invoeren in de **Van** box.
2. Sla de stroom op en voer deze uit.
   
    Wanneer uw stroom wordt uitgevoerd, ziet de uitvoer van **CSV-tabel maken** eruit als deze afbeelding:
   
    ![uitvoer van CSV-tabel maken](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>Gebruik de actie HTML-tabel maken
**Gegevens bewerkingen gebruiken: Maak een HTML-tabel** om de invoer van een JSON-matrix te wijzigen in een HTML-tabel. Desgewenst kunt u de headers zichtbaar laten in de HTML-uitvoer.

Volg hiervoor de stappen in de [sectie CSV-tabel maken](#use-the-create-csv-table-action) voor een gedetailleerd voor beeld. Zorg ervoor dat u de actie **gegevens bewerkingen-HTML-tabel maken** gebruikt in plaats van de actie **gegevens bewerkingen-CSV-tabel maken** .

> [!TIP]
> Als u van plan bent de HTML-tabel via e-mail te verzenden, moet u in de e-mail actie ' IsHtml ' selecteren.
> 
> 

