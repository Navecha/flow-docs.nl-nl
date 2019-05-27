---
title: Een stroom herinnering voor SharePoint-items maken | Microsoft Docs
description: Maken van stromen die u te aan vervaldatum herinneren datums voor SharePoint-items.
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
ms.date: 04/30/2019
ms.author: deonhe
ms.openlocfilehash: b0f1aa80fb92c9718d2b0697d3abb0b0d2478013
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061107"
---
# <a name="sharepoint-remind-me"></a>SharePoint Help me herinneren

SharePoint-lijsten en bibliotheken toegestaan u kolommen met aangepaste metagegevens voor het volgen van datums definiëren. Met de Microsoft Flow-integratie met SharePoint, kunt u eenvoudig herinnering stromen, op basis van datum/tijd-kolommen in SharePoint maken. Met herinnering stromen ontvangt u een persoonlijk e-mailmelding een vooraf bepaald aantal dagen voorafgaand aan een datum op een document of een item in SharePoint.

## <a name="prerequisites"></a>Vereisten
- Toegang tot Microsoft SharePoint Online.
- Een SharePoint-lijst of bibliotheek met een datum/tijd-kolom.
- Toegang tot Microsoft Flow.

## <a name="create-a-reminder-flow"></a>Een herinnering stroom maken

 1. Maak een [SharePoint-lijst](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) met ten minste één datum/tijd-kolom in de huidige weergave. 
 1. Selecteer **Flow** > **een herinnering instellen** > **datum gedeactiveerd** (dit is de kolom met de datum/tijd voor de herinnering).

     ![Selecteer de stroom herinnering](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Geef een **Stroomnaam** en het aantal dagen voorafgaand aan de vermelding van de kolom Datum/tijd wanneer u ontvangen van de herinnering wilt op de **een herinnering instellen** kaart.

    ![Stroomgegevens herinnering instellen](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Selecteer **maken** op de **een herinnering instellen** kaart.

1. U ontvangt het volgende bericht dat aangeeft dat de stroom is gemaakt:

    ![Herinnering stroom die is gemaakt](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Herinneringen ontvangen bevestigen

U ontvangt een herinnering via e-mail, op basis van de **Help me herinneren dit van tevoren veel dag(en)** vermelding die u hebt aangebracht op de **een herinnering instellen** stroom die u eerder hebt gemaakt. 

## <a name="edit-your-flow"></a>Uw stroom bewerken

De herinnering-stroom is, zoals een andere stroom, zodat u kunt openen en via bewerken [Microsoft Flow](https://flow.microsoft.com).

## <a name="learn-more"></a>Meer informatie

- Aan de slag met [Microsoft Flow](https://flow.microsoft.com).
- Stel een [herinnering stroom](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) in SharePoint.


