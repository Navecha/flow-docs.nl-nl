---
title: Geautomatiseerde stromen maken met Common Data Service for Apps | Microsoft Docs
description: Werkstromen maken met Common Data Service for Apps-verbindingen en Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: brandonsimons
manager: ryjones
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: brandonsimons
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f9a417f99b6ea4105a451b65f7ccabbf36922d78
ms.sourcegitcommit: 61f0eb1fdc54da02eb57dadf09899fa6f308b00d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2019
ms.locfileid: "57524492"
---
# <a name="create-an-automated-flow-by-using-common-data-service-for-apps"></a>Geautomatiseerde stromen maken met Common Data Service for Apps

Met de Common Data Service for Apps-connector kunt u stromen maken die door maak- en bijwerkgebeurtenissen in uw Common Data Service-database zijn geïnitieerd. Daarnaast kunt u de acties maken, bijwerken, ophalen en verwijderen uitvoeren op records in de Common Data Service for Apps-database.

## <a name="initiate-a-flow-from-common-data-service-for-apps"></a>Stromen initiëren vanuit Common Data Service for Apps

U kunt eender welke van de volgende triggers gebruiken om uw stroom te initiëren:

- Wanneer een record wordt geselecteerd
- Wanneer een record wordt gemaakt
- Wanneer een record wordt verwijderd
- Wanneer een record wordt bijgewerkt


> [!div class="mx-imgBorder"]
> ![Een trigger selecteren](./media/cds-connector/Triggers.png)

Als u voor de geselecteerde trigger een omgeving moet selecteren, kunt u `(Current)` kiezen. Hiervoor wordt altijd de database in de omgeving waarin Microsoft Flow wordt uitgevoerd, gebruikt. Als u wilt dat uw stroom altijd wordt geactiveerd op basis van een gebeurtenis in een specifieke omgeving, selecteert u die omgeving.

> [!div class="mx-imgBorder"]
> ![Omgeving kiezen](./media/cds-connector/Environments.png)

U kunt bereiken gebruiken om te bepalen of uw stroom wordt uitgevoerd als u zelf een nieuwe record maakt, als een gebruiker in uw business unit een nieuwe record maakt of als een willekeurige gebruiker in uw organisatie een nieuwe record maakt.

> [!div class="mx-imgBorder"]
> ![Bereik kiezen](./media/cds-connector/Scopes.png)

|Bereik|Timing van triggers|
| --- | --- |
|Business Unit|Er wordt een actie uitgevoerd op een record die het eigendom is van uw business unit|
|Organisatie|Er wordt een actie uitgevoerd door iemand in de organisatie of database|
|Bovenliggend item: Onderliggende Business Unit|Er wordt een actie uitgevoerd op een record die het eigendom is van uw business unit of onderliggende business unit|
|Gebruiker|Er wordt een actie uitgevoerd op een record waarvan u de eigenaar bent|

Voor triggers die worden uitgevoerd wanneer een record wordt bijgewerkt, kunnen ook filterkenmerken worden gebruikt. Dit zorgt ervoor dat de stroom alleen wordt uitgevoerd wanneer eender welke van de gedefinieerde kenmerken wordt bijgewerkt.

> [!IMPORTANT]
> Gebruik filterkenmerken om te voorkomen dat uw stroom onnodig wordt uitgevoerd.

Deze stroom wordt telkens geactiveerd wanneer de voor- of achternaam wordt bijgewerkt van de contactpersoon die het eigendom is van de stroomgebruiker.

> [!div class="mx-imgBorder"]
> ![Filterkenmerken](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Triggerprivileges

Als gebruikers een stroom willen maken die wordt geactiveerd op basis van het maken, bijwerken of verwijderen van een record, moeten ze over machtigingen op gebruikersniveau voor het maken, lezen, schrijven en verwijderen op de entiteit Terugbelregistratie beschikken. Daarnaast hebben gebruikers, afhankelijk van de gedefinieerde bereiken, mogelijk ten minste datzelfde leesniveau nodig op die entiteit.  [Meer informatie](https://docs.microsoft.com/power-platform/admin/database-security) over de beveiliging van omgevingen.

## <a name="write-data-into-common-data-service-for-apps"></a>Gegevens naar Common Data Service for Apps schrijven

Gebruik een van de volgende acties om gegevens naar Common Data Service for Apps te schrijven:

- Een nieuwe record maken
- Een record bijwerken

Hier ziet u een voorbeeld waarin een opvolgtaak wordt gemaakt wanneer de desbetreffende gebruiker een nieuwe accountrecord maakt.  

> [!div class="mx-imgBorder"]
> ![Opvolgtaak](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Geavanceerde concepten

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Gegevens schrijven naar de velden Klant, Eigenaar en Betreffende

Als u gegevens naar de velden Klant, Eigenaar en Betreffende wilt schrijven, moeten twee velden worden ingevuld.

| Veldcategorie | Voorbeeldinstellingen |
| --- | --- |
| Betreffende | Betreffende = de id van de record (bijvoorbeeld account-id) en het type Betreffende zoals dit in de lijst is geselecteerd. |
| Klant | Vertegenwoordigt de id van de record en het klanttype zoals dit in de lijst is geselecteerd. |
| Eigenaar | Vertegenwoordigt de id van de systeemeigenaar of het team en het eigenaarstype zoals dit in de lijst is geselecteerd. |

### <a name="enable-upsert-behavior"></a>Upsert-gedrag inschakelen

U kunt gebruikmaken van de opdracht **een record bijwerken** om upsert-acties te bieden waarmee bestaande records worden bijgewerkt of nieuwe records worden gemaakt. Geef de entiteit en een GUID-sleutel op om upsert aan te roepen. Als de record met het opgegeven type en de opgegeven sleutel bestaat, wordt een update uitgevoerd. Anders wordt een record met de opgegeven sleutel gemaakt.

### <a name="trigger-behavior"></a>Triggergedrag

Als u een trigger hebt geregistreerd bij de update van een record, wordt de stroom uitgevoerd voor elke *toegezegde* update van de opgegeven record. Uw stroom wordt door de service asynchroon aangeroepen, met de payload die door de service wordt vastgelegd tijdens de aanroep.

> [!NOTE]
> Als er twee updates zijn die binnen enkele seconden na elkaar worden uitgevoerd, kan de stroom meer dan eens worden geactiveerd met de inhoud van de nieuwste versie.

Mogelijk worden stroomuitvoeringen vertraagd als er een achterstand met systeemtaken in uw omgeving bestaat.  Als deze vertraging zich voordoet, wordt uw stroom geactiveerd wanneer de systeemtaak bestaat uit het aanroepen van stroomuitvoeringen.
