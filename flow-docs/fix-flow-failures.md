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
ms.date: 05/01/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0e151f3c5cd69fe07263e5fa36d46eb3b8be19f5
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64992741"
---
# <a name="troubleshooting-a-flow"></a>Problemen met een stroom oplossen

## <a name="repair-tips-in-email"></a>Tips voor herstel in e-mailbericht

Tips voor herstel worden verzonden naar de eigenaars van stromen via e-mail wanneer een stroom mislukt. Deze e-mailberichten herstellen tips bevatten specifieke, bruikbare feedback over bepaalde fouten. Bijvoorbeeld, een veelvoorkomende fout is instellen van een stroom die probeert op te halen van de manager van een persoon in Office 365, maar er geen manager geconfigureerd in Azure Active Directory (Azure AD is). Als dit of verschillende andere voorwaarden ertoe leiden de stroom dat mislukt, krijgt u een e-mailadres tips herstellen als volgt:

![Tips voor herstel](media/fix-flow-failures/repair-tips-email.png)

Het herstel tips e-mailbericht bevat de volgende secties:

Naam|Beschrijving
---|---
tijd|Geeft de tijd die de stroom voor het eerst is mislukt.
Wat is er gebeurd|Bevat een beschrijving van het probleem dat de fout in de stroom heeft veroorzaakt.
Hoe los ik|Tips biedt voor het oplossen van het probleem dat ertoe leiden dat de fout in de stroom.
Tips voor probleemoplossing|Meer informatie, waaronder het aantal keren dat de stroom is mislukt en een koppeling om opnieuw te proberen de stroom met de dezelfde invoergegevens bevat.

Selecteren om op te lossen de gerapporteerde fouten, **mijn stroom oplossen** en volg de stappen in het e-mailbericht herstellen tips.

Herstel tips e-mailberichten zijn optioneel. Als u niet wilt ontvangen, alleen deze uitschakelen via het menu eigenschappen voor de specifieke stroom.

Als de stroom is mislukt, kunt u deze ook rechtstreeks in Microsoft Flow oplossen.  Hier volgen enkele veelvoorkomende foutscenario's en tips over hoe u deze kunt oplossen.

## <a name="identify-the-error"></a>De fout identificeren
Voordat u een probleem met een stroom kunt oplossen, moet u achterhalen waarom de stroom is mislukt. Klik of tik op het meldingenpictogram boven aan de webportal (of open het tabblad **Activiteit** in de mobiele app) en klik of tik vervolgens op uw stroom in de lijst die wordt weergegeven.

![Meldingen](./media/fix-flow-failures/notifications-toolbar.png)

De details voor de stroom worden weergegeven en er wordt voor minimaal één stap een rood uitroepteken weergegeven. Open deze stap en bekijk het foutbericht.

![Foutbericht](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Verificatiefouten
In veel gevallen mislukken stromen vanwege een verificatiefout. Als u dit type foutbericht ontvangt, bevat het foutbericht de tekst **Niet gemachtigd** of wordt de foutcode **401** of **403** weergegeven. U kunt een verificatiefout doorgaans oplossen door de verbinding bij te werken.

1. Aan de bovenkant van de web-portal, klik of tik op het tandwielpictogram te openen de **instellingen** in het menu en klik of tik **verbindingen**.
2. Schuif naar de verbinding waarvoor het foutbericht **Niet gemachtigd** wordt weergegeven.
3. Klik of tik naast de verbinding op de koppeling **Bevestig uw wachtwoord** in het bericht waarin wordt aangegeven dat de verbinding niet kan worden geverifieerd.
4. Controleer uw referenties door de instructies te volgen die worden weergegeven. Keer terug naar de fout voor de stroomuitvoering en klik of tik vervolgens op **Opnieuw verzenden**.
   
    De stroom moet nu volgens verwachting worden uitgevoerd.

## <a name="action-configuration"></a>Actieconfiguratie
Stromen mislukken ook wanneer een instelling in een actie van de stroom niet werkt zoals verwacht. In dit geval bevat het foutbericht de tekst **Ongeldige aanvraag** of **Niet gevonden** of wordt de foutcode **400** of **404** weergegeven.

In het foutbericht moet worden aangegeven hoe de fout kan worden verholpen. U moet op de knop **Bewerken** klikken of tikken en het probleem in de stroomdefinitie verhelpen. Sla de bijgewerkte stroom op en klik of tik op **Opnieuw verzenden** om de stroom nogmaals uit te voeren met de bijgewerkte configuratie.

## <a name="other-failures"></a>Andere fouten
Als de foutcode **500** of **502** wordt weergegeven, betreft het een tijdelijke fout. Klik of tik op **Opnieuw verzenden** om de stroom opnieuw uit te voeren.

## <a name="getting-help-from-support-or-the-community"></a>Hulp krijgen van de ondersteuning of de community

Als u hulp nodig hebt, kunt u onze **Self Help** opties, of u kunt **om hulp vragen** van anderen.

### <a name="self-help"></a>Zelfondersteuning 

1. Ga naar de [ondersteuningssite](https://flow.microsoft.com/support/).
1. Ga naar de **Self Help** categorie en selecteert u een van de opties voor zelfhulp.

    ![Vragen om help-sectie. Neem contact op met ondersteuning.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Vragen om hulp van anderen

1. Ga naar de [ondersteuningssite](https://flow.microsoft.com/support/).
1. Selecteer **contact opnemen met ondersteuning** in de **om hulp vragen** sectie.
    
    ![Vragen om help-sectie. Neem contact op met ondersteuning.](media/fix-flow-failures/ask-for-help.png)

1. Voltooid de **probleemtype**, **categorie**, en de **laat ons weten wat u nodig hebt bij het** velden en selecteer vervolgens **oplossingen**. 

1. U ziet dat de **oplossingen** sectie wordt weergegeven nadat u hebt geselecteerd **oplossingen**. Het bevat een lijst met resultaten die u gebruiken kunt om het probleem dat u ondervindt. 

    ![Details van de geïntegreerde hulpprogramma](media/fix-flow-failures/integrated-helper-details.png)

Als u hulp nodig met een probleem, Help-informatie is beschikbaar via onze [community](https://go.microsoft.com/fwlink/?LinkID=787467) en Microsoft. 

