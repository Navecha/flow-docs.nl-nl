---
title: Meer informatie over Microsoft Flow omgevingen | Microsoft Docs
description: Meer informatie over het gebruik van omgevingen om uw stromen te isoleren
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/27/2017
ms.author: sunayv
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8890e621d14fb0f2d00af4cdf767f05ddeab9f21
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547938"
---
# <a name="choosing-an-environment"></a>Een omgeving kiezen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

In dit artikel wordt beschreven hoe u Microsoft Flow **omgevingen** kunt maken en uw stromen, gateways, verbindingen en andere resources veilig en op een veilige wijze wilt isoleren.

U leert het volgende:

* De functies die omgevingen bieden.
* Scha kelen tussen omgevingen.
* Hoe u een stroom in de juiste omgeving maakt.

## <a name="environments-overview"></a>Overzicht van omgevingen

Wanneer u een stroom maakt, kiest u een omgeving voor het hosten van de stroom en de resources die door de stroom worden gebruikt. U kunt afzonderlijke omgevingen gebruiken voor verschillende scenario's.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Hier volgen enkele scenario's voor het gebruik van omgevingen

Omstandigheden|Advies
-----|-----
U wilt een stroom maken die gebruikmaakt van een verbinding met de micro soft-Common Data Service.|Plaats uw stroom en de Common Data Service in dezelfde omgeving. Dit zorgt ervoor dat alle gegevens in die omgeving worden geïsoleerd (isolatie grens).
U maakt een stroom voor de afdeling Human resources. U wilt er zeker van zijn dat alleen gebruikers in uw personeels afdeling toegang hebben tot de stroom.|Maak een omgeving en voeg alleen de HR-gebruikers toe. Plaats de stroom en alle andere resources die door de stroom in deze omgeving worden gebruikt.
Er zijn gebruikers in Europa die gebruikmaken van een stroom om share point-gegevens weer te geven.|Maak een omgeving in Europa en maak vervolgens uw stroom en de share point-verbinding. Deze Europa-omgeving biedt de Europese gebruikers de beste prestaties, omdat alle resources lokaal zijn voor Europa (gegevens locatie).

Als u omgevingen wilt maken, moet u een Microsoft Flow beheerder zijn. Beheerders bepalen wie toegang heeft tot omgevingen. Zie het onderwerp [omgevingen beheren](environments-overview-admin.md) voor meer informatie over hoe u omgevingen kunt maken en beheren.

## <a name="switching-environments"></a>Scha kelen tussen omgevingen

Met Microsoft Flow kunt u gemakkelijk tussen omgevingen scha kelen. Wanneer u een andere omgeving selecteert, worden alleen de items weer geven die in die specifieke omgevingen zijn gemaakt. u ziet of heeft geen toegang tot items in een andere omgeving.

Hier volgt een voor beeld.

U hebt een stroom gemaakt met de naam *NewEmployee* in de omgeving *Human Resources* . In [Microsoft flow](https://flow.microsoft.com)opent u de *verkoop* omgeving. De *NewEmployee* -stroom wordt niet weer gegeven. Als u de *NewEmployee* -stroom wilt zien, opent u de omgeving *Human Resources* . Houd er rekening mee dat dezelfde regels van toepassing zijn op alle items die u in de omgeving hebt gemaakt, waaronder verbindingen, gateways, stromen en nog veel meer.

Volg deze stappen om te scha kelen tussen omgevingen:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com).
1. In de rechter bovenhoek ziet u een afbeelding die uw profiel voor stelt.

   ![Profiel afbeelding](./media/environments-overview-maker/default-environment.png)

1. Selecteer de installatie kopie. Er wordt een vervolg keuzelijst weer gegeven met alle omgevingen die voor u beschikbaar zijn. De omgeving waarin u momenteel bent aangemeld, wordt gecontroleerd:

   ![afbeelding van de lijst met omgevingen](./media/environments-overview-maker/all-environments.png)
1. Als u wilt overschakelen naar een andere omgeving, selecteert u die omgeving in de lijst:

   ![Selecteer een omgeving waarnaar u wilt overschakelen](./media/environments-overview-maker/select-europe.png)
1. Microsoft Flow overschakelen naar de nieuwe omgeving.

## <a name="create-flows-in-the-right-environment"></a>Stromen maken in de juiste omgeving

Voordat u een stroom maakt, selecteert u de omgeving waarin u de stroom en de bijbehorende resources gaat toevoegen.

> [!NOTE]
> Als u een stroom in de verkeerde omgeving maakt, moet u deze verwijderen en vervolgens in de juiste omgeving maken.

Houd rekening met de volgende factoren wanneer u een omgeving kiest voor het hosten van uw stromen:

* U kunt alleen gateways maken in de standaard omgeving. Als u dus een gateway wilt gebruiken om uw stroom te verbinden met on-premises gegevens, moet u de standaard omgeving gebruiken.
* Micro soft Common Data Service-data bases zijn gekoppeld aan een specifieke omgeving. Als u dus een stroom wilt maken die gebruikmaakt van de Common Data Service, moet u de stroom maken in de omgeving die als host fungeert voor de-data base.
* U ziet alle omgevingen waarin u resources kunt bewerken. U moet echter een beheerder vragen u als maker toe te voegen aan alle omgevingen waarin u stromen wilt maken.

> [!NOTE]
> U kunt altijd stromen maken in de standaard omgeving.

## <a name="next-steps"></a>Volgende stappen

* [Een stroom maken op basis van een sjabloon](get-started-logic-template.md)
* [Een stroom maken](get-started-logic-flow.md)
* [Overzicht van de omgeving voor beheerders](environments-overview-admin.md)
