---
title: Een voor waarde toevoegen aan een stroom | Microsoft Docs
description: Opgeven dat een stroom een of meer taken alleen uitvoert als een voor waarde waar is.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c67991a008047b2c8c58de3b9ae8833a5874543
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544721"
---
# <a name="add-a-condition-to-a-flow"></a>Een voor waarde toevoegen aan een stroom
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Opgeven dat een stroom een of meer taken alleen uitvoert als een voor waarde waar is. Geef bijvoorbeeld op dat u alleen een e-mail bericht ontvangt als een tweet dat een sleutel woord bevat, ten minste tien keer is geretweet.

## <a name="prerequisites"></a>Vereisten

* [Een stroom maken](get-started-logic-template.md) op basis van een sjabloon: in deze zelf studie [wordt deze sjabloon gebruikt](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) als voor beeld

## <a name="add-a-condition"></a>Een voor waarde toevoegen

1. Selecteer in [Microsoft flow](https://flow.microsoft.com) **mijn stromen** in de bovenste navigatie balk.

    U moet zich mogelijk aanmelden als u nog niet bent aangemeld.

1. Selecteer een van de stromen die u hebt gemaakt in de lijst met stromen.

    In deze zelf studie wordt een voor beeld met een Twitter-trigger en een share point-actie gebruikt.

1. Selecteer **stroom bewerken**.

1. Selecteer **nieuwe stap**onder de laatste actie.

1. Selecteer **een voor waarde toevoegen**.

    ![Knop voor waarde](./media/add-condition/add-condition.png)

1. Selecteer op de kaart **voor waarde** een leeg gebied in het vak aan de linkerkant.

    De lijst met **dynamische inhoud** wordt geopend.

1. Selecteer de para meter **aantal retweets** om deze toe te voegen aan het vak.

1. Selecteer in het vak midden van de kaart **voor waarde** de optie **is groter dan of gelijk aan**.

1. Voer in het vak aan de rechter kant **10**in.

    ![Het vak OBJECT naam met een para meter](./media/add-condition/specify-condition.png)

1. Selecteer de koptekst van de actie die u in de voor waarde wilt gebruiken (zoals **item maken**) en sleep deze onder de tekst die gelezen wordt **als ja**.

    Wanneer u de cursor loslaat, wordt de actie verplaatst naar dat vak.

    ![Actie slepen](./media/add-condition/drag-action.png)

1. Configureer de actie als dat nodig is.

1. Sla de stroom op.

## <a name="edit-in-advanced-mode"></a>Bewerken in geavanceerde modus

U kunt ook **bewerken in geavanceerde modus** selecteren om meer geavanceerde voor waarden te schrijven. U kunt elke expressie uit de *werk stroom definitie taal* in de geavanceerde modus gebruiken. Meer informatie over alle beschik bare [expressies](https://msdn.microsoft.com/library/azure/mt643789.aspx).

## <a name="next-steps"></a>Volgende stappen

Meer informatie over het [gebruik van expressies](use-expressions-in-conditions.md) in voor waarden in de geavanceerde modus.
