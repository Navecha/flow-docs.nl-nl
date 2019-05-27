---
title: Klassieke Common Data Service-werkstromen | MicrosoftDocs
ms.custom: ''
ms.date: 08/06/2018
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
ms.openlocfilehash: b48fd51fcdf5ea85b564f7e422f72afa3f318060
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64463479"
---
# <a name="classic-common-data-service-workflows"></a>Klassieke Common Data Service-werkstromen 

Werkstromen automatiseren bedrijfsprocessen zonder gebruikersinterface. Werkstroomprocessen worden meestal gebruikt om automatisering te initiëren waarvoor geen tussenkomst van de gebruiker vereist is.  
  
 Elk werkstroomproces is gekoppeld aan één entiteit. Er zijn bij het configureren van werkstromen vier belangrijke gebieden waarmee u rekening moet houden:  
  
-   Wanneer moet u deze starten?  
  
-   Moeten deze worden uitgevoerd als realtimewerkstroom of achtergrondwerkstroom?  
  
-   Welke acties moeten deze uitvoeren?  
  
-   Onder welke voorwaarden moeten acties worden uitgevoerd?  
  
 In dit onderwerp wordt behandeld hoe u naar werkstroomprocessen kunt zoeken en wordt beschreven wanneer deze moeten worden gestart en of ze als realtime- of achtergrondwerkstroom uitgevoerd moeten worden. Zie [Werkstroomprocessen configureren](configure-workflow-steps.md) voor informatie over de acties die deze moeten uitvoeren en de voorwaarden.  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Waar past u werkstroomprocessen aan?  
 U kunt de werkstromen in uw organisatie bekijken via het knooppunt **Processen** in de **standaardoplossing**, en deze filteren op processen uit de **categorie** **Werkstroom**.  
  
 ![Processen die zijn gefilterd op werkstroom in Dynamics 365](media/workflow-processes-filtered.PNG "Processen die zijn gefilterd op werkstroom in Dynamics 365")  
  
 Afhankelijk van de samenstelling van de app kunnen gebruikers hun werkstromen in de app maken of wijzigen. 
 
Ontwikkelaars kunnen werkstromen maken met behulp van gegevens in de [Dynamics 365 Customer Engagement-handleiding voor ontwikkelaars](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-guide) en oplossingen die u koopt kunnen werkstromen bevatten die u kunt aanpassen.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Werkstroomeigenschappen  
 Selecteer in de Oplossingsverkenner **Processen** en klik op **Nieuw**.  
  
 Wanneer u een werkstroom maakt, wordt u in het dialoogvenster **Proces maken** gevraagd om drie eigenschappen in te stellen waarover alle processen beschikken:  
  
 ![Een werkstroom maken in Dynamics 365](media/create-workflow.PNG "Een werkstroom maken in Dynamics 365")  
  
 **Procesnaam**  
 De naam van het werkstroomproces hoeft niet uniek te zijn, maar als u verwacht een groot aantal werkstromen te krijgen, wordt aanbevolen om een naamconventie te gebruiken om duidelijk onderscheid te maken in uw processen. Mogelijk wilt u standaardvoorvoegsels op de naam van de werkstroom toepassen. Het voorvoegsel kan de functie van de werkstroom of de afdeling binnen het bedrijf beschrijven. Hierdoor kunt u gelijksoortige items in de lijst van werkstromen groeperen.  
  
 **Categorie**  
 Deze eigenschap bepaalt dat dit een werkstroomproces is.  
  
 **Entiteit**  
 Elk werkstroomproces moet worden ingesteld op één entiteit. U kunt de entiteit niet wijzigen nadat het werkstroomproces is gemaakt.  
  
 **Deze werkstroom op de achtergrond uitvoeren (aanbevolen)**  
 Deze optie wordt weergegeven wanneer u Werkstroom als categorie selecteert. Deze instelling bepaalt of de werkstroom een realtime- of achtergrondwerkstroom is. Realtimewerkstromen worden onmiddellijk uitgevoerd (synchroon) en achtergrondwerkstromen worden asynchroon uitgevoerd. De beschikbare configuratieopties is afhankelijk van uw keuze voor deze instelling. Achtergrondwerkstromen maken wachtvoorwaarden mogelijk die niet beschikbaar zijn voor realtimewerkstromen. Zolang u die wachtvoorwaarden niet gebruikt, kunt u op een later tijdstip achtergrondwerkstromen omzetten in realtimewerkstromen en vice versa. Zie [Voorwaarden instellen voor werkstroomacties](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions) voor meer informatie over wachtvoorwaarden.  
  
 U hebt ook de optie **Type** om op te geven of u een geheel nieuwe werkstroom wilt maken of ervoor wilt kiezen om te beginnen met een bestaande sjabloon. Als u kiest voor **Nieuw proces vanuit een bestaande sjabloon (selecteer in de lijst)**, kunt u kiezen uit de beschikbare werkstroomprocessen die eerder als sjabloon zijn opgeslagen.  
  
 Wanneer u de werkstroom maakt, of als u een bestaande bewerkt, beschikt u de volgende aanvullende eigenschappen:  
  
 ![Tabblad Algemeen in een werkstroom](media/create-workflow-general-tab.PNG "Tabblad Algemeen in een werkstroom")  
  
 **Activeren als**  
 U kunt kiezen voor **Processjabloon** om een geavanceerd startpunt te maken voor andere sjablonen. Als u deze optie kiest na activering van de werkstroom, wordt deze niet toegepast. De optie kan wel worden geselecteerd in het dialoogvenster **Proces maken** als u het volgende selecteert: **Type**: **Nieuw proces van een bestaande sjabloon (selecteer in de lijst)**  
  
 Processjablonen zijn handig wanneer u een aantal soortgelijke werkstroomprocessen hebt en deze zonder dezelfde logica te dupliceren wilt definiëren.  
  
> [!NOTE]
>  Het bewerken van een processjabloon verandert niet het gedrag van andere werkstroomprocessen die eerder met behulp ervan als sjabloon zijn gemaakt. Een nieuwe werkstroom die is gemaakt met behulp van een sjabloon is een kopie van de inhoud in de sjabloon.  
  
 **Beschikbaar voor uitvoering**  
 Deze sectie bevat opties waarmee wordt beschreven hoe de werkstroom kan worden uitgevoerd.  
  
 **Deze werkstroom op de achtergrond uitvoeren (aanbevolen)**  
 Dit selectievakje geeft de optie weer die u hebt geselecteerd tijdens het maken van de werkstroom. Deze optie is uitgeschakeld, maar u kunt het wijzigen vanuit het menu **Acties** door **Converteren naar een realtimewerkstroom** of **Converteren naar een werkstroomachtergrond** te kiezen.  
  
 **Als een proces op aanvraag**  
 Kies deze optie als u wilt toestaan dat gebruikers deze werkstroom uitvoeren vanuit de opdracht **Werkstroom uitvoeren**.  
  
 **Als een onderliggend proces**  
 Kies deze optie als u toestaan dat u wilt dat de werkstroom kan worden gestart vanuit een andere werkstroom.  
  
 **Vasthouden van werkstroomtaken**  
 Deze sectie bevat een optie voor het verwijderen van een werkstroom nadat deze is uitgevoerd.  
  
 **Automatisch voltooide werkstroomtaken verwijderen (om schijfruimte te besparen)**  
 Kies deze optie als u wilt dat een voltooide werkstroomtaak automatisch moeten worden verwijderd.  
  
> [!NOTE]
>  De werkstroomtaken worden niet onmiddellijk na voltooiing verwijderd, maar even erna, via een batchproces.  
  
 **Bereik**  
 Voor entiteiten waarvan de gebruiker eigenaar is, zijn de opties **Organisatie**, **Bovenliggend item: onderliggende business units**, **Business unit** of **Gebruiker**. Voor entiteiten die eigendom zijn van een organisatie is de enige optie **Organisatie**.  
  
 Als het bereik **Organisatie** is, kan de werkstroomlogica worden toegepast op elk record in de organisatie. Anders kan de werkstroom alleen worden toegepast op een subset van de records die binnen het bereik vallen.  
  
> [!NOTE]
>  De standaardwaarde van het bereik is **Gebruiker**. Zorg ervoor dat u controleert of de waarde voor het bereik juist is voordat u de werkstroom activeert.  
  
 **Starten wanneer**  
 Gebruik de opties in deze sectie om op te geven wanneer een werkstroom automatisch moet worden gestart. U kunt een realtimewerkstroom zo configureren dat deze wordt uitgevoerd voorafgaand aan bepaalde gebeurtenissen. Dit is een zeer krachtige functie, omdat de werkstroom de actie kan stoppen voordat deze plaatsvindt. Meer informatie: [Realtime-werkstromen gebruiken](configure-workflow-steps.md#BKMK_SynchronousWorkflows). De opties zijn:  
  
- **Record wordt gemaakt**  
  
- **Recordstatus wordt gewijzigd**  
  
- **Record wordt toegewezen**  
  
- **Recordvelden worden gewijzigd**  
  
- **Record wordt verwijderd**  
  
> [!NOTE]
>  Houd er rekening mee dat bij de acties en voorwaarden die u voor de werkstroom definieert niet bekend is wanneer de werkstroom wordt uitgevoerd. Als u een werkstroom definieert voor het bijwerken van het record, kan deze actie bijvoorbeeld niet worden uitgevoerd door een realtimewerkstroom voordat het record is gemaakt. Een record dat niet bestaat, kan niet worden bijgewerkt. Op deze manier kan een achtergrondwerkstroom niet een record bijwerken dat is verwijderd, ook al kunt u deze actie voor de werkstroom definiëren. Als u een werkstroom zo configureert dat deze een actie uitvoert die niet kan worden uitgevoerd, zal deze mislukken en zal de volledige werkstroom mislukken.  
  
 **Uitvoeren als**  
 Deze optie is alleen beschikbaar als u de optie **Deze werkstroom op de achtergrond uitvoeren (aanbevolen)** uitschakelt wanneer u de werkstroom hebt gemaakt of als u later een achtergrondwerkstroom naar een realtimewerkstroom converteert.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>De beveiligingscontext van de werkstroomprocessen  
 Wanneer een achtergrondwerkstroom is geconfigureerd als een proces op aanvraag en wordt gestart door een gebruiker met behulp van de opdracht **Werkstroom uitvoeren**, zijn de acties die door de werkstroom kunnen worden uitgevoerd beperkt tot de acties die de gebruiker kan uitvoeren op basis van de bevoegdheden en toegangsniveaus die zijn gedefinieerd door de beveiligingsrol(len) die zijn ingesteld voor het gebruikersaccount.  
  
 Wanneer een achtergrondwerkstroom wordt gestart op basis van een gebeurtenis, functioneert de werkstroom in de context van de persoon die de eigenaar ervan is. Dit is doorgaans degene die de werkstroom heeft gemaakt.  
  
 Voor realtimewerkstromen beschikt u over de optie **Uitvoeren als** en kunt u kiezen of de beveiligingscontext van de eigenaar van de werkstroom of de gebruiker die wijzigingen in het record heeft aangebracht, moet worden toegepast door de werkstroom. Als uw werkstroom acties bevat die niet door alle gebruikers kunnen worden uitgevoerd op basis van veiligheidsbeperkingen, moet u ervoor kiezen om de werkstroom uit te voeren als eigenaar van de werkstroom.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Een werkstroom activeren  
 Werkstromen kunnen alleen worden bewerkt wanneer ze zijn gedeactiveerd. Voordat een werkstroom handmatig kan worden gebruikt of op basis van gebeurtenissen kan worden toegepast, moet deze worden geactiveerd. Een werkstroom moet ten minste één stap bevatten voordat deze kan worden geactiveerd. Zie [Werkstroomprocessen configureren](configure-workflow-steps.md) voor meer informatie over het configureren van stappen  
  
 Een werkstroom kan alleen worden in- of uitgeschakeld door de eigenaar van de werkstroom of door iemand met de bevoegdheid **Handelen namens een andere gebruiker**, zoals de systeembeheerder.  De reden hiervoor is dat een kwaadwillende gebruiker iemands werkstroom kan wijzigen zonder dat deze op de hoogte is van de wijziging. U kunt een werkstroom in uw eigendom opnieuw toewijzen door deze van eigenaar te laten veranderen. Dit veld bevindt zich op het tabblad **Beheer**. Als u geen systeembeheerder bent en u een werkstroom wilt bewerken die eigendom is van een andere gebruiker, moet u deze eerst deactiveren en aan u toewijzen. Nadat u klaar bent met het bewerken van de werkstroom, kunt u deze weer aan de andere gebruiker toewijzen, zodat deze de werkstroom kan activeren.  
  
 Voor realtimewerkstromen is vereist dat de gebruiker over de bevoegdheid **Realtimeprocessen activeren** beschikt. Omdat met realtimewerkstromen het risico dat de systeemprestaties worden beïnvloed groter is, moet deze bevoegdheid alleen worden gegeven aan de personen die het mogelijke risico kunnen beoordelen.  
  
 Werkstromen worden opgeslagen wanneer ze worden geactiveerd. Het is dus niet nodig om ze op te slaan voordat u ze activeert.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Werkstroomprocessen configureren](configure-workflow-steps.md)  <br/>
[Een werkstroom op aanvraag toevoegen aan een bedrijfsprocesstroom](bpf-add-on-demand-workflow.md) 

