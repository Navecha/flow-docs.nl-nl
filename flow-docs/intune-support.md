---
title: Microsoft Flow mobiele app biedt nu ondersteuning voor het beheer van mobiele toepassingen van Microsoft Intune. | Microsoft Docs
description: Microsoft Flow mobiele app biedt nu ondersteuning voor het beheer van mobiele toepassingen van Microsoft Intune.
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
ms.openlocfilehash: d5709d7f98c3f4cc1dcf7d0da8fc5c9501adb84c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547401"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>Microsoft Flow mobiele app ondersteunt Microsoft Intune
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

De mobiele app Microsoft Flow voor iOS en Android ondersteunt Mobile Application Management (MAM) van intune zonder apparaatregistratie. Met behulp van MAM kunnen IT-beheerders Mobile Data-beleids regels maken en afdwingen om de Bedrijfs gegevens te beveiligen.

## <a name="why-intune-support-is-important"></a>Waarom de ondersteuning van intune belang rijk is

Organisaties kijken naar meer controle over de gegevens die zich op mobiele apparaten van werk nemers bevinden. Organisaties kunnen bepalen hoe de gegevens naar het apparaat worden verplaatst en ervoor zorgen dat de gegevens worden verwijderd, zodat de werk nemer de organisatie verlaat.

## <a name="what-is-microsoft-application-management-mam"></a>Wat is micro soft Application Management (MAM)?

Met MAM kunnen organisaties beleids regels maken die bepalen hoe apps worden gebruikt binnen een Tenant. Dit omvat het afdwingen van app-gegevens versleuteling, het beperken van gegevens naar alleen goedgekeurde toepassingen of het afdwingen van een pincode op een apparaat.

### <a name="prerequisites"></a>Vereisten

- Een intune- [beleid voor app-beveiliging](https://docs.microsoft.com/intune/app-protection-policies).
- Een Azure Active Directory-groep (Azure AD).
- Bedrijfsportal. Een belang rijk voor deel van het gebruik van MAM is dat apparaten niet hoeven te worden inge schreven bij intune MAM. Alles wat vereist is, is de Bedrijfsportal, die beschikbaar is in de App Store en de Google Play Store.
- Versie 2.31.0 van de mobiele app Microsoft Flow voor iOS, Android of Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Een beveiligings beleid voor apps maken, apps toewijzen aan het beleid, instellingen definiëren en gebruikers toevoegen aan een Azure AD-groep

Voor de Microsoft Flow mobiele app die moet worden beheerd, moet u het volgende doen:

1. Een beveiligings beleid voor apps maken.
1. Wijs de mobiele app voor Microsoft Flow toe aan het beveiligings beleid voor apps.
1. Wijs de beleids instellingen toe. U kunt bijvoorbeeld het beleid toewijzen om een pincode in te stellen voor toegang tot het mobiele apparaat dat de Microsoft Flow mobiele app uitvoert.
1. Het app-beveiligings beleid Toep assen op een specifieke Azure AD-groep.
1. Voeg alle gebruikers toe waarop het app-beveiligings beleid van toepassing is op de Azure AD-groep.

Volg deze stappen voor het maken van een [beveiligings beleid voor apps](https://docs.microsoft.com/intune/app-protection-policies) waarvoor Microsoft flow gebruikers van mobiele apps een pincode moeten invoeren voordat ze toegang kunnen krijgen tot de app. 


## <a name="test-the-app-protection-policy"></a>Het app-beveiligings beleid testen

Nadat u het app-beveiligings beleid hebt gemaakt en gebruikers aan de Azure AD-groep hebt toegewezen, is het tijd om de Microsoft Flow mobiele app te gebruiken en te bevestigen dat het beleid werkt.

Voer de volgende stappen uit om te bevestigen dat het beleid werkt:

1. Installeer de Microsoft Flow mobiele app op een apparaat waarvan het platform overeenkomt met een van de platformen die u in het app-beveiligings beleid hebt gedefinieerd.
1. Meld u aan bij de mobiele app met een account in de Azure AD-groep waarmee het gebruik van de mobiele app wordt beperkt tot gebruikers die een pincode hebben.

U wordt dan gevraagd het volgende te doen:
1. Installeer de Bedrijfsportal.
1. Stel uw pincode in als u nog geen pincode hebt die voldoet aan de criteria van het app-beveiligings beleid.


## <a name="learn-more"></a>Meer informatie

Meer informatie over het maken van een [app-beveiligings beleid](https://docs.microsoft.com/intune/app-protection-policies).

