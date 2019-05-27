---
title: Werkstroomfasen en -stappen configureren in PowerApps | Microsoft Docs
description: Informatie over het configureren van werkstroomstappen
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 0b47dfd5-76db-464f-90c0-c64a0173dcdd
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9ebdb1eddaea1f2fd7918c968879f5da37c287fe
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456182"
---
# <a name="configure-workflow-stages-and-steps"></a>Werkstroomfasen en -stappen configureren

Bij het ontwerpen van werkstromen hebt u de mogelijkheid om de logica op te nemen die u wilt uitvoeren in fasen en stappen.  
  
 **Fasen**  
 Fasen maken de logica van een werkstroom gemakkelijker te lezen en beschrijven de werkstroomlogica. Fasen hebben echter geen invloed op de logica of het gedrag van werkstromen. Als een proces bestaat uit fasen, moeten alle stappen in het proces zijn opgenomen in een fase.  
  
 **Stappen**  
 Stappen zijn een eenheid van bedrijfslogica binnen een werkstroom. Stappen kunnen bestaan uit voorwaarden, acties, andere stappen of een combinatie van deze elementen.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Acties die werkstroomprocessen kunnen uitvoeren  

 Werkstroomprocessen kunnen de acties uit de volgende tabel uitvoeren.  
  
|Actie|Beschrijving|  
|------------|-----------------|  
|**Record maken**|Hiermee maakt u een nieuwe record voor een entiteit en worden de waarden die u kiest, toegewezen aan kenmerken.|  
|**Record bijwerken**|U kunt de record bijwerken waarop de werkstroom wordt uitgevoerd, een record die aan deze record is gekoppeld in een N:1-relatie of een record die in eerdere stappen is gemaakt.|  
|**Record toewijzen**|U kunt de record toewijzen waarop de werkstroom wordt uitgevoerd, een record die aan deze record is gekoppeld met een N:1-relatie of een record die in eerdere stappen is gemaakt.|  
|**E-mail verzenden**|Hiermee verstuurt u een e-mail. U kunt een nieuw e-mailbericht maken of een e-mailsjabloon gebruiken die is geconfigureerd voor de entiteit van de record waarop de werkstroom wordt uitgevoerd, een entiteit met een N:1-relatie met die entiteit of de entiteit voor een record die in eerdere stappen is gemaakt.|  
|**Onderliggende werkstroom starten**|Hiermee start u een werkstroomproces dat is geconfigureerd als een onderliggende werkstroom.|  
|**Status wijzigen**|Hiermee wijzigt u de status van de record waarop de werkstroom wordt uitgevoerd, een record die aan deze record is gekoppeld met een N:1-relatie of een record die in eerdere stappen is gemaakt.|  
|**Werkstroom stoppen**|Hiermee stopt u de huidige werkstroom. U kunt de status instellen op **Succeeded** of **Cancelled** en een statusbericht opgeven.<br /><br /> Als er realtime-werkstromen zijn geconfigureerd voor een gebeurtenis en een werkstroom wordt gestopt met de status Canceled, kan de actie van de gebeurtenis niet worden voltooid. Zie [Using real-time workflows](configure-workflow-steps.md#BKMK_SynchronousWorkflows) (Realtime-werkstromen gebruiken) voor meer informatie.|  
|**Aangepaste stap**|Ontwikkelaars kunnen aangepaste werkstroomstappen maken die acties definiëren. Er zijn standaard geen aangepaste stappen beschikbaar.|  
  
### <a name="setting-record-values"></a>Recordwaarden instellen  

 Wanneer u een record maakt, kunt u waarden instellen voor de record. Als u een record bijwerkt, kunt u waarden instellen, toevoegen, verhogen, verlagen, vermenigvuldigen of wissen.  
  
 Wanneer u **Eigenschappen instellen** selecteert, wordt er een dialoogvenster geopend met het standaardformulier voor de entiteit.  
  
 Onderaan het dialoogvenster ziet u een lijst met aanvullende velden die niet aanwezig zijn in het formulier.  
  
 Voor elk veld kunt u een statische waarde instellen en die wordt dan ingesteld door de werkstroom.  
  
 Aan de rechterkant van het dialoogvenster kunt de **Formulierassistent** gebruiken om dynamische waarden in te stellen of toe te voegen vanuit de context van de huidige record. Dit betreft ook waarden uit verwante records die toegankelijk zijn vanuit de N:1-relaties (veel-op-een) voor de entiteit.  
  
 De beschikbare opties in de **Formulierassistent** zijn afhankelijk van het veld dat u hebt geselecteerd in het formulier. Wanneer u een dynamische waarde instelt, ziet u een gele tijdelijke aanduiding die aangeeft waar de dynamische gegevens worden weergegeven. Als u de waarde wilt verwijderen, selecteert u de tijdelijke aanduiding en verwijdert u deze. Voor tekstvelden kunt u een combinatie van statische en dynamische gegevens gebruiken.  
  
 Met dynamische waarden weet u nooit zeker of een veld of gerelateerde entiteit de waarde bevat die u wilt instellen. U kunt zelfs een aantal velden instellen om de waarde uit te proberen en deze velden sorteren met behulp van de groene pijlen. Als het eerste veld geen gegevens bevat, wordt het tweede veld geprobeerd, enzovoort. Als geen van de velden gegevens bevat, kunt u opgeven dat er een standaardwaarde moet worden gebruikt.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Voorwaarden instellen voor werkstroomacties  

 De acties die u wilt toepassen, zijn vaak afhankelijk van voorwaarden. Werkstroomprocessen bieden verschillende manieren om voorwaarden in te stellen en vertakkingslogica te maken voor het ophalen van de gewenste resultaten. U kunt waarden controleren van de record waarop het werkstroomproces wordt uitgevoerd, van een record die aan deze record is gekoppeld met een N:1-relatie of waarden binnen het proces zelf.  
  
|Type voorwaarde|Beschrijving|  
|--------------------|-----------------|  
|**Voorwaarde controleren**|Een logische 'if-\<voorwaarde>then'-instructie.<br /><br /> U kunt de huidige waarden controleren van de record waarop de werkstroom wordt uitgevoerd, van een record die aan deze record is gekoppeld in een N:1-relatie of van een record die in eerdere stappen is gemaakt. Op basis van deze waarden kunt u extra stappen definiëren wanneer aan de voorwaarde wordt voldaan.<br /><br /> In de 'if-\<condition> then'-opdracht kunt u de volgende operators gebruiken: **Equals**, **Does Not Equal**, **Contains Data**, **Does Not Contain Data**, **Under** en **Not Under**. **Opmerking**:  **Under** en **Not Under** zijn hiërarchische operatoren. Deze kunnen alleen worden gebruikt op de entiteiten waarvoor een hiërarchische relatie is gedefinieerd. Als u deze operators probeert te gebruiken op de entiteiten waarvoor geen hiërarchische relatie is gedefinieerd, ziet u het volgende foutbericht: 'U gebruikt een hiërarchische operator op een entiteit waarvoor geen hiërarchische relatie is gedefinieerd. U wordt geadviseerd om de entiteit hiërarchisch te maken (door een relatie als hiërarchisch te markeren) of een andere operator te gebruiken. Zie [Hiërarchische gegevens definiëren en opvragen](/powerapps/maker/common-data-service/define-query-hierarchical-data) voor meer informatie over hiërarchische relaties. In een schermafbeelding onder de tabel ziet u een voorbeeld van de definitie van het werkstroomproces waarin de operatoren **Under** en **Not Under** worden gebruikt.|  
|**Voorwaardelijke branche**|Een logische 'else-if-then'-instructie; in de editor wordt de tekst 'Otherwise, if \<condition> then:' gebruikt.<br /><br /> Selecteer een controlevoorwaarde die u eerder hebt gedefinieerd en u kunt een voorwaardelijke vertakking toevoegen voor het definiëren van extra stappen wanneer de controlevoorwaarde onwaar is.|  
|**Standaardactie**|Een logische 'else'-instructie. In de editor wordt de tekst 'Otherwise:' gebruikt.<br /><br /> Selecteer een controlevoorwaarde, voorwaardelijke vertakking, een wachtvoorwaarde of een parallelle wachtvertakking die u eerder hebt gedefinieerd en u kunt een standaardactie gebruiken voor het definiëren van stappen voor alle gevallen die niet voldoen aan de criteria die zijn gedefinieerd in voorwaarde- of vertakkingselementen.|  
|**Wachtvoorwaarde**|Hiermee kunt u een achtergrondwerkstroom zichzelf laten onderbreken totdat is voldaan aan de criteria die zijn gedefinieerd door de voorwaarde. De werkstroom wordt verder uitgevoerd zodra aan de criteria in de wachtvoorwaarde is voldaan.<br /><br /> U kunt geen wachtvoorwaarden gebruiken in realtime-werkstromen.|  
|**Parallelle wachtbranche**|Hiermee definieert u een alternatieve wachtvoorwaarde voor een achtergrondwerkstroom met een bijbehorende set extra stappen die alleen worden uitgevoerd als aan het eerste criterium wordt voldaan. U kunt parallelle wachtvertakkingen gebruiken om tijdslimieten in te bouwen in uw werkstroomlogica. U voorkomt zo dat de werkstroom oneindig lang blijft wachten totdat is voldaan aan de criteria die zijn gedefinieerd in een wachtvoorwaarde.|  
|**Aangepaste stap**|Ontwikkelaars kunnen aangepaste werkstroomstappen maken die voorwaarden definiëren. Er zijn standaard geen aangepaste stappen beschikbaar.|  
  
 In de volgende schermafbeelding ziet u een voorbeeld van de definitie van het werkstroomproces waarin de hiërarchische operatoren **Under** en **Not Under** worden gebruikt. In ons voorbeeld passen we twee verschillende kortingen toe op twee groepen accounts. Bij **Stap toevoegen** hebben we **Voorwaarde controleren** geselecteerd om de **if-then**-voorwaarde met de operator **Under** of **Not Under** op te geven. De eerste **if-then**-voorwaarde is van toepassing op alle accounts die zich onder (**Under**) het account Alpine Ski House bevinden. Deze accounts krijgen een korting van 10% op gekochte goederen en diensten. De tweede **if-then**-voorwaarde is van toepassing op alle accounts die zich niet onder (**Not Under**) het account Alpine Ski House bevinden en deze krijgen een korting van 5%. Vervolgens hebben we **Record bijwerken** geselecteerd om de actie te definiëren die op basis van de voorwaarde moet worden uitgevoerd.  
  
 ![Werkstroomproces met de operatoren Under&#47;Not Under](media/wfp-under-not-under.PNG "Werkstroomproces met de operatoren Under/Not Under")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Realtime-werkstromen gebruiken  

 U kunt realtime-werkstromen configureren, maar u moet hierbij wel zorgvuldig te werk gaan. Over het algemeen worden achtergrondwerkstromen aanbevolen omdat deze als resources kunnen worden toegepast op de server indien beschikbaar. Dit helpt om het werk van de server te verdelen en zo de beste prestaties te handhaven voor iedereen die het systeem gebruikt. Het nadeel is dat acties die zijn gedefinieerd in achtergrondwerkstromen niet direct worden uitgevoerd. U kunt niet voorspellen wanneer ze worden toegepast, maar meestal duurt dit een paar minuten. Bij de automatisering van bedrijfsprocessen is dit meestal geen probleem omdat gebruikers van het systeem niet hoeven te weten wanneer het proces precies wordt uitgevoerd.  
  
 Gebruik realtime-werkstromen wanneer een bedrijfsproces vereist dat iemand direct de resultaten van het proces kan controleren of als u de mogelijkheid wilt hebben om een bewerking te annuleren. Dit is bijvoorbeeld handig als u bepaalde standaardwaarden wilt instellen voor een record wanneer deze de eerste keer wordt opgeslagen of als u er zeker van wilt zijn dat bepaalde records niet worden verwijderd.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Realtime-werkstromen converteren naar achtergrondwerkstromen en omgekeerd  

 U kunt een realtime-werkstroom wijzigen in een achtergrondwerkstroom door **Converteren naar een achtergrondwerkstroom** te kiezen op de werkbalk.  
  
 U kunt een achtergrondwerkstroom weer wijzigen in een realtime-werkstroom door **Converteren naar een realtime-werkstroom** te kiezen op de werkbalk. Als in de achtergrondwerkstroom een wachtvoorwaarde wordt gebruikt, wordt de werkstroom ongeldig en kunt u deze pas weer activeren nadat u de wachtvoorwaarde hebt verwijderd.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Realtime-werkstromen starten voor of na statuswijzigingen  

 Wanneer u bij **Opties voor automatische processen** opties configureert voor realtime-werkstromen, kunt u bij **Starten wanneer** de optie **Na** of **Voor** selecteren voor de gebeurtenis Statuswijzigingen. De standaardoptie is **Na**.  
  
 Wanneer u **Voor** selecteert, geeft u aan dat de logica in de werkstroom moet worden toegepast voordat gegevens worden opgeslagen die de status veranderen. Dit biedt u de mogelijkheid om de waarden te controleren voordat andere logica wordt toegepast na de bewerking en te voorkomen dat verdere logica wordt uitgevoerd. Stel dat u aanvullende logica hebt in een invoegtoepassing of aangepaste werkstroomactie die acties op een ander systeem kan starten. Door verdere verwerking te stoppen, kunt u situaties voorkomen waarin externe systemen worden beïnvloed. Het toepassen van realtime werkstromen voor deze gebeurtenis betekent ook dat andere acties van een werkstroom of invoegtoepassing die mogelijk gegevens hebben opgeslagen, niet hoeven te worden 'teruggedraaid' wanneer de bewerking wordt geannuleerd.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>De actie 'Werkstroom stoppen' gebruiken met realtime-werkstromen  

 Wanneer u een actie **Werkstroom stoppen** toepast in een werkstroom, hebt u de mogelijkheid om een statusvoorwaarde op te geven die **Succeeded** of **Canceled** kan zijn. Als u de status instelt op Canceled, voorkomt u de bewerking. Er wordt dan een foutbericht weergegeven aan de gebruiker met de kop **Fout in bedrijfsproces**.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Aangepaste bedrijfslogica maken met processen](guide-staff-through-common-tasks-processes.md)   
 [Overzicht van werkstroomprocessen](workflow-processes.md)   
 [Werkstroomprocessen controleren en beheren](monitor-manage-processes.md)   
 [Aanbevolen procedures voor werkstroomprocessen](best-practices-workflow-processes.md)
