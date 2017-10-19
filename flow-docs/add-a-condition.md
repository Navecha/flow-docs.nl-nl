---
title: Een voorwaarde toevoegen aan een stroom | Microsoft Docs
description: "Stel in dat een stroom één of meer taken alleen uitvoert als aan een bepaalde voorwaarde wordt voldaan."
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
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: 1291b32f001be211acddbf1c83f3b1bdf03f2ac3
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="add-a-condition-to-a-flow"></a>Een voorwaarde toevoegen aan een stroom
Stel in dat een stroom één of meer taken alleen uitvoert als aan een bepaalde voorwaarde wordt voldaan. Stel bijvoorbeeld in dat u alleen een e-mail ontvangt als een tweet met een trefwoord ten minste tien keer wordt geretweet.

**Vereisten**

* [Een stroom](get-started-logic-template.md) maken van een sjabloon: in deze zelfstudie [wordt deze sjabloon gebruikt](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) als voorbeeld

## <a name="add-a-condition"></a>Een voorwaarde toevoegen
1. Ga naar [flow.microsoft.com](https://flow.microsoft.com) en selecteer **Mijn stromen** op de navigatiebalk bovenin.
2. Selecteer in de lijst met stromen een stroom die u hebt gemaakt. In deze zelfstudie wordt een voorbeeld gebruikt met een Twitter-trigger en een SharePoint-actie.
3. Maak de laatste actie ongedaan en selecteer de knop **Nieuwe stap**.
4. Selecteer **Een voorwaarde toevoegen**.
   
    ![Voorwaardeknop](./media/add-a-condition/add-condition.png)
5. Selecteer een leeg gebied in **Objectnaam** en selecteer **Dynamische inhoud toevoegen** om het menu voor dynamische inhoud te openen.
6. Selecteer de parameter **Aantal retweets** om deze toe te voegen aan het vak.
7. In het vak **Relatie** selecteert u de optie **is groter dan of gelijk aan**.
8. In het vak **Waarde** typt u **10**.
   
    ![Het vak OBJECTNAAM met een parameter](./media/add-a-condition/specify-condition.png)
9. Klik op de kop van de actie die u in de voorwaarde wilt hebben (zoals **Item maken**) en sleep dit onder de tekst **IF YES** door. Wanneer u de cursor loslaat, wordt de actie in het vak geplaatst.
   
    ![Actie slepen](./media/add-a-condition/drag-action.png)
10. Sla de stroom op.

## <a name="edit-in-advanced-mode"></a>Bewerken in de geavanceerde modus
U kunt ook de koppeling **Bewerken in geavanceerde modus** selecteren om meer geavanceerde voorwaarden te schrijven. U kunt hier elke expressie van de *Definitietaal van de werkstroom* gebruiken. [Meer informatie over](https://msdn.microsoft.com/library/azure/mt643789.aspx) welke functies beschikbaar zijn.

