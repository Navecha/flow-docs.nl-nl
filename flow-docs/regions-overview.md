---
title: Overzicht van regio's voor Microsoft Flow | Microsoft Docs
description: Overzicht met vragen en antwoorden over regio's in Microsoft Flow
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
ms.openlocfilehash: dce9fa4bb838f931acdcd95710d82d15bdc7dd24
ms.sourcegitcommit: 3bdd6c6b9df40f53e52c31130abaa93ba09a0e9b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2019
ms.locfileid: "60120713"
---
# <a name="faq-for-regions-in-microsoft-flow"></a>Veelgestelde vragen voor regio's in Microsoft Flow
Dit document bevat een lijst met veelgestelde vragen over Microsoft Flow.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Waar kan ik nagaan waar mijn stroom is geïmplementeerd?
Uw stroom wordt geïmplementeerd in de [regio](https://azure.microsoft.com/regions/) die als host voor de [omgeving](environments-overview-admin.md) fungeert. Een voorbeeld: als uw omgeving is gemaakt in de regio Europa, wordt uw stroom geïmplementeerd op Europese datacenters.

Beheerders kunnen de regio bepalen wanneer ze zich aanmelden bij het [beheercentrum](https://admin.flow.microsoft.com) van Microsoft Flow. Op het tabblad **Omgevingen** worden alle bestaande omgevingen en de bijbehorende regio's weergegeven.

![omgevingen weergeven](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Welke regio's zijn er?
* Verenigde Staten
* Europa
* Azië
* Australië
* India
* Japan
* Canada
* Zuid-Amerika
* Verenigd Koninkrijk
* Amerikaanse overheid (GCC)

## <a name="what-features-are-specific-to-a-given-region"></a>Welke functies gelden alleen voor een bepaalde regio?
Omgevingen kunnen in verschillende regio's worden gemaakt en zijn gebonden aan die geografische locatie. Wanneer u een stroom in een omgeving maakt, wordt die stroom geïmplementeerd in datacenters op die geografische locatie. Dit geldt voor alle items die u in die omgeving maakt, waaronder Common Data Model, stromen, verbindingen, gateways, apps en aangepaste connectors.

Voor optimale prestaties moet u de omgeving maken in de dichtstbijzijnde regio voor uw gebruikers. Als uw gebruikers zich bijvoorbeeld in Europa bevinden, maakt u de omgevingen in de regio Europa. Bevinden uw gebruikers zich in de Verenigde Staten, dan maakt u de omgevingen in de regio Verenigde Staten.

## <a name="gateways"></a>Gateways:
Voor gateways geldt het volgende:

* Momenteel niet beschikbaar in de regio India.
* Wordt alleen ondersteund in de standaardomgeving, niet in aangepaste omgevingen.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>Is Microsoft Flow beschikbaar in nationale clouds?
Nee, Microsoft Flow is niet beschikbaar in nationale clouds. Ondersteuning voor nationale clouds staat gepland voor 2018.

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Welke uitgaande IP-adressen worden in de verschillende regio's gebruikt?
Zie [Limieten en configuratie](limits-and-config.md).

