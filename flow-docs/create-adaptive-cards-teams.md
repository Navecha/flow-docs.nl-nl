---
title: Meer informatie over het maken van stromen die adaptieve kaarten in Microsoft Teams plaatsen | Microsoft Docs
description: Informatie over het maken van stromen die tekstvakken met opmaak inhoud met adaptieve kaarten in Microsoft Teams plaatsen.
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
ms.openlocfilehash: d6bb4bb55fe876db1d8b64c157d3b4967e5d067f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061567"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Adaptieve kaarten gebruiken in Microsoft Teams

U kunt een stroom maken die berichten [adaptieve kaarten](https://adaptivecards.io) aan een Microsoft Teams-kanaal. Met adaptieve kaarten, kunt u opmaak voor het maken van uw berichten duidelijker, aantrekkelijke en interactieve. Adaptieve kaarten kunnen onderdelen, zoals afbeeldingen, grafieken en tekstvakken met opmaak bevatten.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Een stroom maken waarmee adaptieve kaarten aan een team berichten

Volg deze stappen voor het maken van een stroom die een adaptieve kaart aan het algemene kanaal in het team van strategie en Planning plaatst. De stroom die we maken maakt gebruik van de **uw eigen adaptieve kaart plaatsen als de bot stroom aan een kanaal (preview)** actie van de adaptieve kaart om inhoud te publiceren naar van het team-kanaal wekelijks.

1. Meld u aan bij Microsoft Teams.
1. Selecteer de **Teams** pictogram in de navigatiebalk aan de linkerkant van de balk en selecteer vervolgens de **strategie en Planning** team.

    ![Selecteer teams](media/create-adaptive-cards-teams/select-teams-team.png)

1. Selecteer de **Flow** tabblad aan de bovenkant van het scherm.
1. Selecteer de **+** pictogram (leeg item maken).
1. Zoeken naar **terugkeerpatroon**, en selecteer vervolgens de **terugkeerpatroon** trigger.

    ![Terugkeerpatroon-kaart](media/create-adaptive-cards-teams/select-recurrence.png)

1. Stel de planning als volgt om te herhalen elke week op een tijd en tijdzone van uw keuze:
    
    ![Terugkeerpatroon-kaart](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Selecteer **Nieuwe stap**.
1. Zoeken naar **adaptieve**, selecteer **Microsoft Teams**, en selecteer vervolgens de **uw eigen adaptieve kaart plaatsen als de bot stroom aan een kanaal (preview)** actie.

   ![Adaptieve kaart](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Geef een **Team**, **kanaal**, en **bericht** op de **uw eigen adaptieve kaart plaatsen als de bot stroom aan een kanaal (Preview)** kaart om aan te geven het team en het kanaal waaraan de adaptieve kaart **bericht** wordt gepost.

   ![Adaptieve kaart](media/create-adaptive-cards-teams/adaptive-card-message.png)

   U kunt deze voorbeeld-JSON-inhoud voor de **bericht**:

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

U ziet dat, nadat de terugkeerpatroon tijd is verstreken, de stroom berichten van de adaptieve kaart inhoud naar het teamkanaal dat u hebt gedefinieerd.

![De stroom uitvoeren](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Meer informatie

- Aan de slag met [adaptieve kaart voorbeelden](https://adaptivecards.io/samples/).
- Maak [inhoud adaptieve kaart](https://adaptivecards.io) de eenvoudige manier.



