---
title: Een mobiele taak stroom maken met PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ccd3b6c0e8cf97a490d01bb9ba5e5c3c4043fda5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546428"
---
# <a name="create-a-mobile-task-flow"></a>Een mobiele taak stroom maken
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Ontwerp een stroom in Dynamics 365 voor telefoons of Dynamics 365 voor tablets op basis van algemene taken die uw gebruikers uitvoeren. Als er bijvoorbeeld regel matig een reeks opvolgings stappen moet worden uitgevoerd na client vergaderingen, maakt u een taak stroom. Wanneer gebruikers op de nieuwe taak in hun mobiele app tikken, worden ze doorheen van begin tot eind, zodat ze een belang rijke stap niet verg eten.  
  
 Taak stromen kunnen gebruikmaken van multi-entity formulieren en logica, en kunnen formulier logica hebben die wordt uitgevoerd op de pagina's van de taak stroom.  
  
## <a name="create-a-task-flow"></a>Een taak stroom maken
  
1. Zorg ervoor dat u beschikt over de beveiligingsrol systeem beheerder of systeemaanpasser of gelijkwaardige machtigingen. De Manager, vice president of CEO-Business Manager, beveiligings rollen kunnen ook mobiele taak stromen maken. 
  
2. Open [Solution Explorer](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) en selecteer **processen**.  
  
3.  Selecteer **Nieuw**op de werk balk **acties** .  
  
4.  In het dialoog venster **proces maken** vult u de vereiste velden in:  
  
    -   Voer een proces naam in.  
  
    -   Selecteer **bedrijfs proces stroom**in de lijst **categorie** .  
  
    -   Selecteer in de lijst **entiteit** de gewenste entiteit.  
  
5.  Selecteer de optie **proces uitvoeren als een taak stroom (Mobile online)** .  
  
6.  Selecteer **OK**.
  
     De taak stroom ontwerper wordt in een nieuw venster geopend.  
  
     ![Venster taak stroom ontwerper](media/task-flow-designer-window.png "Venster taak stroom ontwerper") 
  
7.  Als uw gebruikers in de aangegeven volg orde van de ene pagina naar de andere gaan, sleept u de **pagina** component van het tabblad **onderdelen** aan de rechter kant van het scherm en zet u deze neer op het plus teken in de juiste plaats. Als u een naam wilt toevoegen voor een pagina, selecteert u de pagina, selecteert u het tabblad **Eigenschappen** , typt u een nieuwe naam en selecteert u vervolgens **Toep assen**.  
  
8.  Als u een vertakking wilt toevoegen aan de taak stroom, sleept u het onderdeel **voor waarde** van het tabblad **onderdelen** en zet u het neer op het plus teken in de juiste plaats. Als u eigenschappen voor de voor waarde wilt instellen, selecteert u de voor waarde, stelt u de eigenschappen in op het tabblad **Eigenschappen** en selecteert u vervolgens **Toep assen**.  
  
    > [!NOTE]
    >  Wanneer u pagina's en voor waarden aan de taak stroom toevoegt, ziet u in de linkerbenedenhoek van het venster een Minimap waarin alle pagina's en voor waarden in de taak stroom worden weer gegeven.  
  
9. Als u een veld, label of sectie label wilt toevoegen aan een pagina, sleept u het **veld**, **Label**of **sectie Label** van het tabblad **onderdelen** naar de juiste pagina. Als u de eigenschappen van een van deze items wilt wijzigen, selecteert u het item, stelt u de eigenschappen in op het tabblad **Eigenschappen** en selecteert u vervolgens **Toep assen**.  
  
10. Als u de taak stroom wilt valideren, selecteert u **valideren** op de actie balk.  
  
11. Als u het proces als concept wilt opslaan, selecteert u **Opslaan** boven aan het scherm. (Zolang een proces een concept is, kunnen mensen het niet gebruiken.)  
  
12. Selecteer **activeren**om de taak stroom te activeren zodat mensen deze kunnen gebruiken.  
  
> [!TIP]
>  Hier volgen enkele tips waarmee u op de hoogte blijft van uw taak stroom in het ontwerp venster:  
>   
> -  Als u een moment opname van alles in het taak stroom venster wilt maken, selecteert u **moment opname** op de actie balk.  
> -  Als u een geldig onderdeel wilt verbinden met een ander geldig onderdeel in de ontwerp functie, selecteert u **connector** op de actie balk.  
> -  U kunt de afbeeldingen op het scherm groter of kleiner maken door de knoppen **Zoom niveau verg Roten** of **verkleinen** te selecteren in de rechter bovenhoek van het scherm. Selecteer de knop **passend maken van het canvas** om de installatie kopieën te laten oplopen tot de maximale grootte die op het scherm past.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Een bedrijfs proces stroom maken](create-business-process-flow.md)   

