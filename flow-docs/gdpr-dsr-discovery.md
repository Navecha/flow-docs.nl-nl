---
title: Detectie van Microsoft Flow AVG-gegevens aanvragen | Microsoft Docs
description: Meer informatie over het gebruik van Microsoft Flow om te reageren op aanvragen voor AVG betrokkenen-gegevens voor het onderwerp.
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
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 197d9ebfc38fc4f5b52bf674aef61d419530f439
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548129"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Reageren op aanvragen voor detectie van AVG-gegevens voor Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

De eerste stap bij het reageren op een DSR is het vinden van persoons gegevens die het onderwerp van de aanvraag zijn. Deze eerste stap helpt u om te bepalen of een DSR voldoet aan de vereisten van uw organisatie om een DSR-aanvraag te respecteren of te weigeren. Nadat u bijvoorbeeld de persoons gegevens hebt gevonden en bekeken, kunt u bepalen dat de aanvraag niet voldoet aan de vereisten van uw organisatie, omdat dit de rechten en vrijheden van anderen nadelig kan beïnvloeden.

Hieronder volgt een samen vatting van de typen Microsoft Flow resources die persoonlijke gegevens voor een specifieke gebruiker bevatten.

|**Resources met persoons gegevens**|**Doel**|
|-----|-----|
|Door het systeem gegenereerde logboeken|Telemetrie waarmee systeem gebeurtenissen en geschiedenis worden vastgelegd.|
|uitvoerings geschiedenis|De geschiedenis van elke stroom uitvoering gedurende de afgelopen 28 dagen. Deze gegevens omvatten de begin tijd, eind tijd, status en alle invoer-en uitvoer gegevens voor de stroom. [Meer informatie](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Activiteitsfeed| Biedt een samen vatting aan stroom activiteiten, waaronder uitvoerings status, fouten en meldingen.|
|Gebruikers taken|Systeem taken die namens een gebruiker worden uitgevoerd, zijn niet zichtbaar voor de gebruiker, zodat stromen kunnen worden uitgevoerd.|
|Terugloop|De werk stroom logica die voor een stroom bestaat. [Meer informatie](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Stroom machtigingen|Stromen kunnen worden gedeeld en opnieuw worden toegewezen aan andere gebruikers. Voor alle stromen bestaan machtigingen lijsten. [Meer informatie](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Gebruikers Details|Details die niet worden weer gegeven door de gebruiker en die de uitvoering van stromen ondersteunen.|
|Inbel|Wordt gebruikt door connectors en biedt connectiviteit met Api's, systemen, data bases, enzovoort. [Meer informatie](https://docs.microsoft.com/flow/add-manage-connections)|
|Verbindings machtigingen|Machtigingen voor een specifieke verbinding. [Meer informatie](https://docs.microsoft.com/flow/add-manage-connections)|
|Aangepaste connectors|Aangepaste connectors die een gebruiker heeft gemaakt en gepubliceerd, die verbinding kunnen maken met aangepaste of systemen van derden. [Meer informatie](https://docs.microsoft.com/connectors/custom-connectors/)|
|Machtigingen voor aangepaste connectors|Machtigings lijsten voor aangepaste connectors. [Meer informatie](https://docs.microsoft.com/connectors/custom-connectors/share)|
|#B0|Gateways zijn on-premises gegevens services die door een gebruiker kunnen worden geïnstalleerd om gegevens snel en veilig over te dragen tussen Microsoft Flow en een gegevens bron die zich niet in de Cloud bevindt. [Meer informatie](https://docs.microsoft.com/flow/gateway-manage)|
|Gateway machtigingen|Gateways kunnen worden gedeeld met gebruikers binnen een organisatie. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872249)|
