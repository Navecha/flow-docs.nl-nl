---
title: Aanbevolen procedures voor het gebruik van entiteitskenmerken voor bedrijfsprocesstromen| Microsoft Docs
description: Lees hier alles over de aanbevolen procedures voor het gebruik van entiteitskenmerken voor bedrijfsprocesstromen.
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
ms.openlocfilehash: 950f03d78e708f00f28b68daf7c1012fae231c95
ms.sourcegitcommit: 2931edb777c1ed57e040670fc8a1c55252ac95b1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/25/2019
ms.locfileid: "64472967"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Aanbevolen procedures voor het gebruik van kenmerken voor bedrijfsprocesstromen


Verouderde procesgerelateerde kenmerken in entiteiten zijn afgeschaft. Hier volgen enkele aanbevolen procedures voor het gebruik van het kenmerk *Actieve fase* (activestageid) voor de entiteit van de bedrijfsprocesstroom. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Rapporteren over de actieve fase van een bedrijfsprocesstroom

Stel dat u een weergave van uw verkooppijplijn wilt ophalen door te rapporteren over de actieve fase waarin **Verkoopproces van potentiële klant naar verkoopkans** zich bevindt.

Eerder was het mogelijk om per fase te rapporteren over bedrijfsprocessen door voor elke gerelateerde entiteit van de bedrijfsprocesstroom een weergave te definiëren en vervolgens te rapporteren over het veld *Actieve fase* (activestageid).

Met de afschaffing van het veld *Actieve fase* (activestageid) voor gerelateerde entiteiten zijn er twee manieren om te rapporteren over bedrijfsprocesstromen.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Optie 1: Weergaven en grafieken van de entiteit van de bedrijfsprocesstroom **(aanbevolen)**

In versie 9.0 en hoger wordt voor elke bedrijfsprocesstroom een eigen Common Data Service-entiteit gemaakt, meestal met dezelfde naam als de bedrijfsprocesstroom. Als u wilt rapporteren over een bedrijfsprocesstroom, selecteert u de entiteit voor de bedrijfsprocesstroom waarover u wilt rapporteren en maakt u vervolgens weergaven en grafieken, net als in de oude situatie.

In ons voorbeeld volgt u deze stappen om naar de entiteit **Verkoopproces van potentiële klant naar verkoopkans** te gaan:
1. Ga naar https://web.powerapps.com.
1. Selecteer **Gegevens** aan de linkerkant.
1. Selecteer **Entiteiten** aan de linkerkant.
1. Stel het filter in op **Alle**.
1. Zoek de entiteit **Verkoopproces van potentiële klant naar verkoopkans** en selecteer deze vervolgens.

   ![De entiteit Verkoopproces van potentiële klant naar verkoopkans](media/best-practices-entity-attributes/lead-opportunity-process.png)

Hier kunt u weergaven en grafieken definiëren, net zoals voor elke andere entiteit.

![details van entiteit](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

Een voordeel van deze aanpak is dat u met één weergave of grafiek kunt rapporteren over bedrijfsprocesstromen die meerdere entiteiten omvatten.

Aangezien de entiteit van de bedrijfsprocesstroom niet verschilt van andere aangepaste entiteiten in Common Data Service, kunt u aangepaste velden toevoegen aan de entiteit om aanvullende informatie bij te houden die u nodig hebt.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Optie 2: Actieve fase kopiëren naar een gerelateerde entiteit

Om te blijven rapporteren over de gerelateerde entiteit, kunt u ook een stroom maken om het veld *Actieve fase* (activestageid) van de entiteit van de bedrijfsprocesstroom te kopiëren naar een aangepast veld in de gerelateerde entiteiten van Common Data Service.

Houd rekening met de volgende punten als u kiest voor deze aanpak:

1.  Er kan meer dan één bedrijfsprocesstroom worden uitgevoerd op een entiteit. Met deze aanpak is het raadzaam om één aangepast veld te gebruiken voor het opslaan van de actieve fase voor elke bedrijfsprocesstroom die op de entiteit wordt uitgevoerd. Deze aanpak zorgt voor de integriteit van de rapportage.

1.  Als rapportage wordt aangestuurd vanuit de gerelateerde entiteit, is het niet mogelijk om met één weergave te rapporteren over bedrijfsprocesstromen die meerdere entiteiten omvatten.

## <a name="using-the-active-stage-to-run-logic"></a>De actieve fase gebruiken voor het uitvoeren van logica

Hier volgen enkele gevallen waarin het handig kan zijn om logica uit te voeren die is gebaseerd op de actieve fase:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>De actieve fase gebruiken voor het uitvoeren van logica aan de clientzijde

Als u het bedrijfsproces gebruikt, zijn er veel dingen die u automatisch kunt doen. Bijvoorbeeld:

-   De actieve bedrijfsprocesstroom wijzigen op basis van nieuw beschikbare informatie over het formulier of de bedrijfsprocesstroom.

-   De actieve fase verplaatsen naar de volgende of vorige fase, op basis van waarden die de gebruikers hebben ingevoerd voor stappen of formuliervelden.

-   Formuliertabbladen en -velden verbergen of weergeven op basis van de geselecteerde fase.

-   Informatieve berichten weergeven en berekeningen uitvoeren op basis van de actieve bedrijfsprocesstromen, de actieve of geselecteerde fase, of gebeurtenissen zoals het verplaatsen van de actieve fase.

> [!TIP]
> Voor scenario's zoals deze gebruikt u de ondersteunde set [client-API's](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) voor bedrijfsprocesstromen.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>De actieve fase gebruiken voor het uitvoeren van logica aan de serverzijde

Mogelijk zijn er situaties waarbij automatisering op basis van de bedrijfsprocesstroom moet worden uitgevoerd aan de serverzijde. Bijvoorbeeld:

-   Een e-mailbericht verzenden naar een gebruiker als de fase **Kwalificeren** van **Verkoopproces verkoopkans** langer dan 15 dagen actief is.

-   Automatisch een set activiteiten maken die relevant zijn voor de actieve fase van **Verkoopproces verkoopkans** telkens wanneer deze verandert.

-   **Verkoopproces verkoopkans** automatisch voltooien wanneer de activiteit Telefoongesprek voor afsluiting is voltooid.

> [!TIP]
> Gebruik klassieke Common Data Service-werkstromen of stromen die u voor de entiteit voor de bedrijfsprocesstroom definieert.
> 

Een klassieke Common Data Service werkstroom bouwen die activiteiten maakt voor interne beoordeling van de oplossing en voor vervolgacties voor de klant in de fase **Voorstellen** van **Verkoopproces verkoopkans**:

1. Maak de stroom voor de entiteit **Verkoopproces verkoopkans** en geef aan dat de stroom moet worden uitgevoerd wanneer het veld **Actieve fase** van de entiteit verandert. 
1. Definieer een voorwaarde om te controleren of het veld **Actieve fase** gelijk is aan **Voorstellen**. 
1. Maak een record voor een afspraak en telefoongesprek voor respectievelijk de interne beoordeling van de oplossing en het gesprek met de klant om de oplossing te bespreken.

   ![vervolgactie voor afrondende fase](media/best-practices-entity-attributes/close-stage-followup.png)
