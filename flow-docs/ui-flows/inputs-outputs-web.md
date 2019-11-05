---
title: Invoer en uitvoer gebruiken in webgebruikersinterfaces | Microsoft Docs
description: Invoer en uitvoer gebruiken in webgebruikersinterface flows.
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8506846f8081819ad42c70e820397bdc43536e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549341"
---
# <a name="use-inputs-and-outputs-in-web-ui-flows"></a>Invoer en uitvoer gebruiken in webgebruikersinterface-stromen

[Dit onderwerp bevat voorlopige documentatie en kan worden gewijzigd.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs-for-a-web-ui-flow"></a>Invoer definiëren voor een web-UI-stroom

Met invoer van een UI-flow kunt u informatie door geven uit een externe bron, zoals een Data Base of een andere UI-stroom, naar de verouderde doel software die u wilt automatiseren.

Elke variabele die wordt gebruikt (gelezen) vóór de initialisatie (meestal uitgevoerd via **Store** -opdrachten) wordt automatisch behandeld als een invoer variabele en wordt weer gegeven in de werk **stroom gebruikers interface uitvoeren voor** webacties kaart.

U kunt variabelen gebruiken via de interpolatie van de teken reeks, bijvoorbeeld het doel veld van de opdracht op ' id =\${elementId} ' wijzigen. Of wijzig het veld waarde van het type opdracht in\${inputText}.

De opdracht, **Stel de venster grootte** en het opdracht **type** in de volgende scherm afbeeldingen gebruiken niet-geïnitialiseerde variabelen \${width}, \${Height} en \${Search}. Deze variabelen worden invoer waarden.

![Venster grootte en-type instellen](../media/inputs-outputs-web/f05cb445dad212aaf395b66ba969622c.png "Venster grootte en-type instellen")

U kunt variabelen rechtstreeks in sommige opdrachten gebruiken, bijvoorbeeld: de velden doel/waarde van forEach-opdracht zijn beide variabelen. u hoeft deze niet te omgeven door\${}.

Raadpleeg de naslag informatie voor [selenium-opdrachten](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) om te bepalen welke opdrachten de naam van een variabele rechtstreeks krijgen.

## <a name="define-outputs-for-a-web-ui-flow"></a>Uitvoer definiëren voor een web-UI-stroom

Een variabele die in het selenium-script is gedefinieerd, wordt automatisch een uitvoer waarde. Gebruik de volgende opdrachten om variabelen te declareren:

[Store](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store)

[Archief kenmerk](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-attribute)

[JSON opslaan](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-json)

[Winkel titel](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-title)

[waarde opslaan](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-value)

[Ingang voor archief venster](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-window-handle)

[Aantal Store-XPath](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-xpath-count)

[Voer script](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#execute-script)uit (Voeg de syntaxis ' return ' toe om het object dat u wilt opslaan aan het einde van het script te retour neren)

## <a name="next-steps"></a>Volgende stappen

- Meer informatie over het [maken van front-UI-stromen](create-web.md).
- Meer informatie over het [activeren van UI-stromen](run-ui-flow.md).

