---
title: Samen vatting van AVG-gegevens aanvragen | Microsoft Docs
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
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: c4d2686e9da00aaccc46e62570de387678bd1ece
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548211"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Reageren op aanvragen voor AVG-gegevens voor Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

In dit artikel worden de AVG (AVG) van de Europese Unie voor u en uw organisatie voor bereid. In dit artikel wordt niet alleen beschreven wat micro soft doet om voor te bereiden op de AVG, maar deelt ook voor beelden van stappen die u vandaag kunt uitvoeren om AVG-naleving te ondersteunen bij het gebruik van PowerApps, Microsoft Flow en Common Data Service.

## <a name="prerequisites"></a>Vereisten

Gebruikers en beheerders kunnen de acties uitvoeren die in dit artikel worden beschreven.

### <a name="users"></a>Bezoekers

Een gebruiker moet een actief Azure Active Directory-account hebben met een [Microsoft flow-licentie](https://preview.flow.microsoft.com/pricing/). Gebruikers die niet aan deze vereiste voldoen, moeten een beheerder vragen deze acties uit te voeren.

### <a name="administrators"></a>Beheerders

U kunt de bewerkingen uitvoeren waarvoor beheerders bevoegdheden nodig zijn, zoals beschreven in dit artikel als u zich aanmeldt bij het [Microsoft flow beheer centrum](https://admin.flow.microsoft.com/) of [PowerApps admin Power shell](https://go.microsoft.com/fwlink/?linkid=871804) met een account met beide machtigingen:

- Een betaalde of proef licentie voor PowerApps-abonnement 2.

    [Een proef licentie](http://web.powerapps.com/trial) verloopt over 30 dagen.

- [Office 365 Global Administrator](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) of [Azure Active Directory globale beheerder](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Niet-beheerde tenants
Als u lid bent van een [onbeheerde Tenant](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), wat betekent dat uw Azure AD-Tenant geen globale beheerder heeft, kunt u nog steeds de stappen volgen die in dit artikel worden beschreven om uw eigen persoonlijke gegevens te exporteren en te verwijderen. 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Reageren op DSRs voor Microsoft Flow klant gegevens

De AVG verleent rechten aan personen (bekend in de AVG als betrokkenen) voor het beheren van de persoons gegevens die zijn verzameld door een werk gever of een ander type instantie of organisatie (bekend als de gegevens controller of alleen de controller). Persoonlijke gegevens worden zeer breed volgens de AVG gedefinieerd als gegevens die betrekking hebben op een geïdentificeerde of Identificeer bare natuurlijke persoon. De AVG geeft de betrokkenen specifieke rechten voor hun persoons gegevens. Dit zijn onder andere het verkrijgen van kopieën van persoons gegevens, het aanvragen van correcties, het beperken van de verwerking, het verwijderen ervan of het ontvangen van een elektronisch formaat zodat het kan worden verplaatst naar een andere controller. Een formele aanvraag door een beheerder om een actie op hun persoons gegevens uit te voeren, wordt een DSR-aanvraag (data subject Rights) genoemd.

In dit artikel wordt beschreven hoe u de producten, services en beheer hulpprogramma's van micro soft gebruikt om te helpen bij het zoeken naar en reageren op persoonlijke gegevens bij het reageren op DSRs. In dit artikel vindt u meer informatie over het zoeken, openen en uitvoeren van persoonlijke gegevens die zich in de cloud van micro soft bevinden. Hier volgt een kort overzicht van de processen die in deze hand leiding worden beschreven:

1. Ontdekken: gebruik Zoek-en detectie hulpprogramma's om gemakkelijker klant gegevens te vinden die het onderwerp van een DSR kunnen zijn. Zodra mogelijk responsieve documenten zijn verzameld, kunt u een of meer van de DSR-acties uitvoeren die worden beschreven in de volgende stappen om te reageren op de aanvraag. U kunt ook bepalen dat de aanvraag niet voldoet aan de richt lijnen van uw organisatie voor het reageren op DSRs. [Documentatie voor de DSR-detectie Microsoft Flow](gdpr-dsr-discovery.md)

1. Toegang: persoons gegevens ophalen die zich in de micro soft-cloud bevinden en, indien aangevraagd, een kopie hiervan maken die beschikbaar kan zijn voor de betrokkene.

1. Corrigeren: Breng wijzigingen aan of implementeer andere aangevraagde acties op de persoons gegevens, indien van toepassing.

    Als een betrokkene u vraagt om de persoons gegevens te corrigeren die zich in uw organisatie bevinden, moeten u en uw organisatie bepalen of het geschikt is om te voldoen aan de aanvraag.  Het corrigeren van de gegevens kan het nemen van acties omvatten, zoals het bewerken, redigeren of verwijderen van persoonlijke gegevens.

    U kunt Azure Active Directory gebruiken om de identiteiten van Microsoft Flow gebruikers te beheren. Zakelijke klanten kunnen DSR-aanvragen beheren, inclusief beperkte bewerkings functies, volgens de aard van een bepaalde micro soft-service.  Als gegevens verwerker biedt micro soft niet de mogelijkheid om door het systeem gegenereerde logboeken te corrigeren omdat deze logboeken feitelijke activiteiten weer spie gelen en een historisch overzicht vormen van gebeurtenissen in micro soft-Services.  Meer [informatie over DSR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Beperken: de verwerking van persoons gegevens beperken door licenties voor verschillende onlineservices te verwijderen of de gewenste services waar mogelijk uit te scha kelen. U kunt ook gegevens uit de micro soft-Cloud verwijderen en deze on-premises of op een andere locatie bewaren.

    De betrokkenen kunnen een aanvraag indienen om de verwerking van hun persoons gegevens te beperken.  Micro soft biedt Api's (Application Programming Interfaces) en gebruikers interfaces (UIs) voor dit doel.  Met deze interfaces kan de Tenant beheerder van de zakelijke klant dergelijke DSRs beheren via een combi natie van gegevens export en gegevens verwijdering. Een klant kan (1) een elektronisch exemplaar van de persoons gegevens van de gebruiker exporteren, waaronder account (s), door het systeem gegenereerde logboeken en gekoppelde logboeken, gevolgd door (2) het verwijderen van het account en de bijbehorende gegevens die zich in micro soft-systemen bevinden.

1. Verwijderen: persoons gegevens die zich in de cloud van micro soft bevinden permanent verwijderen. [Meer informatie over het verwijderen van persoonlijke gegevens](gdpr-dsr-delete.md).

1. Exporteren: een elektronisch exemplaar (in een door de machine Lees bare indeling) persoonlijke gegevens verzenden naar de betrokkene. In elke sectie van dit artikel worden de technische procedures beschreven die een organisatie van gegevens controllers kan ondernemen om te reageren op een DSR voor persoons gegevens in de cloud van micro soft. [Meer informatie over het exporteren van persoonlijke gegevens](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Door het systeem gegenereerde logboeken

Raadpleeg deze [hand leiding](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) voor meer informatie over door het systeem gegenereerde logboeken voor Microsoft flow.
