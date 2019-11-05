---
title: Een werk stroom op aanvraag toevoegen aan een bedrijfs proces stroom
description: ''
author: MSFTMAN
ms.author: Deonhe
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
ms.service: flow
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 26c79c20-2987-476e-983a-406e0db13034
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ab30f745d6465cff9551854034c25130697144ba
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546121"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Een werk stroom op aanvraag toevoegen aan een bedrijfs proces stroom
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

U kunt werk stromen op aanvraag activeren vanuit een bedrijfs proces stroom. U kunt bijvoorbeeld een werk stroom op aanvraag toevoegen aan een bedrijfs proces stroom, zodat een activiteit, zoals een taak of e-mail bericht, wordt gemaakt wanneer een fase wordt voltooid. 

Er wordt een werk stroom geactiveerd op basis van waar u de werk stroom op de ontwerp functie voor bedrijfs processen neerzet.
- Fase ring op aanvraag. Wanneer de werk stroom naar een fase van een bedrijfs proces stroom wordt verwijderd, wordt de werk stroom geactiveerd bij het inbrengen of afsluiten van het stadium. 
- Globale processen op aanvraag. Wanneer de werk stroom wordt neergezet op het gebied **globale werk stromen** , wordt de werk stroom geactiveerd tijdens proces activering of archivering van processen (wanneer de status wordt gewijzigd in een toegepaste, voltooide, opnieuw geactiveerde of afgebroken status). 

Let op de volgende vereisten wanneer u een werk stroom toevoegt aan een bedrijfs proces stroom.
- Voor werk stromen die zijn toegevoegd aan een fase: u kunt alleen actieve werk stromen op aanvraag gebruiken die zijn gemaakt voor dezelfde entiteit van de fase waarin u de werk stroom toevoegt.  
- Voor algemene werk stromen: u kunt alleen actieve werk stromen op aanvraag gebruiken die zijn gemaakt voor de primaire entiteit van de stroom van het bedrijfs proces.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Een werk stroom op aanvraag toevoegen aan een fase van een bedrijfs proces stroom

U voegt een werk stroom op aanvraag van de ontwerp functie voor bedrijfs processen toe door de werk stroom component naar een proces fase of naar het gedeelte algemene werk stromen te slepen. 

Selecteer op de [PowerApps](https://web.powerapps.com) -site **model-aangedreven** (linksonder in het navigatie deel venster). 

Open de ontwerp functie voor bedrijfs processen. U kunt dit op een van de volgende twee manieren doen.
- Als de bedrijfs proces stroom al aan een app is toegevoegd, gaat u naar **apps**, naast de app die u wilt selecteren **...** en selecteert u vervolgens **bewerken**. Selecteer in de ontwerp functie voor apps de bedrijfs proces stroom en selecteer vervolgens ![open flow Designer voor bedrijfs processen](media/dynamics365-open-designer.PNG).  
- Als dat niet het geval is, opent u [Solution Explorer](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer)in het navigatie deel venster links selecteert u de optie **processen**en selecteert u vervolgens de gewenste bedrijfs proces stroom. 

Bepaal of u wilt dat de werk stroom op aanvraag wordt geactiveerd door een van de volgende activiteiten voor bedrijfsproces stromen. 
- Fase ring op aanvraag. Hiermee wordt de werk stroom geactiveerd of op het moment dat het stadium wordt afgesloten. 
- Globale processen op aanvraag. Hiermee wordt de werk stroom geactiveerd bij proces activering of proces archivering (wanneer de status wordt gewijzigd in een toegepaste, voltooide, opnieuw geactiveerde of afgebroken status). 

In het onderstaande voor beeld wordt een werk stroom op aanvraag met **de naam mijn op aanvraag werk** stroom toegevoegd aan **fase 1** van de bedrijfs proces stroom. 

1. Vouw fase 1 uit om de sectie **geactiveerd proces** weer te geven. 
2. Selecteer het tabblad **onderdelen** en sleep de **werk stroom** naar het gedeelte **geactiveerd proces** .
    ![werk stroom toe te voegen aan een fase](media/add-workflow-to-bpf-1.png) u kunt ook de **werk** stroom slepen naar het gedeelte **algemene werk stromen** , waardoor de werk stroom wordt geactiveerd door proces activering of proces archivering.
 ![Worfklow toevoegen aan proces activering of archiverings](media/add-workflow-to-bpf-global.png)
3. Typ en zoek in het zoekvak van het tabblad **Eigenschappen** de naam van de werk stroom op aanvraag die u wilt toevoegen aan de fase bedrijfs proces stroom en selecteer vervolgens **Toep assen**.
    ![Voer een naam in en selecteer Toep assen](media/add-workflow-to-bpf-2.png)
4. Selecteer op het tabblad **Eigenschappen** onder **trigger** de optie **fase-item** of **stadium afsluiten**.  
    ![werk stroom trigger selecteren](media/workflow-trigger.png)
   
    Als u de werk stroom op de sectie **algemene werk stromen** verwijdert, worden de trigger opties **toegepast**, wordt het proces **opnieuw geactiveerd**, wordt het **proces afgebroken**en **is het proces voltooid**.

5. Selecteer **bijwerken** op de werk balk van de bedrijfsproces stroom ontwerper.
 
## <a name="next-steps"></a>Volgende stappen
[Werk stroom processen gebruiken om processen te automatiseren waarvoor geen gebruikers interactie is vereist](workflow-processes.md) <br/>
[Zelf studie: een bedrijfs proces stroom maken om processen te standaardiseren](create-business-process-flow.md) <br/>
[Automatisering van bedrijfs processen in Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
