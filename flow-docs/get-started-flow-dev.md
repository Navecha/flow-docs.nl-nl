---
title: Aangepaste connectors maken en stromen insluiten | Microsoft Docs
description: Maak een aangepaste connector, deel deze, sluit een stroom in en doe nog veel meer.
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
ms.date: 11/22/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 80b1d17944d780a1800c91458ee674f5f2afe188
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548274"
---
# <a name="start-to-build-with-microsoft-flow"></a>Beginnen met het bouwen met Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Hier volgen enkele manieren waarop u uw toepassing kunt uitbreiden met Microsoft Flow:

* Maken en verbinding maken met een aangepaste connector.
* Uw aangepaste connector delen met alle gebruikers van Microsoft Flow.
* De stroom ervaring insluiten in een app.
* Markeer alle aangepaste connectors zodat gebruikers op de beste manier kunnen communiceren met Microsoft Flow.

## <a name="prerequisites"></a>Vereisten

* Een [Microsoft flow](https://flow.microsoft.com) -account.

## <a name="create-a-custom-connector"></a>Een aangepaste connector maken

Als u een webservice hebt waarmee u verbinding wilt maken vanaf Microsoft Flow, moet u eerst een aangepaste connector maken. Wanneer u een aangepaste connector registreert, leert u Microsoft Flow over de kenmerken van uw webservice, met inbegrip van de vereiste verificatie, de triggers en acties die worden ondersteund en de para meters en uitvoer voor elk van deze acties.

Volg deze zelf studie voor meer informatie over het [registreren en gebruiken van aangepaste connectors](https://powerapps.microsoft.com/tutorials/register-custom-api/). Nadat u uw aangepaste connector hebt geregistreerd, kunt u deze delen binnen uw organisatie om te testen.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Een aangepaste connector delen met alle Microsoft Flow gebruikers

Nadat u uw aangepaste connector volledig hebt getest, start u het [beoordelings proces](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) zodat dit door micro soft is goedgekeurd voor delen met alle andere Microsoft flow gebruikers.

Dit is wat u nodig hebt voor het beoordelings proces:

* Een OpenAPI-bestand dat uw API en eventuele verificatie gegevens vertegenwoordigt.
* Een pictogram voor de connector.
* Een beschrijving van de connector.
* Ongeveer 10 ideeën over hoe uw connector andere gebruikers kan profiteren van sjablonen.

Nadat u deze informatie hebt verzonden, start micro soft de functionaliteit van uw API in Microsoft Flow en Microsoft PowerApps.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>De stroom ervaring insluiten in uw website of app

U kunt Microsoft Flow [insluiten](developer/embed-flow-dev.md) in uw app om diep gaande integratie binnen de context in te scha kelen tussen uw app en alle andere services die Microsoft flow ondersteunt. U kunt bijvoorbeeld het volgende doen:

* Blader door alle sjablonen die betrekking hebben op uw service en laat gebruikers een sjabloon selecteren.
* De stromen beheren die gebruikers aan uw app hebben gekoppeld.

## <a name="next-steps"></a>Volgende stappen

Meer informatie over het [insluiten](developer/embed-flow-dev.md) van Microsoft flow in uw app.
