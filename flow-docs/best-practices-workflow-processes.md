---
title: Aanbevolen procedures voor werkstroomprocessen | Microsoft Docs
description: Inzicht krijgen in de aanbevolen manieren waarop u werkstromen kunt gebruiken
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c0a59a625f4d43d125bde6ddf6edd5da5b6f6430
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460628"
---
# <a name="best-practices-for-workflow-processes"></a>Aanbevolen procedures voor werkstroomprocessen

Dit onderwerp bevat aanbevolen procedures voor het maken en beheren van werkstroomprocessen.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Oneindige lussen voorkomen  
 Het is mogelijk om logica te maken in een werkstroom waarmee een oneindige lus in werking wordt gesteld, wat serverbronnen verbruikt en van invloed is op prestaties. De typische situatie waarbij een oneindige lus optreedt, vindt plaats als u een werkstroom hebt die is geconfigureerd om te starten wanneer een kenmerk wordt bijgewerkt en vervolgens dat kenmerk bijwerkt in de logica van de werkstroom. Met de updateactie wordt dezelfde werkstroom geactiveerd als waarmee het record is bijgewerkt, waarmee de werkstroom steeds opnieuw wordt geactiveerd.  
  
 De werkstromen die u maakt, bevatten logica voor het detecteren en stoppen van oneindige lussen. Als een werkstroomproces meer dan een bepaald aantal keren binnen een korte tijd wordt uitgevoerd op een bepaald record, mislukt het proces met de volgende fout: **Deze werkstroomtaak is geannuleerd omdat de werkstroom waarmee deze is gestart een oneindige lus bevat. Corrigeer de werkstroomlogica en probeer het opnieuw**. Het aantal keren is beperkt tot 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>Werkstroomsjablonen gebruiken  
 Als u werkstromen hebt die vergelijkbaar zijn en u verwacht meer werkstromen te maken die hetzelfde patroon volgen, moet u uw werkstroom opslaan als werkstroomsjabloon. Op deze manier kunt u de volgende keer dat u een soortgelijke werkstroom wilt maken een werkstroom maken met behulp van de sjabloon en zo voorkomen dat u de voorwaarden en acties helemaal opnieuw moet invoeren.  
  
 Kies in het dialoogvenster **Proces maken** **Nieuw proces van een bestaande sjabloon (selecteer in de lijst)**.  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Onderliggende werkstromen gebruiken  
 Als u dezelfde logica toepast in verschillende werkstromen of voorwaardelijke vertakkingen, moet u die logica definiëren als een onderliggende werkstroom, zodat u die logica niet handmatig hoeft te repliceren in elke werkstroom of voorwaardelijke vertakking. Dit helpt u om uw werkstromen gemakkelijker te onderhouden. In plaats van veel werkstromen te controleren die dezelfde logica toepassen, hoeft u slechts één werkstroom bij te werken.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Automatisch voltooide werkstroomtaken verwijderen
Voor (asynchrone) achtergrondwerkstromen wordt u geadviseerd de optie **Automatisch voltooide werkstroomtaken verwijderen (om schijfruimte te besparen)** te selecteren in de werkstroomdefinitie. Als u dit selectievakje inschakelt, kan het systeem werkstroomlogboeken van geslaagde uitvoeringen verwijderen om ruimte te besparen. U ziet dat de logboeken van mislukte werkstroomuitvoeringen altijd worden opgeslagen voor het oplossen van problemen.  

![Vasthouden van werkstroomtaken](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Logboeken bijhouden voor werkstroomtaken waarin fouten zijn opgetreden  
Voor werkstromen die niet op de achtergrond worden uitgevoerd (synchroon) wordt u geadviseerd de optie **Logboeken bijhouden voor werkstroomtaken waarin fouten zijn opgetreden** in de werkstroomdefinitie te selecteren. Door de selectie van deze optie kunnen logboeken van mislukte werkstroomuitvoeringen worden opgeslagen voor het oplossen van problemen. Logboeken van geslaagde synchrone werkstroomuitvoeringen worden altijd verwijderd om ruimte te besparen.   

![De optie Logboeken bijhouden voor mislukte werkstromen](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Beperk het aantal werkstromen waarmee dezelfde entiteit wordt bijgewerkt
Meer dan één werkstroom uitvoeren waarmee dezelfde entiteit wordt bijgewerkt, kan problemen veroorzaken in verband met het vergrendelen van resources. Stelt u zich verschillende werkstromen voor die worden uitgevoerd waarbij elke update voor een verkoopkans een update activeert voor het gekoppelde account. Meerdere exemplaren van deze werkstromen die op hetzelfde moment worden uitgevoerd en pogen hetzelfde accountrecord bij te werken, kunnen resulteren in problemen in verband met het vergrendelen van resources. Er treden werkstroomfouten op en er wordt een foutbericht vastgelegd, zoals **SQL-time-out: kan geen vergrendeling verkrijgen op resource _naam van resource_**. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Gebruik Notities voor het bijhouden van wijzigingen  
 Tijdens het bewerken van werkstromen moet u het tabblad Notities gebruiken en typt u wat u hebt gedaan en waarom u dit hebt gedaan. Hierdoor kan iemand anders de wijzigingen begrijpen die u hebt gemaakt.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Overzicht van werkstroomprocessen](workflow-processes.md)   
 [Werkstroomprocessen configureren](configure-workflow-steps.md)   
 [Werkstroomprocessen controleren en beheren](monitor-manage-processes.md)
   
