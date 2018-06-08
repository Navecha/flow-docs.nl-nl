---
title: Wachten op goedkeuring in een stroom | Microsoft Docs
description: In Flow kan voordat een actie wordt uitgevoerd (bijvoorbeeld het verzenden van een melding over een beslissing), worden gewacht totdat een externe gebeurtenis plaatsvindt (bijvoorbeeld het goedkeuren of afwijzen van een wijziging door een gebruiker).
services: ''
suite: flow
documentationcenter: na
author: merwanhade
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
ms.author: merwanhade
ms.openlocfilehash: b75cacf14da7d1b339e8a2f9e35eece389c2a6f7
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "29563155"
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Wachten op goedkeuring in Microsoft Flow

> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


Maak een stroom waarmee een goedkeurings-e-mail wordt verzonden als u een item in SharePoint maakt en u vervolgens wordt geïnformeerd of het item is goedgekeurd of afgewezen. Als u deze zelfstudie exact wilt volgen, maakt u een eenvoudige SharePoint-lijst als een triggeractie. U kunt echter ook een andere gegevensbron gebruiken, zoals Dropbox of OneDrive.

**Vereisten**

* Maak een eenvoudige lijst in SharePoint met de naam **Projecttracker**, voeg een kolom met de naam **Titel** toe en voeg een kolom voor personen of groepen toe met de naam **Toegewezen aan**.

   ![Afbeelding van SPO-lijst Projecttracker](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Een gebeurtenis voor het activeren van de stroom toevoegen

1. Ga naar [Microsoft Flow](https://flow.microsoft.com), selecteer **Mijn stromen** op de navigatiebalk bovenaan en selecteer **Een volledig nieuwe stroom maken**.

1. Selecteer het vak **Honderden connectors en triggers doorzoeken**, voer een **nieuw item** in en navigeer vervolgens naar **SharePoint - Wanneer het item wordt gemaakt**.

1. Meld u aan bij SharePoint als u hierom wordt gevraagd.
1. Voer onder **Siteadres** de URL in van de SharePoint-site die uw lijst bevat.

1. Selecteer de lijst die u eerder hebt gemaakt onder **Lijstnaam**. Als u het voorbeeld uit deze zelfstudie volgt, is de naam **Projecttracker**.

    ![Afbeelding van SPO-lijstnaam](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>De resulterende actie toevoegen

1. Selecteer de knop **Nieuwe stap** en selecteer **Een actie toevoegen**.

1. Typ of plak in het vak **Alle connectors en acties doorzoeken** de tekst **e-mail verzenden** en selecteer vervolgens **Office 365 Outlook - Een e-mail verzenden met opties**.

1. Meld u aan bij Office 365 Outlook als u hierom wordt gevraagd.

1. Selecteer het veld **Aan** en selecteer vervolgens het token **E-mailadres Toegewezen aan**.

    De gebruiker in de kolom **Toegewezen aan** ontvangt de e-mail om items goed te keuren of af te wijzen. Wanneer u een item maakt om de stroom te testen, moet u uzelf in dit veld opgeven. Op deze manier kunt u het item niet alleen goedkeuren of afwijzen, maar ontvangt u ook de e-mailmelding.

    > [!NOTE]
    > U kunt de velden **Onderwerp** en **Gebruikersopties** aan uw wensen aanpassen.

    ![Afbeelding van veld Aan voor verzenden van goedkeurings-e-mail](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Een voorwaarde toevoegen

1. Selecteer de knop **Nieuwe stap** selecteer **Een voorwaarde toevoegen**.

    ![Afbeelding van Een voorwaarde toevoegen](./media/wait-for-approvals/add-a-condition.png)
1. Selecteer het eerste vak en selecteer vervolgens het token **Geselecteerde optie**.
1. Selecteer het laatste vak en typ **Goedkeuren**.

    ![Afbeelding van de voorwaardekaart](./media/wait-for-approvals/condition-card-2.png)

1. Selecteer **Een actie toevoegen** in het gebied **Indien ja**.

1. Typ of plak in het vak **Alle connectors en acties doorzoeken** de tekst **e-mail verzenden** en selecteer vervolgens **Office 365 Outlook - Een e-mail verzenden**.

1. Voer de ontvanger in het veld **Aan** in, zoals **E-mailadres Gemaakt door**.

1. Geef in het vak **Onderwerp** een onderwerp op.

    Selecteer bijvoorbeeld **Weergavenaam Toegewezen aan**, typ **heeft goedgekeurd** met een spatie aan het begin en het einde, en selecteer vervolgens **Titel**.

1. Geef in het vak **Hoofdtekst** de hoofdtekst van de e-mail op, zoals **Klaar voor volgende fase van project**.

    > [!NOTE]
    > De persoon die het item in de SharePoint-lijst heeft gemaakt, ontvangt een melding of het project is goedgekeurd of afgewezen.

    ![Afbeelding van Ja, e-mail verzenden](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. Herhaal de laatste vijf stappen in het gebied **Indien nee**, maar geef nu in de velden **Onderwerp** en **Hoofdtekst** aan dat het project is afgewezen.

     ![Afbeelding van Nee, e-mail verzenden](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Uw stroom voltooien en testen

1. Geef uw stroom een naam en selecteer vervolgens **Stroom maken**.

     ![Afbeelding van Stroom maken](./media/wait-for-approvals/create-flow.png)
1. Maak een item in uw SharePoint-lijst.

    Er wordt een goedkeurings-e-mail verzonden naar de ontvanger die u hebt opgegeven. Wanneer de ontvanger in die e-mail **Goedkeuren** of **Afwijzen** selecteert, ontvangt u een e-mail met het antwoord.

## <a name="learn-more"></a>Meer informatie

* [Scenario voor één goedkeurder bij moderne goedkeuringen](modern-approvals.md)
* [Sequentiële goedkeuringen](sequential-modern-approvals.md) maken
* [Parallelle goedkeuringen](parallel-modern-approvals.md) maken
* [Aanvragen onderweg](mobile-approvals.md) goedkeuren
