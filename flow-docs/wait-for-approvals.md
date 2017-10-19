---
title: Wachten op goedkeuring in een stroom | Microsoft Docs
description: In Flow kan voordat een actie wordt uitgevoerd (bijvoorbeeld het verzenden van een melding over een beslissing), worden gewacht totdat een externe gebeurtenis plaatsvindt (bijvoorbeeld het goedkeuren of afwijzen van een wijziging door een gebruiker).
services: 
suite: flow
documentationcenter: na
author: merwanhade
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/24/2016
ms.author: merwanhade
ms.openlocfilehash: a26566486cf6310dc1c33ef226bfc37b30a5ad16
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Wachten op goedkeuring in Microsoft Flow
<iframe width="560" height="315" src="https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

Maak een stroom waarmee, als u een item in SharePoint maakt, een goedkeurings-e-mail wordt verzonden en u vervolgens wordt geïnformeerd of het item is goedgekeurd of afgewezen. Als u deze zelfstudie exact wilt volgen, maakt u een eenvoudige SharePoint-lijst als een triggeractie. U kunt echter ook een andere gegevensbron gebruiken, zoals Dropbox of OneDrive.

**Vereisten**

* Maak een eenvoudige lijst in SharePoint Online met de naam **Projecttracker** met een kolom met de naam **Titel** en voeg een kolom voor personen of groepen toe met de naam **Toegewezen aan**.
  
   ![Afbeelding van SPO-lijst Projecttracker](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Een gebeurtenis voor het activeren van de stroom toevoegen
1. Ga naar [flow.microsoft.com](https://flow.microsoft.com), selecteer **Mijn stromen** in de navigatiebalk bovenin en selecteer **Nieuwe stroom maken**.
   
    ![Afbeelding van het maken van een nieuwe stroom](./media/wait-for-approvals/create-a-new-flow.png)
2. Typ of plak **nieuw item** in het vak met de tekst **Hoe wilt u beginnen?** en selecteer **SharePoint Online - wanneer een nieuw item wordt gemaakt**.
   
    ![Afbeelding van SPO-trigger](./media/wait-for-approvals/send-approval-email-select-2.png)
3. Meld u aan bij SharePoint Online als u hierom wordt gevraagd.
4. Typ of plak de URL van de site met de lijst onder **URL van de site**.
   
    ![Afbeelding van URL van de SPO-site](./media/wait-for-approvals/SPO-site-url.png)
5. Selecteer een lijst onder **Lijstnaam**, zoals **Projecttracker**.
   
    ![Afbeelding van SPO-lijstnaam](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>De resulterende actie toevoegen
1. Selecteer de knop **+** en selecteer **Een actie toevoegen**.
   
    ![Afbeelding van Een actie toevoegen](./media/wait-for-approvals/add-an-action.png)
2. Typ of plak **e-mail verzenden** in het vak met de tekst **Wat wilt u vervolgens doen?** en selecteer **Office 365 Outlook - goedkeurings-e-mail verzenden**.
   
    ![Afbeelding van verzenden van goedkeurings-e-mail](./media/wait-for-approvals/send-approval-mail.png)
3. Meld u aan Office 365 Outlook als u hierom wordt gevraagd.
4. Selecteer het veld **Aan** en selecteer vervolgens **E-mailadres Toegewezen aan**.
   
    De gebruiker in de kolom **Toegewezen aan** ontvangt de e-mail om het item goed te keuren of af te wijzen. Wanneer u een item maakt om de stroom te testen, moet u uzelf in dit veld opgeven. Op deze manier kunt u het item niet alleen goedkeuren of afwijzen, maar ontvangt u ook de e-mailmelding.
   
    **Opmerking**: u kunt de velden **Onderwerp** en **Gebruikersopties** aan uw wensen aanpassen.
   
    ![Afbeelding van veld Aan voor verzenden van goedkeurings-e-mail](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Een voorwaarde toevoegen
1. Selecteer de knop **+** en selecteer **Een voorwaarde toevoegen**.
   
    ![Afbeelding van Een voorwaarde toevoegen](./media/wait-for-approvals/add-a-condition.png)
2. Selecteer **Geselecteerde optie** in het veld **Objectnaam**.
3. Typ of plak **Goedkeuren** in het veld **Waardeveld**.
   
    ![Afbeelding van de voorwaardekaart](./media/wait-for-approvals/condition-card-2.png)
4. Selecteer **Een actie toevoegen** in het gebied **Indien ja**.
   
    ![Afbeelding van Een actie toevoegen in gebied Indien ja](./media/wait-for-approvals/yes-add-an-action.png)
5. Typ of plak **e-mail verzenden** in het vak met de tekst **Wat wilt u vervolgens doen?** en selecteer **Office 365 Outlook - e-mail verzenden**.
   
    ![Afbeelding van Ja, e-mail verzenden](./media/wait-for-approvals/yes-send-email.png)
6. Geef in het vak **Onderwerp** een onderwerp op.
   
    Selecteer bijvoorbeeld **Weergavenaam Toegewezen aan**, typ **heeft goedgekeurd** met een spatie aan het begin en het einde, en selecteer vervolgens **Titel**.
7. Geef in het vak **Hoofdtekst** de hoofdtekst van de e-mail op, zoals **Klaar voor volgende fase van project**.
8. Voer de ontvanger in het veld **Aan** in, zoals **E-mailadres Gemaakt door**.
   
    De persoon die het item in de SharePoint-lijst heeft gemaakt, ontvangt een melding of het project is goedgekeurd of afgewezen.
   
    ![Afbeelding van Ja, e-mail verzenden](./media/wait-for-approvals/if-yes-send-email-card-3.png)
9. Herhaal de laatste vijf stappen in het gebied **Indien nee**, maar geef nu in de velden **Onderwerp** en **Hoofdtekst** aan dat het project is afgewezen.
   
     ![Afbeelding van Nee, e-mail verzenden](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Uw stroom voltooien en testen
1. Geef uw stroom een naam en selecteer vervolgens **Stroom maken**.
   
     ![Afbeelding van Stroom maken](./media/wait-for-approvals/create-flow.png)
2. Maak een item in uw SharePoint-lijst.
   
    Er wordt een goedkeurings-e-mail verzonden naar de ontvanger die u hebt opgegeven. Wanneer de ontvanger in die e-mail **Goedkeuren** of **Afwijzen** selecteert, ontvangt u een e-mail met het antwoord. 

