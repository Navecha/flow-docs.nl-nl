---
title: Mobiele Microsoft Flow-app ondersteunt nu Mobile Application Management van Microsoft Intune | Microsoft Docs
description: Mobiele Microsoft Flow-app ondersteunt nu Mobile Application Management van Microsoft Intune
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 7cc2b37eb27ed0e2107eeaada02afb072d9a0098
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2019
ms.locfileid: "65060486"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>Mobiele Microsoft Flow-app ondersteunt Microsoft Intune

De mobiele Microsoft Flow-app voor iOS en Android ondersteunt MAM (Mobile Application Management) van Intune zonder apparaatinschrijving. Met MAM kunnen IT-beheerders beleid voor mobiele gegevens maken en afdwingen om gegevens van de organisatie te beschermen.

## <a name="why-intune-support-is-important"></a>Waarom Intune-ondersteuning belangrijk is

Organisaties zijn op zoek naar meer controle over de gegevens die zich op mobiele apparaten van werknemers bevinden. Zo is het mogelijk dat organisaties willen beperken hoe die gegevens worden overgebracht naar het apparaat en willen ze wellicht dat de gegevens worden verwijderd op het moment dat een werknemer de organisatie verlaat.

## <a name="what-is-microsoft-application-management-mam"></a>Wat is Microsoft Application Management (MAM)

MAM stelt organisaties in staat om beleidsregels op te stellen die bepalen hoe apps worden gebruikt in een tenant. Denk hierbij aan het geforceerd versleutelen van app-gegevens, beperkingen voor het kopiëren of extraheren van gegevens naar alleen goedgekeurde toepassingen of het afdwingen van een pincode op een apparaat.

### <a name="prerequisites"></a>Vereisten

- Een [beleid voor app-beveiliging](https://docs.microsoft.com/intune/app-protection-policies) van Intune.
- Een Azure AD-groep (Azure Active Directory).
- Bedrijfsportal. Een belangrijk voordeel van het gebruik van MAM is dat apparaten niet hoeven te worden ingeschreven bij MAM van Intune. De enige vereiste is de bedrijfsportal, die beschikbaar is in de App Store en de Google Play Store.
- Versie 2.31.0 van de mobiele Microsoft Flow-app voor iOS, Android of Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Een beleid voor app-beveiliging maken, apps toewijzen aan het beleid, instellingen definiëren en gebruikers toevoegen aan een Azure AD-groep

U moet het volgende doen om de mobiele Microsoft Flow-app te kunnen beheren:

1. Een beleid voor app-beveiliging opstellen.
1. De mobiele Microsoft Flow-app toewijzen aan het beleid voor app-beveiliging.
1. De beleidsinstellingen toewijzen. U kunt bijvoorbeeld het beleid toewijzen dat er een pincode vereist is voor toegang tot het mobiele apparaat waarop de mobiele Microsoft Flow-app wordt uitgevoerd.
1. Het beleid voor app-beveiliging toepassen op een specifieke Azure AD-groep.
1. Alle gebruikers waarop het app-beveiligingsbeleid van toepassing is, toevoegen aan de Azure AD-groep.

Volg deze stappen voor het maken van een [app-beveiligingsbeleid](https://docs.microsoft.com/intune/app-protection-policies) dat ervoor zorgt dat gebruikers van de mobiele Microsoft Flow-app een pincode moeten invoeren om toegang te krijgen tot de app. 


## <a name="test-the-app-protection-policy"></a>Beleid voor app-beveiliging testen

Nadat u het beleid voor app-beveiliging hebt gemaakt en gebruikers hebt toegewezen aan de Azure AD-groep, is het tijd om de mobiele Microsoft Flow-App te gaan gebruiken om te controleren of het beleid werkt.

Ga als volgt te werk om te controleren of het beleid werkt:

1. Installeer de mobiele Microsoft Flow-app op een apparaat waarvan het platform overeenkomt met een van de platformen die u in het beleid voor app-beveiliging hebt gedefinieerd.
1. Meld u aan bij de mobiele app met een account dat deel uitmaakt van de Azure AD-groep die het gebruik van de mobiele app beperkt tot gebruikers die beschikken over een pincode.

U wordt vervolgens gevraagd het volgende te doen:
1. De bedrijfsportal installeren.
1. Een pincode instellen als u nog geen pincode hebt die voldoet aan de criteria van het beleid voor app-beveiliging.


## <a name="learn-more"></a>Meer informatie

Lees hoe u een [beleid voor app-beveiliging](https://docs.microsoft.com/intune/app-protection-policies) opstelt.

