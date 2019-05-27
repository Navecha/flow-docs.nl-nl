---
title: AVG-verzoeken van betrokkenen - samenvatting | Microsoft Docs
description: Informatie over hoe u moet reageren op AVG-verzoeken van betrokkenen voor Microsoft Flow.
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
ms.date: 4/24/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 1eaa98b674e78f46988d253e2be76a5d92283a76
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460427"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Reageren op AVG-verzoeken van betrokkenen voor Microsoft Flow

Dit artikel bereidt u en uw organisatie voor op de Algemene verordening gegevensbescherming (AVG) van de Europese Unie. In dit artikel wordt niet alleen beschreven wat Microsoft doet ter voorbereiding op de AVG, maar er zijn ook voorbeelden van hoe u vandaag al AVG-naleving kunt ondersteunen bij gebruik van PowerApps, Microsoft Flow en Common Data Service.

## <a name="prerequisites"></a>Vereisten

Gebruikers en beheerders kunnen de in dit artikel beschreven acties uitvoeren.

### <a name="users"></a>Gebruikers

Een gebruiker moet een actief Azure Active Directory-account met een [Microsoft Flow-licentie](https://preview.flow.microsoft.com/pricing/) hebben. Gebruikers die niet aan deze vereiste voldoen, moeten een beheerder vragen deze acties uit te voeren.

### <a name="administrators"></a>Beheerders

U kunt de bewerkingen waarvoor beheerdersbevoegdheden zijn vereist (zoals beschreven in dit artikel), uitvoeren als u zich aanmeldt bij het [Microsoft Flow-beheercentrum](https://admin.flow.microsoft.com/) of bij [PowerApps Admin PowerShell](https://go.microsoft.com/fwlink/?linkid=871804) met een account met deze beide machtigingen:

- Een betaalde licentie of proeflicentie voor PowerApps Plan 2.

    [Een proeflicentie](http://web.powerapps.com/trial) verloopt na 30 dagen.

- [Globale beheerder voor Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) of [Globale beheerder voor Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Onbeheerde tenants
Als u lid bent van een [onbeheerde tenant](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), wat betekent dat uw Azure AD-tenant geen algemene beheerder heeft, kunt u nog steeds de in dit artikel beschreven stappen uitvoeren voor het exporteren en verwijderen van uw eigen persoonsgegevens. 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Reageren op verzoeken van betrokkenen voor klantgegevens in Microsoft Flow

De AVG verleent rechten aan personen (in de AVG aangeduid als betrokkenen) voor het beheren van de persoonsgegevens die zijn verzameld door een werkgever of ander type bureau of organisatie (bekend als de verwerkingsverantwoordelijke, of gewoon, verantwoordelijke). Persoonsgegevens zijn in de AVG zeer ruim gedefinieerd als alle gegevens die betrekking hebben op een geïdentificeerde of identificeerbare natuurlijke persoon. De AVG verleent betrokkenen specifieke rechten voor hun persoonsgegevens. Tot deze rechten behoren kopieën van persoonsgegevens verkrijgen, het aanvragen van correcties daarvan, het beperken van de verwerking ervan, het verwijderen ervan of het ontvangen van persoonsgegevens in digitale vorm, zodat deze aan een andere verantwoordelijke kunnen worden doorgegeven. Een formeel verzoek door een betrokkene aan een verantwoordelijke om actie te ondernemen op de persoonsgegevens van de betrokkene wordt een verzoek van betrokkene genoemd.

In dit artikel wordt beschreven hoe u Microsoft-producten, -services en -beheerprogramma's gebruikt om verantwoordelijken te helpen bij het zoeken naar en verwerken van persoonsgegevens als reactie op een verzoek van een betrokkene. Dit artikel laat met name zien hoe persoonsgegevens die zich in de cloud van Microsoft bevinden, kunnen worden gevonden, geopend en verwerkt. Hier volgt een kort overzicht van de processen die in deze handleiding worden beschreven:

1. Ontdekken: Gebruik zoek- en detectieprogramma's om gemakkelijker te zoeken naar klantgegevens die het onderwerp van een verzoek van een betrokkene kunnen zijn. Nadat mogelijk responsieve documenten zijn verzameld, kunt u een of meer van de acties voor verzoeken van betrokkenen uitvoeren die worden beschreven in de volgende stappen om te reageren op het verzoek. U kunt ook vaststellen dat het verzoek niet voldoet aan de richtlijnen van uw organisatie voor het reageren op verzoeken van betrokkenen. [Microsoft Flow: detectiedocumentatie voor verzoeken van betrokkenen](gdpr-dsr-discovery.md)

1. Toegang: Haal persoonsgegevens op die zich in de Microsoft-cloud bevinden en, als daarom wordt verzocht, maakt u er een kopie van die beschikbaar kan worden gesteld aan betrokkene.

1. Rectificeren: Breng waar van toepassing wijzigingen aan of implementeer andere aangevraagde acties voor de persoonsgegevens.

    Als een betrokkene u vraagt om rectificatie van diens persoonsgegevens die zich in uw organisatie bevinden, moeten u en uw organisatie bepalen of aan dat verzoek kan worden voldaan.  Rectificatie van de gegevens kan betrekking hebben op het uitvoeren van acties zoals bewerken, redigeren of verwijderen van persoonlijke gegevens.

    U kunt Azure Active Directory gebruiken voor het beheren van de identiteit van Microsoft Flow-gebruikers. Enterprise-klanten kunnen inzageverzoeken voor rectificatie beheren, met inbegrip van beperkte bewerkingsfuncties, naar gelang de aard van een bepaalde Microsoft-service.  Als gegevensverwerker biedt Microsoft niet de mogelijkheid om door een systeem gegenereerde logboeken te corrigeren omdat deze logboeken feitelijke activiteiten weerspiegelen en een historisch overzicht vormen van gebeurtenissen in Microsoft-services.  [Meer informatie over verzoeken van betrokkenen](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Beperken: Beperk de verwerking van persoonsgegevens, hetzij door het verwijderen van licenties voor verschillende onlineservices, hetzij door het waar mogelijk uitschakelen van de gewenste services. U kunt ook gegevens uit de Microsoft-cloud verwijderen en deze lokaal of op een andere locatie bewaren.

    Betrokkenen kunnen u verzoeken de verwerking van hun persoonsgegevens te beperken.  Microsoft biedt Application Programming Interfaces (API's) en gebruikersinterfaces (UI's) voor dit doel.  Met deze interfaces kan de tenantbeheerder van de Enterprise-klant dergelijke inzageverzoeken beheren door het exporteren en verwijderen van gegevens te combineren. Een klant kan (1) een digitale kopie van de persoonsgegevens van de gebruiker exporteren, inclusief account(s), door het systeem gegenereerde logboeken en bijbehorende logboeken, gevolgd door (2) de verwijdering van het account en de bijbehorende gegevens die zich binnen de Microsoft-systemen bevinden.

1. Verwijderen: Verwijder definitief persoonsgegevens in de Microsoft-cloud. [Meer informatie over het verwijderen van persoonsgegevens](gdpr-dsr-delete.md).

1. Exporteren: Verstrek een digitale kopie (in een voor machines leesbare indeling) van persoonsgegevens aan de betrokkene. Elke sectie in dit artikel bevat een overzicht van de technische procedures die een organisatie als verwerkingsverantwoordelijke kan uitvoeren om te reageren op een verzoek van een betrokkene voor persoonsgegevens in de Microsoft-cloud. [Meer informatie over het exporteren van persoonsgegevens](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Door het systeem gegenereerde logboeken

Raadpleeg deze [handleiding](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) voor meer informatie over door het systeem gegenereerde logboeken voor Microsoft Flow.
