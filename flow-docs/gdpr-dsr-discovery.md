---
title: 'Microsoft Flow: AVG-verzoeken van betrokkenen - detectie | Microsoft Docs'
description: Ontdek hoe u Microsoft Flow kunt gebruiken om te reageren op inzageverzoeken van betrokkenen in het kader van de AVG.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: 9f950da1b62eac66b35a667f307917f704eb9133
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31823187"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Met Microsoft Flow reageren op inzageverzoeken van betrokkenen in het kader van de AVG

De eerste stap om te reageren op een verzoek van een betrokkene, is het vinden van de persoonlijke gegevens waarop het verzoek betrekking heeft. Deze eerste stap helpt u om te bepalen of een verzoek voldoet aan de vereisten van uw organisatie voor het inwilligen of afwijzen van een verzoek van een betrokkene. Nadat de betreffende persoonsgegevens zijn gevonden en bekeken, kunt u bijvoorbeeld vaststellen dat het verzoek niet voldoet aan de vereisten van uw organisatie omdat het inwilligen ervan nadelige gevolgen zou kunnen hebben voor de rechten en vrijheden van anderen.

Hieronder volgt een samenvatting van de typen Microsoft Flow-resources die persoonsgegevens voor een specifieke gebruiker bevatten.

|**Resources met persoonsgegevens**|**Doel**|
|-----|-----|
|Door het systeem gegenereerde logboeken|Telemetrie waarmee systeemgebeurtenissen en de geschiedenis worden vastgelegd.|
|Uitvoeringsgeschiedenis|De geschiedenis van elke uitvoering van een stroom gedurende de afgelopen 28 dagen. Deze gegevens omvatten de begintijd, eindtijd, status en alle i/o-informatie voor de stroom. [Meer informatie](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Activiteitsfeed| Geeft een samenvatting van stroomactiviteiten, waaronder de uitvoeringsstatus, fouten en meldingen.|
|Gebruikerstaken|Systeemtaken (niet zichtbaar voor de gebruiker) die worden uitgevoerd namens een gebruiker zodat stromen kunnen worden uitgevoerd.|
|Stromen|De werkstroomlogica die voor een stroom bestaat. [Meer informatie](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Stroommachtigingen|Stromen kunnen worden gedeeld en opnieuw worden toegewezen aan andere gebruikers. Er zijn lijsten met machtigingen voor alle stromen. [Meer informatie](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Gebruikersdetails|Gegevens (niet zichtbaar voor de gebruiker) die ondersteuning bieden voor uitvoering van de stroom.|
|Verbindingen|Gebruikt door connectors en toegestaan voor verbindingen met API's, systemen, databases, enzovoort. [Meer informatie](https://docs.microsoft.com/flow/add-manage-connections)|
|Verbindingsmachtigingen|Machtigingen voor een specifieke verbinding. [Meer informatie](https://docs.microsoft.com/flow/add-manage-connections)|
|Aangepaste connectors|Aangepaste connectors die een gebruiker heeft gemaakt en gepubliceerd, en waarmee verbinding met aangepaste systemen of systemen van derden kan worden gemaakt. [Meer informatie](https://docs.microsoft.com/connectors/custom-connectors/)|
|Machtigingen voor aangepaste connectors|Lijst met machtigingen voor aangepaste connectors. [Meer informatie](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Gateway|Gateways zijn lokale gegevensservices die door een gebruiker kunnen worden geïnstalleerd om gegevens snel en veilig over te dragen tussen Microsoft Flow en een gegevensbron die zich niet in de cloud bevindt. [Meer informatie](https://docs.microsoft.com/flow/gateway-manage)|
|Gatewaymachtigingen|Gateways kunnen worden gedeeld met gebruikers binnen een organisatie. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872249)|
