---
title: Een mobiele taakstroom maken met PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 7f15f11a4e66d80762384f8183af7973fcca76bf
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462758"
---
# <a name="create-a-mobile-task-flow"></a>Een mobiele taakstroom maken

Ontwerp een stroom in Dynamics 365 voor telefoons of Dynamics 365 voor tablets op basis van veelvoorkomende taken die door uw gebruikers worden uitgevoerd. Maak een taakstroom als gebruikers bijvoorbeeld regelmatig een reeks opvolgingsstappen moeten uitvoeren na vergaderingen met klanten. Wanneer gebruikers op de nieuwe taak in de mobiele app tikken, worden ze van begin tot eind begeleid, zodat ze geen belangrijke stap vergeten.  
  
 Taakstromen kunnen gebruikmaken van formulieren en logica voor meerdere entiteiten en kunnen formulierlogica bevatten die wordt uitgevoerd ten aanzien van de taakstroompagina's.  
  
## <a name="create-a-task-flow"></a>Een taakstroom maken
  
1. Zorg ervoor dat u over de beveiligingsrol van systeembeheerder of de rol van systeemaanpasser of gelijkwaardige machtigingen beschikt. Als u Dynamics 365 Customer Engagement, Manager, Vice President of CEO-Business-Manager gebruikt, kunnen beveiligingsrollen ook mobiele taakstromen maken. 
  
2. Open [Oplossingsverkenner](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) en selecteer **Processen**.  
  
3.  Selecteer **Nieuw** op de werkbalk **Acties**.  
  
4.  Vul in het dialoogvenster **Proces maken** de verplichte velden in:  
  
    -   Voer een procesnaam in.  
  
    -   Selecteer in de lijst **Categorie** de optie **Bedrijfsprocesstroom**.  
  
    -   Selecteer in de lijst **Entiteit** de gewenste entiteit.  
  
5.  Selecteer de optie **Proces uitvoeren als een taakstroom (online mobiel)**.  
  
6.  Selecteer **OK**.
  
     De ontwerpfunctie voor taakstromen wordt in een nieuw venster geopend.  
  
     ![Ontwerpfunctievenster voor taakstromen](media/task-flow-designer-window.png "Ontwerpfunctievenster voor taakstromen") 
  
7.  Als uw gebruikers van de ene pagina naar de andere in volgorde voortgaan, sleept u het onderdeel **Pagina** van het tabblad **Onderdelen** aan de rechterkant van het scherm en zet u dit op de juiste plaats neer op het +-teken. Als u een naam voor een pagina wilt toevoegen, selecteert u de pagina, selecteert u het tabblad **Eigenschappen**, typt u een nieuwe naam en selecteert u vervolgens **Toepassen**.  
  
8.  Als u een vertakking wilt toevoegen aan de taakstroom, sleept u het onderdeel **Voorwaarde** van het tabblad **Onderdelen** en zet u dit op de juiste plaats neer op het +-teken. Als u eigenschappen voor de voorwaarde wilt instellen, selecteert u de voorwaarde, stelt u de eigenschappen in het tabblad **Eigenschappen** in, en selecteert u vervolgens **Toepassen**.  
  
    > [!NOTE]
    >  Wanneer u pagina's en voorwaarden aan de taakstroom wilt toevoegen, ziet u een minimap in de linkerbenedenhoek van het venster waarin alle pagina's en voorwaarden in de taakstroom worden weergegeven.  
  
9. Sleep, als u een veld, label of sectielabel aan een pagina wilt toevoegen, **Veld**, **Label** of **Sectielabel** uit het tabblad **Onderdelen** naar de betreffende pagina. Als u eigenschappen voor een van deze items wilt wijzigen, selecteert u het item, stelt u de eigenschappen in het tabblad **Eigenschappen** in en selecteert u vervolgens **Toepassen**.  
  
10. Als u de processtroom wilt valideren, selecteert u **Valideren** op de actiebalk.  
  
11. Als u het proces wilt opslaan als concept, selecteert u **Opslaan** aan de bovenkant van het scherm. (Zolang een proces een concept is, kan het niet worden gebruikt.)  
  
12. Als u de taakstroom wilt activeren zodat deze kan worden gebruikt, selecteert u **Activeren**.  
  
> [!TIP]
>  Hier volgen een paar tips waarmee u rekening moet houden wanneer u aan uw taakstroom werkt in het venster van de ontwerpfunctie:  
>   
> -  Als u een momentopname wilt maken van alles in het venster taakstroom, selecteert u **Momentopname** op de actiebalk.  
> -  Als u een geldig onderdeel met een ander geldig onderdeel in de ontwerpfunctie wilt verbinden, selecteert u **Connector** in de actiebalk.  
> -  U kunt de afbeeldingen op het scherm groter of kleiner maken door de knoppen **Het zoomniveau verhogen** of **Het zoomniveau verlagen** in de rechterbovenhoek van het scherm te selecteren. Selecteer de knop **Aanpassen aan het canvas** om de afbeeldingen sneller op de maximaal op het scherm passende grootte te krijgen.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Een bedrijfsprocesstroom maken](create-business-process-flow.md)   

