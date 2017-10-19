---
title: Voor certificering indienen als API-connector | Microsoft Docs
description: Door een connector te certificeren, wordt deze beschikbaar voor alle gebruikers van Microsoft Flow, PowerApps en Logic Apps.
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
ms.date: 09/19/2017
ms.author: astay
ms.openlocfilehash: 7eb357458161ba398864604bfe8912636ddc4d39
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="submit-your-connectors-for-microsoft-certification"></a>Uw connectors indienen voor Microsoft-certificering
Als u aangepaste connectors openbaar beschikbaar wilt maken voor alle gebruikers in Microsoft Flow, Azure Logic Apps en Microsoft PowerApps, verzendt u de connector naar Microsoft voor controle, validatie en goedkeuring voor publicatie. 

## <a name="certification-criteria"></a>Certificeringscriteria
| Functionaliteit | Details | Vereist of aanbevolen |
| --- | --- | --- |
| SaaS-app (Software-as-a-Service) |Voldoet aan een gebruikersscenario voor Logic Apps, Flow en PowerApps. |Vereist |
| Verificatietype |Uw API moet ondersteuning bieden voor OAuth2, API-sleutel of basisverificatie. |Vereist |
| Ondersteuning |U moet een contactpersoon voor ondersteuning opgeven waar klanten hulp kunnen vragen. |Vereist |
| Beschikbaarheid en uptime |Uw app heeft minimaal 99,9% uptime. |Aanbevolen |
|  | | |

Daarnaast moet u eigenaar zijn van de onderliggende service of aantonen dat u expliciete rechten hebt voor het gebruik van de API als u niet een Microsoft-partner of onafhankelijke softwareleverancier bent en u een connector wilt certificeren en openbaar wilt maken.

Voor de certificering wordt de connector in twee fasen gecontroleerd: 

1. Validatie van de functionaliteit
   
    De aangepaste connector wordt beoordeeld op:
   
   * Ongeldige swagger- of JSON-fouten in de sectie Definitie van de wizard voor aangepaste connectors
   * Runtime- en schemavalidatiefouten in de sectie Testen van de wizard
     
     Vervolgens wordt elke bewerking in Flow, Logic Apps en PowerApps uitgebreid getest op clientfouten.
2. Validatie van inhoud
   
    In een goed geschreven connector worden duidelijke namen en beschrijvingen gebruikt voor elke entiteit. We beoordelen uw swagger om te controleren dat elke bewerking, elke invoerparameter en elk antwoordkenmerk het volgende bevat:
   
   * [Overzicht](../logic-apps/custom-connector-openapi-extensions.md#summary)
   * [Beschrijving](../logic-apps/custom-connector-openapi-extensions.md#description)
   * [Zichtbaarheidsinformatie](../logic-apps/custom-connector-openapi-extensions.md#visibility)

## <a name="nominate-and-submit-your-connector-to-microsoft-for-certification"></a>Uw connector nomineren en naar Microsoft verzenden voor certificering
Als u certificering wilt aanvragen, voert u de volgende stappen uit:

1. **Nomineren**
   
   1. [Verzend uw nominatie](https://go.microsoft.com/fwlink/?linkid=848754).
   2. Onderteken de voor beide partijen geldende geheimhoudingsovereenkomst en partnerovereenkomst die u ontvangt. 
      Microsoft heeft deze ondertekende contracten nodig om te kunnen doorgaan. 
      We kunnen vervolgens controleren of de connector voldoet aan de criteria voor certificering. 
   3. Als de connector wordt goedgekeurd, ontvangt u van Microsoft een bericht met instructies voor de onboarding.
2. **Controle**
   
   1. Verzend deze gegevens ter controle naar de contactpersoon voor de nominatie:
      
      * Het OpenAPI-bestand met een beschrijving van uw API
      * Het pictogrambestand (.png of .jpg) waarmee de connector wordt aangeduid. (Het pictogram moet een logo van ~ 160 pixels in een vierkant van 230 pixels hebben. Een wit logo op een gekleurde achtergrond heeft de voorkeur.)
      * De merkkleur van het pictogram in hexadecimale indeling, die moet overeenkomen met de gekleurde achtergrond in het pictogrambestand
      * Een testaccount voor validatiedoeleinden
      * Een contactpersoon voor het bieden van ondersteuning
   2. Als we meer informatie nodig hebben, nemen we contact met u op.
3. **Publiceren**
   
    Nadat we functionaliteit en inhoud van de connector hebben gevalideerd, maken we de connector gereed voor implementatie in alle producten en regio's. Het certificerings- en implementatieproces duurt normaal gesproken maximaal drie weken.
   
    Standaard worden alle connectors gepubliceerd als Premium. 
    Als u de app hebt gemaakt met Azure, kunt u een aanvraag indienen om uw connector als standaardconnector voor alle gebruikers van Office 365 Enterprise-abonnementen te laten vermelden. 
    Voor meer informatie kunt u terecht bij uw contactpersoon voor nominatie.

