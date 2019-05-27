---
title: Een werkstroom op aanvraag toevoegen aan een bedrijfsprocesstroom
description: ''
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
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
ms.openlocfilehash: aa061d5e2f668e8950a6cdab89992996f64c6fe8
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460972"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Een werkstroom op aanvraag toevoegen aan een bedrijfsprocesstroom

U kunt werkstromen op aanvraag activeren vanuit een bedrijfsprocesstroom. U kunt bijvoorbeeld een werkstroom op aanvraag toevoegen aan een bedrijfsprocesstroom, zodat een activiteit, zoals een taak of e-mail, wordt gemaakt wanneer er een fase is voltooid. 

Een werkstroom wordt geactiveerd op basis van waar u de werkstroom neerzet in de ontwerpfunctie voor bedrijfsprocesstromen.
- Faseprocessen voor werkstromen op aanvraag. Wanneer de werkstroom wordt toegevoegd aan een fase van een bedrijfsprocesstroom, wordt de werkstroom geactiveerd bij het betreden of verlaten van de fase. 
- Algemene processen voor werkstromen op aanvraag. Wanneer de werkstroom wordt toegevoegd aan het gebied **Algemene werkstromen**, wordt de werkstroom geactiveerd op het moment van procesactivering of procesarchivering (wanneer de status verandert in toegepast, voltooid, opnieuw geactiveerd of afgebroken). 

Let op de volgende vereisten bij het toevoegen van een werkstroom aan een bedrijfsprocesstroom.
- Voor werkstromen die zijn toegevoegd aan een fase: U kunt alleen gebruiken bij actieve en on-demand werkstromen die zijn gemaakt voor dezelfde entiteit van de fase waarin u de werkstroom toevoegen.  
- Voor algemene werkstromen: U kunt alleen op aanvraag, actieve werkstromen die zijn gemaakt voor de primaire entiteit van de zakelijke processtroom gebruiken.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Een werkstroom op aanvraag toevoegen aan een fase van een bedrijfsprocesstroom

U voegt een werkstroom op aanvraag toe in de ontwerpfunctie voor bedrijfsprocesstromen door het werkstroomonderdeel naar een procesfase te slepen of naar de sectie Algemene werkstromen. 

Selecteer op de site van [PowerApps](https://web.powerapps.com) de optie **Modelgestuurd** (linksonder in het navigatiedeelvenster). 

Open de ontwerpfunctie voor bedrijfsprocesstromen. Dit kan op twee manieren.
- Als de bedrijfsprocesstroom al is toegevoegd aan een app, gaat u naar **Apps**, selecteert u **...**  naast de app die u wilt selecteren en selecteert u vervolgens **Bewerken**. Selecteer in de ontwerpfunctie voor apps de bedrijfsprocesstroom en selecteer vervolgens![ ](media/dynamics365-open-designer.PNG)de optie voor het openen van de ontwerpfunctie voor bedrijfsprocesstromen.  
- Anders opent u [Solution Explorer](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer), selecteert u in het navigatiedeelvenster aan de linkerkant **Processen** en selecteert u vervolgens de gewenste bedrijfsprocesstroom. 

Bepaal of de werkstroom op aanvraag moet worden geactiveerd door een van de volgende gebeurtenissen voor bedrijfsprocesstromen. 
- Faseprocessen voor werkstromen op aanvraag. Hiermee wordt de werkstroom geactiveerd bij het betreden of verlaten van de fase. 
- Algemene processen voor werkstromen op aanvraag. De werkstroom wordt geactiveerd op het moment van procesactivering of procesarchivering (wanneer de status verandert in toegepast, voltooid, opnieuw geactiveerd of afgebroken). 

In het volgende voorbeeld wordt een werkstroom op aanvraag met de naam **My on demand workflow** toegevoegd aan **Stage 1** van de bedrijfsprocesstroom. 

1. Vouw fase 1 uit om de sectie **Triggered Process** weer te geven. 
2. Selecteer het tabblad **Onderdelen** en sleep **Workflow** naar de sectie **Triggered Process**.
    ![Werkstroom toevoegen aan een fase](media/add-workflow-to-bpf-1.png) U kunt ook **Workflow** naar de sectie **Algemene werkstromen** slepen, waardoor de werkstroom wordt geactiveerd bij procesactivering of procesarchivering.
 ![Werkstroom toevoegen aan procesactivering of procesarchivering](media/add-workflow-to-bpf-global.png)
3. Typ in het zoekvak van het tabblad **Eigenschappen** de naam van de werkstroom op aanvraag die u wilt toevoegen aan de fase van de bedrijfsprocesstroom en selecteer vervolgens **Toepassen**.
    ![Naam invoeren en Toepassen selecteren](media/add-workflow-to-bpf-2.png)
4. Ga op het tabblad **Eigenschappen** naar **Trigger** en selecteer **Fase-invoer** of **Afsluiten van fase**.  
    ![Trigger voor werkstroom selecteren](media/workflow-trigger.png)
   
    Wanneer u de werkstroom naar de sectie **Algemene werkstromen** sleept, kunt u kiezen uit de trigger-opties **Proces toegepast**, **Proces opnieuw geactiveerd**,  **Proces verlaten** en **Proces voltooid**.

5. Selecteer **Bijwerken** op de werkbalk van de ontwerpfunctie voor bedrijfsprocesstromen.
 
## <a name="next-steps"></a>Volgende stappen
[Werkstroomprocessen gebruiken voor het automatiseren van processen die geen tussenkomst van de gebruiker vereisen](workflow-processes.md) <br/>
[Zelfstudie: Een bedrijfsprocesstroom maken om processen te standaardiseren](create-business-process-flow.md) <br/>
[Automatisering van bedrijfsprocesstromen in Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
