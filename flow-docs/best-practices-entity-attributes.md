---
title: Aanbevolen procedures voor het gebruik van entiteits kenmerken van de bedrijfs proces stroom | MicrosoftDocs
description: Meer informatie over de aanbevolen procedures voor het gebruik van entiteits kenmerken van de bedrijfs proces stroom.
ms.custom: ''
ms.date: 04/23/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Business Process Flows
helpviewer_keywords:
- flow
- process flow
- business process flow
- process
- workflow
author: msftman
ms.author: deonhe
manager: kvivek
ms.openlocfilehash: b46eac7317db8f5b63ebcd7b8b1fe8c79109bc11
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545292"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Aanbevolen procedures voor het gebruik van stroom kenmerken van bedrijfs processen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]


Verouderde proces-gerelateerde kenmerken in entiteiten worden afgeschaft. Hier volgen enkele aanbevolen procedures voor het gebruik van het kenmerk *Active stage* (activestageid) in de entiteit bedrijfs proces stroom. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Rapportage over de actieve fase van een bedrijfs proces stroom

Stel dat u een weer gave van uw verkoop pijplijn wilt krijgen door te rapporteren over de actieve fase waarin het **verkoop proces van leads** op verkoop kansen is ingeschakeld.

Als u voorheen wilt rapporteren over bedrijfs processen per fase, kunt u een weer gave definiëren voor elke gerelateerde entiteit van de bedrijfs proces stroom en vervolgens rapporteren over het veld *Active stage* (activestageid).

Met de afschaffing van het veld *Active stage* (activestageid) op gerelateerde entiteiten zijn er twee manieren om te rapporteren over bedrijfsproces stromen.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Optie 1: weer gaven en grafieken van de entiteit bedrijfs proces stroom **(aanbevolen)**

In versies 9,0 en hoger maakt elke bedrijfs proces stroom een eigen Common Data Service entiteit, meestal met dezelfde naam als de bedrijfs proces stroom. Als u wilt rapporteren over de stroom van het bedrijfs proces, selecteert u de entiteit voor de bedrijfsproces stroom die u wilt rapporteren en maakt u vervolgens weer gaven en grafieken, net zoals u dat eerder hebt gedaan.

In ons voor beeld gaat u als volgt te werk om naar de entiteit **lead to verkoop proces** te gaan:
1. Ga naar https://web.powerapps.com.
1. Selecteer de **gegevens**.
1. Selecteer de **entiteiten**.
1. Stel het filter in op **alle**.
1. Zoek naar en selecteer de entiteit **lead to verkoop proces** .

   ![entiteit verkoop proces lead naar verkoop kans](media/best-practices-entity-attributes/lead-opportunity-process.png)

Hier kunt u weer gaven en grafieken definiëren op dezelfde manier als voor andere entiteiten.

![Details van entiteit Vertaal proces](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

Een voor deel van deze benadering is dat u een enkele weer gave of grafiek kunt gebruiken om te rapporteren over bedrijfs proces stromen die meerdere entiteiten omvatten.

Als de entiteit bedrijfs proces stroom niet anders is dan een andere aangepaste entiteit in Common Data Service, kunt u aangepaste velden aan de entiteit toevoegen om eventuele aanvullende informatie die u nodig hebt bij te houden.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Optie 2: actieve fase kopiëren naar een gerelateerde entiteit

Als u wilt door gaan met de rapportage van de gerelateerde entiteit, maakt u een stroom om het veld *Active stage* (activestageid) van de entiteit bedrijfs proces stroom te kopiëren naar een aangepast veld op de gerelateerde common data service entiteiten.

Hier volgen enkele dingen die u moet onthouden wanneer u deze aanpak gebruikt:

1.  Het is mogelijk om meer dan één proces stroom op één entiteit uit te voeren. Met deze methode kunt u het beste één aangepast veld hebben waarin de actieve fase wordt opgeslagen voor elke bedrijfsproces stroom die wordt uitgevoerd op de entiteit. Deze aanpak zorgt voor de integriteit van de rapportage.

1.  Als rapportage is gebaseerd op de gerelateerde entiteit, is het niet mogelijk om één weer gave te maken die rapporteert over bedrijfs proces stromen die meerdere entiteiten omvatten.

## <a name="using-the-active-stage-to-run-logic"></a>De actieve fase gebruiken om logica uit te voeren

Hier volgen enkele gevallen waarin u mogelijk logica wilt uitvoeren die is gebaseerd op de actieve fase:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>De actieve fase gebruiken om logica aan de client zijde uit te voeren

Wanneer u het bedrijfs proces gebruikt, zijn er veel dingen die u mogelijk automatisch wilt uitvoeren. Bijvoorbeeld:

-   Wijzig de actieve bedrijfsproces stroom op basis van nieuw beschik bare informatie over de formulier-of bedrijfsproces stroom.

-   Verplaats de actieve fase naar het volgende of vorige stadium, op basis van de waarden die door de gebruikers zijn ingevoerd voor stappen of formulier velden.

-   Formulier tabbladen en-velden weer geven of verbergen op basis van de geselecteerde fase.

-   Geef informatieve berichten weer en voer calulations uit op basis van de actieve bedrijfs proces stromen, het actieve of geselecteerde stadium of gebeurtenissen zoals het verplaatsen van de actieve fase.

> [!TIP]
> Gebruik voor scenario's als deze de ondersteunde set client- [api's](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) voor bedrijfsproces stromen.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>De actieve fase gebruiken om logica aan de server zijde uit te voeren

Er zijn mogelijk situaties waarin automatisering op basis van de bedrijfs proces stroom aan de server zijde moet worden uitgevoerd. Bijvoorbeeld:

-   Een e-mail verzenden naar een gebruiker als de fase van het **verkoop proces voor verkoop kansen** **in aanmerking komt** langer dan 15 dagen actief is.

-   Automatisch een set activiteiten maken die relevant zijn voor het actieve stadium van het **verkoop proces van verkoop kansen** telkens wanneer het wordt gewijzigd.

-   Het **verkoop proces voor verkoop kansen** automatisch volt ooien wanneer de telefoon oproep activiteit is voltooid.

> [!TIP]
> Gebruik klassieke Common Data Service werk stromen of stromen die u definieert voor de entiteit voor de bedrijfs proces stroom.
> 

Voor het bouwen van een klassieke Common Data Service werk stroom die activiteiten maakt voor interne beoordelingen van oplossingen en de klant moet opvolgen in de fase Voorst **Ellen** van het **verkoop proces**voor verkoop kansen:

1. Maak het op de entiteit **verkoop proces verkoop kans** en stel deze in op elke keer dat het veld **actieve fase** van de entiteit wordt gewijzigd. 
1. Definieer een voor waarde om te controleren of het veld van de **actieve fase** gelijk is aan Voorst **Ellen**. 
1. Maak een afspraak en telefoon oproep record voor de interne beoordeling van de oplossing en de klant oproep om respectievelijk de oplossing te bekijken.

   ![vervolg fase sluiten](media/best-practices-entity-attributes/close-stage-followup.png)
