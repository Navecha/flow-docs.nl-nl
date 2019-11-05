---
title: Inleiding tot knop trigger tokens | Microsoft Docs
description: Inleiding tot knop trigger tokens voor micro soft-knop stromen.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/12/2016
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1b439a972393f800ea550480b883945664e17e53
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547466"
---
# <a name="get-started-with-button-trigger-tokens"></a>Aan de slag met knop trigger tokens
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-trigger-tokens"></a>Wat zijn knop trigger tokens?
Knop trigger tokens zijn gegevens punten die bekend zijn en beschikbaar zijn voor het apparaat waarop een [knop stroom](introduction-to-button-flows.md) wordt uitgevoerd. Deze tokens veranderen op basis van factoren zoals de huidige tijd of de geografische locatie van het apparaat op een bepaald moment.  

Als u bijvoorbeeld een knop stroom op een smartphone uitvoert, is het waarschijnlijk dat de **telefoon de tijd kent** op uw huidige locatie, evenals de datum en het huidige adres. In deze context worden de tijd, datum en het adres waarop de telefoon zich bevindt, allemaal bepaald op het moment dat de knop stroom wordt uitgevoerd. Ze zijn automatisch beschikbaar voor gebruik in alle knop stromen die op het apparaat worden uitgevoerd. U kunt deze trigger tokens gebruiken om nuttige stromen te bouwen waarmee herhaalde taken worden verkleind, zoals het leveren van uw locatie naar iemand of het bijhouden van de tijd die u hebt besteed aan een bepaalde taak/service oproep.

### <a name="list-of-button-trigger-tokens"></a>Lijst met knop trigger tokens
Hier volgt de lijst met de knop trigger tokens die u kunt gebruiken bij het maken van uw knop stromen.

| Bepaalde | Beschrijvingen |
| --- | --- |
| Waar |De plaats waar het apparaat zich bevindt waarop de stroom wordt uitgevoerd. |
| Land/regio |Het land/de regio waarin het apparaat zich bevindt waarop de stroom wordt uitgevoerd. |
| Volledig adres |Het volledige adres waar het apparaat zich bevindt waarop de stroom wordt uitgevoerd. |
| breedte graad |De breedte graad van het apparaat waarop de stroom wordt uitgevoerd. |
| lengte graad |De lengte graad van het apparaat waarop de stroom wordt uitgevoerd. |
| Code |De post code waarin het apparaat zich bevindt waarop de stroom wordt uitgevoerd. |
| Overheids |De status waarin het apparaat zich bevindt waarop de stroom wordt uitgevoerd. |
| Adressen |De straat waarop het apparaat zich bevindt waarop de stroom wordt uitgevoerd. |
| Neem |De tijd in het gebied waar het apparaat zich bevindt waarop de stroom wordt uitgevoerd. |
| Vallen |De datum in het gebied waar het apparaat zich bevindt waarop de stroom wordt uitgevoerd. |
| Gebruikers naam |De gebruikers naam van de persoon die is aangemeld bij het apparaat waarop de stroom wordt uitgevoerd. |
| E-mail adres van gebruiker |Het e-mail adres van de persoon die is aangemeld bij het apparaat waarop de stroom wordt uitgevoerd. |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>Een knop stroom maken die gebruikmaakt van trigger tokens
Wanneer u een knop maakt, kunt u trigger tokens gebruiken om uitgebreide functionaliteit aan uw knop toe te voegen.

In dit overzicht maken we een knop stroom op een Android-apparaat. De knop stroom gebruikt trigger tokens om de datum en uw volledige adres te verzenden in het e-mail bericht '**werk van thuis**' naar uw chef.

In dit overzicht ziet u scherm afbeeldingen van een Android-apparaat, maar de ervaring is ook vergelijkbaar op iOS-en Windows Phone-apparaten.

### <a name="prerequisites"></a>Vereisten
* Een werk-of school-e-mail adres of een [micro soft-account](https://account.microsoft.com/about?refd=www.microsoft.com) met toegang tot Microsoft flow.
* De mobiele app Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [IOS](https://aka.ms/flowmobiledocsios)of [Windows Phone](https://aka.ms/flowmobilewindows).

Laten we aan de slag:

1. Start de stroom en selecteer **bladeren**   
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/1.png)  
2. Selecteer de **e-mail een werk van vandaag thuis verzenden naar uw manager-** service onder de categorie **knop**   
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/2.png)  
3. Selecteer **deze sjabloon gebruiken**  
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/3.png)  
4. Selecteer **bewerken** in de kaart **een e-mail verzenden**  
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/3-5.png)  
5. Tik op het tekstvak **onderwerp** en voer: ' **vandaag-** ' in het tekstvak na de tekst ' WFH '. Wanneer u op het tekstvak tikt, wordt er ook een lijst met para meters/tokens geopend. We gebruiken een van deze tokens in de volgende stap om de datum toe te voegen aan het onderwerp van het e-mail bericht.  
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/4.png)  
6. Terwijl de cursor nog in het tekstvak onderwerp staat, schuift u naar **de lijst met** para meters en tikt u op **datum**. U ziet dat de para meter date zich nu in het tekstvak **onderwerp** bevindt:  
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/6.png)  
7. Ga naar het tekstvak **Body** en tik na het standaard bericht zodat er extra tokens kunnen worden opgenomen.  
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/7.png)  
8. Tik op de para meter **Full Address** en tik vervolgens op **Create (maken** ).  
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/8.png)  
9. Tik op **gereed**. De knop stroom is nu gemaakt.  
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/9.png)  

## <a name="run-the-button-flow"></a>De knop stroom uitvoeren
**Opmerking**: met deze knop stroom wordt uw huidige locatie via e-mail verzonden.  

1. Tik op de categorie **knoppen** onder aan het scherm. Er wordt een lijst weer geven met de knoppen die u moet gebruiken. Tik op de knop van de knop stroom die u zojuist hebt gemaakt:  
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/10.png)  
2. Tik op **toestaan** om aan te geven dat het gaat om de knop stroom om toegang te krijgen tot de locatie gegevens van uw apparaat:  
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/11.png)  
3. Binnen enkele ogen blikken ziet u dat het e-mail bericht is verzonden naar uw chef:  
   ![knop trigger token](./media/introduction-to-button-trigger-tokens/12.png)  

Gefeliciteerd, u hebt zojuist een knop stroom gemaakt die gebruikmaakt van de trigger tokens datum en volledig adres. 

## <a name="next-steps"></a>Volgende stappen
* [Knop stromen delen](share-buttons.md)
* [Meer informatie over knop stromen](introduction-to-button-flows.md)
