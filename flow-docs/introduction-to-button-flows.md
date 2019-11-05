---
title: Meer informatie over het automatiseren en uitvoeren van terugkerende taken met knop stromen | Microsoft Docs
description: Inleiding tot knop stromen.
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 403c3d7cc116555ab26d5e4168587de5e5a6720f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547541"
---
# <a name="introducing-button-flows"></a>Introductie van knop stromen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-flows"></a>Wat zijn knop stromen?
Er zijn veel terugkerende taken die we graag kunnen uitvoeren met slechts een tik op een knop. U moet bijvoorbeeld snel uw team een e-mail sturen om hen eraan te herinneren deel te nemen aan de dagelijkse synchronisatie van het team, of u kunt een nieuwe Visual Studio online-build van uw code base starten nadat u een melding hebt ontvangen dat er geen ingecheckte items meer zijn gepland voor de dag. Met knop stromen kunt u deze en vele andere taken uitvoeren door simpelweg op een knop op uw mobiele apparaat te tikken.

**Opmerking** U kunt knop stromen maken op basis van uw mobiele apparaat of vanuit de stroom Portal.  
  afbeelding van ![overzicht](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Waarom knoppen maken?
Maak knoppen zodat u eenvoudig terugkerende taken kunt uitvoeren vanaf elke wille keurige manier via uw mobiele apparaat. Als u knoppen uitvoert, bespaart u tijd en, omdat de taken die ze uitvoeren automatisch worden uitgevoerd, zijn er minder fouten dan wanneer u ze hand matig hebt gedaan.  

## <a name="create-a-button"></a>Een knop maken
### <a name="prerequisites"></a>Vereisten
* Toegang tot flow. De beheerder kan u toegang verlenen.
* Een account met machtigingen voor het gebruik van de connectors om uw knop te maken. U hebt bijvoorbeeld een Dropbox-account nodig om een knop te maken die toegang heeft tot Dropbox.

### <a name="from-the-portal"></a>Vanuit de portal
In dit overzicht gaan we een knop maken die een Visual Studio online-build (VSO) start en meldingen verzendt om u te laten weten wanneer de build begint:  

1. Selecteer de vervolg keuzelijst **weer geven** en kies de categorie **knop** . Hiermee wordt de lijst met sjablonen gefilterd op alleen degenen die kunnen worden gebruikt in knop stromen.  
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-1.png)   
2. Selecteer de sjabloon **een nieuwe build in VSO in** de lijst met sjablonen.  
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-2.png)  
3. Selecteer de knop **deze sjabloon gebruiken** op de pagina **een nieuwe build activeren in VSO** .   
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-3.png)  
4. Als u niet bent aangemeld, wordt u op dit punt gevraagd dit te doen:  
   ![Overzichts afbeelding](./media/introduction-to-button-flows/create-button-4.png)  
5. Nadat u zich hebt aangemeld, wordt u gevraagd om u aan te melden bij de connectors die worden gebruikt in de sjabloon die u hebt geselecteerd. In dit voor beeld hebben we in stap 2 hierboven de sjabloon **een nieuwe build in VSO** geselecteerd, dus moet u zich aanmelden bij VSO (en andere connectors waarmee u werkt), als u zich nog niet hebt aangemeld:  
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Selecteer de knop **accepteren** als u de stroom wilt autoriseren voor toegang tot uw VSO-account.  
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-5.png)   
   **Opmerking** U moet elke connector op dezelfde manier autoriseren. De ontwerp functie moet er als volgt uitzien wanneer u klaar bent om door te gaan naar de volgende stap. Selecteer de knop **door gaan om door** te gaan:  
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-6.png)   
7. U bent nu klaar om de eigenschappen te configureren voor de build die u wilt starten:    
   ![Overzichts afbeelding](./media/introduction-to-button-flows/create-button-7.png)  
8. Selecteer of voer de **account naam**, **project naam**, **Build definition id**, **bron vertakking** en optioneel **para meters**in de **wachtrij een nieuwe build** -kaart in.    
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-8.png)  
9. Configureer vervolgens de eigenschappen van de push melding op de kaart voor het **verzenden van een push melding** . Deze push melding is standaard geconfigureerd voor het verzenden van een HTML-koppeling naar een webpagina waarop de status van de build wordt weer gegeven:  
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-9.png)  
10. Selecteer de knop **stroom maken** om de knop stroom op te slaan: ![overzichts afbeelding](./media/introduction-to-button-flows/create-button-10.png)  
11. U ziet dit geslaagde bericht binnen enkele ogen blikken:  
    ![Overzichts afbeelding](./media/introduction-to-button-flows/create-button-11.png)  

Gefeliciteerd, u hebt een knop stroom gemaakt. U kunt deze knop stroom nu altijd en overal uitvoeren, vanaf het tabblad **knoppen** in de flow-app. Als u op de knop klikt, wordt deze uitgevoerd. De mobiele app voor Microsoft Flow is beschikbaar voor [Android](https://aka.ms/flowmobiledocsandroid), [IOS](https://aka.ms/flowmobiledocsios)of [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>Vanaf uw mobiele apparaat
**Opmerking**: Hoewel er schermen worden weer gegeven van een Android-apparaat, zijn de schermen en ervaring op een IOS-apparaat vergelijkbaar.

In de flow-app:

1. Selecteer het tabblad **Bladeren** en schuif naar de categorie **knop** .  
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Selecteer de koppeling **alles weer geven** . Hiermee worden alle sjablonen voor kant-en-klare knoppen weer gegeven.     
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Selecteer het **e-mail bericht verzenden om uw team eraan te herinneren deel te nemen aan een sjabloon voor vergaderingen**    
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Selecteer de koppeling **deze sjabloon gebruiken** onder aan de pagina.    
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. U moet zich aanmelden bij alle services die door deze sjabloon worden gebruikt:    
   ![Overzichts afbeelding](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Selecteer de koppeling **volgende** nadat u zich hebt aangemeld bij alle services.      
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Selecteer de koppeling **maken** . Hier kunt u ook de stroom bekijken en wijzigingen aanbrengen die u nodig hebt om het e-mail bericht te personaliseren.        
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Na enkele ogen blikken wordt de knop stroom gemaakt. Selecteer **mijn stroom bekijken**:   
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Al uw stromen weer geven op het tabblad **mijn stromen**  
   afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Gefeliciteerd, u hebt een knop stroom gemaakt. U kunt deze knop stroom nu altijd en overal uitvoeren, vanaf het tabblad **knoppen** in de flow-app. Als u op de knop klikt, wordt deze uitgevoerd. De flow-app is momenteel beschikbaar op mobiele Android-en iOS-apparaten.  

![Overzichts afbeelding](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Een knop stroom activeren
Nu u een knop stroom hebt gemaakt, is het tijd om deze uit te voeren. Omdat u alleen knop stromen kunt uitvoeren vanuit de flow-app, moet u ervoor zorgen dat u de stroom hebt geïnstalleerd op uw mobiele Android-of iOS-apparaat.  

1. Start nu de flow-app, tik op het tabblad **knoppen** onder aan de pagina en tik op de *knop* van de knop stroom die u wilt activeren:  
   afbeelding van ![overzicht](./media/introduction-to-button-flows/trigger-button-1.png)   
2. De voortgang van de uitvoering van de stroom bekijken:  
   ![Overzichts afbeelding](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Ten slotte wordt de pagina bijgewerkt, wat aangeeft dat de knop stroom is voltooid:  
   ![Overzichts afbeelding](./media/introduction-to-button-flows/trigger-button-3.png)   

Dat is alles wat u moet doen om een stroom uit te voeren. 

U moet nu de push melding ontvangen, waarmee wordt aangegeven dat het e-mail bericht is verzonden.  

## <a name="monitor-your-button-flow-runs"></a>De uitvoering van uw knop stroom controleren
U kunt knop stromen bewaken op het tabblad **activiteit** van de flow-app:   
afbeelding van ![overzicht](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Opmerking**: Tik op een activiteit om uit te zoomen op de resultaten van de uitvoering om meer te weten te komen over de uitvoering.  

![Overzichts afbeelding](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Knop stromen beheren
U hebt de volledige controle over de knop stromen, zodat u een knop op elk gewenst moment kunt in-of uitschakelen, bewerken of verwijderen. Selecteer in de mobiele app of vanuit de stroom Portal **mijn stromen** om aan de slag te gaan met het beheer van uw stromen.    

Op het tabblad **mijn stromen** van de flow-app:

1. Selecteer de stroom die u wilt beheren:    
   ![Overzichts afbeelding](./media/introduction-to-button-flows/trigger-button-4.png)   
2. U kunt op een van deze opties tikken, op basis van wat u wilt doen:    
   ![Overzichts afbeelding](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Tik op **stroom verwijderen** om een stroom te verwijderen.  

**Opmerking** Alle uitvoerings geschiedenis wordt verwijderd wanneer u een stroom verwijdert:   
afbeelding van ![overzicht](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Tik op **bijwerken** nadat u klaar bent met het bewerken van een knop stroom om uw wijzigingen op te slaan:   
   afbeelding van ![overzicht](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Tik op **uitvoerings geschiedenis** om de resultaten van alle uitvoeringen van een bepaalde knop stroom te bekijken:    
   afbeelding van ![overzicht](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Als u een stroom uitschakelt, is deze niet meer beschikbaar op het tabblad **knoppen** :    
   afbeelding van ![overzicht](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Volgende stappen
* [Knop stromen delen](share-buttons.md).
* Leer hoe u [knop trigger tokens](introduction-to-button-trigger-tokens.md) kunt gebruiken voor het verzenden van real-time gegevens wanneer de knop stromen worden uitgevoerd.
* Installeer de mobiele app voor Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [IOS](https://aka.ms/flowmobiledocsios)of [Windows Phone](https://aka.ms/flowmobilewindows).

