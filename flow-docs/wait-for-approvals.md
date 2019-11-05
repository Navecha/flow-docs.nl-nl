---
title: Wachten op goed keuring in een stroom | Microsoft Docs
description: Stromen kunnen wachten tot een externe gebeurtenis plaatsvindt, zoals het goed keuren of afwijzen van een wijziging voordat een actie wordt uitgevoerd, zoals het verzenden van een melding van de beslissing.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ea6be2d1deae080df58afd94c1f1e8d0c13c9fcd
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548360"
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Wachten op goed keuring in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


Maak een stroom die, als u een item in share point maakt, een goedkeurings-e-mail verzendt en vervolgens wordt gewaarschuwd of het item is goedgekeurd of afgewezen. Als u deze zelf studie exact wilt volgen, maakt u een eenvoudige share point-lijst als trigger actie, maar u kunt een andere gegevens bron gebruiken, zoals Dropbox of OneDrive.

**Vereisten**

* Maak een eenvoudige share point-lijst met de naam **project vastleggen**, voeg een kolom toe met de naam **titel**en voeg vervolgens een kolom persoon of groep toe met de naam **toegewezen aan**.

   ![Afbeelding van de lijst SPO van project vastleggen](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Een gebeurtenis toevoegen om de stroom te activeren

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com), selecteer **mijn stromen** in de bovenste navigatie balk en selecteer vervolgens **leeg item maken**.

1. Schakel het selectie vakje **honderden connectors en triggers zoeken** in, Voer **Nieuw item**in en navigeer naar **share point-wanneer een item is gemaakt**.

1. Meld u aan bij share point als u hierom wordt gevraagd.
1. Voer onder **site adres**de URL in van de share point-site die uw lijst bevat.

1. Selecteer onder **lijst naam**de lijst die u eerder hebt gemaakt. Als u de volgende stap uitvoert, is de naam **project vastleggen**.

    ![Afbeelding van SPO-lijst naam](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>De resulterende actie toevoegen

1. Selecteer de knop **nieuwe stap** en selecteer vervolgens **een actie toevoegen.**

1. Typ of plak in het vak **alle connectors en acties doorzoeken** de tekst **e-mail verzenden**en selecteer vervolgens **Office 365 Outlook-e-mail verzenden met opties**.

1. Meld u aan bij Office 365 Outlook als u hierom wordt gevraagd.

1. Selecteer het veld **aan** en selecteer vervolgens het token **toegewezen aan e-mail adres** .

    De gebruiker in de kolom **toegewezen aan** ontvangt het e-mail bericht voor het goed keuren of afwijzen van items. Wanneer u een item maakt om de stroom te testen, moet u uzelf in dit veld opgeven. Op die manier kunt u het item niet alleen goed keuren of afwijzen, maar ontvangt u ook de e-mail melding.

    > [!NOTE]
    > U kunt de velden **onderwerp** en **gebruikers opties** aanpassen aan uw behoeften.

    ![Afbeelding van e-mail goed keuren naar veld verzenden](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Een voor waarde toevoegen

1. Selecteer de knop **nieuwe stap** en selecteer vervolgens **een voor waarde toevoegen**.

    ![Afbeelding van een voor waarde toevoegen](./media/wait-for-approvals/add-a-condition.png)
1. Selecteer het eerste vak en selecteer vervolgens het **token** -token.
1. Selecteer het laatste vak en typ **goed keuren**.

    ![Afbeelding van de kaart voor waarde](./media/wait-for-approvals/condition-card-2.png)

1. Selecteer **een actie toevoegen**in het gedeelte **Indien ja** .

1. Typ of plak in het vak **alle connectors en acties doorzoeken** de tekst **e-mail verzenden**en selecteer vervolgens **Office 365 Outlook-een e-mail verzenden**.

1. Voer een ontvanger in het veld **aan** in, zoals **gemaakt per e-mail**.

1. Geef een onderwerp op in het vak **onderwerp** .

    Selecteer bijvoorbeeld **toegewezen aan DisplayName**, het type **is goedgekeurd** met een spatie aan elke kant en selecteer vervolgens **titel**.

1. Geef in het vak **hoofd tekst** een e-mail bericht **op, bijvoorbeeld gereed om door te gaan met de volgende fase van het project.**

    > [!NOTE]
    > De persoon die het item in de share point-lijst heeft gemaakt, wordt gewaarschuwd of het project is goedgekeurd of afgewezen.

    ![Afbeelding van Ja, e-mail verzenden](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. Herhaal de laatste vijf stappen in het gebied **Indien nee** , behalve het **onderwerp** en de **hoofd tekst** wijzigen om aan te geven dat het project is afgewezen.

     ![Afbeelding van Nee, e-mail verzenden](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Uw stroom volt ooien en testen

1. Geef uw stroom een naam en selecteer vervolgens **stroom maken**.

     ![Afbeelding van Create-flow](./media/wait-for-approvals/create-flow.png)
1. Maak een item in uw share point-lijst.

    Er wordt een goedkeurings-e-mail verzonden naar de ontvanger die u hebt opgegeven. Wanneer de ontvanger in die e-mail **goed keuren** of **afwijzen** selecteert, ontvangt u een e-mail bericht dat het antwoord aangeeft.

## <a name="learn-more"></a>Meer informatie

* [Overzicht van de moderne goed keuringen voor één goed keurder](modern-approvals.md)
* [Sequentiële goed keuringen](sequential-modern-approvals.md) maken
* [Parallelle goed keuringen](parallel-modern-approvals.md) maken
* [Aanvragen](mobile-approvals.md) onderweg goed keuren
