---
title: Goedkeuringsstromen maken met aangepaste antwoorden | Microsoft Docs
description: Leer hoe u goedkeuringsstromen maakt met aangepaste antwoorden.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/04/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- maker
ms.openlocfilehash: d1f4b6d6dad3138bf935947076be4fe75661e36e
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2019
ms.locfileid: "65061705"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Aangepast antwoordopties voor goedkeuringsstromen maken

Stel dat u een goedkeuringsaanvraag wilt verzenden wanneer een werknemer een onkostendeclaratie uploadt naar SharePoint verzendt en dat de fiatteur (ook wel goedkeurder genoemd) vervolgens kan kiezen uit drie vooraf gemaakte antwoordopties: Accepteren, Meer info nodig of Weigeren.


## <a name="prerequisites"></a>Vereisten

- Een Microsoft Flow-account met een P2-licentie (P2 is nodig voor de premium-functies. Goedkeuringen is een premium-functie.)
- Een SharePoint-lijst waarin werknemers hun onkostendeclaraties kunnen invoeren.

## <a name="create-approval-flow"></a>Goedkeuringsstroom maken
1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com).
1. Selecteer **Mijn stromen** in de navigatiebalk aan de linkerkant.
1. Selecteer **Nieuw** > **Geheel nieuw maken**.

    ![De optie Geheel nieuw maken](media/create-approval-response-options/create-approval-response-options.png)

1. Selecteer **Geheel nieuw maken** op het scherm dat wordt geopend. 

    ![De optie Geheel nieuw maken selecteren](media/create-approval-response-options/create-from-blank.png)

1. Zoek naar **sharepoint** en selecteer vervolgens **Wanneer een item is gemaakt** in de lijst met triggers. 

1. Geef waarden op voor **Siteadres** en **Lijstnaam** voor de SharePoint-locatie. 

1. Selecteer **Nieuwe stap**, zoek naar **Goedkeuring** en selecteer **Start en wacht op een goedkeuring (V2)**.

1. Selecteer op de kaart **Start en wacht op een goedkeuring (V2)** de lijst **Goedkeuringstype**.

    ![Goedkeuringstype](media/create-approval-response-options/select-approval-type.png)

1. Selecteer **Aangepaste antwoorden - wachten op een antwoord**.

    ![Aangepaste antwoorden](media/create-approval-response-options/select-custom-responses.png)

    Vervolgens maakt u de aangepaste antwoorden waaruit uw fiatteurs kunnen kiezen bij de beoordeling van een goedkeuringsaanvraag voor onkosten die een werknemer heeft gemaakt.


1. Typ **Accepteren** in het vak **Antwoordopties Item - 1** en selecteer vervolgens **Nieuw item toevoegen**. 

    ![Aangepast antwoord 1](media/create-approval-response-options/enter-response-1.png)

1. Typ **Weigeren** in het vak **Antwoordopties Item - 2** en selecteer vervolgens **Nieuw item toevoegen**.

    ![Aangepast antwoord 2](media/create-approval-response-options/enter-response-2.png)

1. Typ **Meer info nodig** in het vak **Antwoordopties Item - 3**.

    ![Aangepast antwoord 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Geef waarden op voor **Titel**, **Toegewezen aan** (e-mailadres van de fiatteur) en **Details** (de gegevens die moeten worden opgenomen in de goedkeuringsaanvraag).

    Hier ziet u een voorbeeld van wat u voor uw organisatie zou kunnen opnemen.

    ![Details van aangepaste antwoord](media/create-approval-response-options/enter-title-assigned-to-details.png)


De aangepaste antwoorden zijn nu gemaakt. Maar misschien wilt u nog andere dingen doen in uw stroom, afhankelijk van het antwoord van de fiatteur.


## <a name="use-approval-responses"></a>Goedkeuringsantwoorden gebruiken 

Als het antwoord op de aanvraag **Accepteren** is, kunt u automatisch een e-mailbericht sturen naar de administratie, met het verzoek om de onkosten te vergoeden aan de werknemer. 

Als het antwoord **Weigeren** is, kunt u een e-mailbericht naar de werknemer sturen, om toe te lichten waarom de aanvraag is afgewezen.

En als het antwoord van de fiatteur **Meer info nodig** is, kunt u een e-mailbericht naar de werknemer sturen met het verzoek om aanvullende gegevens.

U kunt deze vervolgstappen uitvoeren door een [**voorwaarde**](add-condition.md) of een actie **Switch** actie aan uw stroom toe te voegen en vervolgens het veld **Resultaat** van de goedkeuringsaanvraag te selecteren in de lijst Dynamische inhoud. Vergeet niet om te controleren of de waarde Accepteren, Meer info nodig of Weigeren is.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Met een aangepast antwoord reageren op goedkeuringsaanvragen

Fiatteurs ontvangen goedkeuringsaanvragen per e-mail. De aanvragen worden ook weergegeven in het Goedkeuringscentrum van Microsoft Flow. 

![E-mail met goedkeuringsaanvraag](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Meer informatie
- [Stromen met één fiatteur maken](modern-approvals.md)
- [Stromen met opeenvolgende goedkeuringen maken](sequential-modern-approvals.md)
