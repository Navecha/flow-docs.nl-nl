---
title: Gebruik de Toep assen op elke actie om een matrix met items te door lopen. | Microsoft Docs
description: Gebruik Microsoft Flow om een matrix met items te door lopen om meerdere voor waarden te controleren en acties uit te voeren op basis van deze voor waarden.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/16/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e2852de959f62d5c0ee76fabc9841e3fc9663f73
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546008"
---
# <a name="use-the-apply-to-each-action-in-microsoft-flow-to-process-a-list-of-items-periodically"></a>Gebruik de actie Toep assen op elke bewerking in Microsoft Flow om regel matig een lijst met items te verwerken
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Veel triggers kunnen onmiddellijk een stroom starten op basis van een gebeurtenis, bijvoorbeeld wanneer er een nieuwe e-mail binnenkomt in uw postvak in. Deze triggers zijn geweldig, maar soms wilt u een stroom uitvoeren die een query uitvoert op een gegevens bron volgens een vooraf gedefinieerd schema, waarbij bepaalde acties worden uitgevoerd op basis van de eigenschappen van de items in de gegevens bron. Hiervoor kan uw stroom worden gestart volgens een schema (bijvoorbeeld eenmaal per dag) en moet er een lus worden gebruikt, zoals **Toep assen op elk** item om een lijst met items te verwerken. U kunt bijvoorbeeld **Toep assen op elke** record gebruiken om records uit een Data Base of lijst met items van micro soft share point bij te werken.

In dit overzicht maken we een stroom die elke 15 minuten wordt uitgevoerd en doet het volgende:

1. Hiermee worden de laatste 10 ongelezen berichten in het postvak in van Office 365 Outlook opgehaald.
2. Controleert elk van de 10 berichten om te bevestigen of er **nu aan wordt voldaan** in het onderwerp.
3. Controleert of het e-mail bericht afkomstig is van uw chef of is verzonden met een hoge urgentie.
4. Hiermee verzendt u een push melding en markeert u een e-mail bericht dat op dit **moment aan** het onderwerp is gekoppeld. het certificaat is afkomstig van uw chef of is met hoge urgentie verzonden.

In dit diagram ziet u de details van de stroom die we in deze procedure gaan maken:

![overzicht van de stroom die wordt gebouwd](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Vereisten
Hier volgen de vereisten voor het uitvoeren van de stappen in deze procedure:

* Een account dat is geregistreerd voor gebruik van [Microsoft flow](https://flow.microsoft.com).
* Een Office 365 Outlook-account.
* De mobiele app Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [IOS](https://aka.ms/flowmobiledocsios)of [Windows Phone](https://aka.ms/flowmobilewindows).
* Verbindingen met Office 365 Outlook en de Push Notification Service.

## <a name="create-a-flow"></a>Een stroom maken
1. Aanmelden bij [Microsoft flow](https://flow.microsoft.com):
2. Selecteer het tabblad **mijn stromen** en maak een stroom op basis van een leeg:
   
    ![leeg item maken](./media/apply-to-each/foreach-1.png)
3. Voer ' schema ' in het zoekvak in om te zoeken naar alle services en triggers die zijn gerelateerd aan de planning.
4. Selecteer de trigger **schema-terugkeer patroon** om aan te geven dat de stroom wordt uitgevoerd volgens een planning die u vervolgens volgende kunt opgeven:
   
    ![terugkerende actie plannen](./media/apply-to-each/foreach-2.png)
5. Stel in dat het schema om de 15 minuten wordt uitgevoerd:
   
    ![plannings uitvoeringen](./media/apply-to-each/foreach-3.png)
6. Selecteer **+ nieuwe stap**, **Voeg een actie toe**en typ **Outlook** in het zoekvak om te zoeken naar alle acties met betrekking tot micro soft Outlook.
7. Selecteer de actie **Office 365 Outlook-E-mails ophalen** :
   
    ![Selecteer de actie e-mails ophalen](./media/apply-to-each/foreach-4.png)
8. Hiermee opent u de kaart **E-mails ophalen** . Configureer de kaart **E-mails ophalen** om de Top 10 ongelezen e-mail berichten in de map Postvak in te selecteren. Voeg geen bijlagen toe omdat deze niet in de stroom worden gebruikt:
   
    ![e-mail kaart configureren](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Tot nu toe hebt u een eenvoudige stroom gemaakt waarmee e-mail berichten van uw postvak in worden opgehaald. Deze e-mail berichten worden in een matrix geretourneerd. **voor de Toep assen op elke** actie is een matrix vereist. Dit is dus precies wat er nodig is.
   > 
   > 

## <a name="add-actions-and-conditions"></a>Acties en voor waarden toevoegen
1. Selecteer **+ nieuwe stap**, **meer**en voeg vervolgens **een Toep assen op elke actie toe** :
   
    ![Selecteer Toep assen op elke](./media/apply-to-each/foreach-6.png)
2. Plaats het token **Body** in het vak **Selecteer een uitvoer van de vorige stappen** op de kaart op elk van **toepassing** . Dit wordt opgehaald uit de hoofd tekst van de e-mail berichten die moeten worden gebruikt in de sectie **Toep assen op elke** actie:
   
    ![hoofdtekst token toevoegen](./media/apply-to-each/foreach-7.png)
3. Selecteer **een voor waarde toevoegen**:
   
    ![Voor waarde toevoegen](./media/apply-to-each/foreach-8.png)
4. Configureer de **voorwaarde** kaart om het onderwerp van elke e-mail te doorzoeken op de woorden ' nu verg aderen ':
   
   * Voeg het token **onderwerp** in het vak **object naam** in.
   * Selecteer **bevat** in de lijst **relatie** .
   * Voer **nu verg aderen** in het vak **waarde** in.
     
     ![voor waarde configureren](./media/apply-to-each/foreach-subject-condition.png)
5. Selecteer **meer**en selecteer vervolgens **een voor waarde toevoegen** van de vertakking **Indien ja, niets doen** . Hiermee opent u de kaart **voor waarde 2** . Configureer deze kaart als volgt:
   
   * Voeg het **urgentie** token in het vak **object naam** in.
   * Select **is gelijk aan** in de lijst **relatie** .
   * Voer **hoog** in het vak **waarde** in.
     
     ![Voor waarde toevoegen](./media/apply-to-each/foreach-importance-condition.png)
6. Selecteer **een actie toevoegen** in het gedeelte **Indien ja, niets doen** . Hiermee opent u de kaart **een actie kiezen** , waar u kunt bepalen wat er moet gebeuren als de zoek voorwaarde (de e-mail met de status **nu aan** de slag is verzonden met hoge urgentie) waar is:
   
    ![Actie toevoegen](./media/apply-to-each/foreach-9.png)
7. Zoek naar **melding**en selecteer vervolgens de actie **meldingen-ik wil een mobiele melding ontvangen** :
   
    ![Seach en selecteer een melding](./media/apply-to-each/foreach-10.png)
8. Geef op de kaart **Ik wil een mobiele melding verzenden** de details op voor de push melding die wordt verzonden als het onderwerp van een e-mail bericht ' nu verg aderen ' bevat en selecteer vervolgens **een actie toevoegen**:
   
    ![Melding configureren](./media/apply-to-each/foreach-11.png)
9. Voer **lezen** in als zoek term en selecteer vervolgens de actie **Office 365 Outlook-markeren als gelezen** . Hiermee wordt elke e-mail gemarkeerd als gelezen nadat de push melding is verzonden:
   
    ![de actie markeren als gelezen toevoegen](./media/apply-to-each/foreach-12.png)
10. Voeg het token **bericht-id** toe aan het vak **bericht-id** van de kaart **markeren als gelezen** . U moet mogelijk **meer weer geven** selecteren om het token **bericht-id** te vinden. Hiermee wordt de id aangegeven van het bericht dat als gelezen wordt gemarkeerd:
    
     ![bericht-id toevoegen](./media/apply-to-each/foreach-13.png)
11. Ga terug naar de kaart **voor waarde 2** , op de vertakking **Indien nee, niets doen** :
    
    * Selecteer **een actie toevoegen**en typ vervolgens **Manager ophalen** in het zoekvak.
    * Selecteer de actie **Office 365-gebruikers-manager ophalen** in de lijst met zoek resultaten.
    * Voer uw *volledige* e-mail adres in het vak **gebruiker** van de kaart **Manager ophalen** in.
      
      ![actie Get Manager toevoegen en configureren](./media/apply-to-each/foreach-get-manager.png)
12. Selecteer **meer**en selecteer vervolgens **een voor waarde toevoegen** van de vertakking **Indien nee** . Hiermee opent u de kaart **voor waarde 3** . Configureer de kaart om te controleren of het e-mail adres van de afzender van de e-mail (het token van) gelijk is aan het e-mail adres van uw chef (het e-mail token):
    
    * Voeg het **from** -token in het vak **object naam** in.
    * Selecteer **bevat** in de lijst **relatie** .
    * Voer een **e-mail** token in het vak **waarde** in.
      
      ![Zoek voorwaarde configureren](./media/apply-to-each/foreach-condition3-card.png)
13. Selecteer **een actie toevoegen** in het gedeelte **Indien ja, niets doen** van de kaart **voor waarde 3** . Hiermee opent u de kaart **als ja** , waar u kunt bepalen wat er moet gebeuren als de zoek voorwaarde (de e-mail is verzonden door uw chef) waar is:
    
     ![voor waarde configureren](./media/apply-to-each/foreah-condition3-add-action.png)
14. Zoek naar **melding**en selecteer vervolgens de actie **meldingen-ik wil een mobiele melding ontvangen** :
    
     ![zoeken naar meldings actie](./media/apply-to-each/foreach-10.png)
15. Geef op de kaart **Ik wil een mobiele melding 2 ontvangen** de details op voor de push melding die wordt verzonden als de e-mail afkomstig is van uw chef en selecteer vervolgens **een actie toevoegen**:
    
     ![meldingen kaart configureren](./media/apply-to-each/foreach-boss-notification.png)
16. Voeg de **Office 365 Outlook-markering als Lees** actie toe. Hiermee wordt elke e-mail gemarkeerd als gelezen nadat de push melding is verzonden:
    
     ![de actie markeren als gelezen toevoegen](./media/apply-to-each/foreach-12.png)
17. Voeg het token **bericht-id** toe aan de kaart **markeren als gelezen 2** . U moet mogelijk **meer weer geven** selecteren om het token **bericht-id** te vinden. Hiermee wordt de id aangegeven van het bericht dat als gelezen wordt gemarkeerd:
    
     ![de actie markeren als gelezen configureren](./media/apply-to-each/foreach-mark-as-read2.png)
18. Geef uw stroom een naam en maak deze vervolgens:
    
     ![Geef uw stroom een naam en sla deze op](./media/apply-to-each/foreach-14.png)

Als u de vervolg actie hebt gevolgd, moet uw stroom er ongeveer als volgt uitzien:

![overzicht van de stroom die is gemaakt](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>De stroom uitvoeren
1. Stuur uzelf een e-mail bericht met een hoge prioriteit die **nu aan** het onderwerp is voldaan (of dat iemand in uw organisatie u een dergelijk e-mail bericht moet sturen).
2. Bevestig dat het e-mail bericht zich in uw postvak in bevindt en niet is gelezen.
3. Meld u aan bij Microsoft Flow, selecteer **mijn stromen**en selecteer **nu uitvoeren**:
   
    ![nu uitvoeren](./media/apply-to-each/foreach-run-1.png)
4. Selecteer **stroom uitvoeren** om te bevestigen dat u de stroom echt wilt uitvoeren:
   
    ![uitvoering bevestigen](./media/apply-to-each/foreach-run-2.png)
5. Na enkele ogen blikken ziet u de resultaten van de geslaagde uitvoering:
   
    ![resultaten uitvoeren](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Resultaten van de uitvoering weer geven
Nu u de stroom hebt uitgevoerd, ontvangt u een push melding op uw mobiele apparaat.

1. Open de Microsoft Flow-app op uw mobiele apparaat en selecteer vervolgens het tabblad **activiteit** . U ziet de push melding over de vergadering:
   
    ![het tabblad activiteit selecteren](./media/apply-to-each/foreach-notification-1.png)
2. Als u de volledige inhoud van de melding wilt weer geven, moet u de melding mogelijk selecteren. De volledige melding ziet er ongeveer als volgt uit:
   
    ![Details van melding](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > Als u het push bericht niet ontvangt, controleert u of het mobiele apparaat een werkende gegevens verbinding heeft.
   > 
   > 

