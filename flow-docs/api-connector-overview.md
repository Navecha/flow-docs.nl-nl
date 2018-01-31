---
title: Overzicht API-connector  | Microsoft Docs
description: ISV's en eigenaren van SaaS-services kunnen connectors maken en deze laten certificeren door Microsoft.
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: 62f8f8d0af72292a61324d75bd46f53d559b46a3
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2018
---
# <a name="api-connector-overview-microsoft-flow"></a>Overzicht API-connector (Microsoft Flow)
Een **API-connector** is een op een OpenAPI (Swagger) gebaseerde wrapper rond een REST-API via welke de onderliggende service kan communiceren met [Microsoft Flow](https://flow.microsoft.com), [PowerApps](https://powerapps.microsoft.com) en [Logic Apps](https://docs.microsoft.com/azure/logic-apps/). Het is een methode die gebruikers in staat stelt verbinding te maken met hun accounts en gebruik te maken van een reeks vooraf ontwikkelde **triggers** en **acties** om hun apps en werkstromen te bouwen.

Als **Independent Software Vendor (ISV)** of eigenaar van een **SaaS-service** kunt u connectors bouwen waardoor uw gebruikers met de meest uiteenlopende zakelijke en op productiviteit gerichte scenario’s kunnen werken. Met een connector hebt u geen last van de beperkingen die worden opgelegd door een vastomlijnde reeks integraties, vergroot u het bereik van uw service en de kans dat deze wordt gevonden en gebruikt.

## <a name="requirements"></a>Vereisten
Er moet aan de volgende vereisten worden voldaan om een connector te kunnen maken en indienen:

* Er moet een gebruikersscenario zijn dat geschikt is voor Microsoft Flow, PowerApps en Logic Apps
* Er moet een openbaar beschikbare service zijn met stabiele REST-API's

## <a name="build-your-connector"></a>De connector maken
De eerste stap bij het bouwen van een API-connector bestaat uit het bouwen van een volledig functionele aangepaste connector. Een aangepaste connector functioneert precies hetzelfde als een API-connector, maar is binnen de tenant van de auteur beperkt beschikbaar voor de auteur en voor specifieke gebruikers.

Het bouwen van een connector bestaat uit meerdere stappen:

![Stappen voor het schrijven van een API-connector](./media/api-connectors-overview/authoring-steps.png)

[Meer informatie](api-connector-dev.md) over het ontwikkelen van een API-connector.

## <a name="submit-for-certification"></a>Indienen voor certificering
Nadat u een connector hebt gemaakt, gaat u deze indienen voor certificering. Als onderdeel van ons certificeringsproces dat door derden wordt uitgevoerd, controleert Microsoft de connector voordat deze wordt gepubliceerd.

Tijdens dit proces wordt de functionaliteit van de connector in Microsoft Flow en PowerApps gevalideerd, en wordt gecontroleerd of de inhoud en technische aspecten van de connector aan de vereisten voldoen.

[Meer informatie](api-connector-submission.md) over het proces om uw connector in te dienen zodat deze kan worden gecertificeerd en gepubliceerd.

## <a name="get-support"></a>Krijg ondersteuning
Voor ondersteuning bij de onboardingsfase en de ontwikkeling kunt u een e-mail sturen naar [ condevhelp@microsoft.com ](mailto:condevhelp@microsoft.com). Dit account wordt actief bewaakt en beheerd. Vragen van ontwikkelaars en incidenten waar deze mee te maken krijgen, worden snel doorgespeeld naar het juiste team.

