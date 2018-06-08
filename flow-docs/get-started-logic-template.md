---
title: Een stroom maken op basis van een sjabloon | Microsoft Docs
description: U kunt een stroom maken op basis van een van de ingebouwde sjablonen.
services: ''
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
ms.author: anneta
ms.openlocfilehash: b755d9abe70740a97ad85aaa60b8a3f4685a7b26
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31008375"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>een stroom maken op basis van een sjabloon in Microsoft Flow
U kunt een stroom maken op basis van een van de vele ingebouwde sjablonen, bijvoorbeeld de sjabloon waarmee u een Slack-bericht ontvangt wanneer uw manager u een e-mail stuurt in Office 365.

**Opmerking:** als u al een proces in gedachte hebt en hiervoor geen bijpassende sjabloon kunt vinden, kunt u [een volledig nieuwe stroom maken](get-started-logic-flow.md).

**Vereisten**

* Een account op [flow.microsoft.com](https://flow.microsoft.com)
* Een Slack-account
* Office 365-referenties

## <a name="choose-a-template"></a>Een sjabloon kiezen
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Ga naar [flow.microsoft.com](https://flow.microsoft.com) en selecteer **Sjablonen** bovenin op de navigatiebalk.
2. Typ **Slack** op de zoekbalk en selecteer vervolgens het zoekpictogram.
3. U ziet alleen de sjablonen die zijn gerelateerd aan Slack. Selecteer **Een bericht in Slack verzenden wanneer mijn manager mij een e-mail stuurt**.
   
    ![Optie Nieuw in de linkernavigatiebalk](./media/get-started-logic-template/select-template.png)
4. Controleer of deze sjabloon doet wat u wilt dat die doet en selecteer vervolgens **Deze sjabloon gebruiken**.
5. Als u niet bent aangemeld bij Office of Slack, selecteert u **Aanmelden** en volgt u de prompts.
   
    ![Lijst met verbindingen die nodig zijn voor de sjabloon](./media/get-started-logic-template/confirm-connections.png)
6. Selecteer **Doorgaan** nadat u uw verbindingen hebt bevestigd.
   
    Uw stroom wordt weergegeven, met alle acties waarvoor een oranje titelbalk wordt afgebeeld.
   
    ![Standaardgebeurtenissen en -acties op basis van een sjabloon](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Uw stroom aanpassen
1. Selecteer de titelbalk van een gebeurtenis om deze uit te vouwen en pas de gebeurtenis vervolgens aan (bijvoorbeeld door een filter op te geven voor het e-mailbericht waarin u bent geïnteresseerd).
2. Acties waarvoor invoer nodig is, worden automatisch uitgevouwen.
   
    Zo wordt de actie **Bericht posten** uitgevouwen omdat u een kanaal moet invoeren, bijvoorbeeld *\@gebruikersnaam*. U kunt ook de inhoud van het bericht aanpassen. Standaard bevat het bericht alleen het onderwerp, maar u kunt ook andere informatie opnemen.
   
    ![Kanaal voor Slack opgeven](./media/get-started-logic-template/specify-keyword.png)
3. Ga naar de bovenkant van het scherm, geef uw stroom een naam en selecteer vervolgens **Stroom maken**.
4. Als u tevreden bent met de stroom, selecteert u **Gereed**.
   
    ![Knop Gereed](./media/get-started-logic-template/done.png)

Wanneer uw manager u nu een e-mailbericht stuurt, ontvangt u een Slack-bericht met de informatie die u hebt opgegeven.

## <a name="next-steps"></a>Volgende stappen
* [Uw stroom in actie zien](see-a-flow-run.md)
* [Uw eigen sjabloon publiceren](publish-a-template.md)
* [Een sjabloon gebruiken voor de Microsoft Common Data-service](common-data-model-intro.md)
* [Aan de slag gaan met teamstromen](create-team-flows.md) en anderen uitnodigen om samen met u stromen te ontwerpen.

