---
title: Goedkeurings stromen maken met aangepaste antwoorden | Microsoft Docs
description: Goedkeurings stromen met aangepaste antwoorden maken.
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
ms.openlocfilehash: eaaa87f9213c5ed04aee65e37ee642436e49dfca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547204"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Aangepaste antwoord opties maken voor goedkeurings stromen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Stel dat u een goedkeurings aanvraag wilt verzenden telkens wanneer een werk nemer een onkosten rapport uploadt naar share point en vervolgens de fiatteur toestaat te reageren met een van de volgende drie opties: accepteren, meer informatie of afwijzen.


## <a name="prerequisites"></a>Vereisten

- Een Microsoft Flow-account.
- Een share point-lijst voor werk nemers om hun onkosten rapporten in te voeren.

## <a name="create-approval-flow"></a>Goedkeurings stroom maken
1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com).
1. Selecteer **mijn stromen** in de navigatie balk aan de linkerkant.
1. Selecteer **nieuw** > **leeg maken**.

    ![Maken van lege optie](media/create-approval-response-options/create-approval-response-options.png)

1. Op het scherm dat wordt geopend, selecteert u **leeg item maken**. 

    ![Selecteer leeg item maken](media/create-approval-response-options/create-from-blank.png)

1. Zoek naar **share point** en selecteer **Wanneer een item wordt gemaakt** in de lijst met triggers. 

1. Geef het share point- **site adres** en de **lijst naam**op. 

1. Selecteer **nieuwe stap**, zoek naar **goed keuring**en selecteer **Start en wacht op goed keuring (v2)** .

1. Selecteer op de **Start en wacht op een kaart voor goed keuring (v2)** de lijst **goedkeurings type** .

    ![Goedkeurings type](media/create-approval-response-options/select-approval-type.png)

1. **Aangepaste antwoorden selecteren: wacht op één reactie (Premium)** .

    ![Aangepaste antwoorden](media/create-approval-response-options/select-custom-responses.png)

    Vervolgens maakt u de aangepaste antwoorden die uw goed keurders zullen gebruiken wanneer ze reageren op een goedkeurings aanvraag voor onkosten van werk nemers.


1. In het vak voor de **antwoord opties item-1** voert u **accepteren** in en selecteert u vervolgens **Nieuw item toevoegen**. 

    ![Aangepast antwoord 1](media/create-approval-response-options/enter-response-1.png)

1. Voer in het dialoog venster **antwoord opties item-2** de optie **weigeren** in en selecteer vervolgens **Nieuw item toevoegen**.

    ![Aangepast antwoord 2](media/create-approval-response-options/enter-response-2.png)

1. Voer in het vak **item-3 van de antwoord opties** **meer informatie**in.

    ![Aangepast antwoord 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Voer een **titel** **in, toegewezen aan** (e-mail adres voor de goed keurder) en **Details** (de gegevens die moeten worden opgenomen in de goedkeurings aanvraag).

    Hier volgt een voor beeld van wat u mogelijk voor uw organisatie opneemt.

    ![Details van aangepaste antwoorden](media/create-approval-response-options/enter-title-assigned-to-details.png)


Nu u uw aangepaste antwoorden hebt gemaakt, wilt u mogelijk verschillende dingen in uw stroom doen, afhankelijk van de reactie van de goed keurder.


## <a name="use-approval-responses"></a>Goedkeurings reacties gebruiken 

Als het antwoord op de aanvraag wordt **geaccepteerd**, wilt u mogelijk een e-mail verzenden naar de afdeling Accounting en vragen om de werk nemer voor de onkosten te betalen. 

Als het antwoord wordt **afgewezen**, wilt u mogelijk een e-mail naar de werk nemer verzenden, zodat ze weten dat de aanvraag is afgewezen.

En ten slotte, als de reactie van de goed keurder **meer informatie nodig**heeft, wilt u mogelijk een e-mail verzenden naar de werk nemer en wordt u gevraagd om meer informatie op te geven.

Als u een van deze acties in de stroom wilt uitvoeren, voegt u een [**voor waarde**](add-condition.md) of een **Switch** actie toe aan uw stroom en selecteert u vervolgens het veld **resultaat** van de goedkeurings aanvraag van de kiezer voor dynamische inhoud. Controleer of de waarde is geaccepteerd, meer informatie nodig of afwijzen.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Reageren op goedkeurings aanvragen met een aangepast antwoord

Goed keurders ontvangen goedkeurings aanvragen in het e-mail bericht. De aanvragen worden ook weer gegeven in het goedkeurings centrum op Microsoft Flow. 

![E-mail met goedkeurings aanvraag](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Meer informatie
- [Eén goedkeurings stroom](modern-approvals.md) maken
- [Sequentiële goedkeurings stromen](sequential-modern-approvals.md) maken
