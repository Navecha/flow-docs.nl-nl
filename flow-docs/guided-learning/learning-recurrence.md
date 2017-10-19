---
title: Geplande stromen maken | Microsoft Docs
description: Informatie over het maken van stromen die worden uitgevoerd volgens een schema.
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: hh4nmS_M8Co
courseduration: 9m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 85c145364d684b5f91bc9f3bc7d1651f061f29d3
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="create-scheduled-flows"></a>Geplande stromen maken
In dit onderwerp ziet u hoe u vooraf geplande stromen kunt uitvoeren met de trigger **Terugkeerpatroon**.  U maakt een stroom voor het marketingteam van Contoso waarmee e-mailadressen van klanten automatisch worden opgehaald uit een Excel-tabel in OneDrive. U hebt de stroom zo geconfigureerd dat er één keer per dag nieuwe e-mailadressen die zijn toegevoegd aan het werkblad, worden toegevoegd aan een MailChimp-klantenlijst. 

## <a name="create-a-scheduled-flow"></a>Een geplande stroom maken
1. Open **Microsoft Flow**, selecteer **Mijn stromen** en selecteer vervolgens **Leeg item maken**. 
   
    ![](./media/learning-recurrence/flow-create-blank.png)
2. Selecteer **Honderden connectors en triggers zoeken**.
3. Zoek naar de **Planning**-service, selecteer deze en selecteer de trigger **Planning - Terugkeerpatroon**
   
    ![](./media/learning-recurrence/flow-recurrence-trigger.png)
4. Stel **Frequentie** in op **Dag** en stel **Interval** in op **1**. Selecteer **Nieuwe stap** en selecteer **Een actie toevoegen**. 
   
    ![](./media/learning-recurrence/frequency-interval.png)
5. Zoek naar **Excel**, selecteer de **Excel**-service en selecteer de actie **Excel - Rijen ophalen**. 
   
    ![](./media/learning-recurrence/excel-get-rows.png)
   
    **Opmerking**: selecteer **Rijen ophalen**, niet **Rij ophalen**. 
6. Selecteer **Bestandsnaam** en navigeer naar de bestandslocatie. Selecteer **Tabelnaam** en selecteer de gewenste tabel in het werkblad. 
   
    ![](./media/learning-recurrence/excel-get-file.png)
7. Voeg een nieuwe actie toe. 
   
    ![](./media/learning-recurrence/new-step.png)
8. Zoek naar de **MailChimp**-service en selecteer de actie **MailChimp - Lid aan lijst toevoegen**.
   
    ![](./media/learning-recurrence/select-mailchimp.png)
   
    **Opmerking:** MailChimp is een *premium*-connector. Afhankelijk van uw Microsoft Flow-licentie moet u zich mogelijk registreren voor een proefversie om deze connector te gebruiken.
9. Voeg de velden **Lijst-id** en **Status** toe uit het vervolgkeuzemenu's:
   
   * **Lijst-id**: selecteer de gewenste MailChimp-adressenlijst
   * **Status**: selecteer **Geabonneerd** 
     
     ![](./media/learning-recurrence/mailchimp-id-status.png)
10. Gebruik bij **E-mailadres** de functie voor dynamische inhoud om het veld **ContactEmail** toe te voegen. 
    
     ![](./media/learning-recurrence/mailchimp-address.png)
    
     U ziet dat via de stroom automatisch een aanvullende stap wordt gemaakt. In Flow wordt gedetecteerd dat u een actie wilt instellen waarvoor een aanvullende actie is vereist. Wanneer de stroom een nieuw e-mailadres leest, wordt er ook een nieuwe actie voor elke rij gemaakt. 
    
     ![](./media/learning-recurrence/mailchimp-for-each.png)
11. Gebruik dynamische inhoud om de velden **Voornaam** en **Achternaam** in te vullen:
    
    * **Voornaam**: FirstName
    * **Achternaam**: LastName
      
      ![](./media/learning-recurrence/mailchimp-names.png)

Nu wordt deze stroom eenmaal per dag uitgevoerd om nieuwe rijen uit deze Excel-tabel op te halen met het e-mailadres en de naam en deze te gebruiken om de MailChimp Contoso-adressenlijst in te vullen, wat u tijd en geld bespaart. 

