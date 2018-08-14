---
title: Aangepaste connectors maken en stromen insluiten | Microsoft Docs
description: Maak een aangepaste connector, deel deze, sluit deze in een stoom in, en doe nog veel meer.
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: barathb
ms.openlocfilehash: 1bcdbf3772ab2481b15bd224523dff74afc53101
ms.sourcegitcommit: 77aae180d972373d1f251fa6a5c8f484f08ffc15
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39718276"
---
# <a name="start-to-build-with-microsoft-flow"></a>Beginnen met bouwen met Microsoft Flow

Dit zijn een aantal manieren waarop u uw toepassing kunt uitbreiden met Microsoft Flow:

* Een aangepaste connector maken en verbinding maken.
* Uw aangepaste connector delen met alle Microsoft Flow-gebruikers.
* De stroomervaring insluiten in een app.
* Alle aangepaste connectors markeren zodat gebruikers met Microsoft Flow kunnen werken op de manier die voor hen het beste werkt

## <a name="prerequisites"></a>Vereisten

* Een [Microsoft Flow](https://flow.microsoft.com)-account.

## <a name="create-a-custom-connector"></a>Een aangepaste connector maken

Als u een webservice hebt waarmee u verbinding wilt maken vanuit Microsoft Flow, moet u eerst een aangepaste connector maken. Als u een aangepaste connector registreert, geeft u aan Microsoft Flow door wat de kenmerken van uw webservice zijn, zoals welke verificatie vereist ervoor is, welke triggers en acties worden ondersteund en wat de parameters en uitvoer voor alle acties zijn.

Volg deze zelfstudie om [aangepaste connectors te registreren en gebruiken](https://powerapps.microsoft.com/tutorials/register-custom-api/). Nadat u uw aangepaste connector hebt geregistreerd, kunt u deze delen binnen uw organisatie om te worden getest.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Een aangepaste connector delen met alle Microsoft Flow-gebruikers

Nadat u uw aangepaste connector volledig hebt getest, start u het [controleproces](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) om de connector te laten goedkeuren door Microsoft om deze te delen met alle andere Microsoft Flow-gebruikers.

Dit is wat u nodig hebt voor het controleproces:

* Een OpenAPI-bestand met uw API en de verificatiegegevens.
* Een pictogram voor uw connector.
* Een beschrijving van uw connector.
* Ongeveer tien ideeën waarmee wordt uitgelegd hoe uw connector andere gebruikers kan helpen via sjablonen.

Nadat u deze gegevens hebt verzonden, wordt de functie van uw API in Microsoft Flow en Microsoft PowerApps beoordeeld door Microsoft.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>De stroomervaring insluiten in uw website of app

U kunt Microsoft Flow in uw app [insluiten](developer/embed-flow-dev.md) om een diepgaande integratie binnen de context in te schakelen tussen uw app en alle andere services die Microsoft Flow ondersteunt. U kunt bijvoorbeeld het volgende doen:

* Door alle sjablonen bladeren die betrekking hebben op uw service en gebruikers een sjabloon laten selecteren.
* De stromen beheren die gebruikers aan uw app hebben gekoppeld.

## <a name="next-steps"></a>Volgende stappen

Meer informatie over het [insluiten](developer/embed-flow-dev.md) van Microsoft Flow in uw app.
