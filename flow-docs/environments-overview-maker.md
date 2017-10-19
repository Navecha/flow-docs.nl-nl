---
title: Schakelen tussen omgevingen bij het maken van een Microsoft Flow | Microsoft Docs
description: Hoe u verschillende omgevingen gebruikt bij het maken van een stroom met Microsoft Flow
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: bcbb566c20291da14881d771c538dd89689b6b1d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="choosing-an-environment"></a>Een omgeving kiezen
Met Microsoft Flow kunt u in verschillende omgevingen werken en daartussen eenvoudig overschakelen. Dit artikel heeft betrekking op de volgende omgevingsonderwerpen:

* Achtergrond over waar omgevingen voor zorgen
* Schakelen tussen omgevingen
* Hoe u een stroom in de juiste omgeving maakt

## <a name="environments-overview"></a>Overzicht van omgevingen
Omgevingen zorgen voor een scheiding tussen uw stromen, verbindingen, gateways en andere bronnen. Wanneer u een stroom maakt, kiest u welke omgeving u als host van de stroom wilt laten fungeren en welke resources door die stroom worden gebruikt. U kunt verschillende omgevingen voor verschillende scenario's gebruiken.

Enkele voorbeelden:

* U maakt een stroom die gebruikmaakt van een verbinding met de Microsoft Common Data-service In dit scenario bevinden de stroom en de Microsoft Common Data-service zich in dezelfde omgeving. Hierdoor worden alle gegevens geïsoleerd in die omgeving (scheidingsgrens).
* U maakt een stroom voor de afdeling Human Resources. U wilt ervoor zorgen dat alleen gebruikers in uw afdeling Human Resources toegang tot de stroom hebben. U wilt bijvoorbeeld niet dat de groep Sales de stroom gebruikt. In dit scenario kunt u een afzonderlijke omgeving gebruiken, waarvoor alleen HR-gebruikers zijn gemachtigd, om de stroom te hosten en alle resources die de stroom gebruikt, waaronder gateways en verbindingen.
* Er zijn gebruikers in Europa die gebruikmaken van een stroom om SharePoint-gegevens weer te geven. In dit scenario maakt u een omgeving in Europa die als host fungeert voor de stroom en maakt u de SharePoint-verbinding. Deze omgeving Europa biedt de Europese gebruikers de beste prestaties, omdat alle resources lokaal zijn voor Europa (de plaats waar zich de gegevens bevinden).

Omgevingen worden gemaakt door Microsoft Flow-beheerders. Deze beheerders bepalen ook wie toegang heeft tot de verschillende omgevingen.

In dit onderwerp wordt beschreven hoe u kunt navigeren tussen verschillende omgevingen. Zie [Omgevingen beheren](environments-overview-admin.md) voor meer informatie over hoe u omgevingen maakt en beheert.

## <a name="switching-environments"></a>Schakelen tussen omgevingen
Bij Microsoft Flow kunt u gemakkelijk tussen omgevingen schakelen. Wanneer u overschakelt, ziet u alle items in de specifieke omgeving. U ziet geen items uit een andere omgeving.

Hier volgt een voorbeeld.

U maakt een stroom met de naam *NewEmployee* in de omgeving*Human Resources*. Open in [flow.microsoft.com](http://flow.microsoft.com) de omgeving *Sales*. De stroom *NewEmployee* staat niet vermeld. Om de stroom *NewEmployee* te zien, opent u de omgeving *Human Resources* Onthoud dat dit geldt voor alle items die u in de omgeving maakt, waaronder verbindingen, gateways en PowerApps.

1. Open [flow.microsoft.com](http://flow.microsoft.com).
2. In de rechterbovenhoek ziet u uw naam en de omgeving waarin u werkt:  
   ![](./media/environments-overview-maker/default-environment.png)
   
    In de afbeelding ziet u de meldingen. Deze meldingen zijn specifiek voor de stroom in deze standaardomgeving.
3. Selecteer uw naam. Alle omgevingen die voor u beschikbaar zijn worden weergegeven in de vervolgkeuzelijst. Uw huidige omgeving wordt gecontroleerd:  
   ![](./media/environments-overview-maker/all-environments.png)
4. Als u wilt overschakelen naar een andere omgeving, selecteert u die omgeving in de lijst:  
   ![](./media/environments-overview-maker/select-europe.png)
5. In Microsoft Flow wordt automatisch overgeschakeld naar de nieuwe omgeving:  
   ![](./media/environments-overview-maker/europe-environment.png)
   
    In de afbeelding ziet u dat er geen meldingen zijn. De nieuwe omgeving Europe heeft geen meldingen.

## <a name="create-flows-in-the-right-environment"></a>Stromen in de juiste omgeving maken
Voordat u een stroom maakt, moet u er altijd voor zorgen dat u de omgeving selecteert waarin u wilt dat de stroom zich bevindt. Anders moet u de stroom verwijderen en de stroom in de juiste omgeving opnieuw maken.

Denk aan de volgende factoren als u kiest in welke omgeving u uw stromen wilt maken:

* Gateways worden in de standaardomgeving gemaakt. Gateways kunnen niet worden gemaakt in een andere omgeving, dus als u verbinding wilt maken met on-premises gegevens, moet u de standaardomgeving gebruiken.
* Stromen kunnen alleen verbindingen en andere resources in dezelfde omgeving gebruiken. Stromen kunnen geen resources in een andere omgeving gebruiken. Een voorbeeld: stel u maakt een stroom die gebruikmaakt van een aangepaste connector. Deze aangepaste connector moet zich in dezelfde omgeving bevinden als de stroom.
* De database van de Microsoft Common Data-service is altijd aan precies één omgeving gekoppeld. Dit betekent dat als u ooit met de Microsoft Common Data-service wilt werken, u dezelfde omgeving moet selecteren als die waarin zich de database bevindt.
* U ziet alle omgevingen waarin u resources kunt bewerken. Dit betekent echter niet dat u in alle omgevingen nieuwe resources kunt maken. Dus in bepaalde omgevingen kunt u mogelijk geen nieuwe stromen maken. U moet de beheerder vragen u als **Maker** toe te voegen aan die omgeving of kies een andere omgeving waarin u de stroom maakt (u kunt altijd stromen in de standaardomgeving maken).

## <a name="what-you-did"></a>Wat u hebt gedaan
Aan de hand van deze stappen schakelt u tussen omgevingen waarvoor u gebruiksmachtigingen hebt. Nu gaat u uw stromen maken.

## <a name="next-steps"></a>Volgende stappen
[Een stroom maken met een sjabloon](get-started-logic-template.md)  
[Een stroom maken](get-started-logic-flow.md)  
[Overzicht van de omgeving voor beheerders](environments-overview-admin.md)

