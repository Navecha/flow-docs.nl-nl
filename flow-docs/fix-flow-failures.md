---
title: Problemen met een stroom oplossen | Microsoft Docs
description: Een aantal van de meest voorkomende oorzaken voor het mislukken van stromen oplossen
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
ms.openlocfilehash: 2981c125d722cb766a1cc840f404d84dfa57ac96
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547877"
---
# <a name="troubleshooting-a-flow"></a>Problemen met een stroom oplossen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

## <a name="repair-tips-in-email"></a>Tips voor het oplossen van problemen in e-mail

Herstel tips worden via e-mail naar flow-eigen aren verzonden wanneer een stroom mislukt. Deze e-mails met reparatie tips bevatten specifieke, actie bare feedback over bepaalde fouten. Er is bijvoorbeeld een gemeen schappelijke fout opgetreden bij het instellen van een stroom die een persoons manager in Office 365 probeert te krijgen, maar er is geen manager geconfigureerd in Azure Active Directory (Azure AD). Als deze of andere voor waarden ervoor zorgen dat uw stroom mislukt, ontvangt u een e-mail bericht over de reparatie tips, zoals hieronder:

![Tips voor herstellen](media/fix-flow-failures/repair-tips-email.png)

Het e-mail bericht met reparatie tips bevat de volgende secties:

Naam|Beschrijvingen
---|---
Tegelijk|Geeft de tijd weer waarop de stroom voor het eerst is mislukt.
Wat is er gebeurd|Hierin wordt een beschrijving gegeven van het probleem dat de fout in de stroom heeft veroorzaakt.
Hoe kan ik oplossen|Bevat tips voor het oplossen van het probleem dat de stroom veroorzaakt.
Tips voor probleem oplossing|Bevat details, inclusief het aantal keren dat de stroom is mislukt en een koppeling om de stroom opnieuw uit te voeren met dezelfde invoer gegevens.

Als u de gerapporteerde fouten wilt verhelpen, selecteert u **mijn stroom corrigeren** en volgt u de stappen in het e-mail bericht met reparatie tips.

E-mails met reparatie tips zijn optioneel. Als u deze niet wilt ontvangen, schakelt u deze uit in het menu eigenschappen voor de specifieke stroom.

Als uw stroom uitvalt, kunt u deze ook rechtstreeks in Microsoft Flow oplossen.  Hier volgen enkele veelvoorkomende fout scenario's en tips voor het oplossen ervan.

## <a name="identify-the-error"></a>De fout identificeren
Voordat u een stroom kunt oplossen, moet u aangeven waarom deze is mislukt. Klik of tik op het pictogram meldingen boven aan de webportal (of open het tabblad **activiteit** in de mobiele app) en klik of tik vervolgens op de stroom in de lijst die wordt weer gegeven.

![Meldingen](./media/fix-flow-failures/notifications-toolbar.png)

Details over de stroom worden weer gegeven en ten minste één stap ziet u een rood uitroep teken. Open die stap en Bekijk het fout bericht.

![Fout bericht](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Verificatie fouten
In veel gevallen mislukken stromen vanwege een verificatie fout. Als u dit type fout hebt, wordt het fout bericht niet **toegestaan** of wordt de fout code **401** of **403** weer gegeven. U kunt een verificatie fout doorgaans oplossen door de verbinding bij te werken:

1. Klik of Tik boven aan de webportal op het tandwiel pictogram om het menu **instellingen** te openen en klik of tik vervolgens op **verbindingen**.
2. Ga naar de verbinding waarvoor u het niet- **geautoriseerde** fout bericht hebt gezien.
3. Klik of tik naast de verbinding op de koppeling **wacht woord verifiëren** in het bericht over de verbinding die niet wordt geverifieerd.
4. Verifieer uw referenties door de instructies te volgen die worden weer gegeven, keer terug naar uw stroom-run-fout en klik of tik vervolgens op **opnieuw verzenden**.
   
    De stroom moet nu volgens verwachting worden uitgevoerd.

## <a name="action-configuration"></a>Actie configuratie
Stromen mislukken ook als een instelling in een actie van de stroom niet werkt zoals verwacht. In dit geval bevat het fout bericht een **Ongeldige aanvraag** of **niet gevonden**of wordt de fout code **400** of **404** weer gegeven.

In het fout bericht moet worden aangegeven hoe u de fout wilt corrigeren. U moet op de knop **bewerken** klikken of tikken en vervolgens het probleem in de stroom definitie corrigeren. Sla de bijgewerkte stroom op en klik of tik op opnieuw **verzenden** om de bewerking opnieuw uit te voeren met de bijgewerkte configuratie.

## <a name="other-failures"></a>Andere fouten
Als de fout code **500** of **502** wordt weer gegeven, is de fout tijdelijk of tijdelijk. Klik of tik op opnieuw **verzenden** om de stroom opnieuw te proberen.

## <a name="getting-help-from-support-or-the-community"></a>Hulp krijgen van ondersteuning of de Community

Wanneer u hulp nodig hebt, kunt u de opties voor **zelf ondersteuning** gebruiken of kunt u **hulp vragen** aan anderen.

### <a name="self-help"></a>Zelf hulp 

1. Ga naar de [ondersteunings site](https://flow.microsoft.com/support/).
1. Ga naar de categorie **zelf ondersteuning** en selecteer een van de opties voor zelf ondersteuning.

    ![Vragen om hulp. Neem contact op met ondersteuning.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Hulp vragen aan anderen

1. Ga naar de [ondersteunings site](https://flow.microsoft.com/support/).
1. Selecteer **contact opnemen met ondersteuning** in het gedeelte **vragen om hulp** .
    
    ![Vragen om hulp. Neem contact op met ondersteuning.](media/fix-flow-failures/ask-for-help.png)

1. Voltooi het **probleem type**, de **categorie**en de **vertel ons wat u hulp nodig hebt bij** velden en selecteer vervolgens **oplossingen weer geven**. 

1. U ziet dat de sectie **oplossingen** wordt weer gegeven nadat u de optie **oplossingen weer geven**hebt geselecteerd. Het bevat een lijst met resultaten die u kunt gebruiken om te helpen bij het oplossen van het probleem dat u hebt. 

    ![Details van geïntegreerde helper](media/fix-flow-failures/integrated-helper-details.png)

Als u hulp nodig hebt bij een probleem, is Help beschikbaar vanuit onze [Community](https://go.microsoft.com/fwlink/?LinkID=787467) en micro soft. 

