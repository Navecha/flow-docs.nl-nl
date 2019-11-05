---
title: Werk stroom processen bewaken en beheren met PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 05/06/2018
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
ms.assetid: a987a803-4674-4eb0-87de-caefa003b1eb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 00d20d361dd7b3db9f55d6b975c472bea0c4160e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548993"
---
# <a name="monitor-and-manage-workflow-processes"></a>Werk stroom processen bewaken en beheren
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Als u processen wilt bewaken en beheren, moet u het proces vinden, de status evalueren en alle acties uitvoeren die nodig zijn om problemen op te lossen.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Achtergrond werk stromen bewaken  
 Met achtergrond werk stromen worden systeem taak records gegenereerd om hun status bij te houden. Meer informatie over deze systeem taken vindt u op verschillende locaties in de toepassing:  
  
 **[Instellingen](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > systeem taken**  
 Hiermee worden alle typen systeem taken vermeld. U moet de records filteren op de locatie van het **systeem taak type** **werk stroom**.  
  
 **Vanuit het werk stroom proces**  
 Open de definitie van de achtergrond werk stroom en ga naar het tabblad **proces sessie** . Hiermee worden alleen de systeem taken voor deze achtergrond werk stroom weer gegeven.  
  
 **Uit de record**  
 U kunt het entiteits formulier bewerken zodat de navigatie de **achtergrond proces** relatie bevat. Hiermee worden alle systeem taken weer gegeven die zijn gestart in de context van de record.  
  
> [!NOTE]
>  Als een asynchrone systeem taak (werk stroom) meerdere keren achter elkaar mislukt, begint het systeem de uitvoering van de taak langer en langere tijd uit te stellen, zodat de beheerder of app maker het probleem kan onderzoeken en oplossen. Zodra de taak weer is voltooid, wordt deze normaal uitgevoerd.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Acties voor het uitvoeren van achtergrond werk stromen  
 Terwijl een werk stroom op de achtergrond wordt uitgevoerd, hebt u opties om de werk stroom te **Annuleren**, te **onderbreken**of uit te **stellen** . Als u een werk stroom eerder hebt onderbroken, kunt u deze **hervatten** .  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Real-time werk stromen en acties bewaken  
 In realtime werk stromen en acties worden geen systeem taak records gebruikt, omdat deze direct optreden. Eventuele fouten die zich voordoen, worden weer gegeven aan de gebruiker in de toepassing met het **bedrijfs proces fout**voor de titel.  
  
 Er is geen logboek voor geslaagde bewerkingen. U kunt logboek registratie inschakelen voor fouten door de optie **Logboeken bewaren voor werk stroom taken waarvoor fouten zijn aangetroffen** te controleren in het gebied **Bewaar periode van het werk stroom logboek** onder aan het tabblad **beheer** voor het proces.  
  
 Als u het logboek met fouten voor een specifiek proces wilt weer geven, opent u de real-time werk stroom of de definitie van de actie en gaat u naar het tabblad **proces sessie** . Hiermee worden alleen de fouten weer gegeven die voor dit proces zijn geregistreerd.  
  
 Als u een overzicht wilt weer geven van alle fouten voor elk proces, gaat u naar **Geavanceerd zoeken** en maakt u een weer gave met fouten op de entiteit proces sessie.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>Status van werk stroom processen  
 Wanneer u een lijst met werk stroom processen bekijkt, kan elk afzonderlijk proces een van de volgende **status** -en **status** waarden hebben:  
  
|Overheids|Reden van status|  
|-----------|-------------------|  
|Voortzetten|Wachten op resources|  
|Gebroken|Tijd|  
|Lock|Wordt uitgevoerd<br /><br /> Onderbreken<br /><br /> Annuleren|  
|gevuld|Is voltooid<br /><br /> is mislukt<br /><br /> Geannuleerd|  

## <a name="deleting-process-log-records"></a>Proces logboek records verwijderen

Als uw organisatie achtergrond werk stromen of bedrijfsproces stromen gebruikt die regel matig worden uitgevoerd, kan de hoeveelheid proces logboek records groot genoeg worden om prestatie problemen te veroorzaken en aanzienlijke hoeveel heden opslag ruimte in beslag nemen. Het verwijderen van proces logboek records die niet voldoende zijn verwijderd door een van de standaard taken voor het verwijderen van bulk records, kunt u de functie systeem taken bulksgewijs verwijderen gebruiken om een aangepaste taak voor het verwijderen van bulk records te maken.

1. Ga naar **instellingen** > **Gegevensbeheer** > **bulksgewijs verwijderen van records**.
2. Selecteer in het gebied **verwijderen bulk records** de optie **Nieuw**. 
3. Selecteer **volgende**op de start pagina van de **wizard voor bulk verwijdering** .
4. Selecteer in de lijst **zoeken naar** de optie **systeem taken**.
5. De volgende voor waarden worden gebruikt om een taak voor het verwijderen van een bulk record te maken om proces logboek records te verwijderen. 
 - **Systeem taak type is gelijk aan werk stroom**. Hiermee worden werk stroom records doel. 
 - De **status is gelijk aan voltooid**. Alleen voltooide werk stromen zijn geldig om de taak uit te voeren.
 - **Status reden is gelijk aan geslaagd**. Voltooide, geannuleerde en mislukte taken verwijderen.
 - **Voltooid op ouder dan X dagen 30**. Gebruik het veld voltooid op om alleen logboek records van werk stroom processen te verwijderen die ouder zijn dan 30 dagen.
 ![Custom-bulk-record-deletion. png](media/custom-bulk-record-deletion.png)
6. Klik op **volgende**.
7. Stel de frequentie in waarmee uw bulk verwijderings taak wordt uitgevoerd. U kunt de taak zodanig plannen dat deze wordt uitgevoerd met ingestelde intervallen of een eenmalige bulk verwijderings taak maken [met behulp van de optie direct](#using-the-immediately-option). In dit voor beeld is een terugkerende taak zo ingesteld dat deze wordt uitgevoerd op 21 mei 2018 en vervolgens om de 30 dagen. 
![opties voor het verwijderen van bulk records](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Met de optie onmiddelijk

U hebt de mogelijkheid om een onmiddellijke synchrone bulk verwijdering van de records uit te voeren door de optie **direct** te selecteren. Deze verwijdering wordt uitgevoerd met directe SQL Server uitvoering in plaats van elke record door te geven via de pijp lijn voor het verwijderen van de gebeurtenis, waardoor de invloed op de systeem prestaties kan verminderen. Dit is een goede optie als u de extra werk stroom records snel wilt opschonen in plaats van de taak bulksgewijze verwijderen in de asynchrone wachtrij voor verwerking. 

De optie **direct** is ingeschakeld wanneer aan de volgende voor waarden wordt voldaan: 
- Bulk verwijderings taak is voor de entiteit systeem taken.
- De zoek criteria hebben het type systeem taak voor waarde is gelijk aan de werk stroom. 
- De gebruiker die de bulk verwijderings taak maakt, heeft globale diepte voor de bevoegdheid verwijderen voor de entiteit AsyncOperation. De beveiligingsrol systeem beheerder heeft deze bevoegdheid.  

Bij bulksgewijs verwijderen worden alleen AsyncOperation-records met de status voltooid verwijderd. Er worden Maxi maal 1.000.000 records verwerkt voor elke aanroep. U moet de taak meerdere keren uitvoeren als uw omgeving meer dan 1.000.000 records bevat om te verwijderen.  
  
## <a name="next-steps"></a>Volgende stappen   
 [Aanbevolen procedures voor werk stroom processen](best-practices-workflow-processes.md) <br />

