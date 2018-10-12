---
title: Een flow maken met Dynamics 365 (online) | Microsoft Docs
description: Nuttige werkstromen maken met behulp van een Dynamics 365-verbinding en Microsoft Flow
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
ms.openlocfilehash: c780b3d305fbd5549f9c7ffc2a23571007dac7a7
ms.sourcegitcommit: f7985b96afe68b079b7fd4a6d04cd0a042d893e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2018
ms.locfileid: "47188611"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Een stroom maken met behulp van Dynamics 365 (online)
Met behulp van een Dynamics 365-connector kunt u stromen maken die worden gestart wanneer in Dynamics 365 of een andere service een gebeurtenis plaatsvindt, waardoor vervolgens een actie wordt uitgevoerd in Dynamics 365 of een andere service. 

In Microsoft Flow kunt u geautomatiseerde werkstromen tussen uw favoriete apps en services instellen, onder andere om bestanden te synchroniseren, meldingen te ontvangen en gegevens te verzamelen. Zie [Aan de slag met Microsoft Flow](getting-started.md) voor meer informatie.

> [!IMPORTANT] 
> Als u een stroomtrigger wilt aanroepen, moet **Wijzigingen bijhouden** zijn ingeschakeld voor de entiteit van Dynamics 365 Customer Engagement die wordt gebruikt met de stroom. Meer informatie: [Bijhouden van wijzigingen inschakelen om gegevenssynchronisatie te beheren](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>Een stroom maken met een sjabloon
U kunt een stroom maken met een van de vele beschikbare sjablonen, zoals deze voorbeelden:

* Een lijstitem in SharePoint maken als in Dynamics 365 een object wordt gemaakt.
* Records met potentiële klanten in Dynamics 365 maken vanuit een Excel-tabel.
* Dynamics 365-accounts kopiëren naar klanten in Dynamics 365 for Operations.

Volg deze stappen om een stroom te maken vanuit een sjabloon.

1. Meld u aan bij de [Microsoft Flow-website](https://flow.microsoft.com/).
2. Klik of tik op **Services** en vervolgens op **Dynamics 365**.
3. Er zijn verschillende sjablonen beschikbaar. Selecteer om te beginnen de gewenste sjabloon.

## <a name="create-a-task-from-a-lead"></a>Een taak maken vanuit een potentiële klant
Als geen gewenste sjabloon beschikbaar is, maakt u een volledig nieuwe stroom. In dit scenario ziet u hoe u een taak maakt in Dynamics 365 telkens als een potentiële klant wordt gemaakt in Dynamics 365.

1. Meld u aan bij de [Microsoft Flow-website](https://flow.microsoft.com/).
2. Klik of tik op **Mijn stromen** en klik of tik vervolgens op **Leeg item maken**.
3. Klik of tik in de lijst van stroomtriggers op **Dynamics 365 - wanneer een record wordt gemaakt**.
4. Meld u aan bij Dynamics 365 als dat wordt gevraagd.
5. Selecteer onder **Organisatienaam** de Dynamics 365-instantie waarop de stroom moet luisteren.
6. Selecteer bij **Entiteitnaam** de entiteit waarnaar u wilt luisteren en die moet dienen als trigger die de stroom start.
   
     Selecteer voor dit scenario **Potentiële klanten**.
   
    ![Stroomgegevens](./media/connection-dynamics365/flow-details.png)
    > [BELANGRIJK] Als u wilt dat de Dynamics 365-entiteit wordt geactiveerd met de stroom, moet voor de definitie van de entiteit **Wijzigingen bijhouden** zijn ingeschakeld. Zie [Bijhouden van wijzigingen inschakelen om gegevenssynchronisatie te beheren](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. Klik of tik op **Nieuwe stap** en vervolgens op **Een actie toevoegen**.
8. Klik of tik op **Dynamics 365 - een nieuwe record maken**.
9. Selecteer onder **Organisatienaam** de Dynamics 365-instantie waarin de stroom de record moet maken. Dit hoeft niet dezelfde instantie te zijn vanwaar de gebeurtenis wordt geactiveerd.
10. Selecteer onder **Entiteitnaam** de entiteit die een record maakt als de gebeurtenis optreedt.
    
     Selecteer voor dit scenario **Taken**.
11. Het vak **Onderwerp** verschijnt. Als u erop klikt of tikt, wordt een dynamisch inhoudsvenster weergegeven waarin u een van deze twee velden kunt selecteren.
    
    * **Achternaam**. Als u dit veld selecteert, wordt de achternaam van de potentiële klant in het veld **Onderwerp** van de taak ingevoegd als deze wordt gemaakt.
    * **Onderwerp** Als u dit veld selecteert, wordt het veld **Onderwerp** ingevoegd in het veld **Onderwerp** van de taak als deze wordt gemaakt.
    
    Selecteer voor dit scenario **Onderwerp**.
    
    ![Onderwerp toevoegen aan stroom](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Tip:** klik of tik in het deelvenster met dynamische inhoud op **Meer weergeven** om meer velden weer te geven die zijn gekoppeld aan de entiteit. U kunt het veld **Onderwerp** van de taak bijvoorbeeld ook vullen met het veld **Bedrijfsnaam**, **Klant**, **Beschrijving** of **E-mail** van de potentiële klant.
    > 
    > 
12. Klik of tik op **Stroom maken**.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Een Wunderlist-taak maken vanuit een Dynamics 365-taak
In dit scenario ziet u hoe u een taak maakt in [Wunderlist](https://www.wunderlist.com) telkens als een taak wordt gemaakt in Dynamics 365. Wunderlist is een Internet-service waarmee u takenlijsten kunt maken, herinneringen kunt toevoegen of boodschappen kunt bijhouden.

1. Meld u aan bij de [Microsoft Flow-website](https://flow.microsoft.com/).
2. Klik of tik op **Mijn stromen** en klik of tik vervolgens op **Leeg item maken**.
3. Klik of tik in de lijst van stroomtriggers op **Dynamics 365 - wanneer een record wordt gemaakt**.
4. Selecteer onder **Organisatienaam** de Dynamics 365-instantie waarop de stroom moet luisteren.
5. Selecteer bij **Entiteitnaam** de entiteit waarnaar u wilt luisteren en die moet dienen als trigger die de stroom start.
   
    Selecteer voor dit scenario **Taken**.
6. Klik of tik op **Nieuwe stap** en vervolgens op **Een actie toevoegen**.
7. Typ *Een taak maken* en klik of tik op **Wunderlist – een taak maken**.
8. Selecteer **Postvak IN** onder **Lijst-id**.
9. Selecteer **Onderwerp** onder **Titel** in het deelvenster met dynamische inhoud.
10. Klik of tik op **Stroom maken**.  

## <a name="trigger-based-logic"></a>Op triggers gebaseerde logica
Door middel van triggers zoals **Wanneer een record wordt gemaakt**, **Wanneer een record wordt bijgewerkt** en **Wanneer een record wordt verwijderd** activeren uw stroom binnen enkele minuten na het begin van de gebeurtenis.  In zeldzame gevallen kan het tot twee uur duren voordat uw stroom wordt geactiveerd.

Wanneer de trigger plaatsvindt, ontvangt de stroom een melding, maar de stroom wordt uitgevoerd aan de hand van gegevens die bestaan op het moment dat de actie wordt uitgevoerd.  Als uw stroom bijvoorbeeld wordt geactiveerd zodra een nieuwe record wordt gemaakt en u de record twee keer bijwerkt voordat de stroom wordt uitgevoerd, wordt uw stroom slechts één keer uitgevoerd met de meest recente gegevens.

## <a name="specify-advanced-options"></a>Geavanceerde opties opgeven
Als u een stap aan een stroom toevoegt, kunt u op **Geavanceerde opties weergeven** klikken of tikken om een filter- of orderby-query toe te voegen die bepaalt hoe de gegevens in de stroom worden gefilterd.

U kunt bijvoorbeeld een filterquery gebruiken om alleen actieve contactpersonen op te halen en deze te sorteren op achternaam. Hiervoor voert u de OData-filterquery **statuscode eq 1** in en selecteert u **Achternaam** in het dynamische inhoudsvenster. Zie voor meer informatie over filter- en orderby-query's [MSDN: $filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) en [MSDN: $orderby](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Orderby-query voor stroom](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Aanbevolen procedures als geavanceerde opties worden gebruikt
Als u een waarde toevoegt aan een veld, moet deze overeenkomen met het veldtype. Dit geldt als u een waarde typt of er een selecteert in het dynamische inhoudsvenster.

| Veldtype | Gebruik | Plaats | Naam | Gegevenstype |
| --- | --- | --- | --- | --- |
| Tekstvelden |Voor tekstvelden is één regel tekst of dynamische inhoud uit een veld van een teksttype vereist. Voorbeelden zijn onder meer de velden **Categorie** en **Subcategorie**. |**Instellingen** > **Aanpassingen** > **Het systeem aanpassen** > **Entiteiten** > **Taak** > **Velden** |**category** |**Eén regel tekst** |
| Velden voor gehele getallen |Voor sommige velden is een geheel getal of dynamische inhoud uit een veld van het type geheel getal vereist. Voorbeelden zijn onder meer **Percentage voltooid** en **Duur**. |**Instellingen** > **Aanpassingen** > **Het systeem aanpassen** > **Entiteiten** > **Taak** > **Velden** |**percentcomplete** |**Geheel getal** |
| Datumvelden |Voor sommige velden is een datum in de notatie dd-mm-jjjj of dynamische inhoud uit een veld van het datumtype vereist. Voorbeelden zijn onder meer **Gemaakt op**, **Begindatum**, **Werkelijke begindatum**, **Laatste tijd in de wacht**, **Werkelijke einddatum**, en **Vervaldatum**. |**Instellingen** > **Aanpassingen** > **Het systeem aanpassen** > **Entiteiten** > **Taak** > **Velden** |**createdon** |**Datum en tijd** |
| Velden waarvoor een record-id en een opzoektype zijn vereist |Voor sommige velden die verwijzen naar een andere entiteitsrecord, zijn de record-id en het opzoektype vereist. |**Instellingen** > **Aanpassingen** > **Het systeem aanpassen** > **Entiteiten** > **Account** > **Velden** |**accountid** |**Primaire sleutel** |

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Meer voorbeelden van velden waarvoor een record-id en een opzoektype zijn vereist
U vindt hier als aanvulling op de vorige tabel meer voorbeelden van velden waarvoor geen waarden uit de lijst met dynamische inhoud kunnen worden gebruikt. In plaats daarvan moeten voor deze velden een record-id en een opzoektype worden ingevoerd in PowerApps.

* **Eigenaar** en **Type eigenaar**.
  
  * Het veld **Eigenaar** moet een geldige id voor een gebruikers- of teamrecord bevatten.
  * Het veld **Type eigenaar** moet een van de waarden **systemusers** of **teams** bevatten.
* **Klant** en **Type klant**.
  
  * Het veld **Klant** moet een geldige record-id voor een account of contactpersoon bevatten.
  * Het **Type klant** moet **accounts** of **contacts** zijn.
* **Betreffende** en **Betreffend type**.
  
  * Het veld **Betreffende** moet een geldige record-id bevatten, bijvoorbeeld voor een account of contactpersoon.
  * Het veld **Betreffend type** moet het opzoektype voor de record zijn, zoals **accounts** of **contacts**.

In dit voorbeeld wordt een accountrecord die overeenkomt met de record-id toegevoegd, waarbij de record wordt toegevoegd aan het veld **Betreffende** van de taak.

  ![Record-id en type account voor stroom](./media/connection-dynamics365/flow-recordid-account.png)

In dit voorbeeld wordt de taak ook toegewezen aan een specifieke gebruiker op basis van de record-id van de gebruiker.

  ![Record-id en type gebruiker voor stroom](./media/connection-dynamics365/flow-recordid-user.png)

Zie [De record-id opzoeken](#find-the-records-id) verderop in dit onderwerp voor meer informatie over het opzoeken van record-id’s.

> **Belangrijk:** velden mogen geen waarde bevatten als ze de beschrijving Alleen voor intern gebruik hebben. Tot deze velden behoren **Afgelegd pad**, **Aanvullende parameters** en **Versienummer van tijdzoneregel**.
> 
> 

## <a name="find-the-records-id"></a>De record-id opzoeken
1. Open in de webtoepassing van Dynamics 365 een record, zoals een accountrecord.
2. Klik of tik op **Nieuw venster**
   ![record nieuw venster](./media/connection-dynamics365/popout.png) op de werkbalk Acties (of klik op of tik op **Een koppeling via e-mail verzenden** om de volledige URL naar uw standaard-e-mailprogramma te kopiëren).
   
    De URL in de adresbalk van de webbrowser bevat de record-id tussen de coderingstekens %7b en %7d.
   
   ![Record-id](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Verwante onderwerpen
[Problemen met een stroom oplossen](fix-flow-failures.md)

[Vragen en antwoorden over Flow in uw organisatie](organization-q-and-a.md)

[Veelgestelde vragen](frequently-asked-questions.md)

