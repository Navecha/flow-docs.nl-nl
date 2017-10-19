---
title: Een stroom maken om taken te automatiseren | Microsoft Docs
description: U kunt een stroom maken om automatisch een of meer acties (bijvoorbeeld het verzenden van een e-mail) uit te voeren wanneer een gebeurtenis plaatsvindt (bijvoorbeeld wanneer iemand een rij toevoegt aan een SharePoint-lijst).
services: 
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/28/2017
ms.author: deonhe
ms.openlocfilehash: fd6ed3973ed09442108bf780f76b750deea20eeb
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-in-microsoft-flow"></a>Een stroom maken in Microsoft Flow
<iframe width="560" height="315" src="https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

U kunt een stroom maken om een of meer taken automatisch uit te voeren nadat de stroom door een bepaalde trigger is geactiveerd. U kunt bijvoorbeeld een stroom maken waarmee u per e-mail wordt gewaarschuwd wanneer iemand een tweet verstuurt met daarin een trefwoord dat u opgeeft. In dit voorbeeld is het verzenden van de tweet de gebeurtenis en is het verzenden van de e-mail de actie.

## <a name="prerequisites"></a>Vereisten
* Een account op [flow.microsoft.com](https://flow.microsoft.com)
* Een Twitter-account
* Office 365-referenties

## <a name="specify-an-event-to-start-the-flow"></a>Een gebeurtenis opgeven voor het starten van de stroom
Eerst moet u selecteren door welke gebeurtenis, of *trigger*, de stroom wordt geactiveerd.

1. Ga naar [flow.microsoft.com](https://flow.microsoft.com), selecteer **Mijn stromen** op de navigatiebalk bovenaan en selecteer **Een volledig nieuwe stroom maken**.
   
    ![De optie Stromen in de linkernavigatiebalk](./media/get-started-logic-flow/create-logic-flow.png)
2. Typ of plak in het vak **Alle connectors en triggers doorzoeken** de tekst **Twitter** en selecteer vervolgens **Twitter - Wanneer er een nieuwe tweet wordt geplaatst**.
   
    ![Twitter-gebeurtenis](./media/get-started-logic-flow/twitter-search.png)
3. Als u uw Twitter-account nog niet met Microsoft Flow hebt verbonden, selecteert u **Aanmelden bij Twitter** en geeft u uw referenties op.
   
    ![Aanmelden bij Twitter](./media/get-started-logic-flow/twitter-signin.png)
4. Typ in het vak **Zoektekst** het trefwoord dat u wilt zoeken.
   
    ![Twitter-trefwoord](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Een actie opgeven
1. Selecteer de knop **Nieuwe stap** en vervolgens **Een actie toevoegen**.
   
    ![Actie toevoegen](./media/get-started-logic-flow/add-action-icon.png)
2. Typ of plak in het vak **Alle connectors en acties doorzoeken** de tekst **e-mail verzenden** en selecteer vervolgens **Office 365 Outlook - Een e-mail verzenden**.
   
    ![Lijst met acties](./media/get-started-logic-flow/send-email.png)
3. Klik op de knop Aanmelden als u hierom wordt gevraagd en geef uw referenties op.
4. Typt of plak uw e-mailadres in het vak **Aan** van het formulier dat verschijnt en selecteer vervolgens uw naam in de lijst met contactpersonen die wordt weergegeven.
   
    ![Leeg e-mailbericht](./media/get-started-logic-flow/blank-email.png)
5. Typ of plak in het vak **Onderwerp** de tekst **Nieuwe tweet van:** en typ vervolgens een spatie.
   
    ![Onderwerpregel met tijdelijke aanduiding](./media/get-started-logic-flow/message-token.png)
6. Selecteer **Getweet door** in de lijst met parameters om een tijdelijke aanduiding voor de tweet toe te voegen.
   
    ![Parameter toevoegen](./media/get-started-logic-flow/add-parameter.png)
7. Klik of tik in het vak **Hoofdtekst** en klik of tik op het token **Tekst van tweet** om een tijdelijke aanduiding voor de tekst van de tweet toe te voegen.
8. (optioneel) Voeg meer tokens, andere inhoud of beide toe aan de hoofdtekst van het e-mailbericht.
9. Ga naar de bovenkant van het scherm en geef uw stroom een naam. Selecteer vervolgens **Stroom maken**.
   
    ![Selecteer de knop Stroom maken](./media/get-started-logic-flow/create-button.png)
10. Selecteer **Gereed** om de lijst met uw stromen bij te werken.
    
     ![De knop Gereed selecteren](./media/get-started-logic-flow/done-button.png)
11. Verzend een tweet met het opgegeven trefwoord.
    
     Binnen een minuut wordt u via een e-mailbericht op de hoogte gebracht van de nieuwe tweet.

## <a name="manage-a-flow"></a>Een stroom beheren
1. Ga naar [flow.microsoft.com](https://flow.microsoft.com) en selecteer **Mijn stromen** in de navigatiebalk bovenin.
2. Ga op een van de volgende manieren te werk in de lijst met stromen:
   
   * Als u een stroom wilt onderbreken, zet u de wisselknop op **Uit**.
     
       ![Stroom onderbreken](./media/get-started-logic-flow/pause-flow.png)
   * Als u een stroom wilt hervatten, zet u de wisselknop op **Aan**.
     
       ![Stroom hervatten](./media/get-started-logic-flow/resume-flow.png)
   * Als u een stroom wilt bewerken, selecteert u het potloodpictogram bij de stroom die u wilt bewerken.
     
       ![Stroom selecteren](./media/get-started-logic-flow/select-flow.png)
   * Als u een stroom wilt verwijderen, selecteert u het pictogram **...** , selecteert u **Verwijderen** en selecteert u ten slotte **Verwijderen** in het bericht dat wordt weergegeven.
     
       ![Pictogram Verwijderen](./media/get-started-logic-flow/delete-icon.png)
   * Als u de uitvoeringsgeschiedenis van een stroom wilt weergeven, selecteert u de stroom op de pagina **Mijn stromen** en bekijkt u de geschiedenis in de sectie **Uitvoeringsgeschiedenis** op de pagina die wordt geopend.
     
       ![uitvoeringsgeschiedenis](./media/get-started-logic-flow/run-history.png)
     
     Selecteer een stroomuitvoering in de lijst met uitvoeringen om de invoer en uitvoer van elke stap weer te geven.

**Opmerking**: Uw account kan maximaal vijftig stromen bevatten. Als u al vijftig stromen hebt en u een nieuwe stroom wilt maken, moet u eerst een stroom verwijderen.

## <a name="next-steps"></a>Volgende stappen
* [Voeg stappen toe](multi-step-logic-flow.md) aan de stroom, bijvoorbeeld verschillende manieren om te worden gewaarschuwd.
* [Voer taken uit op basis van een schema](run-tasks-on-a-schedule.md) wanneer u een actie dagelijks, op een bepaalde datum of na een bepaald aantal minuten wilt uitvoeren.
* [Voeg een stroom aan een app toe](https://powerapps.microsoft.com/tutorials/using-logic-flows/) om toe te staan dat de app een bepaalde logica in de cloud kan starten.
* [Ga aan de slag met teamstromen](create-team-flows.md) en nodig anderen uit om samen met u stromen te ontwerpen.

