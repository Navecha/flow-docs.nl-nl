---
title: Meer informatie over het maken en beheren van stromen in micro soft teams | Microsoft Docs
description: U kunt stromen maken en beheren om berichten op aanvraag te plaatsen, @mention gebruikers en kanalen, kaarten post met respons opties en meer.
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
ms.openlocfilehash: 34cb8577d57d70686fd9811db9146443b56a07b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547980"
---
# <a name="microsoft-flow-in-teams"></a>Microsoft Flow in teams
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

### <a name="prerequisites"></a>Vereisten

1. Toegang tot micro soft teams.
1. Toegang tot Microsoft Flow.

## <a name="install-the-microsoft-flow-app-in-teams"></a>De Microsoft Flow-app installeren in teams

Volg deze stappen om de app Microsoft Flow te installeren in micro soft teams.

1. Meld u aan bij micro soft teams.

1. Tik op het pictogram **apps** linksonder in de navigatie balk teams.

    ![Apps selecteren](media/flows-teams/apps.png)

1. Selecteer de **flow** -app. Mogelijk moet u zoeken naar **flow** als u deze niet ziet.

    ![Flow-app selecteren](media/flows-teams/select-flow-app.png)

1. Selecteer **installeren**.

    ![Knop installeren](media/flows-teams/select-install.png)

1. Microsoft Flow is nu geïnstalleerd.

    ![Nstalleerd](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Een stroom maken in teams

1. Meld u aan bij micro soft teams.

1. Selecteer de koppeling **meer toegevoegde apps** (...) op de navigatie balk en selecteer vervolgens de **flow** -app.

    ![Pictogram toegevoegde apps](media/flows-teams/added-apps-icon.png)

1. Als u dit nog niet eerder hebt gedaan, moet u zich mogelijk aanmelden en machtigingen verlenen.

    ![Aanmelden](media/flows-teams/grant-permissions-sign-in.png)


    Let op de volgende tabbladen:

    ![Pagina stroom overloop](media/flows-teams/flow-landing-page.png)

    Naam|Doel
    ----|-----|
    Enger|Interactie met de bot van de stroom.
    Terugloop|Stromen maken en beheren.
    Goed keuringen|Geeft een lijst van ontvangen en verzonden goedkeurings aanvragen.
    wilt|Geeft versie en andere informatie weer over Microsoft Flow.


    U ziet nu alle stromen die u hebt gemaakt op basis van de Microsoft Flow Designer (indien van toepassing). 

    U kunt ook stromen maken op basis van een aangepaste sjabloon of vanuit een lege sjabloon, net als bij de Microsoft Flow Designer. 

## <a name="manage-approvals"></a>Goed keuringen beheren

U kunt [goed keuringen](modern-approvals.md) beheren in micro soft teams, net zoals u dat zou doen in Microsoft flow. Volg deze stappen voor het beheren van uw goed keuringen:

1. Meld u aan bij micro soft teams.
1. Selecteer het tabblad **goed keuringen** .

    ![Tabblad goed keuringen](media/flows-teams/approvals-tab.png)

    U ziet de volgende subtabbladen:

    Tabbesturingselement|Doel
    ----|-----|
    Ontvangen|Geeft een lijst van de goedkeurings aanvragen die u hebt ontvangen en waarvoor u actie kunt ondernemen.
    Zonden|Geeft een lijst van de goedkeurings aanvragen die u hebt verzonden en die actie van anderen in behandeling zijn.
    Transactie|Geeft een lijst van ontvangen en verzonden goedkeurings aanvragen.
    Goedkeurings stroom maken|Goedkeurings stromen maken.

1. Selecteer de tabbladen **ontvangen**, **verzonden**of **geschiedenis** voor meer informatie.

    ![Tabblad goed keuringen](media/flows-teams/approvals-tab-2.png)

1. Selecteer **goedkeurings stroom maken** om een goedkeurings stroom te maken.

    ![Tabblad goed keuringen](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>De bot gebruiken met stromen

### <a name="list-and-launch-flows-with-the-bot"></a>Stromen weer geven en starten met de bot

> [!TIP]
> De bot bevat een lijst met stromen en voert deze uit die worden geactiveerd door een planning of hand matig worden geactiveerd zonder tussen komst van de gebruiker.

1. Meld u aan bij micro soft teams.
1. Selecteer de koppeling **meer toegevoegde apps** (...) op de navigatie balk en selecteer vervolgens de **flow** -app.

    ![Pictogram toegevoegde apps](media/flows-teams/added-apps-icon.png)
    
1. Selecteer het tabblad **gesprek** .

    ![Tabblad conversatie](media/flows-teams/conversations-tab.png)

Op het tabblad **conversatie** kunt u opdrachten naar de bot verzenden, die reageert door de acties uit te voeren die u opdracht wilt uitvoeren. Als u bijvoorbeeld uw stromen wilt weer geven en de stroom met index 1 wilt uitvoeren, voert u de volgende opdrachten uit:

- ```List flows```: de bot bevat een lijst met uw stromen, voorafgegaan door een index nummer.
- ```Run flow 1```-voert stroom nummer 1 uit. Hier is *1* het index nummer van de stroom die u wilt uitvoeren.

   ![Bot-opdrachten](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>De beschrijving voor stromen ophalen

Als u de beschrijving voor de stroom met index 1 uit uw lijst met stromen wilt ophalen, voert u ```describe flow 1```uit. De bot-reactie is vergelijkbaar met deze installatie kopie:

   ![Stromen beschrijven](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>De lijst met opdrachten voor de bot ophalen

Als u de lijst met opdrachten van de bot wilt ophalen, vraagt u deze met de volgende opdracht: ```learn more``` 

De bot-reactie is vergelijkbaar met deze installatie kopie:

![Stromen beschrijven](media/flows-teams/bot-learn-more.png) 
