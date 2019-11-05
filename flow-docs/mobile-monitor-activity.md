---
title: Activiteiten van uw telefoon controleren | Microsoft Docs
description: Weer geven hoe vaak elke stroom is geslaagd of mislukt, wanneer elke uitvoering heeft plaatsgevonden en hoe lang het duurde
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9696ff09f41822b9daeb84b748f32e1babaf5af1
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549024"
---
# <a name="monitor-activity-in-microsoft-flow-from-your-phone"></a>Activiteit in Microsoft Flow bewaken vanaf uw telefoon
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Bekijk een samen vatting van het aantal keren dat elke stroom vandaag, gisteren en eerdere dagen is geslaagd of mislukt. Bekijk de details van elke uitvoering, zoals wanneer deze is uitgevoerd, hoe lang elke stap duurde en, als dat niet het geval is, waarom.

**Vereisten**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* Installeer de mobiele app voor Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [IOS](https://aka.ms/flowmobiledocsios)of [Windows Phone](https://aka.ms/flowmobilewindows) op een [ondersteund apparaat](getting-started.md#use-the-mobile-app). De afbeeldingen in dit onderwerp zijn gebaseerd op de iPhone-versie van de app, maar de afbeeldingen op Android en Windows Phone zijn vergelijkbaar.
* Als u nog geen stroom hebt, maakt u er een op [de website voor Microsoft flow](https://flow.microsoft.com/). Voor eenvoudiger testen gebruikt u een die u zelf kunt activeren in plaats van te wachten op een externe gebeurtenis.

De stroom in deze zelf studie wordt uitgevoerd wanneer u e-mail van een specifiek adres ontvangt:

![Stroom activeren bij ontvangst van e-mail vanuit een specifiek adres](./media/mobile-monitor-activity/create-trigger.png)

U kunt een dergelijke stroom met uw persoonlijke e-mail adres configureren voor testen en een ander adres (bijvoorbeeld uw manager) wanneer de stroom gereed is voor werkelijk gebruik.

Wanneer de stroom wordt uitgevoerd, wordt er een aangepaste push melding met deze syntaxis naar uw telefoon verzonden:

![Push melding verzenden](./media/mobile-monitor-activity/create-event.png)

**Opmerking:** U kunt ook [uw stromen beheren](mobile-manage-flows.md) vanuit de mobiele app.

## <a name="display-a-summary-of-activity"></a>Een samen vatting van de activiteit weer geven
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Als uw stroom nog niet eerder is uitgevoerd, moet u een uitvoering activeren om gegevens te genereren.
   
    Het kan enige tijd duren voordat de gegevens in de app worden weer gegeven.
2. Open de mobiele app, waarin standaard het tabblad **activiteit** wordt weer gegeven.
   
    Op dit tabblad worden gegevens per dag geordend, met de gegevens van vandaag aan de bovenkant.
   
    ![Activiteit georganiseerd per dag](./media/mobile-monitor-activity/activity-day2.png)
   
    Elk item toont de naam van een stroom met pictogrammen die overeenkomen met de trigger gebeurtenissen en-acties.
   
    ![Naam en pictogrammen voor elke stroom](./media/mobile-monitor-activity/activity-flow-name.png)
   
    Als ten minste één uitvoering van een stroom op een dag is geslaagd, wordt in een item het aantal geslaagde en tijdstippen weer gegeven waarop het het meest recent is geslaagd. Een andere vermelding toont soort gelijke informatie als een stroom mislukt.
   
    ![Samen vatting van geslaagde of mislukte pogingen](./media/mobile-monitor-activity/activity-summary.png)
   
    Als een stroom een push melding verzendt, wordt de tekst van de meest recente melding onder aan de vermelding weer gegeven voor geslaagde uitvoeringen.
   
    ![Voor beeld van een push melding](./media/mobile-monitor-activity/activity-notification.png)
3. Als er op een dag meerdere push meldingen zijn verzonden, veegt u naar links in de melding om meldingen van Maxi maal drie vorige uitvoeringen weer te geven. Als er op een dag meer dan vier meldingen zijn verzonden, veegt u naar links voordat **meer** wordt weer gegeven en tikt u op de melding om een lijst met alle meldingen weer te geven.
   
    ![Voor beeld van een push melding](./media/mobile-monitor-activity/activity-notification-list.png)
4. Tik op **terug** om terug te gaan naar het activiteiten overzicht.
5. Als u het activiteiten overzicht wilt filteren, tikt u op het pictogram in de rechter bovenhoek.
   
    U kunt alle vermeldingen, alleen de fout vermeldingen, of alleen de vermeldingen met push meldingen weer geven.
   
    ![Alle uitvoeringen, alleen mislukte of alleen meldingen weer geven](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>Details van een uitvoering weer geven
1. Tik in het activiteiten overzicht op een vermelding om details weer te geven voor de meest recente uitvoering.
   
     Elke gebeurtenis en actie wordt weer gegeven met een pictogram dat aangeeft of de gebeurtenis of actie is geslaagd of mislukt. Als dat is gelukt, wordt de hoeveelheid tijd die nodig was (in seconden) ook weer gegeven.
   
    ![Details van een uitvoering](./media/mobile-monitor-activity/activity-icons.png)
2. Tik onder aan het scherm op **vorige uitvoeringen weer** geven om alle uitvoeringen van de stroom weer te geven en tik vervolgens op een uitvoering om de details ervan te bekijken.
   
    ![Geschiedenis van geslaagde/mislukte pogingen](./media/mobile-monitor-activity/history-mixed.png)

