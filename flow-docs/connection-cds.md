---
title: Een geautomatiseerde stroom maken met Common Data Service | Microsoft Docs
description: Werk stromen maken met behulp van een Common Data Service verbinding en Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 110f3947cf7ece97bfd9b83ca6a12ee46d04b4d6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547116"
---
# <a name="create-an-automated-flow-by-using-common-data-service"></a>Een automatische stroom maken met behulp van Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Met de Common Data Service-connector kunt u stromen maken die worden geïnitieerd door gebeurtenissen in uw Common Data Service-data base te maken en bij te werken. Daarnaast kunt u acties voor het maken, bijwerken, ophalen en verwijderen van records in de Common Data Service Data Base uitvoeren.

## <a name="initiate-a-flow-from-common-data-service"></a>Een stroom initiëren vanuit Common Data Service

U kunt een van de volgende triggers gebruiken om uw stroom te initiëren:

- Wanneer een record wordt geselecteerd
- Wanneer een record wordt gemaakt
- Wanneer een record wordt verwijderd
- Wanneer een record wordt bijgewerkt


> [!div class="mx-imgBorder"]
> ![een trigger selecteren](./media/cds-connector/Triggers.png)

Als voor de geselecteerde trigger een omgeving moet worden geselecteerd, kunt u `(Current)`kiezen. de data base wordt altijd gebruikt in de omgeving waarin Microsoft Flow wordt uitgevoerd. Als u de stroom altijd wilt activeren op basis van een gebeurtenis in een specifieke omgeving, selecteert u die omgeving.

> [!div class="mx-imgBorder"]
> ![omgeving kiezen](./media/cds-connector/Environments.png)

U kunt bereiken gebruiken om te bepalen of de stroom wordt uitgevoerd als u een nieuwe record maakt, als er een nieuwe record wordt gemaakt door een gebruiker in uw bedrijfs unit of als er een nieuwe record wordt gemaakt door een gebruiker in uw organisatie.

> [!div class="mx-imgBorder"]
> ![bereik kiezen](./media/cds-connector/Scopes.png)

|ligt|Trigger tijd|
| --- | --- |
|Bedrijfs eenheid|Er wordt actie ondernomen voor een record die eigendom is van uw Business Unit|
|Organisatie|De actie wordt uitgevoerd door iedereen binnen de organisatie of data base|
|Bovenliggend item: onderliggende Business Unit|Er wordt actie ondernomen voor een record die eigendom is van uw Business Unit of een onderliggende Business Unit|
|Gebruiker|Er wordt actie ondernomen voor een record waarvan u eigenaar bent|

Triggers die worden uitgevoerd wanneer een record wordt bijgewerkt, kunnen ook filter kenmerken gebruiken. Dit zorgt ervoor dat de stroom alleen wordt uitgevoerd wanneer een van de gedefinieerde kenmerken worden bijgewerkt.

> [!IMPORTANT]
> Gebruik filter kenmerken om te voor komen dat uw stroom onnodig wordt uitgevoerd.

Deze stroom wordt elke keer geactiveerd wanneer de eerste of de achternaam van de contact persoon is bijgewerkt dat de gebruiker van de stroom eigenaar is.

> [!div class="mx-imgBorder"]
> ![filter kenmerken](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Bevoegdheid activeren

Voor het maken van een stroom die wordt geactiveerd op basis van maken, bijwerken of verwijderen van een record, moet de gebruiker machtigingen voor maken, lezen, schrijven en verwijderen hebben op de registratie-entiteit van de retour aanroep. Daarnaast moet de gebruiker, afhankelijk van de gedefinieerde bereiken, mogelijk ten minste het niveau van lezen hebben voor dezelfde entiteit.  Meer [informatie](https://docs.microsoft.com/power-platform/admin/database-security) over omgevings beveiliging.

## <a name="write-data-into-common-data-service"></a>Gegevens schrijven naar Common Data Service

Gebruik een van de volgende acties om gegevens naar Common Data Service te schrijven:

- Een nieuwe record maken
- Een record bijwerken

Hier volgt een voor beeld van het maken van een vervolg taak wanneer de opgegeven gebruiker een nieuwe account record maakt.  

> [!div class="mx-imgBorder"]
> ![vervolg taak](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Geavanceerde concepten

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Gegevens schrijven naar de velden klant, eigenaar en betreft

Voor het schrijven van gegevens naar de velden klant, eigenaar en betreft, moeten twee velden worden ingevuld.

| Veld categorie | voorbeeld instellingen |
| --- | --- |
| Over | Betreft = ID van de record (bijvoorbeeld account-ID) en het type dat is geselecteerd in de lijst. |
| Gebruikers | Vertegenwoordigt de ID van de record en het klant type dat is geselecteerd in de lijst. |
| Bent | Hiermee wordt de ID van de gebruiker of het team van het systeem, en het type eigenaar, geselecteerd in de lijst. |

### <a name="enable-upsert-behavior"></a>Gedrag van upsert inschakelen

U kunt de opdracht voor het **bijwerken van een record** gebruiken om upsert acties te bieden, waarmee de record wordt bijgewerkt als deze al bestaat, of een nieuwe record wordt gemaakt. Geef de entiteit en een GUID-sleutel op om upsert aan te roepen. Als de record met het opgegeven type en de sleutel bestaat, wordt er een update uitgevoerd. Anders wordt een record met de opgegeven sleutel gemaakt.

### <a name="trigger-behavior"></a>Gedrag activeren

Als u een trigger hebt geregistreerd voor de update van een record, wordt de stroom uitgevoerd voor elke *vastgelegde* update voor de gegeven record. De service roept uw stroom asynchroon aan en met de nettolading die wordt vastgelegd op het moment dat de aanroep plaatsvindt.

> [!NOTE]
> Als u twee updates hebt die binnen enkele seconden van elkaar plaatsvinden, kan de stroom meerdere keren worden geactiveerd met de nieuwste versie-inhoud.

Stroom uitvoeringen kunnen worden vertraagd als er sprake is van systeem taken in uw omgeving.  Als deze vertraging optreedt, wordt de stroom geactiveerd wanneer de systeem taak de stroom uitvoeringen aanroept.
