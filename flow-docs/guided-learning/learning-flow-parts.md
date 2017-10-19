---
title: Bouwstenen van Microsoft Flow | Microsoft Docs
description: Bekijk de verschillende onderdelen van Microsoft Flow en ontdek hoe deze in verhouding staan tot elkaar. Maak stromen op basis van sjablonen en volledig nieuwe stromen.
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: 9U8jMRO-Jv0
courseduration: 9m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 6a7fe2d56c7bc3b2253b675ce26f3f29042a7a71
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="building-blocks-of-microsoft-flow"></a>Bouwstenen van Flow
Nu u de basisprincipes van Microsoft Flow onder de knie hebt, gaan we verder met **een rondleiding door Microsoft Flow**. We kijken kort naar het maken van stromen op basis van een sjabloon of vanaf de basis.

## <a name="check-out-the-templates"></a>De sjablonen bekijken
Als u op flow.microsoft.com op de koppeling **Sjablonen** boven aan de pagina klikt, ziet u verschillende sjablonen die u meteen kunt gebruiken in uw webservices. Blader door deze apps om een **idee te krijgen van de mogelijkheden** en te zien wat Microsoft Flow voor uw onderneming kan betekenen.

![Stroomsjablonen](./media/learning-flow-parts/template-list.png)

Elke stroomsjabloon is ontworpen voor een specifiek doel, zoals het ontvangen van meldingen wanneer er iets gebeurt, het kopiëren van een nieuw bestand van de ene service naar de andere of het bijhouden van SharePoint-goedkeuringen. Deze sjablonen zijn **gereed voor gebruik**.  U hoeft alleen **de sjablonen te configureren** om stromen toe te voegen aan uw account. U doet dit door te klikken op **Deze sjabloon gebruiken**, u aan te melden bij de vereiste services en vervolgens de formulieren in te vullen die worden weergegeven.  Dit is bijvoorbeeld een stroom die is gemaakt op basis van een sjabloon voor het verzenden van e-mailmeldingen wanneer een SharePoint-lijst is gewijzigd. 

![Voorbeeld van een stroomsjabloon](./media/learning-flow-parts/example-template.png)

Er zijn honderden sjablonen beschikbaar en u vindt deze in **Microsoft Flow voor webtoepassingen** of **Microsoft Flow voor mobiel**.

![Flow voor toepassingen en voor mobiel](./media/learning-flow-parts/flow-web-mobile.png)

## <a name="create-a-flow-from-scratch"></a>Een volledig nieuwe stroom maken
U hebt gezien hoe u een stroom maakt met een sjabloon, maar wat als u een taak wilt automatiseren, maar hiervoor geen geschikte sjabloon kunt vinden? U kunt **een volledig nieuwe stroom maken**.  Wanneer u een volledig nieuwe stroom maakt, begint u met een schone lei en voegt u **services, triggers en acties** toe om de stroom te bouwen.  

![Lege stroom](./media/learning-flow-parts/flow-from-blank.png)

## <a name="building-blocks-of-a-flow"></a>Bouwstenen van een stroom
Of u nu een stroom op basis van een sjabloon of een volledig nieuwe stroom maakt, elk stroom bevat **bouwstenen** die op bepaalde manieren met elkaar samenwerken, net als bij een stroomdiagram.

* **Services** zijn bronnen en bestemmingen van gegevens in een stroom.
* **Triggers** zijn gebeurtenissen waarmee een stroom wordt gestart.
* **Acties** zijn taken die worden uitgevoerd door de stroom.
* **Voorwaarden** staan als/dan-vertakkingen toe in een stroom.
* **Lussen** dienen om acties te herhalen.

### <a name="services"></a>Services
Microsoft Flow kan verbinding maken met veel verschillende **toepassingen en services**.  Voorbeelden van deze services zijn **Twitter**, **Github**, **Wunderlist**, **Office 365** en **Google Docs**.  Dit zijn de **bronnen** die gegevens verstrekken aan Microsoft Flow en bovendien de **locaties** vormen voor het werk dat door Microsoft Flow wordt uitgevoerd.  U kunt de volledige lijst met services weergeven door te klikken op de koppeling **Services** bovenaan **flow.microsoft.com**.

![Stroomconnectors](./media/learning-flow-parts/flow-connectors.png)

### <a name="triggers"></a>Triggers
Elke stroom begint met een **trigger**.  Er zijn veel verschillende typen triggers.  Sommige hiervan zijn gebeurtenissen in uw verbonden webservices, zoals **wanneer een bepaalde gebruiker een tweet verzendt** of **een bestand wordt opgeslagen in uw Dropbox-account**.  Andere triggers zijn ingebouwd, zoals **het uitvoeren van een stroom volgens een terugkerend schema** of **het uitvoeren van een stroom als reactie op een webaanvraag**.  Ten slotte zijn er handmatige triggers, zoals het starten van een stroom door te klikken op een **knop in Microsoft Flow of Microsoft PowerApps**.  Triggers **geven vaak informatie over de gebeurtenis die heeft plaatsgevonden** door aan acties in uw stroom.

![Stroomtriggers](./media/learning-flow-parts/flow-triggers.png)  

### <a name="actions"></a>Acties
Een **actie** is datgene waarvan u graag wilt dat het **gebeurt** nadat de stroom is geactiveerd.  Dit kan een **melding**, het **kopiëren van gegevens of bestanden** van een bron naar een locatie, of een andere actie zijn, zoals het **plaatsen van een bericht op sociale media** of het **voor een vastgestelde periode inbouwen van een vertraging**.  U kunt acties ook gebruiken voor het **ophalen van gegevens uit een service** om deze te gebruiken met andere acties.

![Stroomacties](./media/learning-flow-parts/flow-actions.png) 

### <a name="conditions"></a>Voorwaarden
Met **voorwaarden** kunt u besluitvorming aan de stroom toevoegen.  Wanneer een voorwaarde is geëvalueerd, wordt de stroom gesplitst in een **Ja**-pad en een **Nee**-pad.   Als u bijvoorbeeld vakantiefoto's die u hebt geplaatst op **Dropbox** wilt kopiëren naar **OneDrive**, kunt u een voorwaarde maken na een trigger voor een **nieuw bestand in Dropbox** waarmee wordt gecontroleerd of de bestandsnaam het woord *vakantie* bevat. Als dit het geval is, wordt het bestand naar **OneDrive** gekopieerd. Als dit niet het geval is, gebeurt er niets.

![Flowvoorwaarde](./media/learning-flow-parts/flow-condition.png) 

### <a name="loops"></a>Lussen
Met **lussen** kunt u een actie meer dan één keer uitvoeren, bijvoorbeeld als een actie herhaaldelijk of één keer per item in een verzameling items moet plaatsvinden.

## <a name="next-lesson"></a>Volgende les
In dit onderwerp hebben we Microsoft Flow verkend.  We hebben door **sjablonen** gebladerd en gesproken over het **maken van een volledig nieuwe stroom**.  Wij bouwen stromen door verbinding te maken met apps en services, **triggers** om de stroom te starten, **acties** om in de stroom iets te laten gebeuren, **voorwaarden** om beslissingen te nemen en **lussen** om een stroom te herhalen.  **De eenvoudigste manier om met Microsoft Flow te leren werken, is om te beginnen met een sjabloon** en deze te verbinden met de apps en services die u al gebruikt. 

Hierna volgt een overzicht van hetgeen we tot nu tot hebben geleerd in deze Begeleide training.

