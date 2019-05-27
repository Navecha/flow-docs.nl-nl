---
title: Een stroom maken om taken te automatiseren | Microsoft Docs
description: U kunt een stroom maken waarmee automatisch een of meer acties (bijvoorbeeld het verzenden van een e-mail) worden uitgevoerd wanneer een gebeurtenis plaatsvindt (bijvoorbeeld wanneer iemand een rij toevoegt aan een SharePoint-lijst).
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/28/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4ea24ed12ab12d2d52502477cdb7a4a9eb822076
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64992580"
---
# <a name="create-a-flow-in-microsoft-flow"></a>Een stroom maken in Microsoft Flow

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

U kunt een stroom maken om een of meer taken automatisch uit te voeren nadat de stroom door een bepaalde trigger is geactiveerd. U kunt bijvoorbeeld een stroom maken waarmee u per e-mail wordt gewaarschuwd wanneer iemand een tweet verstuurt met daarin een trefwoord dat u opgeeft. In dit voorbeeld is het verzenden van de tweet de gebeurtenis en is het verzenden van de e-mail de actie.

## <a name="prerequisites"></a>Vereisten

* Een account op [flow.microsoft.com](https://flow.microsoft.com)
* Een Twitter-account
* Office 365-referenties

## <a name="specify-an-event-to-start-the-flow"></a>Een gebeurtenis opgeven voor het starten van de stroom

Eerst moet u selecteren door welke gebeurtenis, of *trigger*, de stroom wordt geactiveerd.

1. Ga naar [flow.microsoft.com](https://flow.microsoft.com), selecteer **Mijn stromen** op de navigatiebalk bovenaan en selecteer **Een volledig nieuwe stroom maken**.

    ![De optie Stromen in de linkernavigatiebalk](./media/get-started-logic-flow/create-logic-flow.png)
1. Selecteer het vak **Honderden connectors en triggers doorzoeken** aan de onderkant van het scherm, voer **Twitter** in het vak met de tekst **Alle connectors en triggers doorzoeken** in en selecteer vervolgens **Twitter - Wanneer een nieuwe tweet wordt gepost**.

    ![Twitter-gebeurtenis](./media/get-started-logic-flow/twitter-search.png)

1. Als u uw Twitter-account nog niet met Microsoft Flow hebt verbonden, selecteert u **Aanmelden bij Twitter** en geeft u uw referenties op.

1. Typ in het vak **Zoektekst** het trefwoord dat u wilt zoeken.

    ![Twitter-trefwoord](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Een actie opgeven

1. Selecteer de knop **Nieuwe stap** en vervolgens **Een actie toevoegen**.

    ![Actie toevoegen](./media/get-started-logic-flow/add-action-icon.png)

1. Typ of plak in het vak **Alle connectors en acties doorzoeken** de tekst **e-mail verzenden** en selecteer vervolgens **Office 365 Outlook - Een e-mail verzenden**.

    ![Lijst met acties](./media/get-started-logic-flow/send-email.png)

1. Klik op de knop Aanmelden als u hierom wordt gevraagd en geef uw referenties op.

1. Typt of plak uw e-mailadres in het vak **Aan** van het formulier dat verschijnt en selecteer vervolgens uw naam in de lijst met contactpersonen die wordt weergegeven.

    ![Leeg e-mailbericht](./media/get-started-logic-flow/blank-email.png)
1. Typ of plak in het vak **Onderwerp** de tekst **Nieuwe tweet van:** en typ vervolgens een spatie.

    ![Onderwerpregel met tijdelijke aanduiding](./media/get-started-logic-flow/message-token.png)
1. Selecteer **Getweet door** in de lijst met parameters om een tijdelijke aanduiding voor de tweet toe te voegen.

    ![Parameter toevoegen](./media/get-started-logic-flow/add-parameter.png)
1. Selecteer het vak **Hoofdtekst** en selecteer het token **Tekst van tweet** om een tijdelijke aanduiding voor de tekst van de tweet toe te voegen.
1. (optioneel) Voeg meer tokens, andere inhoud of beide toe aan de hoofdtekst van het e-mailbericht.
1. Ga naar de bovenkant van het scherm en geef uw stroom een naam. Selecteer vervolgens **Stroom maken**.

    ![Selecteer de knop Stroom maken](./media/get-started-logic-flow/create-button.png)
1. Selecteer **Gereed** om de lijst met stromen bij te werken.

     ![De knop Gereed selecteren](./media/get-started-logic-flow/done-button.png)
1. Verzend een tweet met het trefwoord dat u hebt opgegeven of wacht totdat iemand anders een tweet met het trefwoord post.

     Binnen een minuut na het posten van de tweet wordt u via een e-mailbericht op de hoogte gebracht van de nieuwe tweet.

> [!TIP]
> Gebruik de **e-mail verzenden (V2)** actie om de opmaak van e-mailadres waarop u het lettertype, gebruik vet, cursief of onderstreping aanpassen de kleur aanpassen en markeren en maak lijsten of koppelingen en meer.

![Uitgebreide bewerken e-mail](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>Een stroom beheren

1. Ga naar [flow.microsoft.com](https://flow.microsoft.com) en selecteer **Mijn stromen** op de navigatiebalk bovenin.
1. Ga op een van de volgende manieren te werk in de lijst met stromen:

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

> [!NOTE]
> Uw account kan maximaal vijftig stromen bevatten. Als u al vijftig stromen hebt en u een nieuwe stroom wilt maken, moet u eerst een stroom verwijderen.
>
>

## <a name="next-steps"></a>Volgende stappen

* [Voeg stappen toe](multi-step-logic-flow.md) aan de stroom, bijvoorbeeld verschillende manieren om te worden gewaarschuwd.
* [Voer taken uit op basis van een schema](run-scheduled-tasks.md) wanneer u een actie dagelijks, op een bepaalde datum of na een bepaald aantal minuten wilt uitvoeren.
* [Voeg een stroom aan een app toe](https://powerapps.microsoft.com/tutorials/using-logic-flows/) om toe te staan dat de app een bepaalde logica in de cloud kan starten.
* [Ga aan de slag met teamstromen](create-team-flows.md) en nodig anderen uit om samen met u stromen te ontwerpen.
