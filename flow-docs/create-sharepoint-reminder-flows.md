---
title: Een herinnerings stroom maken voor share point-items | Microsoft Docs
description: Maak stromen die u eraan herinneren dat er eind datums voor share point-items zijn.
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
ms.openlocfilehash: c7c87df5288ba58d303de441b41e7493cd713f4a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547551"
---
# <a name="sharepoint-remind-me"></a>Share point mij herinneren
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Met share point-lijsten en-bibliotheken hebt u de mogelijkheid om aangepaste meta gegevens kolommen te definiëren om datums bij te houden. Met de integratie van Microsoft Flow met share point kunt u eenvoudig herinnerings stromen maken op basis van datum-en tijd kolommen in share point. Met een herinnerings stroom ontvangt u een persoonlijk e-mail bericht met een vooraf bepaald aantal dagen vóór een datum in een document of item in share point.

## <a name="prerequisites"></a>Vereisten
- Toegang tot micro soft share point online.
- Een share point-lijst of bibliotheek met een datum/tijd-kolom.
- Toegang tot Microsoft Flow.

## <a name="create-a-reminder-flow"></a>Een herinnerings stroom maken

 1. Maak een [share point-lijst](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) met ten minste één datetime-kolom in de huidige weer gave. 
 1. **Stroom** selecteren > **een herinnering instellen** > **datum gedeactiveerd** (dit is de kolom met de datum/tijd voor de herinnering).

     ![Herinnerings stroom selecteren](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Geef een **stroom naam** en het aantal dagen vóór de kolom vermelding datetime op als u de herinnerings waarschuwing wilt ontvangen op de kaart **een herinnering instellen** .

    ![Details van de herinnerings stroom instellen](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Selecteer **maken** in de kaart **een herinnering instellen** .

1. U ontvangt het volgende bericht dat aangeeft dat de stroom is gemaakt:

    ![Herinnerings stroom gemaakt](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Ontvangen herinneringen bevestigen

U ontvangt een herinnering via e-mail, op basis van het **aantal dagen dat u dit veel dag (en)** hebt opgegeven voor de vooraf **ingestelde herinnerings** stroom die u eerder hebt gemaakt. 

## <a name="edit-your-flow"></a>Uw stroom bewerken

De herinnerings stroom is net als elke andere stroom, zodat u deze kunt openen en bewerken via [Microsoft flow](https://flow.microsoft.com).

## <a name="learn-more"></a>Meer informatie

- Aan de slag met [Microsoft flow](https://flow.microsoft.com).
- Een [herinnerings stroom](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) instellen in share point.


