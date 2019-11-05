---
title: Een stroom maken met Dynamics 365 (online) | Microsoft Docs
description: Maak handige werk stromen met behulp van een Dynamics 365-verbinding en Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c3a138cef3761b188998766a60ceb84619ae5f0a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546923"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Een stroom maken met behulp van Dynamics 365 (online)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Met een Dynamics 365-connector kunt u stromen maken die worden gestart wanneer er een gebeurtenis optreedt in Dynamics 365 of een andere service, die vervolgens een actie uitvoert in Dynamics 365 of een andere service. 

In Microsoft Flow kunt u geautomatiseerde werk stromen tussen uw favoriete apps en services instellen om bestanden te synchroniseren, meldingen te ontvangen, gegevens te verzamelen en meer. Zie [aan de slag met Microsoft flow](getting-started.md)voor meer informatie.

> [!IMPORTANT] 
> Voor het aanroepen van een stroom trigger moet **Wijzigingen bijhouden** zijn ingeschakeld voor de common data service entiteit die met de stroom wordt gebruikt. Meer informatie: [bijhouden van wijzigingen inschakelen voor het beheren van gegevens synchronisatie](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>Een stroom maken op basis van een sjabloon
U kunt een stroom maken met behulp van een van de vele beschik bare sjablonen, zoals deze voor beelden:

* Wanneer een object wordt gemaakt in Dynamics 365, maakt u een lijst item in share point.
* Dynamics 365-lead records maken op basis van een Excel-tabel.
* Dynamics 365-accounts kopiëren naar klanten in Dynamics 365 voor bewerkingen.

Volg deze stappen om een stroom te maken op basis van een sjabloon.

1. Meld u aan bij de [Microsoft flow-website](https://flow.microsoft.com/).
2. Klik of tik op **Services**en klik of tik vervolgens op **Dynamics 365**.
3. Er zijn verschillende sjablonen beschikbaar. Selecteer de gewenste sjabloon om aan de slag te gaan.

## <a name="create-a-task-from-a-lead"></a>Een taak maken op basis van een lead
Als er geen sjabloon beschikbaar is voor wat u nodig hebt, maakt u een volledig nieuwe stroom. In dit scenario ziet u hoe u een taak maakt in Dynamics 365 wanneer een lead wordt gemaakt in Dynamics 365.

1. Meld u aan bij de [Microsoft flow-website](https://flow.microsoft.com/).
2. Klik of tik op **mijn stromen**en klik of tik op **leeg item maken**.
3. Klik of tik in de lijst met stroom triggers op **Dynamics 365-wanneer een record wordt gemaakt**.
4. Meld u aan bij Dynamics 365 als u hierom wordt gevraagd.
5. Selecteer onder **organisatie naam**het Dynamics 365-exemplaar waar u de stroom wilt laten Luis teren.
6. Selecteer bij **entiteit naam**de entiteit waarnaar u wilt Luis teren, die zal fungeren als trigger voor het initiëren van de stroom.
   
     Voor dit scenario selecteert u **leads**.
   
    ![Details van stroom](./media/connection-dynamics365/flow-details.png)
    > BELANG rijk De entiteits definitie moet **Wijzigingen bijhouden** ingeschakeld hebben om de stroom te activeren op de Dynamics 365-entiteit. Zie [Wijzigingen bijhouden inschakelen om gegevens synchronisatie te beheren](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. Klik of tik op **nieuwe stap**en klik of tik vervolgens op **een actie toevoegen**.
8. Klik of tik op **Dynamics 365 – een nieuwe record maken**.
9. Selecteer onder **organisatie naam**het Dynamics 365-exemplaar waar u de stroom wilt maken. Merk op dat het niet hetzelfde exemplaar moet zijn als waarin de gebeurtenis wordt geactiveerd.
10. Selecteer bij **entiteit naam**de entiteit waarmee een record wordt gemaakt wanneer de gebeurtenis optreedt.
    
     Voor dit scenario selecteert u **taken**.
11. Het vak **onderwerp** wordt weer gegeven. Wanneer u erop klikt of tikt, wordt er een deel venster met dynamische inhoud weer gegeven waarin u een van deze velden kunt selecteren.
    
    * **Achternaam**. Als u dit veld selecteert, wordt de achternaam van de lead ingevoegd in het veld **onderwerp** van de taak wanneer deze wordt gemaakt.
    * **Onderwerp**. Als u dit veld selecteert, wordt het veld **onderwerp** voor de lead ingevoegd in het veld **onderwerp** van de taak wanneer deze wordt gemaakt.
    
    Voor dit scenario selecteert u **onderwerp**.
    
    ![Stroom toevoegen onderwerp](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Tip:** Klik of tik in het deel venster dynamische inhoud op **meer** informatie om meer velden weer te geven die zijn gekoppeld aan de entiteit. U kunt bijvoorbeeld ook het veld **onderwerp** van de taak invullen met het veld **Bedrijfs naam**, de **klant**, de **Beschrijving**of het **e-mail adres** van de lead.
    > 
    > 
12. Klik of tik op **stroom maken**.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Een Wunderlist-taak maken op basis van een Dynamics 365-taak
In dit scenario ziet u hoe u een taak in [Wunderlist](https://www.wunderlist.com) maakt wanneer een taak wordt gemaakt in Dynamics 365. Wunderlist is een service op Internet die u kunt gebruiken om taken lijsten te maken, herinneringen toe te voegen of boodschappen te volgen.

1. Meld u aan bij de [Microsoft flow-website](https://flow.microsoft.com/).
2. Klik of tik op **mijn stromen**en klik of tik op **leeg item maken**.
3. Klik of tik in de lijst met stroom triggers op **Dynamics 365-wanneer een record wordt gemaakt**.
4. Selecteer onder **organisatie naam**het Dynamics 365-exemplaar waar u de stroom wilt laten Luis teren.
5. Selecteer bij **entiteit naam**de entiteit waarnaar u wilt Luis teren. deze fungeert als een trigger om de stroom te initiëren.
   
    Voor dit scenario selecteert u **taken**.
6. Klik of tik op **nieuwe stap**en klik of tik vervolgens op **een actie toevoegen**.
7. Typ *een taak maken*en klik of tik op **Wunderlist – een taak maken**.
8. Selecteer **Postvak in**onder **lijst-ID**.
9. Onder **titel**selecteert u **onderwerp** in het deel venster dynamische inhoud.
10. Klik of tik op **stroom maken**.  

## <a name="trigger-based-logic"></a>Logica op basis van trigger
Triggers zoals **Wanneer een record wordt gemaakt**, **Wanneer een record wordt bijgewerkt**en **Wanneer een record wordt verwijderd** , initieert de stroom binnen een paar minuten van de gebeurtenis die optreedt.  In zeldzame gevallen kan het tot twee uur duren voordat de stroom wordt geactiveerd.

Wanneer de trigger plaatsvindt, ontvangt de stroom een melding, maar wordt de stroom uitgevoerd op gegevens die bestaan op het moment dat de actie wordt uitgevoerd.  Als uw stroom bijvoorbeeld wordt geactiveerd wanneer er een nieuwe record wordt gemaakt en u de record twee keer bijwerkt voordat de stroom wordt uitgevoerd, wordt de stroom slechts één keer uitgevoerd met de meest recente gegevens.

## <a name="specify-advanced-options"></a>Geavanceerde opties opgeven
Wanneer u een stap aan een stroom toevoegt, kunt u op **Geavanceerde opties weer geven** klikken of tikken om een filter of order by-query toe te voegen die bepaalt hoe de gegevens in de stroom worden gefilterd.

U kunt bijvoorbeeld een filter query gebruiken om alleen actieve contact personen op te halen, en u kunt deze sorteren op achternaam. Hiervoor voert u de OData-filter query **status code EQ 1** in en selecteert u **Achternaam** in het deel venster dynamische inhoud. Zie voor meer informatie over filteren en sorteren op query's [MSDN: $filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) en [MSDN: $OrderBy](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![OrderBy-query flow](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Aanbevolen procedures voor het gebruik van geavanceerde opties
Wanneer u een waarde toevoegt aan een veld, moet u overeenkomen met het veld type, ongeacht of u een waarde typt of er een selecteert in het deel venster dynamische inhoud.

| Veld type | Het gebruik van | Waar zoeken | Naam | Gegevens type |
| --- | --- | --- | --- | --- |
| Tekst velden |Voor tekst velden is één tekst regel of dynamische inhoud vereist die een veld voor tekst type is. Voor beelden zijn de velden **categorie** en **subcategorie** . |**Instellingen** > **aanpassingen** > **de systeem** > **entiteiten** > **taak** > **velden** aanpassen |**rubriek** |**Eén tekst regel** |
| Velden met gehele getallen |Voor sommige velden is een geheel getal of dynamische inhoud vereist die een veld van het type geheel getal is. Voor beelden zijn onder meer **percentage voltooid** en **duur**. |**Instellingen** > **aanpassingen** > **de systeem** > **entiteiten** > **taak** > **velden** aanpassen |**PercentComplete** |**Geheel getal** |
| Datum velden |Voor sommige velden is een datum vereist die is ingevoerd in de notatie mm/dd/jjjj of dynamische inhoud die een datum type veld is. Voor beelden zijn onder meer: **gemaakt op**, **begin datum**, **werkelijke start**, **laatst op wacht tijd**, **werkelijk einde**en **verval datum**. |**Instellingen** > **aanpassingen** > **de systeem** > **entiteiten** > **taak** > **velden** aanpassen |**createdon** |**Datum en tijd** |
| Velden waarvoor een record-ID en een opzoek type zijn vereist |Voor sommige velden die naar een andere entiteits record verwijzen, moeten zowel de record-ID als het opzoek type zijn vereist. |**Instellingen** > **aanpassingen** > **de systeem** > **entiteiten** > **account** > **velden** aanpassen |**AccountId** |**Primaire sleutel** |
|Optieset|De velden van de optieset vereisen een bekende integer-waarde die moet worden door gegeven aan dit type veld.  In het gebied Dynamics 365-aanpassing kunt u een weer gave met de optie back-up van een geheel getal instellen samen met het bijbehorende label.|Instellingen > aanpassing > de systeem > entiteiten > account > velden aanpassen | Voorkeurs methode voor contact persoon| Geheel getal|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Meer voor beelden van velden waarvoor een record-ID en een opzoek type zijn vereist
Uitvouwen in de vorige tabel zijn hier meer voor beelden van velden die niet werken met waarden die zijn geselecteerd in de lijst met dynamische inhoud. In plaats daarvan moeten voor deze velden een record-ID en een opzoek type zijn ingevoerd in de velden in PowerApps.

* Type **eigenaar** en **eigenaar**.
  
  * Het veld **eigenaar** moet een geldige record-id van een gebruiker of een team zijn.
  * Het **type eigenaar** moet **systemusers** of **teams**zijn.
* **Klant** -en **klant type**.
  
  * Het veld **klant** moet een geldige account-of contact record-id zijn.
  * Het **klant type** moet **accounts** of **contact personen**zijn.
* **Met betrekking** tot en **type**.
  
  * Het veld **betreft** moet een geldige record-id zijn, zoals een account of record-id van een contact persoon.
  * Het **betreffende type** moet het opzoek type voor de record zijn, zoals **accounts** of **contact personen**.

In dit voor beeld wordt een account record toegevoegd die overeenkomt met de record-ID, die wordt toegevoegd aan het veld **betreft** van de taak.

  ![Flow, recordID en type account](./media/connection-dynamics365/flow-recordid-account.png)

In dit voor beeld wordt de taak ook toegewezen aan een specifieke gebruiker op basis van de record-ID van de gebruiker.

  ![Flow RecordID en type gebruiker](./media/connection-dynamics365/flow-recordid-user.png)

Zie [de record-id zoeken](#find-the-records-id) verderop in dit onderwerp om de id van een record te vinden.

> **Belang rijk:** Velden mogen geen waarde bevatten als ze een beschrijving hebben van ' alleen voor intern gebruik '. Deze velden zijn onder andere **pad**, **aanvullende para meters**en het **versie nummer van de tijdzone regel.**
> 
> 

## <a name="find-the-records-id"></a>De record-ID zoeken
1. Open in de Dynamics 365-webtoepassing een record, zoals een account record.
2. Klik of tik op de werk balk acties op **pop Out**
   ![popout record](./media/connection-dynamics365/popout.png) (of klik of tik op **e-mail adres een koppeling** om de volledige URL naar uw standaard e-mail programma te kopiëren).
   
    De URL in de adres balk van de webbrowser bevat de record-ID tussen% 7b en% 7d encoding-tekens.
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Verwante onderwerpen
[Problemen met een stroom oplossen](fix-flow-failures.md)

[De stroom in uw organisatie Q & A](organization-q-and-a.md)

[Veelgestelde vragen](frequently-asked-questions.md)

