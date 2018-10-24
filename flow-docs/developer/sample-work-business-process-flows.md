---
title: 'Voorbeeld: Werken met bedrijfsprocesstromen (Handleiding voor ontwikkelaars voor Dynamics 365 Customer Engagement) | MicrosoftDocs'
description: Dit voorbeeld laat zien hoe u programmatisch kunt werken met bedrijfsprocesstromen, zoals het ophalen van de exemplaren van bedrijfsprocesstromen voor een entiteitsrecord, het ophalen van het actieve pad voor een exemplaar van een bedrijfsprocesstroom en de bijbehorende procesfasen, en wijzigen van de actieve fase.
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 6fe2b6d600d86dfd807dbb1ef794a1f428f26fbf
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690047"
---
# <a name="sample-work-with-business-process-flows"></a>Voorbeeld: Werken met bedrijfsprocesstromen

Dit voorbeeld laat zien hoe u programmatisch kunt werken met bedrijfsprocesstromen, zoals het ophalen van de exemplaren van bedrijfsprocesstromen voor een entiteitsrecord, het ophalen van het actieve pad voor een exemplaar van een bedrijfsprocesstroom en de bijbehorende procesfasen, en wijzigen van de actieve fase. Meer informatie over deze concepten vindt u in [Work with business process flows using code](business-process-flows-code.md) (Werken met bedrijfsprocesstromen met behulp van code).  

 U kunt dit voorbeeld downloaden van de Engelstalige site [Work with business process flows in Dynamics 365](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Vereisten  
 Voordat u het voorbeeld kunt uitvoeren:  

1. U moet toegang hebben tot een Common Data Service for Apps-omgeving.  

2. U moet beschikken over de juiste machtigingen voor de entiteiten Lead, Opportunity en Workflow, en entiteitsrecords voor de definitie van de bedrijfsprocesstroom die worden gebruikt in dit voorbeeld.  

3. Visual Studio 2015 of hoger moet zijn geïnstalleerd.  

4. U moet beschikken over een internetverbinding om het voorbeeldproject te downloaden en de NuGet-pakketten te herstellen die worden gebruikt in het voorbeeldproject.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Wat dit voorbeeld doet  

1.  Maakt een voorbeeldrecord voor een potentiële klant (Lead). Hiermee wordt automatisch een exemplaar gemaakt van de bedrijfsprocesstroom Lead To Opportunity Sales Process voor de Lead-record.  

2.  Converteert de Lead-record naar een record voor een verkoopkans (Opportunity).  


4.  Haalt de exemplaren van de bedrijfsprocesstroom op die zijn gekoppeld aan de Opportunity-record, met behulp van het bericht `RetrieveProcessInstances`. De eerste record in de geretourneerde verzameling is het actieve exemplaar van de bedrijfsprocesstroom voor de Opportunity-record, Lead To Opportunity Sales Process in dit geval.  

5.  Haalt het actieve pad en de procesfasen op voor het exemplaar Lead To Opportunity Sales Process, met behulp van het bericht `RetrieveActivePath`.  

6.  Haalt de fase op die nu actief is voor het exemplaar Lead To Opportunity Sales Process en vraagt de gebruiker of deze naar de volgende fase wil gaan. Als dat is bevestigd, wordt de volgende fase in het actieve pad ingesteld als de actieve fase voor het exemplaar Lead To Opportunity Sales Process.  

7.  Ten slotte wordt de gebruiker gevraagd of deze de records wil verwijderen die tijdens het uitvoeren van het voorbeeld zijn gemaakt.  

     Dit is de uitvoer van het voorbeeld:  

    ![Uitvoer van voorbeeld](media/work-with-bpf-sample-output.png "Uitvoer van voorbeeld")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Het voorbeeld uitvoeren  

1. [Download](https://go.microsoft.com/fwlink/p/?LinkId=846108) het voorbeeldproject van Visual Studio met de naam WorkWithBPF en pak het uit in een map op uw computer.  

2. Zoek het bestand `WorkWithBPF.sln` in de uitgepakte map en open het in Visual Studio.  

3. Het voorbeeldproject maakt gebruik van NuGet-pakketten, die moeten worden hersteld voordat u het voorbeeld uitvoert. Zorg er daarom voor dat het automatisch herstellen van NuGet-pakketten is ingeschakeld in Visual Studio. Meer informatie: [Enabling and disabling package restore](https://go.microsoft.com/fwlink/?linkid=846106) (Herstellen van pakketten in- en uitschakelen).  

    U kunt ook **Project** > **Manage NuGet Packages** selecteren en vervolgens **Restore** om de pakketten die worden gebruikt in het voorbeeld handmatig te herstellen.  

4. Druk op F5 of selecteer **Debug** > **Start Debugging**.  

5. Als u nog niet eerder een van de voorbeelden hebt uitgevoerd, moet u gegevens invoeren voor het ui van de code. Voer anders het nummer in voor een van de exemplaren die u eerder hebt ingesteld.  


   |                                 Optie                                  |                                                                                             Beschrijving                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Enter a Dynamics 365 server name and port [crm.dynamics.com]       | Typ de naam van uw Dynamics 365-server. De standaardwaarde is Dynamics 365 (online)  (crm.dynamics.com) in Noord-Amerika.<br /><br /> Voorbeeld: <br />crm5.dynamics.com |
   | Is this organization provisioned in Microsoft online services (y/n) [n] |                                                 Typ **y** als dit een organisatie is die is ingericht in Microsoft Online Services. Anders typt u **n**.                                                  |
   |                          Enter domain\username                          |                                                                                    Voer uw Microsoft-account in.                                                                                     |
   |                             Enter password                              |                      Voer uw wachtwoord in. De ingevoerde tekens worden weergegeven als '\*' in het venster. Uw wachtwoord wordt veilig opgeslagen in Microsoft Credential Manager voor later gebruik.                       |
   |                Specify an organization number (1-n) [1]                 |                      Typ het nummer van de gewenste organisatie uit de lijst met organisaties waarvan u deel uitmaakt. De standaardwaarde is 1, wat verwijst naar de eerste organisatie in de lijst.                       |


6. Het voorbeeld voert de bewerkingen uit die worden beschreven in [Wat dit voorbeeld doet](#what-this-sample-does) en u wordt mogelijk gevraagd om extra opties op te geven.  

7. Wanneer het voorbeeld is voltooid, drukt u op Enter om het consolevenster te sluiten.  

