---
title: 'Voor beeld: werken met bedrijfs proces stromen | MicrosoftDocs'
description: In het voor beeld ziet u hoe u programmatisch kunt werken met bedrijfsproces stromen, zoals het ophalen van de bedrijfs proces stroom-instanties voor een entiteits record, het ophalen van een actief pad voor een exemplaar van een bedrijfsproces stroom en de bijbehorende proces fasen, en het wijzigen van de actieve fase.
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
ms.openlocfilehash: 2eb6f7586ddc8d5bf51b9c57f91bbc5c7c10131b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547758"
---
# <a name="sample-work-with-business-process-flows"></a>Voor beeld: werken met bedrijfs proces stromen
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Dit voor beeld laat zien hoe u programmatisch kunt werken met bedrijfsproces stromen, zoals het ophalen van de bedrijfs proces stroom-instanties voor een entiteits record, het ophalen van een actief pad voor een exemplaar van een bedrijfsproces stroom en de bijbehorende proces fasen, en het wijzigen van de actieve fase. Zie voor meer informatie over deze concepten [werken met bedrijfs proces stromen met behulp van code](business-process-flows-code.md)  

 Dit voor beeld is beschikbaar om te downloaden van [voor beeld: werken met bedrijfs proces stromen](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Vereisten  
 Voordat u het voor beeld kunt uitvoeren:  

1. Toegang hebben tot een Common Data Service omgeving.  

2. Over de juiste bevoegdheden beschikken voor de entiteits records voor leads, verkoop kansen en werk stromen die in dit voor beeld worden gebruikt.  

3. Gebruik Visual Studio 2015 of hoger om het voor beeld uit te voeren.  

4. Een Internet verbinding hebben om het voorbeeld project te downloaden en de NuGet-pakketten die in het voorbeeld project worden gebruikt, te herstellen.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Wat dit voor beeld doet  

1.  Hiermee maakt u een voor beeld van een lead record. Hiermee wordt automatisch een exemplaar gemaakt van de bedrijfs proces stroom ' lead to verkoop kansen ' voor de lead record.  

2.  Hiermee wordt de record van de lead naar een verkoopkansrecord geconverteerd.  


4.  Hiermee worden de bedrijfsproces stroom exemplaren opgehaald die zijn gekoppeld aan de record verkoop kans met behulp van het `RetrieveProcessInstances` bericht. In dit geval is de eerste record in de geretourneerde verzameling het actieve exemplaar van de bedrijfs proces stroom voor de verkoopkansrecord.  

5.  Haalt het actieve pad en de proces fasen voor het exemplaar ' lead to Sales Process verkoop proces ' op met behulp van het `RetrieveActivePath` bericht.  

6.  Hiermee wordt de huidige actieve fase opgehaald voor het exemplaar ' lead to Opportunity Sales Process ' en wordt de gebruiker gevraagd of deze moet worden verplaatst naar de volgende fase. Wanneer de bevestiging moet worden verplaatst, wordt de volgende fase in het actieve pad ingesteld als de actieve fase voor het exemplaar ' lead to verkoop kans Sales Process '.  

7.  Ten slotte wordt de gebruiker gevraagd of de records die tijdens de voorbeeld uitvoering zijn gemaakt, moeten worden verwijderd.  

     Dit is de uitvoer van het voor beeld:  

    ![Voorbeeld uitvoer](media/work-with-bpf-sample-output.png "Voorbeeld uitvoer")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Het voor beeld uitvoeren  

1. [Down load](https://go.microsoft.com/fwlink/p/?LinkId=846108) het voorbeeld project van WorkWithBPF Visual Studio en pak het uit naar een map op uw computer.  

2. Zoek het `WorkWithBPF.sln`-bestand in de uitgepakte map en open het in Visual Studio.  

3. Het voorbeeld project gebruikt NuGet-pakketten die moeten worden hersteld voordat het voor beeld kan worden uitgevoerd. Zorg ervoor dat automatisch herstellen van NuGet-pakketten is ingeschakeld in Visual Studio. Meer informatie: het in- [en uitschakelen](https://go.microsoft.com/fwlink/?linkid=846106) van het herstellen van het NuGet-pakket  

    U kunt ook **Project** > **NuGet-pakketten beheren**en vervolgens **herstellen** selecteren om de pakketten die in het voor beeld worden gebruikt, hand matig te herstellen.  

4. Druk op F5 of selecteer **fout** opsporing > **fout opsporing starten**.  

5. Als u nog niet eerder een van de voor beelden hebt uitgevoerd, moet u gegevens invoeren om de code uit te voeren. anders voert u het nummer in voor een van de exemplaren die u eerder hebt ingesteld.  


   |                                 verschijnt                                  |                                                                                             Beschrijvingen                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Voer een Dynamics 365-server naam en-poort in [crm.dynamics.com]       | Typ de naam van uw Dynamics 365-server. De standaard waarde is Dynamics 365 (online) (crm.dynamics.com) in Noord-Amerika.<br /><br /> Hierbij <br />crm5.dynamics.com |
   | Is deze organisatie ingericht in micro soft onlineservices (j/n) [n] |                                                 Typ **y** als dit een micro soft onlineservices ingerichte organisatie is. Anders typt u **n**.                                                  |
   |                          Voer domein\gebruikersnaam in                          |                                                                                    Typ uw Microsoft-account.                                                                                     |
   |                             Wacht woord invoeren                              |                      Typ uw wacht woord. De tekens worden weer gegeven als '\*' in het venster. Uw wacht woord wordt veilig opgeslagen in micro soft referentie beheer voor later gebruik.                       |
   |                Geef een organisatie nummer op (1-n) [1]                 |                      Typ in de lijst met organisaties waarvan wordt aangegeven dat u behoort, het overeenkomende nummer. De standaard waarde is 1, die de eerste organisatie in de lijst aangeeft.                       |


6. In het voor beeld worden de bewerkingen uitgevoerd die worden beschreven in [wat dit voor beeld doet](#what-this-sample-does) en wordt u mogelijk gevraagd om extra opties.  

7. Wanneer het voor beeld is voltooid, drukt u op ENTER om het console venster te sluiten.  

