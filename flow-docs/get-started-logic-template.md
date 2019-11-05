---
title: Een stroom maken op basis van een sjabloon | Microsoft Docs
description: Een stroom maken op basis van een van de verschillende ingebouwde sjablonen.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 874a942c4422fb402bc564609aff6ea06449ef78
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548231"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>Een stroom maken op basis van een sjabloon in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Maak een stroom op basis van een van de vele ingebouwde sjablonen die bijvoorbeeld een bericht met een toegestane vertraging kunnen verzenden wanneer uw manager u een e-mail stuurt in Office 365.

**Opmerking:** [Maak een nieuwe stroom](get-started-logic-flow.md) als u al een proces in gedachte hebt en er geen sjabloon voor hebt gevonden.

**Vereisten**

* Een account op [flow.Microsoft.com](https://flow.microsoft.com)
* Een toegestane vertragings account
* Office 365-referenties

## <a name="choose-a-template"></a>Een sjabloon kiezen
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Selecteer in [flow.Microsoft.com](https://flow.microsoft.com)de optie **sjablonen** in de bovenste navigatie balk.
2. Typ **toegestane vertraging**in de zoek balk en selecteer vervolgens het zoek pictogram.
3. U ziet alleen sjablonen die betrekking hebben op toegestane vertraging, zodat u nu **een bericht verzenden in de toegestane vertraging kunt selecteren wanneer mijn manager mij een E-mail stuurt**.
   
    ![De optie Nieuw in de linkernavigatiebalk](./media/get-started-logic-template/select-template.png)
4. Controleer of deze sjabloon is wat u wilt en selecteer vervolgens **deze sjabloon gebruiken**.
5. Als u niet bent aangemeld bij Office of een toegestane vertraging, selecteert u **Aanmelden** en volgt u de aanwijzingen.
   
    ![Lijst met verbindingen die voor de sjabloon zijn vereist](./media/get-started-logic-template/confirm-connections.png)
6. Nadat u uw verbindingen hebt bevestigd, selecteert u **door gaan**.
   
    Uw stroom wordt weer gegeven, met daarin elke actie met een oranje titel balk.
   
    ![Standaard gebeurtenissen en acties op basis van een sjabloon](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Uw stroom aanpassen
1. Selecteer de titel balk voor een gebeurtenis om deze uit te vouwen en pas deze aan (bijvoorbeeld door een filter op te geven voor het e-mail bericht dat u interesset).
2. Acties waarvoor invoer moet worden uitgevoerd, worden automatisch uitgevouwen.
   
    Zo wordt de actie **bericht posten** uitgevouwen omdat u een kanaal moet invoeren, zoals uw *\@gebruikers naam*. U kunt ook de inhoud van het bericht aanpassen. Het bericht bevat standaard alleen het onderwerp, maar u kunt ook andere informatie opnemen.
   
    ![Kanaal opgeven voor toegestane vertraging](./media/get-started-logic-template/specify-keyword.png)
3. Geef aan de bovenkant van het scherm een naam voor de stroom op en selecteer vervolgens **stroom maken**.
4. Ten slotte, als u tevreden bent met uw stroom, selecteert u **gereed**.
   
    ![Knop gereed](./media/get-started-logic-template/done.png)

Als uw manager u nu een e-mail stuurt, ontvangt u een bericht over de toegestane vertraging dat de door u opgegeven informatie bevat.

## <a name="next-steps"></a>Volgende stappen
* [Bekijk uw stroom in actie](see-a-flow-run.md)
* [Uw eigen sjabloon publiceren](publish-a-template.md)
* [Een sjabloon gebruiken voor de Common Data Service](common-data-model-intro.md)
* Aan de [slag met team stromen](create-team-flows.md) en anderen uitnodigen om samen met u stromen te ontwerpen.

