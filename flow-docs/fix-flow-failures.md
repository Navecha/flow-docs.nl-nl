---
title: Problemen met een stroom oplossen | Microsoft Docs
description: Veelvoorkomende problemen voor stromen oplossen
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
ms.date: 01/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 30efc05dad57bc86a99b90e849fd1c9459930e54
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689474"
---
# <a name="troubleshooting-a-flow"></a>Problemen met een stroom oplossen
## <a name="identify-the-error"></a>De fout identificeren
Voordat u een probleem met een stroom kunt oplossen, moet u achterhalen waarom de stroom is mislukt. Klik of tik op het meldingenpictogram boven aan de webportal (of open het tabblad **Activiteit** in de mobiele app) en klik of tik vervolgens op uw stroom in de lijst die wordt weergegeven.

![Meldingen](./media/fix-flow-failures/notifications-toolbar.png)

De details voor de stroom worden weergegeven en er wordt voor minimaal één stap een rood uitroepteken weergegeven. Open deze stap en bekijk het foutbericht.

![Foutbericht](./media/fix-flow-failures/flow-run-failure.png)

## <a name="authentication-failures"></a>Verificatiefouten
In veel gevallen mislukken stromen vanwege een verificatiefout. Als u dit type foutbericht ontvangt, bevat het foutbericht de tekst **Niet gemachtigd** of wordt de foutcode **401** of **403** weergegeven. U kunt een verificatiefout doorgaans oplossen door de verbinding bij te werken.

1. Klik of tik boven aan de webportal op het tandwielpictogram om het menu **Instellingen** te open en klik of tik vervolgens op **Verbindingen**.
2. Schuif naar de verbinding waarvoor het foutbericht **Niet gemachtigd** wordt weergegeven.
3. Klik of tik naast de verbinding op de koppeling **Bevestig uw wachtwoord** in het bericht waarin wordt aangegeven dat de verbinding niet kan worden geverifieerd.
4. Controleer uw referenties door de instructies te volgen die worden weergegeven. Keer terug naar de fout voor de stroomuitvoering en klik of tik vervolgens op **Opnieuw verzenden**.
   
    De stroom moet nu volgens verwachting worden uitgevoerd.

## <a name="action-configuration"></a>Actieconfiguratie
Stromen mislukken ook wanneer een instelling in een actie van de stroom niet werkt zoals verwacht. In dit geval bevat het foutbericht de tekst **Ongeldige aanvraag** of **Niet gevonden** of wordt de foutcode **400** of **404** weergegeven.

In het foutbericht moet worden aangegeven hoe de fout kan worden verholpen. U moet op de knop **Bewerken** klikken of tikken en het probleem in de stroomdefinitie verhelpen. Sla de bijgewerkte stroom op en klik of tik op **Opnieuw verzenden** om de stroom nogmaals uit te voeren met de bijgewerkte configuratie.

## <a name="other-failures"></a>Andere fouten
Als de foutcode **500** of **502** wordt weergegeven, betreft het een tijdelijke fout. Klik of tik op **Opnieuw verzenden** om de stroom opnieuw uit te voeren.

Als u een ander probleem ondervindt, kunt u [een vraag aan onze community stellen](https://go.microsoft.com/fwlink/?LinkID=787467). Het is namelijk mogelijk dat anderen een vergelijkbaar probleem hebben gehad.

