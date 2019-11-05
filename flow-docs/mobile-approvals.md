---
title: Aanvragen goed keuren op een mobiel apparaat | Microsoft Docs
description: Een mobiel apparaat gebruiken voor het goed keuren van aanvragen die zijn gemaakt in Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a71d1e53199f0dacfc2086812cc3cd2fd9585f4d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548679"
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>Aanvragen goed keuren op uw mobiele apparaat met behulp van Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Als een stroom u identificeert als fiatteur en u de mobiele app voor Microsoft Flow hebt geïnstalleerd, ontvangt u een push melding wanneer u wordt gevraagd om uw goed keuring uit te voeren.

In dit artikel vindt u een aantal veelvoorkomende scenario's die waarschijnlijk optreden tijdens het beheren van goedkeurings aanvragen in de mobiele app voor Microsoft Flow.

> [!NOTE]
> De afbeeldingen in dit onderwerp zijn afkomstig van een Android-apparaat. de ervaring op iOS is echter vergelijkbaar.
> 
> 

## <a name="prerequisites"></a>Vereisten
U hebt het volgende nodig om dit scenario te volt ooien:

* Een [Android](https://aka.ms/flowmobiledocsandroid) -of [IOS](https://aka.ms/flowmobiledocsios) -apparaat met de mobiele app voor Microsoft flow.
* Moet worden aangewezen als fiatteur in een goedkeurings stroom.
* Aanvragen voor goed keuring in behandeling.

## <a name="view-pending-requests"></a>In behandeling zijnde aanvragen weer geven
1. Open de mobiele app voor Microsoft Flow.
   
    ![de mobiele app starten](./media/mobile-approvals/open-app.png)
2. Selecteer **goed keuringen** in de rechter bovenhoek.
   
    ![goed keuringen selecteren](./media/mobile-approvals/select-approvals.png)
3. Alle in behandeling zijnde goed keuringen weer geven:
   
    ![goedkeurings aanvragen in behandeling weer geven](./media/mobile-approvals/show-pending-approval-requests.png)

Als er geen goedkeurings aanvragen in behandeling zijn, maakt u een [goedkeurings stroom](modern-approvals.md), stelt u zichzelf in als fiatteur en vervolgens de stroom activeren. Goedkeurings aanvragen worden een paar seconden weer gegeven in het goedkeurings centrum en verzenden een aanvraag voor goed keuring.

## <a name="approve-requests-and-leave-an-optional-comment"></a>Aanvragen goed keuren en een optionele opmerking laten staan
1. Als u dit nog niet hebt gedaan, volgt u de voor gaande stappen om [aanvragen in behandeling weer te geven](mobile-approvals.md#view-pending-requests).
2. Selecteer **goed keuren** in de aanvraag die u wilt goed keuren.
   
    ![selecteren goed keuren](./media/mobile-approvals/select-approve.png)
3. (Optioneel) Selecteer **Opmerking toevoegen (optioneel)** .
   
    ![Selecteer een opmerking toevoegen](./media/mobile-approvals/select-add-comment.png)
   
    Voer een opmerking in het scherm **Opmerking toevoegen** in.
   
    ![Voer uw opmerking in](./media/mobile-approvals/enter-comment-for-approval.png)
4. Selecteer **bevestigen** in de rechter bovenhoek.
   
    ![Bevestig dat u klaar bent](./media/mobile-approvals/tap-confirm-button.png)
   
    Het scherm geslaagd wordt weer gegeven nadat uw beslissing is vastgelegd door de stroom.
   
    ![scherm geslaagd](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>Aanvragen afwijzen en een optionele opmerking plaatsen
Volg de [stappen voor het goed keuren van een aanvraag](mobile-approvals.md#approve-requests-and-leave-an-optional-comment), maar Selecteer in de tweede stap **afwijzen** .

## <a name="learn-more"></a>Meer informatie
[Moderne goedkeurings stromen maken](modern-approvals.md).

