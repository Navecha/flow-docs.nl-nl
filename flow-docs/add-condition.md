---
title: Een voorwaarde toevoegen aan een stroom | Microsoft Docs
description: Stel in dat een stroom een of meer taken alleen uitvoert als er aan een voorwaarde wordt voldaan.
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/17/2017
ms.author: stepsic
ms.openlocfilehash: 135b3509a9412f7674a1e9cb2ada86ebd2bb9f4f
ms.sourcegitcommit: 122870842a07183ab3b90e07d99b60d822d6c5ae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/18/2017
---
# <a name="add-a-condition-to-a-flow"></a>Een voorwaarde toevoegen aan een stroom

Stel in dat een stroom een of meer taken alleen uitvoert als er aan een voorwaarde wordt voldaan. Stel bijvoorbeeld in dat u alleen een e-mail ontvangt als een tweet met een trefwoord ten minste tien keer wordt geretweet.

## <a name="prerequisites"></a>Vereisten

* [Een stroom maken](get-started-logic-template.md) op basis van een sjabloon: in deze zelfstudie [wordt deze sjabloon gebruikt](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) als voorbeeld

## <a name="add-a-condition"></a>Een voorwaarde toevoegen

1. Ga naar [Microsoft Flow](https://flow.microsoft.com) en selecteer **Mijn stromen** in de navigatiebalk bovenin.

    Als u nog niet bent aangemeld, doet u dat nu.

1. Selecteer in de lijst met stromen een van de stromen die u hebt gemaakt.

    In deze zelfstudie wordt een voorbeeld gebruikt met een Twitter-trigger en een SharePoint-actie.

1. Selecteer **Stroom bewerken**.

1. Selecteer **Nieuwe stap** onder de laatste actie.

1. Selecteer **Een voorwaarde toevoegen**.

    ![Voorwaardeknop](./media/add-condition/add-condition.png)

1. In de kaart **Voorwaarde** selecteert u een leeg gebied in het vak aan de linkerkant.

    De lijst **Dynamische inhoud** wordt geopend.

1. Selecteer de parameter **Aantal retweets** om deze toe te voegen aan het vak.

1. In het vak in het midden van de kaart **Voorwaarde** selecteert u **is groter dan of gelijk aan**.

1. Typ **10** in het vak aan de rechterkant.

    ![Het vak OBJECTNAAM met een parameter](./media/add-condition/specify-condition.png)

1. Selecteer de kop van de actie die u in de voorwaarde wilt gebruiken (zoals **Item maken**) en sleep dit tot onder de tekst **Indien ja**.

    Wanneer u de cursor loslaat, wordt de actie naar dat vak verplaatst.

    ![Actie slepen](./media/add-condition/drag-action.png)

1. Configureer de actie naar wens.

1. Sla de stroom op.

## <a name="edit-in-advanced-mode"></a>Bewerken in de geavanceerde modus

U kunt ook **Bewerken in geavanceerde modus** selecteren om geavanceerdere voorwaarden te schrijven. U kunt hier elke expressie van de *Definitietaal van de werkstroom* in de geavanceerde modus gebruiken. Informatie over alle beschikbare [expressies](https://msdn.microsoft.com/library/azure/mt643789.aspx).

## <a name="next-steps"></a>Volgende stappen

Informatie over hoe u [expressies gebruikt](use-expressions-in-conditions.md) in voorwaarden in de geavanceerde modus.
