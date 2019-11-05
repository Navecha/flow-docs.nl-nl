---
title: Meer informatie over het maken van stromen die adaptieve kaarten in micro soft teams plaatsen | Microsoft Docs
description: Meer informatie over het maken van stromen die inhouds opgemaakte inhoud met adaptieve kaarten naar micro soft teams kunnen verzenden.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 0aa5b4727bea569732fe5b76f717a87d8d7ddb02
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546502"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Adaptieve kaarten gebruiken in micro soft teams
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

U kunt een stroom maken die [adaptieve kaarten](https://adaptivecards.io) naar een micro soft teams-kanaal verzendt. Met adaptieve kaarten kunt u uitgebreide opmaak gebruiken om uw berichten duidelijker, interactief en aantrekkelijker te maken. Adaptieve kaarten kunnen onderdelen bevatten zoals afbeeldingen, grafieken, tekst met opmaak en meer.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Een stroom maken waarmee u adaptieve kaarten naar een team kunt posten

Volg deze stappen om een stroom te maken die een adaptieve kaart naar het algemene kanaal in het strategie-en plannings team post. De stroom die we maken, maakt gebruik van de **post uw eigen adaptieve kaart als de bot naar een kanaal (preview)** -actie om de inhoud van de adaptieve kaart wekelijks te plaatsen naar het kanaal van het team.

1. Meld u aan bij micro soft teams.
1. Selecteer het pictogram **teams** in de navigatie balk aan de linkerkant en selecteer vervolgens de **strategie en het plannings** team.

    ![Teams selecteren](media/create-adaptive-cards-teams/select-teams-team.png)

1. Selecteer het tabblad **stroom** boven aan het scherm.
1. Selecteer het pictogram **+** (leeg item maken).
1. Zoek naar **terugkeer patroon**en selecteer vervolgens de trigger **terugkeer patroon** .

    ![Terugkerende kaart](media/create-adaptive-cards-teams/select-recurrence.png)

1. Stel de planning als volgt in om elke week te herhalen, op een tijdstip en tijd zone van uw keuze:
    
    ![Terugkerende kaart](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Selecteer **nieuwe stap**.
1. Zoek naar **adaptief**, selecteer **micro soft teams**en selecteer vervolgens het item **uw eigen adaptieve kaart plaatsen als de stroom van een kanaal (Preview-actie)** .

   ![Adaptieve kaart](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Geef een **team**, een **kanaal**en een **bericht** op de plaats **waar u uw eigen adaptieve kaart kunt plaatsen als de bot naar een kanaal kaart (preview)** om het team en het kanaal aan te geven waarop het adaptieve kaart **bericht** wordt geplaatst.

   ![Adaptieve kaart](media/create-adaptive-cards-teams/adaptive-card-message.png)

   U kunt deze voor beeld-JSON-inhoud gebruiken voor het **bericht**:

    ````
        {
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "speak": "Our team meeting is starting soon. Do you want to snooze  or do you want to send a late notification to the attendees?",
    "body": [
        {
        "type": "TextBlock",
        "text": "Strategy and Planning Weekly Team meeting",
        "size": "large",
        "weight": "bolder"
        },
        {
        "type": "TextBlock",
        "text": "Conf Room 112/3377 (10)",
        "isSubtle": true
        },
        {
        "type": "TextBlock",
        "text": "12:30 PM - 1:30 PM",
        "isSubtle": true,
        "spacing": "none"
        },
        {
        "type": "TextBlock",
        "text": "Snooze for"
        },
        {
        "type": "Input.ChoiceSet",
        "id": "snooze",
        "style": "compact",
        "value": "5",
        "choices": [
            {
            "title": "5 minutes",
            "value": "5",
            "isSelected": true
            },
            {
            "title": "15 minutes",
            "value": "15"
            },
            {
            "title": "30 minutes",
            "value": "30"
            }
        ]
        }
    ],
    "actions": [
        {
        "type": "Action.Submit",
        "title": "Snooze",
        "data": {
            "x": "snooze"
        }
        },
        {
        "type": "Action.Submit",
        "title": "I'll be late",
        "data": {
            "x": "late"
        }
        }
    ]
    }
    ````


1. Geef uw stroom een naam en sla deze op.


## <a name="run-the-flow"></a>De stroom uitvoeren

Nadat de tijd van het terugkeer patroon is verstreken, wordt de inhoud van de adaptieve kaart door de stroom naar het door u opgegeven team kanaal gepost.

![De stroom uitvoeren](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Meer informatie

- Aan de slag met voor [beelden van adaptieve kaarten](https://adaptivecards.io/samples/).
- U kunt op eenvoudige wijze een [adaptieve kaart inhoud](https://adaptivecards.io) maken.



