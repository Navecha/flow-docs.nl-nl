---
title: Overzicht van regio's voor Microsoft Flow | Microsoft Docs
description: Overzicht met vraag en antwoord over regio's in Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 33c5a1c331d9874f6b794e8fd2ea92b541024ec6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548470"
---
# <a name="faq-for-regions-in-microsoft-flow"></a>Veelgestelde vragen over regio's in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Dit document bevat een lijst met veelgestelde vragen over Microsoft Flow.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Hoe kan ik wilt u nagaan waar mijn stroom is geïmplementeerd?
Uw stroom wordt geïmplementeerd in de [regio](https://azure.microsoft.com/regions/) die als host fungeert voor de [omgeving](environments-overview-admin.md). Als uw omgeving is gemaakt in de regio Europa, wordt uw stroom bijvoorbeeld in Europa data centers geïmplementeerd.

Beheerders kunnen de regio identificeren als ze zich aanmelden bij het Microsoft Flow- [beheer centrum](https://admin.flow.microsoft.com). Op het tabblad **omgevingen** worden alle bestaande omgevingen en hun regio's weer gegeven.

![omgevingen weer geven](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Welke regio's zijn er beschikbaar?
* Verenigde Staten
* Europa
* Asia
* Australië
* India
* Japan
* Canada
* Zuid-Amerika
* Verenigd Koninkrijk
* Amerikaanse overheid (GCC)
* Frankrijk

## <a name="what-features-are-specific-to-a-given-region"></a>Welke functies zijn specifiek voor een bepaalde regio?
Omgevingen kunnen in verschillende regio's worden gemaakt en zijn gebonden aan die geografische locatie. Wanneer u een stroom in een omgeving maakt, wordt die stroom geïmplementeerd in data centers op die geografische locatie. Dit geldt voor alle items die u in die omgeving maakt, met inbegrip van het common data model, stromen, verbindingen, gateways, apps en aangepaste connectors.

Voor optimale prestaties kunt u uw omgeving maken in de regio die het dichtst bij uw gebruikers ligt. Als uw gebruikers zich bijvoorbeeld in Europa bevinden, maakt u uw omgevingen in de regio Europa. Als uw gebruikers zich in de Verenigde Staten bevinden, maakt u uw omgevingen in de Verenigde Staten regio.

## <a name="gateways"></a>gateways
Gateways zijn:

* Niet beschikbaar in de regio India.
* Alleen ondersteund in de standaard omgeving, niet in aangepaste omgevingen.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>Is Microsoft Flow beschikbaar in nationale Clouds?
Klikt. [Meer informatie](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Welke uitgaande IP-adressen worden in elke regio gebruikt?
Zie [limieten en configuratie](limits-and-config.md).

