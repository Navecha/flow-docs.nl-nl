---
title: Stromen maken en beheren in Microsoft Teams | Microsoft Docs
description: Leer hoe u stromen maakt en beheert om berichten op aanvraag te plaatsen, gebruikers en kanalen noemt met @mention, kaarten plaatst met antwoordopties en meer.
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
ms.openlocfilehash: 4987d1f4fb504c0279540eb86dcb6ad1b983ff4a
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061843"
---
# <a name="microsoft-flow-in-teams"></a>Microsoft Flow in Teams

### <a name="prerequisites"></a>Vereisten

1. Toegang tot Microsoft Teams.
1. Toegang tot Microsoft Flow.

## <a name="install-the-microsoft-flow-app-in-teams"></a>Microsoft Flow-app installeren in Teams

Volg deze stappen voor het installeren van de Microsoft Flow-app in Microsoft Teams.

1. Meld u aan bij Microsoft Teams.

1. Tik linksonder op de navigatiebalk van Teams op het pictogram **Apps**.

    ![Apps selecteren](media/flows-teams/apps.png)

1. Selecteer de app **Flow**. U moet mogelijk zoeken naar **Flow** als u de app niet ziet.

    ![De app Flow selecteren](media/flows-teams/select-flow-app.png)

1. Selecteer **Installeren**.

    ![De knop Installeren](media/flows-teams/select-install.png)

1. Microsoft Flow is nu geïnstalleerd.

    ![Geïnstalleerd](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Een stroom maken in Teams

1. Meld u aan bij Microsoft Teams.

1. Selecteer de koppeling **Meer toegevoegde apps** (...) op de navigatiebalk en selecteer vervolgens de app **Flow**.

    ![Het pictogram Meer toegevoegde apps](media/flows-teams/added-apps-icon.png)

1. Als u dit nog niet eerder hebt gedaan, moet u zich mogelijk aanmelden en machtigingen verlenen.

    ![Aanmelden](media/flows-teams/grant-permissions-sign-in.png)


    U ziet de volgende tabbladen:

    ![Landingspagina van Flow](media/flows-teams/flow-landing-page.png)

    Naam|Doel
    ----|-----|
    Gesprek|Interactie met de bot van Flow.
    Stromen|Stromen maken en beheren.
    Goedkeuringen|Hier ziet u ontvangen en verzonden goedkeuringsaanvragen.
    Info|Hier ziet u de versie en andere informatie over Microsoft Flow.


    U ziet nu alle stromen die u hebt gemaakt met de Microsoft Flow Designer (als u stromen hebt gemaakt). 

    U kunt ook stromen maken van een aangepaste sjabloon of een lege sjabloon, net als in de Microsoft Flow Designer. 

## <a name="manage-approvals"></a>Goedkeuringen beheren

U kunt [goedkeuringen](modern-approvals.md) beheren in Microsoft Teams, op dezelfde manier als in Microsoft Flow. Volg deze stappen voor het beheren van uw goedkeuringen:

1. Meld u aan bij Microsoft Teams.
1. Selecteer het tabblad **Goedkeuringen**.

    ![Het tabblad Goedkeuringen](media/flows-teams/approvals-tab.png)

    Hier ziet u de volgende subtabbladen:

    Tabblad|Doel
    ----|-----|
    Ontvangen|Hier ziet u de goedkeuringsaanvragen die u hebt ontvangen en die wachten op actie van u.
    Verzonden|Hier ziet u de goedkeuringsaanvragen die u hebt verzonden en die wachten op actie van anderen.
    Geschiedenis|Hier ziet u ontvangen en verzonden goedkeuringsaanvragen.
    Goedkeuringsstroom maken|Hiermee kunt u een goedkeuringsstroom maken.

1. Selecteer het tabblad **Ontvangen**, **Verzonden** of **Geschiedenis** voor meer informatie.

    ![Het tabblad Goedkeuringen](media/flows-teams/approvals-tab-2.png)

1. Selecteer **Goedkeuringsstroom maken** om een goedkeuringsstroom te maken.

    ![Het tabblad Goedkeuringen](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>De bot gebruiken met stromen

### <a name="list-and-launch-flows-with-the-bot"></a>Stromen weergeven en starten met de bot

> [!TIP]
> Met de bot kunt u stromen weergeven en uitvoeren die worden geactiveerd door een schema of die handmatig worden geactiveerd zonder invoer van een gebruiker.

1. Meld u aan bij Microsoft Teams.
1. Selecteer de koppeling **Meer toegevoegde apps** (...) op de navigatiebalk en selecteer vervolgens de app **Flow**.

    ![Het pictogram Meer toegevoegde apps](media/flows-teams/added-apps-icon.png)
    
1. Selecteer het tabblad **Gesprek**.

    ![Het tabblad Gesprek](media/flows-teams/conversations-tab.png)

Gebruik het tabblad **Gesprek** om opdrachten te verzenden naar de bot. Deze reageert door de gevraagde acties uit te voeren. Als u bijvoorbeeld uw stromen wilt weergeven en de stroom met index 1 wilt uitvoeren, geeft u de volgende opdrachten:

- ```List flows``` -De bot toont een lijst van uw stromen, voorafgegaan door een indexnummer.
- ```Run flow 1``` -Hiermee wordt de stroom met het nummer 1 uitgevoerd. Hier is *1* het indexnummer van de stroom die u wilt uitvoeren.

   ![Bot-opdrachten](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>De beschrijving voor stromen opvragen

Om de beschrijving voor de stroom met index 1 op te vragen uit de lijst met stromen, geeft u de opdracht ```describe flow 1```. Het antwoord van de bot is vergelijkbaar met deze afbeelding:

   ![Stromen beschrijven](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>De lijst met opdrachten voor de bot ophalen

Als u de lijst met opdrachten wilt zien die de bot ondersteunt, gebruikt u deze opdracht: ```learn more``` 

Het antwoord van de bot is vergelijkbaar met deze afbeelding:

![Stromen beschrijven](media/flows-teams/bot-learn-more.png) 
