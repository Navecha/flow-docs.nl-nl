---
title: Meer informatie over Microsoft Flow-omgevingen | Microsoft Docs
description: Informatie over het gebruik van omgevingen voor het isoleren van uw stromen
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/27/2017
ms.author: sunayv
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0e6b410f75f28ba13357878a5cda178bc66b69ff
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690256"
---
# <a name="choosing-an-environment"></a>Een omgeving kiezen

Dit artikel is een inleiding tot Microsoft Flow-**omgevingen**, waarin u uw stromen, gateways, verbindingen en andere resources veilig kunt maken en isoleren.

U krijgt informatie over het volgende:

* De functies die omgevingen bieden.
* Schakelen tussen omgevingen.
* Hoe u een stroom in de juiste omgeving maakt.

## <a name="environments-overview"></a>Overzicht van omgevingen

Wanneer u een stroom maakt, kiest u een omgeving die u als host van de stroom wilt laten fungeren en kiest u welke resources door die stroom worden gebruikt. U kunt verschillende omgevingen voor verschillende scenario's gebruiken.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Hier volgen enkele scenario's voor het gebruik van omgevingen

Scenario|Aanbeveling
-----|-----
U wilt een stroom maken die gebruikmaakt van een verbinding met de Microsoft Common Data-service.|Plaats uw stroom en de Microsoft Common Data-service in dezelfde omgeving. Hierdoor worden alle gegevens geïsoleerd in die omgeving (scheidingsgrens).
U maakt een stroom voor de afdeling Human Resources. U wilt ervoor zorgen dat alleen gebruikers in uw afdeling Human Resources toegang tot de stroom hebben.|Maak een omgeving en voeg alleen de HR-gebruikers toe die deze stroom kunnen gebruiken. Plaats de stroom en alle andere resources die voor de stroom worden gebruikt in deze omgeving.
Er zijn gebruikers in Europa die gebruikmaken van een stroom om SharePoint-gegevens weer te geven.|Maak een omgeving in Europa en maak uw stroom en de SharePoint-verbinding in deze stroom. Deze omgeving Europa biedt de Europese gebruikers de beste prestaties, omdat alle resources lokaal zijn voor Europa (de plaats waar zich de gegevens bevinden).

Als u omgevingen wilt maken, moet u een Microsoft Flow-beheerder zijn. Beheerders bepalen wie toegang tot de omgevingen heeft. Zie het onderwerp [Omgevingen beheren](environments-overview-admin.md) voor meer informatie over het maken en beheren van omgevingen.

## <a name="switching-environments"></a>Schakelen tussen omgevingen

Bij Microsoft Flow kunt u gemakkelijk tussen omgevingen schakelen. Wanneer u schakelt tussen omgevingen, ziet u alleen items die in die specifieke omgeving zijn gemaakt; u ziet geen items in andere omgevingen en hebt hier ook geen toegang tot.

Hier volgt een voorbeeld.

U hebt een stroom gemaakt met de naam *NewEmployee* in de omgeving *Human Resources*. Open in [Microsoft Flow](https://flow.microsoft.com) de omgeving *Sales*. De stroom *NewEmployee* staat niet vermeld. Om de stroom *NewEmployee* te zien, opent u de omgeving *Human Resources* Onthoud dat dezelfde regels gelden voor alle items die u in de omgeving hebt gemaakt, waaronder verbindingen, gateways, stromen en meer.

Volg deze stappen als u wilt schakelen tussen omgevingen:

1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com).
1. In de rechterbovenhoek ziet u een afbeelding die uw profiel vertegenwoordigt.

   ![profielafbeelding](./media/environments-overview-maker/default-environment.png)

1. Selecteer de afbeelding. Alle omgevingen die voor u beschikbaar zijn, worden weergegeven in de vervolgkeuzelijst. De omgeving waarbij u momenteel bent aangemeld, wordt geselecteerd:

   ![afbeelding van lijst met omgevingen](./media/environments-overview-maker/all-environments.png)
1. Als u wilt overschakelen naar een andere omgeving, selecteert u die omgeving in de lijst:

   ![selecteer een omgeving om te activeren](./media/environments-overview-maker/select-europe.png)
1. In Microsoft Flow wordt overgeschakeld naar de nieuwe omgeving.

## <a name="create-flows-in-the-right-environment"></a>Stromen in de juiste omgeving maken

Voordat u een stroom maakt, selecteert u de omgeving waarin u de stroom en de bijbehorende resources gaat toevoegen.

> [!NOTE]
> Als u een stroom in de verkeerde omgeving maakt, moet u deze verwijderen en vervolgens in de juiste omgeving maken.

Denk aan de volgende factoren als u een omgeving kiest die als host voor uw stromen moet fungeren:

* U kunt alleen gateways maken in de standaardomgeving. Als u dus uw stroom via een gateway wilt verbinden met on-premises gegevens, moet u de standaardomgeving gebruiken.
* Microsoft Common Data Service-databases zijn gekoppeld aan een specifieke omgeving. Als u dus een stroom wilt maken die de Common Data Service gebruikt, moet u de stroom maken in de omgeving waarin de database wordt gehost.
* U ziet alle omgevingen waarin u resources kunt bewerken. U moet echter een beheerder vragen u als maker toe te voegen aan alle omgevingen waarin u stromen wilt maken.

> [!NOTE]
> U kunt altijd stromen maken in de standaardomgeving.

## <a name="next-steps"></a>Volgende stappen

* [Een stroom maken met een sjabloon](get-started-logic-template.md)
* [Een stroom maken](get-started-logic-flow.md)
* [Overzicht van de omgeving voor beheerders](environments-overview-admin.md)
