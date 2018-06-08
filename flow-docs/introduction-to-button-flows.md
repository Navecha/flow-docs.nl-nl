---
title: Meer informatie over het automatiseren en uitvoeren van terugkerende taken met knopstromen | Microsoft Docs
description: Inleiding tot knopstromen.
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
ms.date: 01/30/2017
ms.author: deonhe
ms.openlocfilehash: 558570733819e1fde6c1845ed5ca9debe9232c88
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440511"
---
# <a name="introducing-button-flows"></a>Kennismaken met knopstromen
## <a name="what-are-button-flows"></a>Wat zijn knopstromen?
Er zijn veel terugkerende taken die we allemaal graag met één tik op een knop willen kunnen uitvoeren. U moet bijvoorbeeld snel uw team een e-mail sturen om hen eraan te herinneren deel te nemen aan de dagelijkse teamsynchronisatie, of wilt een nieuwe Visual Studio Online-build van de codebasis starten nadat u hebt ervan op de hoogte bent gesteld dat er voor die dag geen checkins zijn gepland. Met knopstromen kunt u deze en vele andere taken uitvoeren door op een knop op uw mobiele apparaat te tikken.

**Opmerking**: u kunt knopstromen maken vanaf uw mobiele apparaat of vanuit de Flow-portal.  
  ![Overzichtsafbeelding](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Waarom knoppen maken?
Maak knoppen om eenvoudig terugkerende taken overal en altijd vanaf het mobiele apparaat te kunnen uitvoeren. Met knoppen bespaart u tijd. Omdat de taken automatisch worden uitgevoerd, is er bovendien minder kans op fouten dan wanneer u ze handmatig uitvoert.  

## <a name="create-a-button"></a>Een knop maken
### <a name="prerequisites"></a>Vereisten
* Toegang tot Flow. De beheerder kan u toegang verlenen.
* Een account met machtigingen om de connectoren te gebruiken waarmee u de knop maakt. U moet bijvoorbeeld een Dropbox-account hebben om een knop te kunnen maken die toegang heeft tot Dropbox.

### <a name="from-the-portal"></a>Vanuit de portal
In deze walkthrough maken we een knop waarmee een VSO-build (Visual Studio Online) wordt gestart en meldingen worden verzonden zodat u weet wanneer de build start:  

1. Selecteer de vervolgkeuzelijst **Weergeven** en kies de categorie **Knop**. Hiermee wordt de lijst met sjablonen gefilterd tot alleen die sjablonen worden weergegeven die kunnen worden gebruikt in knopstromen.  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-1.png)   
2. Selecteer de sjabloon **Trigger a new build in VSO** (Een nieuwe build activeren in VSO) uit de lijst met sjablonen.  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-2.png)  
3. Selecteer de knop **Deze sjabloon gebruiken** op de pagina **Trigger a new build in VSO** (Een nieuwe build activeren in VSO).   
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-3.png)  
4. Als u niet bent aangemeld, wordt u gevraagd dit nu te doen:  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-4.png)  
5. Nadat u zich bij Flow hebt aangemeld, wordt u gevraagd zich aan te melden bij de connectors die worden gebruikt in de sjabloon die u hebt geselecteerd. In dit voorbeeld hebben we in stap 2 hierboven de sjabloon **Trigger a new build in VSO** (Een nieuwe build activeren in VSO) geselecteerd, zodat we moeten aanmelden bij VSO (en eventuele andere connectors waarmee u werkt) als u nog niet bent aangemeld:  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Selecteer de knop **Accepteren** als u ermee akkoord gaat Flow toegang tot uw VSO-account te geven.  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-5.png)   
   **Opmerking**: u moet elke connector op dezelfde manier toestemming geven. De designer moet als er volgt uitzien als u klaar bent om verder te gaan naar de volgende stap. Selecteer de knop **Doorgaan** om verder te gaan:  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-6.png)   
7. U bent nu klaar om de eigenschappen te configureren voor de build die u wilt starten:    
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-7.png)  
8. Selecteer de **Accountnaam**, **Projectnaam**, **Build-definitie-id**, **Bronvertakking** en desgewenst **Parameters** of voer deze in op de kaart **Queue a new build** (Een nieuwe build in de wachtrij plaatsen):    
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-8.png)  
9. Configureer vervolgens de eigenschappen van de pushmelding op de kaart **Send a push notification** (Een pushmelding verzenden). Deze pushmelding is standaard geconfigureerd voor het verzenden van een HTML-koppeling naar een webpagina waarop de status van de build wordt weergegeven:  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-9.png)  
10. Selecteer de knop **Stroom maken** om uw knopstroom op te slaan: ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-10.png)  
11. Binnen enkele ogenblikken ziet u dit bericht:  
    ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-11.png)  

U hebt een knopstroom gemaakt. U kunt deze knopstroom nu altijd en overal uitvoeren, vanaf het tabblad **Knoppen** in de Flow-app. Druk op de 'knop' en de stroom wordt uitgevoerd. De mobiele app voor Microsoft Flow is beschikbaar voor [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) en [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>Op uw mobiele apparaat
**Opmerking**: in dit overzicht worden schermafbeeldingen weergegeven van een Android-apparaat. De schermen en ervaring op een iOS-apparaat zijn vergelijkbaar.

In de Flow-app:

1. Selecteer het tabblad **Bladeren** en schuif naar de categorie **Knop**.  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Selecteer de koppeling **See all** (Allemaal weergeven). Hiermee worden alle sjablonen vooraf geconfigureerde knopsjablonen weergegeven.     
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Selecteer de sjabloon **Send an email to remind your team to join a meeting** (Een e-mail sturen naar uw team om hen te herinneren aan een vergadering)    
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Selecteer de koppeling **USE THIS TEMPLATE** (DEZE SJABLOON GEBRUIKEN) onder aan de pagina.    
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. U moet zich aanmelden bij alle services die gebruikmaken van dit sjabloon:    
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Selecteer de koppeling **Volgende** nadat u zich hebt aangemeld bij alle services.      
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Selecteer de koppeling **maken**. Hier kunt u ook de stroom bekijken en bijvoorbeeld wijzigingen aanbrengen die u nodig vindt om het e-mailbericht te personaliseren.        
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Na enkele ogenblikken wordt de knopstroom gemaakt. Selecteer **SEE MY FLOW** (ZIE MIJN STROOM):   
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Al uw stromen bekijken op het tabblad **Mijn stromen**  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

U hebt een knopstroom gemaakt. U kunt deze knopstroom nu altijd en overal uitvoeren, vanaf het tabblad **Knoppen** in de Flow-app. Druk op de 'knop' en de stroom wordt uitgevoerd. De Flow-app is momenteel beschikbaar op mobiele Android- en iOS-apparaten.  

![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Een knopstroom activeren
Nu u een knopstroom hebt gemaakt, is het tijd deze uit te voeren. Omdat u knopstromen alleen kunt uitvoeren vanuit de Flow-app, moet Flow zijn geïnstalleerd op uw mobiele Android- of iOS-apparaat.  

1. Start de Flow-app, tik op het tabblad **Knoppen** onder aan de pagina en tik op de *knop* van de knopstroom die u wilt activeren:  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Bekijk de voortgang terwijl de stroom wordt uitgevoerd:  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Ten slotte wordt de pagina bijgewerkt en wordt aangegeven dat de knopstroom is voltooid:  
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/trigger-button-3.png)   

Meer heeft het uitvoeren van een stroom niet om het lijf. 

U ontvangt nu de pushmelding waarin wordt aangegeven dat het e-mailbericht is verzonden.  

## <a name="monitor-your-button-flow-runs"></a>De uitvoering van uw knopstromen bewaken
U kunt knopstromen bewaken vanaf het tabblad **Activiteit** van de Flow-app:   
![Overzichtsafbeelding](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Opmerking**: tik op elke activiteit om te zoomen op de resultaten van de uitvoering voor meer informatie over de uitvoering.  

![Overzichtsafbeelding](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Knopstromen beheren
U hebt volledige controle over knopstromen. U kunt een knop daarom altijd en overal in- of uitschakelen. Selecteer vanuit de mobiele app of van de Flow-portal **Mijn stromen** om uw stromen te beheren.    

Op het tabblad **Mijn stromen** van de Flow-app:

1. Selecteer de stroom die u wilt beheren:    
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Tik op een van deze opties, afhankelijk van wat u wilt bereiken:    
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Tik op **Delete flow** (Stroom verwijderen) om een stroom te verwijderen.  

**Opmerking**: de volledige uitvoeringsgeschiedenis wordt verwijderd wanneer u een stroom verwijdert:   
![Overzichtsafbeelding](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Tik op **Update** (Bijwerken) als u klaar bent met het bewerken van een stroomknop om uw wijzigingen op te slaan:   
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Tik op **Run history** (Uitvoeringsgeschiedenis) om de resultaten van alle uitvoeringen van een bepaalde knopstroom te bekijken:    
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Als u een stroom uitschakelt, is deze niet meer beschikbaar op het tabblad **Knoppen**:    
   ![Overzichtsafbeelding](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Volgende stappen
* [Knopstromen delen](share-buttons.md).
* Leer hoe u [knoptriggertokens](introduction-to-button-trigger-tokens.md) kunt gebruiken om realtimegegevens te verzenden wanneer uw knopstromen worden uitgevoerd.
* Installeer de mobiele app voor Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) of [Windows Phone](https://aka.ms/flowmobilewindows).

