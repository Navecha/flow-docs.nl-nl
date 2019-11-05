---
title: Share point-pagina goedkeuringen beheren met Microsoft Flow | Microsoft Docs
description: Meer informatie over het beheren van share point-pagina goedkeuringen met Microsoft Flow..
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
ms.openlocfilehash: 1b328b604f9b199c2303dde3a0aa00898f188ada
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547636"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>Share point-pagina goedkeuringen beheren met Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Share point-site beheerders kunnen Microsoft Flow gebruiken om nieuwe of bijgewerkte site pagina's te moeten goed keuren voordat ze worden gepubliceerd.

In dit artikel leert u hoe u uw share point-site kunt configureren voor het gebruik van een stroom om te vereisen dat wijzigingen in de site worden goedgekeurd voordat ze live gaan.

## <a name="configure-sharepoint-for-page-approvals"></a>Share point configureren voor het goed keuren van pagina's

### <a name="prerequisites"></a>Vereisten 

U moet een share point-site beheerder zijn om de activiteiten in dit artikel uit te voeren.

1. Meld u aan bij share point als een site beheerder.
1. Selecteer **pagina's** in de navigatie balk.

    ![Pagina goedkeurings stroom selecteren](media/customize-sharepoint-page-approvals/pages.png)

1. Selecteer **stroom** en selecteer vervolgens **pagina goedkeurings stroom configureren**.
    
    ![Pagina goedkeurings stroom selecteren](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Geef een **stroom naam**op, ten minste één naam in het vak **goed keurders** , en selecteer vervolgens **maken**.
    
    ![Pagina goedkeurings stroom selecteren](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Dat is alles! Telkens wanneer een pagina wordt toegevoegd of gewijzigd, gaat een goedkeurings aanvraag naar de **goed keurders** die u in de stroom hebt opgenomen.

De pagina goedkeurings stroom is net als elke andere stroom, zodat deze wordt weer gegeven op het tabblad **mijn stromen** .

![Pagina goedkeurings stroom selecteren](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Een pagina voor goed keuring verzenden

Nu u een pagina goedkeurings stroom hebt gemaakt, moet iedereen die een pagina toevoegt of wijzigt, het volgende doen:

 - Breng een wijziging aan in de site (bijvoorbeeld een nieuwe pagina toevoegen) en sla de wijziging op.

     ![Pagina voor goed keuring verzenden](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Wacht totdat iemand de wijziging goedkeurt.
    
    ![Pagina voor goed keuring verzenden](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Een pagina goed keuren

Goed keurders ontvangen een e-mail wanneer er een aanvraag voor het goed keuren van pagina's is. Ze kunnen de aanvragen rechtstreeks in het e-mail bericht goed keuren (als hun e-mailclient actie berichten ondersteunt) of de pagina openen vanuit het e-mail bericht om te controleren en vervolgens de pagina in share point goed keuren.

## <a name="customize-page-approval-flows"></a>Pagina goedkeurings stromen aanpassen

Omdat pagina goedkeuringen Microsoft Flow achter de schermen worden gebruikt, is de pagina goedkeurings stroom beschikbaar voor site-eigen aren om aangepaste bedrijfs logica in de stroom te wijzigen en toe te voegen. Als u de stroom wilt wijzigen, kan de eigenaar van de site **stromen** selecteren en vervolgens **weer geven van uw stromen** in de pagina bibliotheek selecteren om de goedkeurings stroom voor pagina's te vinden.

## <a name="learn-more"></a>Meer informatie

- [Pagina goedkeurings stroom](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Pagina goedkeuring configureren](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
