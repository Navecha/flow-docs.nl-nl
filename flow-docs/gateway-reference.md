---
title: On-premises gegevens gateway | Microsoft Docs
description: Dit artikel bevat een overzicht van de on-premises gegevens gateway voor Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8349361b7ee543c19635dc5899726d69adaa917a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544639"
---
# <a name="what-is-an-on-premises-data-gateway"></a>Wat is een on-premises gegevens gateway?
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

De on-premises gegevens gateway fungeert als een brug om snelle en veilige gegevens overdracht mogelijk te maken tussen on-premises gegevens (gegevens die zich niet in de Cloud bevindt) en verschillende micro soft-Cloud Services. Deze Cloud Services omvatten Power BI, PowerApps, Microsoft Flow, Azure Analysis Services en Azure Logic Apps. Door gebruik te maken van een gateway kunnen organisaties data bases en andere gegevens bronnen in hun on-premises netwerken opslaan, maar deze on-premises gegevens ook veilig gebruiken in Cloud Services.

## <a name="how-the-gateway-works"></a>Hoe de gateway werkt

![Overzicht van de gateway](media/gateway-reference/on-premises-data-gateway.png)

Zie [architectuur voor on-premises gegevens gateway](/data-integration/gateway/service-gateway-onprem-indepth)voor meer informatie over de werking van de gateway.

## <a name="types-of-gateways"></a>Typen gateways

Er zijn twee verschillende soorten gateways voor een ander scenario:

- Met **on-premises gegevens gateway** kunnen meerdere gebruikers verbinding maken met meerdere on-premises gegevens bronnen. U kunt een on-premises gegevens gateway gebruiken met alle ondersteunde services, met één gateway installatie. Deze gateway is goed geschikt voor complexe scenario's met meerdere personen die toegang hebben tot meerdere gegevens bronnen.

- Met **on-premises gegevens gateway (persoonlijke modus)** kan één gebruiker verbinding maken met bronnen en kan deze niet worden gedeeld met anderen. Een on-premises gegevens gateway (persoonlijke modus) kan alleen worden gebruikt met Power BI. Deze gateway is zeer geschikt voor scenario's waarbij u de enige persoon bent die rapporten maakt en u geen gegevens bronnen met anderen hoeft te delen.

## <a name="use-a-gateway"></a>Een gateway gebruiken

Er zijn vier belang rijke stappen voor het gebruik van een gateway.

1. [Down load en installeer de gateway](/data-integration/gateway/service-gateway-install) op een lokale computer.
2. [Configureer](/data-integration/gateway/service-gateway-app) de gateway op basis van uw firewall en andere netwerk vereisten.
3. [Voeg gateway beheerders toe](/data-integration/gateway/service-gateway-manage) die ook andere netwerk vereisten kunnen beheren en beheren.
4. [Problemen met](/data-integration/gateway/service-gateway-tshoot) de gateway oplossen in geval van fouten.

## <a name="next-steps"></a>Volgende stappen

- [De on-premises gegevens gateway installeren](/data-integration/gateway/service-gateway-install)
