---
title: Aangepaste acties vanuit een werk stroom aanroepen | MicrosoftDocs
description: Meer informatie over het aanroepen van een aangepaste actie vanuit een werk stroom
ms.custom: ''
ms.date: 11/22/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 1fd5d39e-3dc8-4d1a-8b4b-ccaa303f4bbb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9ed3c2114bfb167eb8d4d6a5670ccec8050ee9d0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547414"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Aangepaste acties vanuit een werk stroom aanroepen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Werk stromen hebben talloze mogelijkheden om bedrijfs scenario's te ondersteunen. Bij het aanroepen van elementaire gegevens bewerkingen voor een record, zoals maken, bijwerken en verwijderen, kunt u vanuit een werk stroom een aantal zakelijke scenario's oplossen. Als u echter de mogelijkheden van de werk stromen koppelt aan de kracht van de aangepaste acties die rechtstreeks vanuit een werk stroom worden aangeroepen, voegt u een geheel nieuwe bedrijfs scenario's toe aan uw toepassing zonder dat u code hoeft te schrijven.  
  
 Laten we eens kijken naar het scenario waarin een aangepaste actie wordt aangeroepen vanuit een werk stroom. Er wordt een aangepaste actie aangeroepen om de goed keuring van de Manager aan te vragen wanneer een korting voor een bepaalde kans groter is dan 20%.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Voor beeld: een aangepaste actie maken met de entiteit verkoop kans
  
1. Selecteer [](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) in Solution Explorer **processen**selecteren.  
  
2.  Kies **Nieuw**in de navigatie balk. Geef het proces een naam en kies de **actie** categorie.  
  
 Als u een goed keuring voor de korting wilt aanvragen, wordt een aangepaste actie met de naam **goedkeurings proces**gebruikt. We hebben een invoer parameter, **SpecialNotes**en een stap **e-mail verzenden** toegevoegd om een nieuw bericht te maken en een aanvraag voor goed keuring van de Manager te verzenden, zoals hier wordt weer gegeven.  
  
 ![Een stap &#45; toevoegen e-mail verzenden](media/enable-custom-action-approval-proces-sadd-email.png "Een stap toevoegen-e-mail verzenden")  
  
 Als u het e-mail bericht wilt configureren, kiest u **Eigenschappen instellen**. Wanneer het formulier wordt geopend, gebruikt **u de Formulierenassistent** om speciale notities en andere informatie toe te voegen aan het e-mail bericht, zoals gemarkeerd op de scherm opname. Als u de speciale notities wilt toevoegen, plaatst u de cursor waar u deze wilt weer geven in het bericht en kiest u **in de Formulierenassistent, onder** **zoeken naar**, de optie **argumenten** in de eerste vervolg keuzelijst en kiest u **SpecialNotes** in de tweede en klik vervolgens op **OK**.  
  
 ![E-mail instellen](media/enable-custom-action-approval-process-setup-email.png "E-mail instellen")  
  
 Voordat u de actie vanuit een werk stroom kunt aanroepen, moet u deze activeren. Nadat u de actie hebt geactiveerd, kunt u de eigenschappen ervan weer geven door **weer gave-eigenschappen**te kiezen.  
  
 ![Goedkeurings proces &#45; van aangepaste actie activeren](media/enable-custom-action-approval-process-activate-action.png "Goedkeurings proces voor aangepaste actie activeren")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Een aangepaste actie aanroepen vanuit een werk stroom  
  
1. Selecteer [](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) in Solution Explorer **processen**selecteren.   
  
2.  Kies **Nieuw**in de navigatie balk. Geef het proces een naam en kies de categorie **werk stroom** .  
  
 We hebben een werk stroom gemaakt die de aangepaste actie voor het **goedkeurings proces** aanroept wanneer de goed keuring van de Manager voor een korting van meer dan 20% voor een verkoop kans is vereist.  
  
 ![Actie-eigenschappen van werk stroom instellen](media/enable-custom-action-from-workflow.png "Actie-eigenschappen van werk stroom instellen")  
  
 U kunt de invoer eigenschappen van de actie instellen door **Eigenschappen instellen**te kiezen. We hebben in de speciale notities een naam toegevoegd van het account dat aan de opportuniteit is gerelateerd. Kies in **de Formulierenassistent**, onder **zoeken naar**, **account** in de eerste vervolg keuzelijst, selecteer **account naam** in de tweede vervolg keuzelijst en kies vervolgens **OK**. De **doel** eigenschap is vereist en wordt ingevuld door het systeem. De **{Opportunity (opportunity)}** in de **doel** eigenschap is dezelfde mogelijkheid als waarop de werk stroom voor aanroepen wordt uitgevoerd. U kunt ook een specifieke mogelijkheid voor de doel eigenschap kiezen met behulp van zoeken.  
  
 ![Invoer parameters voor ApprovalProcess-actie instellen](media/enable-customaction-workflow-set-properties.png "Invoer parameters voor ApprovalProcess-actie instellen")  
  



