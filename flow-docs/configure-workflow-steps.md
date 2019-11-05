---
title: Werk stroom stadiums en stappen configureren in PowerApps | MicrosoftDocs
description: Meer informatie over het configureren van werk stroom stappen
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
ms.openlocfilehash: 4239e939f9522b4b3a22e56dfc69275482b017a7
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547077"
---
# <a name="configure-workflow-stages-and-steps"></a>Werk stroom stadiums en stappen configureren
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Wanneer u werk stromen ontwerpt, hebt u de mogelijkheid om de logica te bevatten die u wilt uitvoeren in fasen en stappen.  
  
 **Handels**  
 Met fasen wordt de werk stroom logica eenvoudiger te lezen en wordt de werk stroom logica uitgelegd. De fasen hebben echter geen invloed op de logica of het gedrag van werk stromen. Als een proces fasen heeft, moeten alle stappen binnen het proces deel uitmaken van een fase.  
  
 **Stappen**  
 Stappen zijn een eenheid van bedrijfs logica binnen een werk stroom. De stappen kunnen voor waarden, acties, andere stappen of een combi natie van deze elementen bevatten.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Acties die werk stroom processen kunnen uitvoeren  

 Werk stroom processen kunnen de acties uitvoeren die worden vermeld in de volgende tabel.  
  
|Optreden|Beschrijvingen|  
|------------|-----------------|  
|**Record maken**|Hiermee maakt u een nieuwe record voor een entiteit en wijst u waarden toe die u hebt gekozen voor kenmerken.|  
|**Record bijwerken**|U kunt de record waarop de werk stroom wordt uitgevoerd, bijwerken naar een van de records die zijn gekoppeld aan deze record in een N:1-relatie, of records die zijn gemaakt door eerdere stappen.|  
|**Record toewijzen**|U kunt de record waarop de werk stroom wordt uitgevoerd, toewijzen aan een van de records die zijn gekoppeld aan deze record met een N:1-relatie, of records die zijn gemaakt door eerdere stappen.|  
|**E-mail verzenden**|Hiermee verzendt u een e-mail bericht. U kunt ervoor kiezen om een nieuw e-mail bericht te maken of een e-mail sjabloon te gebruiken die is geconfigureerd voor de entiteit van de record waarop de werk stroom wordt uitgevoerd, of entiteiten die een N:1-relatie hebben met de entiteit, of de entiteit voor records die door eerdere stappen zijn gemaakt.|  
|**Onderliggend werk stroom starten**|Start een werk stroom proces dat is geconfigureerd als een onderliggende werk stroom.|  
|**Status wijzigen**|Wijzigt de status van de record waarop het proces wordt uitgevoerd, een van de records die aan deze record zijn gekoppeld met een N:1-relatie of records die zijn gemaakt door eerdere stappen.|  
|**Werk stroom stoppen**|Hiermee wordt de huidige werk stroom gestopt. U kunt de status **geslaagd** of **geannuleerd** instellen en een status bericht opgeven.<br /><br /> Wanneer realtime-werk stromen voor een gebeurtenis worden geconfigureerd, voor komt u dat de gebeurtenis actie wordt voltooid wanneer een werk stroom met de status geannuleerd wordt gestopt. Zie [realtime werk stromen gebruiken](configure-workflow-steps.md#BKMK_SynchronousWorkflows) voor meer informatie.|  
|**Aangepaste stap**|Ontwikkel aars kunnen aangepaste werk stroom stappen maken waarmee acties worden gedefinieerd. Er zijn standaard geen aangepaste stappen beschikbaar.|  
  
### <a name="setting-record-values"></a>Record waarden instellen  

 Wanneer u een record maakt, kunt u waarden voor de record instellen. Wanneer u een record bijwerkt, kunt u waarden instellen, toevoegen, verhogen, verkleinen, vermenigvuldigen of wissen.  
  
 Wanneer u **Eigenschappen instellen**selecteert, wordt er een dialoog venster geopend met het standaard formulier voor de entiteit.  
  
 Onder in het dialoog venster ziet u een lijst met aanvullende velden die niet aanwezig zijn in het formulier.  
  
 Voor elk veld kunt u een statische waarde instellen en die wordt ingesteld door de werk stroom.  
  
 Aan de rechter kant van het dialoog venster **biedt de Formulierenassistent u** de mogelijkheid om dynamische waarden in te stellen of toe te voegen aan de context van de huidige record. Dit omvat waarden van gerelateerde records die kunnen worden geopend vanuit de N:1-relaties (veel-op-één) voor de entiteit.  
  
 De beschik bare opties in de **Formulierenassistent** zijn afhankelijk van het veld dat u hebt geselecteerd in het formulier. Wanneer u een dynamische waarde instelt, ziet u een gele tijdelijke aanduiding die ook wel ' witruimte ' wordt genoemd. deze geeft aan waar de dynamische gegevens worden opgenomen. Als u de waarde wilt verwijderen, selecteert u de witruimte en verwijdert u deze. Voor tekst velden kunt u een combi natie van statische en dynamische gegevens gebruiken.  
  
 Met dynamische waarden weet u niet zeker dat een veld of gerelateerde entiteit de waarde heeft die u wilt instellen. U kunt in feite een aantal velden instellen om te proberen, de waarde in te stellen en deze in volg orde te sorteren met de groene pijlen. Als het eerste veld geen gegevens bevat, wordt het tweede veld geprobeerd, enzovoort. Als geen van de velden gegevens bevat, kunt u een standaard waarde opgeven die moet worden gebruikt.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Voor waarden voor werk stroom acties instellen  

 De acties die u vaak toepast, zijn afhankelijk van de voor waarden. Werk stroom processen bieden verschillende manieren om voor waarden in te stellen en vertakkings logica te maken om de gewenste resultaten te krijgen. U kunt de waarden controleren van de record waarmee het werk stroom proces wordt uitgevoerd, een van de records die zijn gekoppeld aan deze record met een N:1-relatie of waarden binnen het proces zelf  
  
|Voorwaarde type|Beschrijvingen|  
|--------------------|-----------------|  
|**Controle voorwaarde**|Een logische ' If-\<condition >-instructie.<br /><br /> U kunt de huidige waarden controleren voor de record waarop de werk stroom wordt uitgevoerd, een van de records die zijn gekoppeld aan deze record in een N:1-relatie of records die zijn gemaakt door eerdere stappen. Op basis van deze waarden kunt u extra stappen definiëren wanneer de voor waarde waar is.<br /><br /> In de ' If-\<-voor waarde > '-instructie kunt u de volgende opera toren gebruiken: **is gelijk**aan, is **niet gelijk aan** **gegevens**, bevat **geen gegevens** **onder** en **niet onder**. **Opmerking:**  De **onder** en **niet onder** zijn hiërarchische Opera tors. Ze kunnen alleen worden gebruikt voor entiteiten waarvoor een hiërarchische relatie is gedefinieerd. Als u deze opera tors wilt gebruiken op de entiteiten waarvoor geen hiërarchische relatie is gedefinieerd, wordt het volgende fout bericht weer gegeven: ' u gebruikt een hiërarchische operator voor een entiteit waarvoor geen hiërarchische relatie is gedefinieerd. Maak de entiteit hiërarchisch (door een relatie als hiërarchisch te markeren) of gebruik een andere operator. " Zie [hiërarchisch gerelateerde gegevens definiëren en query's uitvoeren](/powerapps/maker/common-data-service/define-query-hierarchical-data)voor meer informatie over hiërarchische relaties. Een scherm opname die volgt op de tabel is een voor beeld van de definitie van het werk stroom proces dat gebruikmaakt van de **onder** en **niet onder** hiërarchische Opera tors.|  
|**Voorwaardelijke vertakking**|Een logische ' Else-If-then '-instructie, de editor gebruikt de tekst ' anders als \<voor waarde > dan: '<br /><br /> Selecteer een voor waarde die u eerder hebt gedefinieerd en u kunt een voorwaardelijke tak toevoegen om extra stappen te definiëren wanneer de check-voor waarde ONWAAR retourneert.|  
|**Standaard actie**|Een logische else-instructie. de editor gebruikt de tekst "anderszins:"<br /><br /> Selecteer een controle voorwaarde, voorwaardelijke vertakking, wacht voorwaarde of parallelle wait-vertakking die u eerder hebt gedefinieerd. u kunt een standaard actie gebruiken om de stappen te definiëren voor alle cases die niet overeenkomen met de criteria die zijn gedefinieerd in voor waarde of vertakkings elementen.|  
|**Wacht voorwaarde**|Hiermee kan een werk stroom op de achtergrond zichzelf onderbreken totdat aan de criteria die zijn gedefinieerd door de voor waarde is voldaan. De werk stroom wordt automatisch opnieuw gestart wanneer aan de criteria in de wacht voorwaarde is voldaan.<br /><br /> Realtime werk stromen kunnen geen wacht voorwaarden gebruiken.|  
|**Parallelle wait-vertakking**|Definieert een alternatieve wacht tijd voor een werk stroom op de achtergrond met een bijbehorende set extra stappen die alleen worden uitgevoerd wanneer aan het eerste criterium wordt voldaan. U kunt parallelle wachtende vertakkingen gebruiken om tijds limieten in uw werk stroom logica te maken. Ze helpen te voor komen dat de werk stroom oneindig wacht totdat aan de criteria die zijn gedefinieerd in een wacht voorwaarde is voldaan.|  
|**Aangepaste stap**|Ontwikkel aars kunnen aangepaste werk stroom stappen maken waarmee voor waarden worden gedefinieerd. Er zijn standaard geen aangepaste stappen beschikbaar.|  
  
 De volgende scherm afbeelding bevat een voor beeld van de definitie van het werk stroom proces met de **onder** en **niet onder** hiërarchische Opera tors. In ons voor beeld hebben we twee verschillende kortingen toegepast op twee groepen accounts. In **stap toevoegen**hebben we de **controle voorwaarde** geselecteerd om de **If-then-** voor waarde op te geven met de Opera tors **onder** of **niet onder** . De eerste **als-then-** voor waarde is van toepassing op alle accounts die **onder** het account Alpine Ski House vallen. Deze accounts ontvangen een korting van 10% op gekochte goede en services. De tweede **als-then-** voor waarde is van toepassing op alle accounts die zich **niet onder** de Alpine Ski House-account bevinden en een korting van 5% krijgen. Vervolgens hebt u een **Update record** geselecteerd om de actie te definiëren die moet worden uitgevoerd op basis van de voor waarde.  
  
 ![Werk stroom proces met&#47;onder andere opera tors](media/wfp-under-not-under.PNG "Werk stroom proces met onder/niet onder Opera tors")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Realtime werk stromen gebruiken  

 U kunt real-time werk stromen configureren, maar u moet deze gebruiken. Achtergrond werk stromen worden meestal aanbevolen omdat ze toestaan dat het systeem ze toepast als resources op de server beschikbaar zijn. Zo kunt u het werk dat de server moet doen vloeiend maken en helpt u de beste prestaties te behouden voor iedereen die het systeem gebruikt. Het nadeel is dat acties die zijn gedefinieerd door de achtergrond werk stromen niet direct zijn. Het is niet mogelijk om te voors pellen wanneer ze worden toegepast, maar over het algemeen duurt het enkele minuten. Voor de meeste automatisering van bedrijfs processen is dit prima, omdat gebruikers die het systeem gebruiken niet bewust hoeven te zijn dat het proces wordt uitgevoerd.  
  
 Gebruik realtime werk stromen wanneer iemand een bedrijfs proces nodig heeft om onmiddellijk de resultaten van het proces te zien of als u de mogelijkheid wilt hebben om een bewerking te annuleren. U kunt bijvoorbeeld bepaalde standaard waarden instellen voor een record wanneer deze voor de eerste keer worden opgeslagen of u ervoor wilt zorgen dat sommige records niet worden verwijderd.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Conversie tussen realtime-en achtergrond werk stromen  

 U kunt een real-time werk stroom wijzigen in een werk stroom op de achtergrond door te klikken op **converteren naar een achtergrond werk stroom** op de werk balk.  
  
 U kunt een werk stroom op de achtergrond wijzigen in een realtime-werk stroom door **omzetten naar een real-time werk stroom** op de werk balk te kiezen. Als de werk stroom voor de achtergrond een wacht tijd gebruikt, wordt deze ongeldig en kunt u deze niet activeren totdat u de wacht voorwaarde verwijdert.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Het initiëren van real-time werk stromen vóór of na status wijzigingen  

 Wanneer u **Opties voor automatische processen** voor realtime-werk stromen configureert, kunt u met de optie **starten als** opties voor de status wijzigings gebeurtenis selecteren **na** of **vóór** wanneer de status wordt gewijzigd. De standaard optie is **na**.  
  
 Wanneer u **ervoor** kiest om u te laten zien dat de logica in de werk stroom moet worden toegepast voordat gegevens die de status wijzigen, worden opgeslagen. Dit biedt u de mogelijkheid om de waarden te controleren voordat er een andere logica is toegepast na de bewerking en te voor komen dat verdere logica wordt uitgevoerd. U kunt bijvoorbeeld aanvullende logica in een invoeg toepassing of aangepaste werk stroom actie hebben die acties op een ander systeem kan initiëren. Door verdere verwerking te stoppen, kunt u gevallen voor komen waarbij externe systemen worden beïnvloed. Het Toep assen van realtime werk stromen vóór deze gebeurtenis houdt ook in dat andere werk stroom-of invoeg toepassingen die mogelijk opgeslagen gegevens bevatten, niet opnieuw moeten worden teruggedraaid wanneer de bewerking wordt geannuleerd.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>De actie werk stroom stoppen met realtime werk stromen gebruiken  

 Wanneer u een actie voor het stoppen van de **werk stroom** in een werk stroom toepast, hebt u de optie om een status voorwaarde op te geven die ofwel **geslaagd** of **geannuleerd**kan zijn. Wanneer u de status instelt op geannuleerd, voor komt u dat de bewerking wordt uitgevoerd. Er wordt een fout bericht weer gegeven met de tekst van het status bericht voor het stoppen van de actie voor de **zakelijke proces fout**.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Aangepaste bedrijfs logica maken met processen](guide-staff-through-common-tasks-processes.md)   
 [Overzicht van werk stroom processen](workflow-processes.md)   
 [Werk stroom processen bewaken en beheren](monitor-manage-processes.md)   
 [Aanbevolen procedures voor werk stroom processen](best-practices-workflow-processes.md)
