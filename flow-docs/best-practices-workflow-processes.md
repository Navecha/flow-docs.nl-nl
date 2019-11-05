---
title: Aanbevolen procedures voor het beheren van werk stroom processen | MicrosoftDocs
description: Meer informatie over de aanbevolen manieren om werk stromen te gebruiken
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
ms.openlocfilehash: ad9935b171568b62376232f450a62dbda4752cac
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546018"
---
# <a name="best-practices-for-workflow-processes"></a>Aanbevolen procedures voor werk stroom processen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Dit onderwerp bevat aanbevolen procedures voor het maken en beheren van werk stroom processen.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Oneindige lussen voor komen  
 Het is mogelijk om logica te maken in een werk stroom die een oneindige lus initieert, waarbij Server bronnen worden verbruikt en de prestaties van invloed zijn. De typische situatie waarin een oneindige lus kan optreden, is als u een werk stroom hebt geconfigureerd die moet worden gestart wanneer een kenmerk wordt bijgewerkt en vervolgens dat kenmerk in de logica van de werk stroom wordt bijgewerkt. Met de actie bijwerken wordt dezelfde werk stroom geactiveerd waarmee de record wordt bijgewerkt en de werk stroom opnieuw wordt geactiveerd.  
  
 De werk stromen die u maakt, bevatten logica voor het detecteren en stoppen van oneindige lussen. Als een werk stroom proces in korte tijd meer dan een bepaald aantal keer wordt uitgevoerd, mislukt het proces met de volgende fout: **deze werk stroom taak is geannuleerd omdat er een oneindige lus is opgenomen in de werk stroom die is gestart. Corrigeer de werk stroom logica en probeer het opnieuw**. De maximale tijd is 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>Werk stroom sjablonen gebruiken  
 Als u werk stromen hebt die vergelijkbaar zijn en u verwacht meer werk stromen te maken die hetzelfde patroon volgen, slaat u uw werk stroom op als een werk stroom sjabloon. Op deze manier kunt u de volgende keer dat u een vergelijk bare werk stroom moet maken, de werk stroom maken met behulp van de sjabloon en voor komen dat alle voor waarden en acties helemaal volledig worden ingevoerd.  
  
 Kies in het dialoog venster **proces maken** de optie **nieuw proces op basis van een bestaande sjabloon (selecteren in de lijst)** .  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Onderliggende werk stromen gebruiken  
 Als u dezelfde logica toepast in verschillende werk stromen of voorwaardelijke vertakkingen, definieert u die logica als een onderliggende werk stroom, zodat u die logica niet hand matig hoeft te repliceren in elke werk stroom of voorwaardelijke vertakking. Zo kunt u uw werk stromen eenvoudiger maken. In plaats van veel werk stromen te controleren die dezelfde logica kunnen Toep assen, kunt u slechts één werk stroom bijwerken.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Voltooide werk stroom taken automatisch verwijderen
Voor achtergrond werk stromen (asynchroon) kunt u het beste de optie **voltooide werk stroom taken automatisch verwijderen (om schijf ruimte te besparen)** selecteren in de werk stroom definitie. Als u dit selectie vakje inschakelt, kan het systeem werk stroom logboeken verwijderen voor geslaagde uitvoeringen om ruimte te besparen. Houd er rekening mee dat Logboeken van mislukte werk stroom uitvoeringen altijd worden opgeslagen voor probleem oplossing.  

![Bewaren van werk stroom taken](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Logboeken voor werk stroom taken die fouten hebben aangetroffen, hand haven  
Voor werk stromen die niet op de achtergrond worden uitgevoerd (synchroon), raden we u aan om de optie **Logboeken voor werk stroom taken met fouten gevonden** in de werk stroom definitie in te scha kelen. Als u deze optie selecteert, worden logboeken van mislukte werk stroom uitvoeringen opgeslagen voor probleem oplossing. Logboeken van voltooide synchrone werk stroom uitvoeringen worden altijd verwijderd om ruimte te besparen.   

![Logboeken voor mislukte werk stromen gebruiken](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Het aantal werk stromen beperken dat dezelfde entiteit bijwerkt
Het uitvoeren van meer dan één werk stroom waarmee dezelfde entiteit wordt bijgewerkt, kan problemen met bron vergrendeling veroorzaken. Stel dat er meerdere werk stromen worden uitgevoerd waarbij elke update van de verkoop kans een update activeert op het gekoppelde account. Meerdere exemplaren van deze werk stromen die worden uitgevoerd en proberen dezelfde account record op hetzelfde moment bij te werken, kunnen leiden tot het vergren delen van problemen. Er treden werk stroom fouten op en een fout bericht, zoals **SQL-time-out: de vergren deling van de resource _bron naam_kan niet worden**genoteerd. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Notities gebruiken om wijzigingen bij te houden  
 Wanneer u werk stromen bewerkt, moet u het tabblad notities gebruiken en typen wat u hebt gedaan. Hierdoor kan iemand anders de aangebrachte wijzigingen begrijpen.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Overzicht van werk stroom processen](workflow-processes.md)   
 [Werk stroom processen configureren](configure-workflow-steps.md)   
 [Werk stroom processen bewaken en beheren](monitor-manage-processes.md)
   
