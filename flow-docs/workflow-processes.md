---
title: Klassieke Common Data Service-werk stromen | MicrosoftDocs
ms.custom: ''
ms.date: 08/27/2019
ms.reviewer: matp
ms.service: flow
ms.topic: article
ms.assetid: 1f3c9780-26ad-49ec-a3fb-fc226def19c5
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 42ac7bd75268010a8d7e2bf88a600621504dda39
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548341"
---
# <a name="classic-common-data-service-workflows"></a>Klassieke Common Data Service-werk stromen 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Werk stromen automatiseren bedrijfs processen zonder gebruikers interface. Personen gebruiken meestal werk stroom processen om Automation te initiëren waarvoor geen interactie van de gebruiker is vereist.

> [!IMPORTANT]
> Gebruik stromen in plaats van klassieke werk stromen om uw bedrijfs processen te automatiseren. Meer informatie: [klassieke common data service-werk stromen vervangen door stromen](replace-workflows-with-flows.md)  
  
 Elk werk stroom proces is gekoppeld aan één entiteit. Bij het configureren van werk stromen moet u rekening houden met vier belang rijke gebieden:  
  
-   Wanneer moet u deze starten?  
  
-   Moeten ze worden uitgevoerd als een real-time werk stroom of een werk stroom op de achtergrond?  
  
-   Welke acties moet er worden uitgevoerd?  
  
-   Onder welke voor waarden moeten acties worden uitgevoerd?  
  
 In dit onderwerp wordt beschreven hoe u werk stroom processen kunt vinden en hoe u deze kunt starten en of ze als realtime of achtergrond moeten worden uitgevoerd. Zie [werk stroom processen configureren](configure-workflow-steps.md)voor meer informatie over de acties die ze moeten uitvoeren en de voor waarden.  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Waar kunt u werk stroom processen aanpassen?  
 U kunt de werk stromen in uw organisatie zien door het knoop punt **processen** te bekijken in de **standaard oplossing** en te filteren op processen met de **werk stroom** **categorie** .  
  
 ![Processen gefilterd op werk stroom in Dynamics 365](media/workflow-processes-filtered.PNG "Processen gefilterd op werk stroom in Dynamics 365")  
  
 Afhankelijk van hoe de app is gebouwd, kunnen gebruikers hun werk stromen in de app maken of wijzigen. 
 
Ontwikkel aars kunnen werk stromen maken met behulp van informatie in de [common data service ontwikkelaars gids](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions) en oplossingen die u aanschaft, werk stromen kunnen bevatten die u kunt wijzigen.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Eigenschappen van werk stroom  
 Selecteer in de Solution Explorer **processen** en klik op **Nieuw**.  
  
 Wanneer u in het dialoog venster **proces maken** een werk stroom maakt, moet u drie eigenschappen instellen die alle processen hebben:  
  
 ![Een werk stroom maken in Dynamics 365](media/create-workflow.PNG "Een werk stroom maken in Dynamics 365")  
  
 **Proces naam**  
 De naam van het werk stroom proces hoeft niet uniek te zijn, maar als u verwacht dat u veel werk stromen hebt, wilt u mogelijk een naamgevings Conventie gebruiken om uw processen duidelijk te onderscheiden. Mogelijk wilt u standaard voorvoegsels Toep assen op de naam van de werk stroom. Het voor voegsel kan de functie van de werk stroom of de afdeling binnen het bedrijf beschrijven. Dit helpt u bij het groeperen van vergelijk bare items in de lijst met werk stromen.  
  
 **Rubriek**  
 Deze eigenschap bepaalt dat dit een werk stroom proces is.  
  
 **Vennootschap**  
 Elk werk stroom proces moet worden ingesteld op één entiteit. U kunt de entiteit niet wijzigen nadat het werk stroom proces is gemaakt.  
  
 **Deze werk stroom op de achtergrond uitvoeren (aanbevolen)**  
 Deze optie wordt weer gegeven wanneer u werk stroom als categorie selecteert. Met deze instelling wordt bepaald of de werk stroom in realtime of op een achtergrond werk stroom is. Realtime werk stromen worden direct uitgevoerd (synchroon) en werk stromen die op de achtergrond asynchroon worden uitgevoerd. Welke configuratie opties er beschikbaar zijn, is afhankelijk van uw keuze voor deze instelling. Met achtergrond werk stromen kunnen wacht voorwaarden worden opgegeven die niet beschikbaar zijn voor realtime werk stromen. Als u deze voor waarden niet gebruikt, kunt u op een later tijdstip achtergrond werk stromen omzetten in realtime werk stromen en realtime werk stromen naar achtergrond werk stromen. Zie voor [waarden instellen voor werk stroom acties](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions)voor meer informatie over wachtende voor waarden.  
  
 U hebt ook de optie **type** om op te geven of u een nieuwe werk stroom wilt maken of dat u wilt beginnen met een bestaande sjabloon. Wanneer u **nieuw proces kiest op basis van een bestaande sjabloon (selecteren in de lijst),** kunt u kiezen uit de beschik bare werk stroom processen die eerder als een proces sjabloon zijn opgeslagen.  
  
 Nadat u de werk stroom hebt gemaakt of als u een bestaand item bewerkt, hebt u de volgende aanvullende eigenschappen:  
  
 ![Tabblad Algemeen in een werk stroom](media/create-workflow-general-tab.PNG "Tabblad Algemeen in een werk stroom")  
  
 **Activeren als**  
 U kunt **proces sjabloon** kiezen om een geavanceerd uitgangs punt voor andere sjablonen te maken. Als u deze optie kiest, wordt de werk stroom pas toegepast nadat u deze hebt geactiveerd, maar in plaats daarvan beschikbaar is in het dialoog venster **proces maken** als u **type**: **nieuw proces van een bestaande sjabloon selecteert (Selecteer in de lijst)**  
  
 Proces sjablonen zijn handig wanneer u een aantal vergelijk bare werk stroom processen hebt en deze wilt definiëren zonder dezelfde logica te dupliceren.  
  
> [!NOTE]
>  Het bewerken van een proces sjabloon heeft geen invloed op het gedrag van andere werk stroom processen die eerder zijn gemaakt als sjabloon. Een nieuwe werk stroom die is gemaakt met behulp van een sjabloon, is een kopie van de inhoud in de sjabloon.  
  
 **Beschikbaar voor uitvoering**  
 Deze sectie bevat opties die beschrijven hoe de werk stroom beschikbaar moet worden uitgevoerd.  
  
 **Deze werk stroom op de achtergrond uitvoeren (aanbevolen)**  
 Dit selectie vakje weerspiegelt de optie die u hebt geselecteerd tijdens het maken van de werk stroom. Deze optie is uitgeschakeld, maar u kunt deze wijzigen in het menu **acties** door ofwel **converteren naar een realtime werk stroom** te kiezen of **converteren naar een werk stroom op de achtergrond**.  
  
 **Als een proces op aanvraag**  
 Kies deze optie als u wilt toestaan dat gebruikers deze werk stroom uitvoeren via de opdracht **werk stroom uitvoeren** .  
  
 **Als onderliggend proces**  
 Kies deze optie als u wilt toestaan dat de werk stroom beschikbaar is om te worden gestart vanuit een andere werk stroom.  
  
 **Bewaren van werk stroom taken**  
 Deze sectie bevat een optie voor het verwijderen van een werk stroom nadat de uitvoering van de werk stroom is voltooid.  
  
 **Voltooide werk stroom taken automatisch verwijderen (om schijf ruimte te besparen)**  
 Kies deze optie als u wilt dat een voltooide werk stroom taak automatisch wordt verwijderd.  
  
> [!NOTE]
>  De werk stroom taken worden niet onmiddellijk verwijderd na voltooiing, maar na een batch proces.  
  
 **Ligt**  
 Voor entiteiten die eigendom zijn van een gebruiker, zijn de opties **organisatie**, **bovenliggend item: onderliggende Business Units**, **bedrijfs eenheid**of **gebruiker**. Voor entiteiten die eigendom zijn van een organisatie is de enige optie **organisatie**.  
  
 Als de scope **organisatie**is, kan de werk stroom logica worden toegepast op elke record in de organisatie. Anders kan de werk stroom alleen worden toegepast op een subset records die binnen het bereik vallen.  
  
> [!NOTE]
>  De standaard waarde voor het bereik is **gebruiker**. Zorg ervoor dat u controleert of de bereik waarde juist is voordat u de werk stroom activeert.  
  
 **Starten wanneer**  
 Gebruik de opties in dit gedeelte om op te geven wanneer een werk stroom automatisch moet worden gestart. U kunt een real-time werk stroom zo configureren dat deze wordt uitgevoerd vóór bepaalde gebeurtenissen. Dit is een zeer krachtige functie, omdat de werk stroom de actie kan stoppen voordat deze wordt uitgevoerd. Meer informatie: het [gebruik van real-time werk stromen](configure-workflow-steps.md#BKMK_SynchronousWorkflows). De opties zijn:  
  
- **Record wordt gemaakt**  
  
- **Record status wijzigingen**  
  
- **Record wordt toegewezen**  
  
- **Record velden wijzigen**  
  
- **Record is verwijderd**  
  
> [!NOTE]
>  Houd er rekening mee dat de acties en voor waarden die u voor de werk stroom definieert, niet weten wanneer de werk stroom wordt uitgevoerd. Als u bijvoorbeeld een werk stroom definieert om de record bij te werken, kan deze actie niet worden uitgevoerd door een realtime werk stroom voordat de record wordt gemaakt. Een record die niet bestaat, kan niet worden bijgewerkt. Op dezelfde manier kan een record die is verwijderd door een werk stroom op de achtergrond niet worden bijgewerkt, ook al kunt u deze actie voor de werk stroom definiëren. Als u een werk stroom configureert om een actie uit te voeren die niet kan worden uitgevoerd, mislukt dit en wordt de hele werk stroom mislukt.  
  
 **Uitvoeren als**  
 Deze optie is alleen beschikbaar als u de optie **deze werk stroom uitvoeren op de achtergrond (aanbevolen)** hebt uitgeschakeld tijdens het maken van de werk stroom of als u later een werk stroom op de achtergrond hebt geconverteerd om een realtime werk stroom te zijn.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Beveiligings context van werk stroom processen  
 Wanneer een werk stroom op de achtergrond is geconfigureerd als een on-demand proces en door een gebruiker wordt gestart met de opdracht **werk stroom uitvoeren** , zijn de acties die de werk stroom kan uitvoeren beperkt tot die welke de gebruiker kan uitvoeren op basis van de bevoegdheden en toegangs niveaus die zijn gedefinieerd door de beveiligingsrol (s) die zijn ingesteld voor hun gebruikers account.  
  
 Wanneer een werk stroom op de achtergrond wordt gestart op basis van een gebeurtenis, werkt de werk stroom in de context van de persoon die de werk stroom heeft gemaakt.  
  
 Voor realtime werk stromen hebt u de optie **uitvoeren als** en kunt u kiezen of de werk stroom de beveiligings context moet Toep assen van de eigenaar van de werk stroom of de gebruiker die wijzigingen heeft aangebracht in de record. Als uw werk stroom acties bevat die alle gebruikers niet kunnen uitvoeren op basis van beveiligings beperkingen, moet u ervoor kiezen om de werk stroom uit te voeren als de eigenaar van de werk stroom.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Een werk stroom activeren  
 Werk stromen kunnen alleen worden bewerkt wanneer ze worden gedeactiveerd. Vóór een werk stroom kan hand matig worden gebruikt of worden toegepast als gevolg van gebeurtenissen die moeten worden geactiveerd. Voordat een werk stroom kan worden geactiveerd, moet deze ten minste één stap bevatten. Zie [werk stroom processen configureren](configure-workflow-steps.md) voor meer informatie over het configureren van stappen.  
  
 Een werk stroom kan alleen worden geactiveerd of gedeactiveerd door de eigenaar van de werk stroom of door iemand die namens **een andere gebruikers** bevoegdheid heeft, zoals de systeem beheerder.  De reden hiervoor is dat een kwaadwillende gebruiker de werk stroom van iemand kan wijzigen zonder dat ze op de hoogte zijn van de wijziging. U kunt een werk stroom die u bezit opnieuw toewijzen door de eigenaar te wijzigen. Dit veld bevindt zich op het tabblad **beheer** . Als u niet de systeem beheerder bent en u een werk stroom wilt bewerken die eigendom is van een andere gebruiker, moet u deze eerst deactiveren en toewijzen aan u. Nadat u klaar bent met het bewerken van de werk stroom, kunt u deze weer toewijzen zodat deze kan worden geactiveerd.  
  
 Voor realtime-werk stromen moet de gebruiker de bevoegdheid **realtime-processen activeren** hebben. Omdat realtime werk stromen een grotere kans hebben om de systeem prestaties te beïnvloeden, moeten alleen mensen die het potentiële risico kunnen evalueren, deze bevoegdheid krijgen.  
  
 Werk stromen worden opgeslagen wanneer ze zijn geactiveerd. het is dus niet nodig ze op te slaan voordat ze worden geactiveerd.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Werk stroom processen configureren](configure-workflow-steps.md)  <br/>
[Een werk stroom op aanvraag toevoegen aan een bedrijfs proces stroom](bpf-add-on-demand-workflow.md) 

