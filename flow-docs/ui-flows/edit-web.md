---
title: Meer informatie over het bewerken van webgebruikersinterfaces | Microsoft Docs
description: Meer informatie over het bewerken van webgebruikersinterface flows.
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
ms.openlocfilehash: 263f8634b2435217fba436e68ab7e744dd3b52b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549571"
---
# <a name="edit-web-ui-flows"></a>Web-UI-stromen bewerken

[Dit onderwerp bevat voorlopige documentatie en kan worden gewijzigd.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Webgebruikersinterface flows automatiseren websites die worden uitgevoerd in de [volgende versie van micro soft Edge](https://www.microsoftedgeinsider.com/) of Google Chrome. Nadat u [een web-UI-stroom hebt gemaakt](create-web.md), moet u deze mogelijk bewerken. Volg de stappen in dit document voor meer informatie over het bewerken van uw Web-UI-stromen.

## <a name="edit-in-selenium-ide"></a>Bewerken in Selenium IDE

Gebruik de Selenium IDE om uw Web-UI-stromen te bewerken.

>[!NOTE]
>Bewerken in de Selenium IDE is gericht op geavanceerde gebruikers en ontwikkel aars.

U kunt de selenium- [opdrachten](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) raadplegen voor informatie over het bewerken van het script.

De Selenium-IDE stelt verschillende selecters en een standaard waarde voor voor het instellen van een element van de gebruikers interface. U kunt ook een nieuwe selector definiëren als geen van de voorgestelde selecters geschikt is. Dit gebeurt meestal wanneer de HTML-structuur van de website zeer dynamisch is.

Hier volgt een voor beeld van mogelijke selecters die de Selenium IDE heeft geïdentificeerd:

![Mogelijke selecters](../media/edit-web/possible-selectors.png "Mogelijke selecters")

## <a name="accessing-a-property-of-an-object-variable-or-item-of-an-array-variable"></a>Toegang krijgen tot een eigenschap van een object variabele of een item van een matrix variabele * *

Met deze geavanceerde functie kunt u de syntaxis zoals \${foo. Bar} gebruiken om toegang te krijgen tot de eigenschap bar van het object foo. U kunt ook naar de eigenschap staaf van Foo schrijven door Foo. bar te gebruiken als de waarde van de eigenschap value in een Store-opdracht. U kunt ook een syntaxis zoals \${foo [0]} gebruiken om toegang te krijgen tot het item op index 0 in de Foo-matrix.

## <a name="next-steps"></a>Volgende stappen

- [Web-UI-stromen maken](create-web.md)
- [UI-stromen uitvoeren](run-ui-flow.md)
