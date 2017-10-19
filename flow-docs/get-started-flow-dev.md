---
title: Beginnen met bouwen | Microsoft Docs
description: Maak een aangepaste connector, deel deze, sluit deze in een stoom in, en doe nog veel meer.
services: 
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: barathb
ms.openlocfilehash: d22193ac40b6eb8f90abf2ae5ced91b39c2faad9
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="start-to-build-with-microsoft-flow"></a>Beginnen met bouwen met Microsoft Flow
U kunt uw toepassing met Microsoft Flow op onder meer de volgende manieren uitbreiden:

* Maak een aangepaste connector en maak hiermee verbinding
* Deel deze API met alle gebruikers van Microsoft Flow
* Sluit de stroomervaring in vanuit een app
* Stel alle API's van ontwikkelaars beschikbaar, zodat gebruikers met Microsoft Flow kunnen werken op de manier die voor hen het beste werkt

## <a name="prerequisites"></a>Vereisten
* Een account op [flow.microsoft.com](https://flow.microsoft.com)

## <a name="create-a-custom-connector"></a>Een aangepaste connector maken
Wanneer u een webservice hebt die u wilt automatiseren met Microsoft Flow, moet u eerst een aangepaste connector bouwen. Als u een aangepaste connector registreert, geeft u aan Microsoft Flow door wat de kenmerken van uw Web-API zijn, zoals welke verificatie vereist is, welke triggers en acties worden ondersteund en wat de parameters en uitvoer voor alle acties zijn.

Volg [deze zelfstudie](https://powerapps.microsoft.com/tutorials/register-custom-api/) om een aangepaste connector te registreren. Nadat u de aangepaste API hebt geregistreerd, kunt u deze in uw organisatie delen, zodat anderen u kunnen helpen met het testen van de API.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Een aangepaste connector delen met alle Microsoft Flow-gebruikers
Nadat u uw aangepaste connector volledig hebt getest, start u het beoordelingsproces zoals beschreven in [dit blogbericht](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/):

* Een OpenAPI-bestand met uw API en de verificatiegegevens
* Een pictogram voor de connector
* Een beschrijving van de API
* Ongeveer tien ideeën waarmee wordt uitgelegd hoe uw API andere gebruikers kan helpen via sjablonen

Nadat u deze gegevens hebt verzonden, wordt de functie van uw API in Microsoft Flow en Microsoft PowerApps beoordeeld door Microsoft.

## <a name="embed-the-flow-experience-in-your-website-or-app"></a>De stroomervaring insluiten in uw website of app
Tot slot kunt u Microsoft Flow vanuit uw app insluiten, om een diepgaande, integratie binnen de context in te schakelen tussen uw app en alle andere services die Microsoft Flow ondersteunt. U kunt bijvoorbeeld het volgende doen:

* Door alle sjablonen bladeren die betrekking hebben op uw service en gebruikers een sjabloon laten selecteren
* De stromen beheren die gebruikers aan uw app hebben gekoppeld

Volg [deze zelfstudie](embed-flow-dev.md) voor meer informatie over hoe u Microsoft Flow in een app kunt insluiten.

