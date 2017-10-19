---
title: Activiteiten bekijken op uw telefoon | Microsoft Docs
description: Zie hoe vaak elke stroom succesvol is uitgevoerd of is mislukt, wanneer die is uitgevoerd en hoelang dit duurde
services: 
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
ms.openlocfilehash: a9318a1571d46635babbb0b061ff65734ad172fe
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="monitor-activity-in-microsoft-flow-from-your-phone"></a>Activiteiten in Microsoft Flow bekijken op uw telefoon
Bekijk in een overzicht hoe vaak elke stroom vandaag, gisteren of op een eerdere dag is geslaagd of mislukt. Lees de details over elke uitvoering, bijvoorbeeld wanneer die plaatsvond, hoelang elke stap duurde en waarom een uitvoering is mislukt.

**Vereisten**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* Installeer de mobiele app voor Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) of [Windows Phone](https://aka.ms/flowmobilewindows) op een [ondersteund apparaat](getting-started.md#use-the-mobile-app). Op de afbeeldingen in dit artikel is de iPhone-versie van de app te zien, maar de afbeeldingen op een Android- en Windows Phone-apparaat zien er vergelijkbaar uit.
* Als u nog geen stroom hebt, kunt u er een maken op [de website van Microsoft Flow](https://flow.microsoft.com/). Om het testen gemakkelijker te maken, gebruikt u een stroom die u zelf kunt activeren. U bent dan niet afhankelijk van een externe gebeurtenis.

De stroom in deze zelfstudie wordt uitgevoerd wanneer u een e-mail ontvangt van een specifiek adres:

![Stroom activeren bij ontvangst van e-mail van specifiek adres](./media/mobile-monitor-activity/create-trigger.png)

U kunt uw persoonlijke e-mailadres instellen voor het testen en vervangen door een ander adres (bijvoorbeeld dat van uw manager) wanneer de stroom gereed is voor gebruik.

Wanneer de stroom wordt uitgevoerd, wordt er een aangepaste pushmelding naar uw telefoon gestuurd met de volgende syntaxis:

![Pushmelding verzenden](./media/mobile-monitor-activity/create-event.png)

**Opmerking:** u kunt [uw stromen ook beheren](mobile-manage-flows.md) vanaf de mobiele app.

## <a name="display-a-summary-of-activity"></a>Een overzicht van activiteiten weergeven
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Als de stroom niet eerder is uitgevoerd, activeert u deze zelf om gegevens te genereren.
   
    Het kan even duren voordat de gegevens in de app worden weergegeven.
2. Open de mobiele app. Deze opent standaard op het tabblad **Activiteit**.
   
    Op dit tabblad ziet u de gegevens per dag, met bovenaan de gegevens van vandaag.
   
    ![Activiteiten ingedeeld per dag](./media/mobile-monitor-activity/activity-day2.png)
   
    Elke vermelding bevat de naam van een stroom en pictogrammen die de triggergebeurtenissen en -acties weerspiegelen.
   
    ![Naam en pictogrammen voor elke stroom](./media/mobile-monitor-activity/activity-flow-name.png)
   
    Als een stroom op een dag ten minste één keer succesvol is uitgevoerd, wordt het aantal geslaagde uitvoeringen en de tijd van de laatste geslaagde uitvoering in een vermelding weergegeven. Als een stroom is mislukt, wordt vergelijkbare informatie in een andere vermelding weergegeven.
   
    ![Overzicht van geslaagde of mislukte uitvoeringen](./media/mobile-monitor-activity/activity-summary.png)
   
    Als een stroom een pushmelding activeert, verschijnt de tekst van de meest recente melding onder aan de vermelding voor geslaagde uitvoeringen.
   
    ![Voorbeeld van pushmelding](./media/mobile-monitor-activity/activity-notification.png)
3. Als er op een dag meerdere pushmeldingen zijn verzonden, veegt u op de melding naar links om meldingen van maximaal drie eerdere uitvoeringen weer te geven. Als er op een dag meer dan vier meldingen zijn verzonden, veegt u naar links tot u **Meer bekijken** ziet. Tik hierop om een lijst met alle meldingen te bekijken.
   
    ![Voorbeeld van pushmelding](./media/mobile-monitor-activity/activity-notification-list.png)
4. Tik op **Terug** om terug te keren naar het activiteitenoverzicht.
5. Om het activiteitenoverzicht te filteren, tikt u op het pictogram in de rechterbovenhoek.
   
    U kunt alle vermeldingen weergeven of filteren op mislukte uitvoeringen of pushmeldingen.
   
    ![Alle uitvoeringen, alleen mislukte uitvoeringen of alleen pushmeldingen weergeven](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>Details van een uitvoering weergeven
1. Tik in het activiteitenoverzicht op een vermelding om de details van de meest recente uitvoering weer te geven.
   
     Elke gebeurtenis en actie wordt weergegeven met een pictogram dat aangeeft of deze is geslaagd of mislukt. Als deze is geslaagd, wordt ook de benodigde tijd (in seconden) vermeld.
   
    ![Details van een uitvoering](./media/mobile-monitor-activity/activity-icons.png)
2. Tik onder aan het scherm op **Vorige uitvoeringen bekijken** voor een lijst met alle uitvoeringen van de stroom. Tik vervolgens op een uitvoering om de details te zien.
   
    ![Geschiedenis van geslaagde/mislukte uitvoeringen](./media/mobile-monitor-activity/history-mixed.png)

