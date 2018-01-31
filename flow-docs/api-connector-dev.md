---
title: Een API-connector ontwikkelen | Microsoft Docs
description: Beschrijf uw API, geef het verificatietype op, ontwikkel triggers en acties en voer een test uit.
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: 8731e8a90a62bac4a05068386d23d2449952860b
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2018
---
# <a name="develop-an-api-connector-microsoft-flow"></a>Een API-connector ontwikkelen (Microsoft Flow)
Het bouwen van een connector bestaat uit meerdere stappen. Om te beginnen klikt of tikt u in [Microsoft Flow](https://flow.microsoft.com/) op de **instellingenknop** (het tandwielpictogram) in de rechterbovenhoek van de pagina. Klik of tik vervolgens op **Aangepaste connectors**.

![Zoeken naar API-connectors](./media/api-connectors-dev/finding-custom-apis.png)

## <a name="describe-your-api"></a>Uw API beschrijven
API-connectors worden beschreven met behulp van de [OpenAPI-standaard](https://swagger.io/) om de interface van een HTTP-API te definiëren. U kunt bij het ontwikkelen beginnen met een bestaand OpenAPI-bestand of u kunt een [Postman Collection](https://www.getpostman.com/docs/collections), importeren waarmee automatisch het OpenAPI-bestand voor u wordt gegenereerd. 

![Het API-diagram definiëren](./media/api-connectors-dev/build-your-api-updated.png)

Als u vanuit één van deze API-beschrijvingen begint, worden de metagegevensvelden in de wizard automatisch ingevuld. U kunt deze op elk gewenst moment bewerken.  

## <a name="build-security"></a>Beveiliging inbouwen
Kies het verificatietype dat wordt ondersteund door uw service, en geef meer informatie zodat de identiteit op de juiste manier tussen uw service en eventuele clients heen en weer kan stromen. 

![Beveiligingsdiagram](./media/api-connectors-dev/security.png)

[Meer informatie](register-custom-api.md) over de beveiliging van de connector.

## <a name="build-triggers-and-actions"></a>Triggers en acties bouwen
1. Voor het bouwen van de triggers en acties voor uw connector gaat u naar het tabblad **Definitie**. 
   
    ![Diagram van definitie](./media/api-connectors-dev/definition.png)
2. Met de wizard kunt u nieuwe bewerkingen toevoegen of het schema en de reactietijd van bestaande bewerkingen wijzigen. Met de eigenschap **Algemeen** van elke bewerking kunt u de ervaring voor de eindgebruiker van uw connector beheren. Meer informatie over de verschillende soorten bewerkingen vindt u via de volgende koppelingen:
   
   * [Triggers](customapi-webhooks.md) (niet zichtbaar in PowerApps)
   * [Acties](register-custom-api.md)
     
     Raadpleeg [OpenAPI extensions for API connectors](https://flow.microsoft.com/documentation/customapi-how-to-swagger/) (OpenAPI-extensies voor API-connectors) als u geavanceerde functies van Microsoft Flow wilt implementeren. 
3. Tot slot klikt of tikt u op **Connector maken** om de API-connector te registeren.

Voor aanvullende functies die niet beschikbaar zijn in de wizard, neemt u contact op via [ condevhelp@microsoft.com ](mailto:condevhelp@microsoft.com).

## <a name="test-the-connector"></a>De connector testen
Test uw API-connector op een of meer manieren voordat u deze indient: 

* Met de API-connector [Testing wizard](https://flow.microsoft.com/blog/new-updates-custom-api/) kunt u elke bewerking aanroepen om de functionaliteit en het antwoordschema ervan te controleren.
* In de ontwerpfunctie voor Microsoft Flow kunt u visueel stromen bouwen met behulp van uw API-connector. Door deze testmethode te gebruiken, worden de functies van de gebruikersinterface en de functies van de connector voor u zichtbaar.
* In de PowerApps Studio kunt u elke bewerking aanroepen via de formulebalk, en het antwoord verbinden aan besturingselementen op het scherm.

Dit onderwerp bevat een overzicht; zie [Aangepaste connectors registreren in Microsoft Flow](register-custom-api.md) voor meer informatie.

