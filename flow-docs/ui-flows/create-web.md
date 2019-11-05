---
title: Meer informatie over het maken van GEBRUIKERSINTERFACE stromen voor websites | Microsoft Docs
description: Meer informatie over het automatiseren van web-apps met UI-stromen.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 010b6632a60f2c81c138fa98d850df79be814f68
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589860"
---
# <a name="create-and-test-your-web-ui-flows"></a>Uw Web-UI-stromen maken en testen

[Dit onderwerp bevat voorlopige documentatie en kan worden gewijzigd.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Volg deze stappen om een eenvoudige webgebruikersinterface flow te maken:

## <a name="create-a-web-ui-flow"></a>Een web-UI-stroom maken

1. Open de [volgende versie van micro soft Edge](https://www.microsoftedgeinsider.com/) of Google Chrome en navigeer vervolgens naar [energie automatisering](https://flow.microsoft.com/).

1. Aanmelden met uw werk-of schoolaccount, indien nodig.

1. Selecteer **mijn stromen** > **UI-stromen (preview)**  > **Nieuw**.

   ![Nieuwe UI-flow maken](../media/create-windows-ui-flow/create-new.png "Nieuwe UI-flow maken")

1. Selecteer **Web-app** > **volgende**
    
   ![Web-app selecteren](../media/create-web-ui-flow/select-web-app.png "Web-app selecteren")

1. Voer een naam in voor de gebruikers interface stroom in het veld **stroom naam** .

1. Voer de URL in voor de website die u wilt automatiseren in het veld **basis-URL** en selecteer vervolgens **recorder starten**.

   ![Geef een naam en een URL op](../media/create-web-ui-flow/give-a-name.png "Geef een naam en een URL op") 

   De Selenium IDE wordt gestart.

   >[!TIP] 
   >Tip: u kunt acties op meerdere HTTP-of HTTPS-websites op hetzelfde tabblad registreren.  

1. Selecteer in Selenium IDE de knop rode **REC** in de rechter bovenhoek van het scherm om de recorder te starten.

   De URL die u in de vorige stap hebt gekozen, wordt geopend.

   ![REC selecteren](../media/create-web-ui-flow/select-rec.png "REC selecteren")

1.  Voer de acties uit die u op de website wilt opnemen. 
    
    >[!TIP]
    >Aan de rechter kant ziet u de opname status.

    ![Opname status](../media/create-web-ui-flow/recording-status.png "Opname status")

1.  Wanneer u klaar bent met opnemen, selecteert u op de knop rood **Stop** in de rechter bovenhoek van de Selenium IDE.

    ![Knop stoppen](../media/create-web-ui-flow/stop-button.png "Knop stoppen" )

1. Selecteer de knop **huidige test uitvoeren** in de linkerbovenhoek van het scherm om de gebruikers interface stroom te zien die u zojuist hebt gemaakt.

    ![Huidige test uitvoeren](../media/create-web-ui-flow/run-test.png "Huidige test uitvoeren")

   >[!TIP]
   >U kunt de wacht tijd tussen de stappen instellen om het lokaal afspelen voor testen te vertragen. Deze instelling geldt alleen voor test doeleinden en heeft geen invloed op de implementatie van uw GEBRUIKERSINTERFACE stroom.  
  
1. Selecteer de knop **project opslaan** in de rechter bovenhoek van de Selenium IDE. Hiermee wordt het project gesloten en vervolgens geüpload.

Nu u een web-UI-stroom hebt gemaakt, gebruikt u deze in uw andere stromen.

## <a name="limitations-and-known-issues-for-web-ui-flows"></a>Beperkingen en bekende problemen voor de gebruikers interface van de Web-UI

>[!WARNING]
>**Wacht woorden in Selenium IDE worden opgeslagen als tekst zonder opmaak.**  


**Gebruikers interface-stromen records of spelen geen back-ups meer van Windows-toepassingen na de installatie van een nieuwe versie.**

U moet de vorige versie verwijderen voordat u een nieuwe installeert.

Hiervoor opent u het menu Start, gaat u naar **instellingen** > **apps**, zoekt u naar **UI-stromen** in de lijst met apps > UI- **stromen (preview)** en selecteert u vervolgens verwijderen. De wizard leidt u door het proces.

**Tijdelijk gebruikers profiel voor afspelen**

Selenium IDE-opnamen worden uitgevoerd met het profiel van de huidige gebruiker, maar het afspelen wordt uitgevoerd met behulp van een tijdelijk gebruikers profiel. Dit betekent dat websites die verificatie nodig hebben, mogelijk niet om referenties vragen tijdens een opname sessie, maar dat de verificaties tappen nodig zijn tijdens het afspelen. 

Om dit op te lossen, moet de gebruiker het script hand matig bewerken om de opdrachten in te voegen die nodig zijn voor het aanmeldings proces.

**Andere beperkingen**

-   Het opnemen van bureaublad toepassingen tijdens een web-opname sessie. Als u zowel web-als bureaublad toepassingen wilt automatiseren, kunt u voor elk type een afzonderlijke UI-stroom maken en deze vervolgens combi neren in een stroom.

-   Multi-Factor Authentication (MFA) wordt niet ondersteund. gebruik een Tenant waarvoor MFA niet is vereist.

-   Deze Selenium IDE-opdrachten worden niet ondersteund: Run, AnswerOnNextPrompt, ChooseCancelOnNextConfirmation, ChooseCancelOnNextPrompt, ChooseOkOnNextConfirmation, debugger, ClickAt, DoubleClickAt, ECHO, MouseOut, MouseUpAt en MouseDownAt.

-   Met de rechter muisknop wordt niet ondersteund. 

-   Wanneer u foreach-opdrachten gebruikt, wordt extra stroom voor webui-invoer gegenereerd. U kunt dit probleem omzeilen door elke waarde in de extra velden in te voeren. Dit heeft geen invloed op het afspelen.

-   Als het bestand met de extensie meerdere test projecten bevat, wordt alleen de eerste versie uitgevoerd die is gemaakt. 

     >[!TIP]
     >Houd er rekening mee dat de Selenium IDE de tests op naam en niet op aanmaak datum bestelt, zodat de eerste test die u hebt gemaakt, niet het eerste is in de lijst.

-   Direct afspelen in de Selenium IDE werkt mogelijk niet zoals bedoeld. Afspelen tijdens runtime via de UI-stroom infrastructuur werkt echter goed.

## <a name="next-steps"></a>Volgende stappen

- Meer informatie over het [uitvoeren van UI-stromen](run-ui-flow.md).

- Als u meer wilt doen met UI-stromen, kunt u ook de gebruikers interface stromen uitproberen met [invoer-en uitvoer](inputs-outputs-web.md) parameters.

