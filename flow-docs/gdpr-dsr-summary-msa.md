---
title: Samen vatting van AVG-gegevens aanvragen voor micro soft-accounts (MSA) | Microsoft Docs
description: Meer informatie over hoe u kunt reageren op aanvragen voor AVG betrokkenen-gegevens voor Microsoft Flow.
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
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: bff3e050db40c60622496202a092f94cc1d36fca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548161"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>Reageren op DSRs-aanvragen (AVG data subject Rights)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

In dit artikel worden de AVG (AVG) van de Europese Unie beschreven en vindt u stappen die u kunt nemen om AVG-naleving te ondersteunen voor Microsoft Flow gebruikers die verifiëren met micro soft-accounts (MSA).

## <a name="prerequisites"></a>Vereisten

U hebt een MSA met een [gratis Microsoft flow-licentie](https://flow.microsoft.com/pricing/) nodig om de stappen in dit artikel uit te voeren.

>[!TIP]
> AVG-compatibiliteits informatie is ook beschikbaar voor gebruikers die zich verifiëren met [Azure Active Directory accounts](gdpr-dsr-summary.md).
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>Reageren op DSRs voor Microsoft Flow klant gegevens

De formele aanvraag van een ondertekenaar naar een controller om een actie op hun persoons gegevens uit te voeren, wordt een DSR-aanvraag (data subject Rights) genoemd. AVG definieert persoons gegevens als **gegevens die betrekking hebben op een geïdentificeerde of Identificeer bare natuurlijke persoon**. De AVG biedt personen (ook wel bekend als betrokkene) rechten voor het beheren van de persoons gegevens die door een werk gever, instantie of organisatie worden verzameld (ook wel bekend als de gegevens controller of de controller). Deze rechten zijn onder andere:

* Het verkrijgen van kopieën van persoons gegevens.
* Correcties aanvragen voor persoons gegevens.
* Het beperken van de verwerking van persoons gegevens.
* De persoonlijke gegevens worden verwijderd.
* Het ontvangen van persoons gegevens in een elektronische indeling zodat deze kan worden verplaatst naar een andere controller.

Micro soft biedt-producten,-services en-hulpprogram ma's om te helpen bij het zoeken naar en reageren op persoonlijke gegevens bij het reageren op DSRs-aanvragen voor gegevens die zich in de cloud bevinden.

Hier volgt een overzicht van de processen die in deze hand leiding worden beschreven:

1. **Ontdekken**: gebruik Zoek-en detectie hulpprogramma's om eenvoudig klant gegevens te vinden die het onderwerp van een DSR-aanvraag kunnen zijn. Als u vaststelt dat de documenten die u verzamelt voldoen aan de richt lijnen voor het nemen van de actie, kunt u een of meer van de DSR-acties uitvoeren die in de volgende stappen worden beschreven. Meer informatie vindt u in de [Microsoft flow DSR-detectie documentatie voor micro soft-accounts](gdpr-dsr-discovery-msa.md). U kunt ook bepalen dat de aanvraag niet voldoet aan de richt lijnen van uw controller voor het reageren op DSR-aanvragen.

1. **Toegang**: persoons gegevens ophalen die zich in de micro soft-cloud bevinden en, indien aangevraagd, een kopie hiervan maken, zodat deze beschikbaar is voor de betrokkene.

1. **Corrigeren**: Breng wijzigingen aan of implementeer andere aangevraagde acties op de persoons gegevens, indien van toepassing.

1. **Beperken**: de verwerking van persoons gegevens beperken door licenties voor verschillende onlineservices te verwijderen of de gewenste services waar mogelijk uit te scha kelen. U kunt ook gegevens uit de micro soft-Cloud verwijderen en deze on-premises of op een andere locatie bewaren.

1. **Verwijderen**: persoons gegevens die zich in de cloud van micro soft bevinden permanent verwijderen. Meer informatie over het [verwijderen van persoonlijke gegevens voor micro soft-accounts](gdpr-dsr-delete-msa.md). Meer informatie over [het sluiten van een micro soft-account](gdpr-dsr-accountclose-msa.md).

1. **Exporteren**: een elektronisch exemplaar (in een door de machine Lees bare indeling) persoonlijke gegevens opgeven. [Meer informatie over het exporteren van persoonlijke gegevens voor micro soft-accounts](gdpr-dsr-export-msa.md).
