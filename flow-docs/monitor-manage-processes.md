---
title: Werkstroomprocessen controleren en beheren met PowerApps | MicrosoftDocs
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
ms.openlocfilehash: 007caa66731870f359e8cb33ba0919390d3196cd
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462873"
---
# <a name="monitor-and-manage-workflow-processes"></a>Werkstroomprocessen controleren en beheren

Voor het controleren en beheren van processen moet u het proces opzoeken, de status evalueren en eventuele acties ondernemen die nodig zijn om problemen te verhelpen.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Achtergrondwerkstromen controleren  
 Achtergrondwerkstromen genereren systeemtaakrecords voor het volgen van hun status. U kunt op verschillende plaatsen in de toepassing toegang krijgen tot informatie over deze systeemtaken:  
  
 **[Instellingen](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Systeemtaken**  
 Hierbij worden alle typen systeemtaken inbegrepen. U moet records filteren op records waarbij het **Systeemtaaktype** is **Werkstroom**.  
  
 **In het werkstroomproces**  
 Open de achtergrondwerkstroomdefinitie en ga naar het tabblad **Processessie**. Hiermee worden alleen de systeemtaken voor deze achtergrondwerkstroom weergegeven.  
  
 **Vanuit het record**  
 U kunt het formulier voor entiteit bewerken, zodat de navigatie de relatie **Achtergrondprocessen** bevat. Hiermee worden alle systeemtaken die zijn gestart in de context van het record weergegeven.  
  
> [!NOTE]
>  Als een asynchrone systeemtaak (werkstroom) meerdere keren achtereen is mislukt, wordt door het systeem de uitvoering van die taak met steeds langer wordende tijdsintervallen uitgesteld, zodat de beheerder of appmaker het probleem kan onderzoeken en oplossen. Zodra de taak opnieuw is gestart, wordt deze weer normaal uitgevoerd.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Acties voor het uitvoeren van achtergrondwerkstromen  
 Wanneer een achtergrondwerkstroom wordt uitgevoerd, kunt u kiezen voor het **annuleren**, **onderbreken** of **uitstellen** van de werkstroom. Als u een werkstroom eerder hebt onderbroken, kunt u deze **hervatten**.  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Realtime werkstromen en acties controleren  
 Realtime werkstromen en acties gebruiken geen systeemtaakrecords omdat ze onmiddellijk plaatsvinden. Eventuele fouten die optreden worden aan de gebruiker weergegeven in de toepassing met de kop **Bedrijfsprocesfout**.  
  
 Er is geen logboek voor geslaagde bewerkingen. U kunt logboekregistratie van fouten inschakelen door de optie **Logboeken bijhouden voor werkstroomtaken waarin fouten zijn opgetreden** te selecteren in het gebied **Werkstroomlogboek bewaren** onderaan het tabblad **Beheer** van het proces.  
  
 Als u het logboek van fouten voor een specifiek proces wilt weergeven, opent u de definitie realtimewerkstroom of -actie en gaat u naar het tabblad **Processessie**. Hiermee worden alleen eventuele fouten weergegeven die zijn vastgelegd voor dit proces.  
  
 Als u een weergave wilt van alle fouten voor elk proces, gaat u naar **Geavanceerd zoeken** en maakt u een weergave waarin fouten voor de entiteit Processessie worden getoond.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>Status van werkstroomprocessen  
 Wanneer u een lijst met werkstroomprocessen weergeeft, kan elk afzonderlijk proces een van de volgende waarden **Status** en **Reden van de status** bevatten:  
  
|Staat|Reden van de status|  
|-----------|-------------------|  
|Gereed|Wachten op resources|  
|Onderbroken|Wachten|  
|Vergrendeld|Wordt uitgevoerd<br /><br /> Onderbreken<br /><br /> Annuleren|  
|Voltooid|Geslaagd<br /><br /> Mislukt<br /><br /> Geannuleerd|  

## <a name="deleting-process-log-records"></a>Records van proceslogboeken verwijderen

Als uw organisatie gebruikmaakt van achtergrondwerkstromen of bedrijfsprocesstromen die vaak worden uitgevoerd, kan de hoeveelheid records van proceslogboeken groot genoeg worden om prestatieproblemen te veroorzaken, maar ook een aanzienlijke hoeveelheid opslagruimte in beslag nemen. Als u records van proceslogboeken wilt verwijderen die onvoldoende zijn verwijderd door een van de standaardtaken voor het bulksgewijs verwijderen van records, kunt u via de functie Systeemtaken voor bulksgewijs verwijderen een aangepaste taak voor het bulksgewijs verwijderen van de records maken.

1. Ga naar **Instellingen** > **Gegevensbeheer** > **Bulksgewijs verwijderen van records**.
2. Selecteer in het gebied **Bulksgewijs verwijderen van records** **Nieuw**. 
3. Selecteer op de startpagina **Wizard bulksgewijs verwijderen** **Volgende**.
4. Selecteer in de lijst **Zoeken naar** **Systeemtaken**.
5. De volgende voorwaarden worden gebruikt voor het maken van een taak voor het bulksgewijs verwijderen van records waarmee u records van proceslogboeken kunt verwijderen. 
 - **Systeemtaaktype is gelijk aan Werkstroom**. Dit is bedoeld voor werkstroomrecords. 
 - **De status is gelijk aan Voltooid**. Alleen de voltooide werkstromen zijn geldig voor het uitvoeren van de taak.
 - **Reden van de status is gelijk aan Geslaagd**. Verwijder geslaagde, geannuleerde en mislukte taken.
 - **Voltooid op ouder dan X dagen 30**. Gebruik het veld Voltooid om alleen records van proceslogboeken te verwijderen die ouder zijn dan 30 dagen.
 ![custom-bulk-record-deletion.png](media/custom-bulk-record-deletion.png)
6. Klik op **Volgende**.
7. Stel de frequentie in waarmee uw taak voor het bulksgewijs verwijderen wordt uitgevoerd. U kunt plannen dat uw taak met ingestelde intervallen wordt uitgevoerd of een taak maken voor eenmalig bulksgewijs verwijderen [met de optie Onmiddellijk](#using-the-immediately-option). In dit voorbeeld is een terugkerende taak ingesteld op 21 mei 2018 en om de 30 dagen erna. 
![Opties voor bulksgewijs verwijderen van records](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Met behulp van de optie Onmiddellijk

U ziet dat u de mogelijkheid hebt om de records onmiddellijk, synchroon en bulksgewijs te verwijderen door de optie **Onmiddellijk** te selecteren. Deze verwijdering wordt uitgevoerd via een directe SQL Server-uitvoerbewerking in plaats van elk record via de pijplijn voor verwijderen van gebeurtenissen te leiden, wat minder invloed op de systeemprestaties kan hebben. Dit is een goede optie als u de extra werkstroomrecords snel wilt opschonen in plaats van de taak voor bulksgewijs verwijderen die in afwachting is in de asynchrone wachtrij voor verwerking. 

De optie **Onmiddellijk** is ingeschakeld wanneer aan de volgende voorwaarden wordt voldaan: 
- De taak voor bulksgewijs verwijderen is bestemd voor de entiteit Systeemtaken.
- De zoekcriteria bevatten de voorwaarde dat het systeemtaaktype gelijk is aan Werkstroom. 
- De gebruiker die de taak voor bulksgewijs verwijderen heeft gemaakt, heeft globale diepte voor de bevoegdheid voor verwijderen voor de entiteit AsyncOperation. De beveiligingsrol van de systeembeheerder heeft deze bevoegdheid.  

De synchrone bulkverwijdering betreft alleen AsyncOperation-records met de status Voltooid. Er worden maximaal een miljoen records verwerkt voor elke aanroep. U moet de taak meerdere keren uitvoeren als in uw omgeving meer dan één miljoen records moeten worden verwijderd.  
  
## <a name="next-steps"></a>Volgende stappen   
 [Aanbevolen procedures voor werkstroomprocessen](best-practices-workflow-processes.md) <br />

