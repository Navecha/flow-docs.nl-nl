---
title: Taken automatiseren door een stroom te maken | Microsoft Docs
description: Maak een stroom waarmee automatisch een of meer acties worden uitgevoerd, zoals het verzenden van e-mail berichten, wanneer een gebruiker een rij toevoegt aan een share point-lijst.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/04/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 494a5f978b7792fa971a53cfda85addd9b78f929
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548311"
---
# <a name="create-a-flow-in-microsoft-flow"></a>Een stroom maken in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

Een stroom maken waarmee een of meer taken automatisch worden uitgevoerd nadat deze is geactiveerd door een gebeurtenis. U kunt bijvoorbeeld een stroom maken waarmee u per e-mail wordt gewaarschuwd wanneer iemand een Tweet verzendt met een tref woord dat u opgeeft. In dit voor beeld is het verzenden van een Tweet de gebeurtenis en het verzenden van e-mail de actie.

## <a name="prerequisites"></a>Vereisten

* Een account op [flow.Microsoft.com](https://flow.microsoft.com)
* Een Twitter-account
* Office 365-referenties

## <a name="specify-an-event-to-start-the-flow"></a>Geef een gebeurtenis op om de stroom te starten

Eerst moet u selecteren welke gebeurtenis, of *trigger*, de stroom start.

1. Selecteer in [flow.Microsoft.com](https://flow.microsoft.com) **mijn stromen** in de bovenste navigatie balk en selecteer vervolgens leeg item **maken**.

    ![De optie stromen in de linkernavigatiebalk](./media/get-started-logic-flow/create-logic-flow.png)
1. Selecteer het vak **honderden connectors en triggers zoeken** onder aan het scherm, geef **Twitter** op in het vak met de tekst **alle connectors en triggers doorzoeken**en selecteer vervolgens **Twitter-wanneer er een nieuwe tweet wordt geplaatst**.

    ![Twitter-gebeurtenis](./media/get-started-logic-flow/twitter-search.png)

1. Als u uw Twitter-account nog niet hebt verbonden met Microsoft Flow, selecteert u **Aanmelden bij Twitter**en geeft u uw referenties op.

1. Typ het tref woord dat u wilt zoeken in het tekstvak **zoeken** .

    ![Twitter-tref woord](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Een actie opgeven

1. Selecteer **nieuwe stap**en selecteer vervolgens **een actie toevoegen**.

    ![Actie toevoegen](./media/get-started-logic-flow/add-action-icon.png)

1. In het vak waarin **alle connectors en acties**worden weer gegeven, typt of plakt u **e-mail verzenden**en selecteert u vervolgens **Office 365 Outlook-een e-mail verzenden**.

    ![Lijst met acties](./media/get-started-logic-flow/send-email.png)

1. Als u hierom wordt gevraagd, selecteert u de knop aanmelden en geeft u uw referenties op.

1. In het formulier dat wordt weer gegeven, typt of plakt u uw e-mail adres in het vak **aan** en selecteert u uw naam in de lijst met contact personen die wordt weer gegeven.

    ![Leeg e-mail bericht](./media/get-started-logic-flow/blank-email.png)
1. Typ of plak in het vak **onderwerp** **nieuwe Tweet van:** en typ een spatie.

    ![Onderwerpregel met tijdelijke aanduiding](./media/get-started-logic-flow/message-token.png)
1. Selecteer in de lijst met tokens het **getweet per** token om een tijdelijke aanduiding voor de sleutel toe te voegen.

    ![Para meter toevoegen](./media/get-started-logic-flow/add-parameter.png)
1. Selecteer het vak **hoofd** tekst en selecteer vervolgens het token **tweet text** om een tijdelijke aanduiding voor de tekst toe te voegen.
1. Beschrijving Voeg meer tokens, andere inhoud of beide toe aan de hoofd tekst van het e-mail bericht.
1. Geef de stroom aan de bovenkant van het scherm en selecteer vervolgens **stroom maken**.

    ![Selecteer de knop stroom maken](./media/get-started-logic-flow/create-button.png)
1. Selecteer **gereed** om de lijst met stromen bij te werken.

     ![Selecteer de knop gereed](./media/get-started-logic-flow/done-button.png)
1. Verzend een tweet met het tref woord dat u hebt opgegeven of wacht tot iemand anders een dergelijke tweet post.

     Binnen een minuut nadat de Tweet is gepost, ontvangt u een e-mail bericht van de nieuwe Tweet.

> [!TIP]
> Gebruik de actie **E-mail verzenden (v2)** voor het opmaken van e-mail waarin u het letter type aanpast, vet, cursief of onderstreept, de kleur aanpassen en markeren, en lijsten of koppelingen maken, en meer.

![E-mail met uitgebreide bewerkingen](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>Een stroom beheren

1. Selecteer in [flow.Microsoft.com](https://flow.microsoft.com) **mijn stromen** in de bovenste navigatie balk.
1. Ga op een van de volgende manieren te werk in de lijst met stromen:

   * Als u een stroom wilt onderbreken, stelt u de wissel knop in op **uit**.

       ![Stroom onderbreken](./media/get-started-logic-flow/pause-flow.png)
   * Als u een stroom wilt hervatten, stelt u de wissel knop **in op**aan.

       ![Stroom hervatten](./media/get-started-logic-flow/resume-flow.png)
   * Als u een stroom wilt bewerken, selecteert u het potlood pictogram dat overeenkomt met de stroom die u wilt bewerken.

       ![Stroom selecteren](./media/get-started-logic-flow/select-flow.png)
   * Als u een stroom wilt verwijderen, selecteert u het pictogram **...** , selecteert u **verwijderen**en selecteert u **verwijderen** in het bericht venster dat wordt weer gegeven.

       ![Pictogram verwijderen](./media/get-started-logic-flow/delete-icon.png)
   * Als u de uitvoerings geschiedenis van een stroom wilt weer geven, selecteert u de stroom op de pagina **mijn stromen** en bekijkt u de geschiedenis in het gedeelte **uitvoerings geschiedenis** van de pagina die wordt geopend.

       ![uitvoerings geschiedenis](./media/get-started-logic-flow/run-history.png)

     Selecteer een stroom uitvoering in de lijst met uitvoeringen om de invoer en uitvoer van elke stap weer te geven.

> [!NOTE]
> Uw account kan Maxi maal 600 stromen bevatten. Als u al 600 stromen hebt, moet u er een verwijderen voordat u een andere stroom maakt.
>
>

## <a name="next-steps"></a>Volgende stappen

* [Voeg stappen toe](multi-step-logic-flow.md), zoals verschillende manieren om op de hoogte te worden gesteld, aan uw stroom.
* [Voer taken uit volgens een planning](run-scheduled-tasks.md), wanneer u een actie dagelijks, op een bepaalde datum of na een bepaald aantal minuten wilt uitvoeren.
* [Voeg een stroom toe aan een app](https://powerapps.microsoft.com/tutorials/using-logic-flows/) om de logica van de app in de cloud te laten starten.
* Aan de [slag met team stromen](create-team-flows.md) en anderen uitnodigen om samen met u stromen te ontwerpen.
