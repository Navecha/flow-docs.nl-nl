---
title: Overzicht bedrijfsprocesstromen | MicrosoftDocs
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
- PowerApps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b1e23a3ddfd4302c4a5429029ea4fb47f0ab9808
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64464994"
---
# <a name="business-process-flows-overview"></a>Overzicht bedrijfsprocesstromen

U kunt ervoor zorgen dat personen gegevens consistent invoeren en telkens wanneer ze met een klant werken dezelfde stappen volgen door een bedrijfsprocesstroom te maken. U wilt bijvoorbeeld een bedrijfsprocesstroom maken zodat iedereen klantenservice-aanvragen op dezelfde manier verwerkt of om te vereisen dat personen goedkeuring voor een factuur krijgen voordat ze een order indienen. Voor bedrijfsprocesstromen wordt dezelfde onderliggende technologie gebruikt als voor andere processen, maar de mogelijkheden die ze bieden zijn heel anders dan andere functies die gebruikmaken van processen. Zie [Een bedrijfsprocesstroom maken](create-business-process-flow.md) voor informatie over het maken of bewerken van een bedrijfsprocesstroom.  
  
 [Bekijk een korte video (4:49) over bedrijfsprocesstromen.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Redenen om bedrijfsprocesstromen te gebruiken  
Bedrijfsprocesstromen bieden een handvat voor personen om hun werkzaamheden uit te voeren. Ze bieden een gestroomlijnde gebruikerservaring die personen door de processen leidt die hun organisatie heeft gedefinieerd voor interacties die op de een of andere manier moeten worden afgesloten. Deze gebruikerservaring kan worden aangepast zodat personen met verschillende beveiligingsrollen een ervaring kunnen hebben die het beste bij hun werkzaamheden past.  
  
 Gebruik bedrijfsprocesstromen om een reeks stappen te definiëren die personen moeten volgen om een gewenst resultaat te bereiken. Deze stappen bieden een visuele indicator waaraan personen kunnen zien waar ze zich in het bedrijfsproces bevinden. Dankzij bedrijfsprocesstromen is er minder behoefte aan training, omdat nieuwe gebruikers zich niet hoeven te richten op welke entiteit ze moeten gebruiken. Ze kunnen zich door het proces laten leiden. U kunt bedrijfsprocesstromen configureren ter ondersteuning van gemeenschappelijke verkoopmethoden waarmee uw verkoopgroepen betere resultaten kunnen behalen. Voor servicegroepen kunnen bedrijfsprocesstromen helpen bij het snel inwerken van nieuwe medewerkers en helpen fouten te vermijden die tot ontevreden klanten kunnen leiden.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>Wat kunnen bedrijfsprocesstromen doen?  
 Met bedrijfsprocesstromen definieert u een reeks *fasen* en *stappen* die vervolgens in een besturingselement boven aan het formulier worden weergegeven.  
  
 ![Bedrijfsproces met fasen](media/business-process-stages.png "Bedrijfsproces met fasen")  
  
 Elke fase van bevat een groep stappen. Elke stap vertegenwoordigt een veld waarin gegevens kunnen worden ingevoerd. Personen gaan door naar de volgende fase met de knop **Volgende fase**. U kunt instellen dat een stap vereist is zodat personen gegevens voor het bijbehorende veld moeten invoeren voordat ze door kunnen gaan naar de volgende fase. Dit wordt gewoonlijk 'stage-gating' genoemd.  
  
 Bedrijfsprocesstromen lijken relatief eenvoudig vergeleken met andere soorten processen omdat ze geen voorwaardelijke bedrijfslogica of automatisering bieden behalve de gestroomlijnde ervaring voor gegevens invoer en het beheer van invoer in fasen. Wanneer u de processen echter combineert met andere processen en aanpassingen, kunnen ze een belangrijke rol spelen bij het besparen van tijd, het verminderen van trainingskosten en het vergroten van de acceptatie door gebruikers.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Bedrijfsprocesstromen geïntegreerd met andere aanpassingen  
 Wanneer u of uw gebruiker gegevens invoert met behulp van bedrijfsprocesstromen, worden de gegevenswijzigingen ook toegepast op formuliervelden zodat automatisering die wordt geboden door bedrijfsregels of formulierscripts direct kan worden toegepast. Er kunnen stappen worden toegevoegd waarmee waarden worden ingesteld voor velden die niet aanwezig zijn in het formulier, en deze velden worden aan het `Xrm.Page`-objectmodel toegevoegd dat wordt gebruikt voor formulierscripts. Werkstromen die worden geïnitieerd door wijzigingen in velden die zijn opgenomen in een bedrijfsprocesstroom worden toegepast wanneer de gegevens in het formulier worden opgeslagen. Als de automatisering wordt toegepast door een werkstroom in realtime, worden de wijzigingen onmiddellijk zichtbaar voor de gebruiker wanneer de gegevens in het formulier worden vernieuwd nadat de record is opgeslagen.  
  
 Hoewel het besturingselement van de bedrijfsprocesstroom in het formulier geen directe programmeerbaarheid aan de clientzijde biedt, worden wijzigingen die worden toegepast door bedrijfsregels of formulierscripts automatisch toegepast op besturingselementen van de bedrijfsprocesstroom. Als u een veld in een formulier verbergt, wordt dat veld ook verborgen in het besturingselement van de bedrijfsprocesstroom. Als u een waarde instelt met behulp van bedrijfsregels of formulierscripts, wordt die waarde binnen de bedrijfsprocesstroom ingesteld.  
  
### <a name="concurrent-process-flows"></a>Gelijktijdige processtromen  
 Aanpassers kunnen met gelijktijdige bedrijfsprocesstromen meerdere bedrijfsprocessen configureren en deze aan dezelfde beginrecord koppelen. Gebruikers kunnen schakelen tussen meerdere bedrijfsprocessen die gelijktijdig worden uitgevoerd en hun werk hervatten in de fase in het proces waarin ze zich bevonden.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Systeembedrijfsprocesstromen  
 De volgende bedrijfsprocesstromen zijn inbegrepen. Als u wilt begrijpen hoe bedrijfsprocesstromen werken, bekijkt u deze systeembedrijfsprocesstromen:  
  
-   Verkoopproces van potentiële klant naar verkoopkans  
  
-   Verkoopproces verkoopkans  
  
-   Proces van telefoongesprek naar aanvraag  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Meerdere entiteiten in bedrijfsprocesstromen  
 U kunt een bedrijfsprocesstroom voor één entiteit of voor meerdere entiteiten gebruiken. Mogelijk heeft u bijvoorbeeld een proces dat begint met een verkoopkans, die leidt tot een prijsopgave, een order en vervolgens een factuur voordat ten slotte wordt teruggegaan om de verkoopkans te sluiten.  
  
 U kunt bedrijfsprocesstromen ontwerpen die de records voor maximaal vijf verschillende entiteiten in een enkel proces verbinden zodat personen die de app gebruiken zich kunnen richten op de stroom van hun proces, in plaats van zich af te vragen in welke entiteit ze werken. Ze kunnen eenvoudiger navigeren tussen gerelateerde entiteitsrecords.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Per entiteit zijn meerdere bedrijfsprocesstromen beschikbaar  
 Mogelijk volgt niet elke gebruiker in een organisatie hetzelfde proces en bij verschillende omstandigheden is mogelijk de toepassing van een ander proces vereist. U kunt maximaal 10 actieve bedrijfsprocesstromen per entiteit hebben om geschikte processen te bieden voor verschillende situaties.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Beheren welke bedrijfsprocesstroom wordt toegepast  
 U kunt bedrijfsprocesstromen koppelen aan beveiligingsrollen, zodat alleen personen met deze beveiligingsrollen ze kunnen zien of gebruiken. U kunt ook de volgorde van de bedrijfsprocesstromen instellen, zodat u kunt bepalen welke bedrijfsprocesstroom standaard wordt ingesteld. Dit werkt op dezelfde manier als het definiëren van meerdere formulieren voor een entiteit.  
  
 Wanneer iemand een nieuwe entiteitsrecord maakt, wordt de lijst met beschikbare actieve bedrijfsprocesdefinities gefilterd op de beveiligingsrol van de gebruiker. De eerste geactiveerde bedrijfsprocesdefinitie die beschikbaar is voor de beveiligingsrol van de gebruiker volgens de procesvolgordelijst is de definitie die standaard wordt toegepast. Als er meerdere actieve bedrijfsprocesdefinities beschikbaar zijn, kunnen gebruikers nog een definitie laden vanuit het dialoogvenster Proces omwisselen. Wanneer processen worden omgewisseld, gaat het proces dat momenteel wordt weergegeven naar de achtergrond en wordt vervangen door het geselecteerde proces. Het proces behoudt wel zijn status en kan weer worden terug gewisseld. Aan elke record kunnen meerdere procesexemplaren zijn gekoppeld (elk voor een andere bedrijfsprocesstroomdefinitie, met een maximum van 10). Bij het laden van een formulier wordt slechts één bedrijfsprocesstroom weergegeven. Wanneer een gebruiker een ander proces toepast, kan dat proces alleen standaard worden geladen voor die bepaalde gebruiker.  
  
 Als u ervoor wilt zorgen dat een bedrijfsproces standaard wordt geladen voor alle gebruikers (gedrag equivalent aan het 'vastmaken' van het proces), kan een aangepast Client API-script (webresource) worden toegevoegd bij het laden van het formulier waarmee een bestaand bedrijfsprocesexemplaar wordt geladen op basis van de bedrijfsprocesdefinitie-ID. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Overwegingen bij bedrijfsprocesstromen  
 U kunt bedrijfsprocesstromen alleen definiëren voor entiteiten die de stromen ondersteunen. U moet ook rekening houden met de limieten voor het aantal processen, fasen en stappen dat kan worden toegevoegd.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Bedrijfsprocesstromen die een werkstroom aanroepen  
 U kunt werkstromen op aanvraag aanroepen vanuit een bedrijfsprocesstroom. U kunt dit configureren vanuit de nieuwe bedrijfsprocesstroomontwerper door een werkstroomonderdeel naar een procesfase of naar de sectie Algemene werkstromen te slepen. Zie voor meer informatie over het gebruik van werkstromen in bedrijfsprocesstromen [Blog: Automatisering van bedrijfsprocesstromen in Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Als u een werkstroom opneemt die u wilt activeren bij het afsluiten van een fase in uw bedrijfsprocesstroom en die fase is de laatste fase in de stroom, dan geeft de ontwerper de indruk dat de werkstroom wordt geactiveerd wanneer die fase wordt voltooid. De werkstroom wordt echter niet geactiveerd omdat er geen faseovergang plaatsvindt. U ontvangt geen waarschuwing of foutmelding om te voorkomen dat u de werkstroom in de fase opneemt. Wanneer een gebruiker interactie met de bedrijfsprocesstroom heeft, resulteert het voltooien of afbreken van het proces niet in een faseovergang en daarom wordt de werkstroom niet geactiveerd. Bekijk de volgende voorbeelden:  
  
-   U maakt een bedrijfsprocesstroom met twee fasen, S1 is verbonden met S2, met een werkstroom in fase S2 en u stelt de trigger in op **Afsluiten van fase**.  
  
-   U maakt een bedrijfsprocesstroom met drie fasen, S1 is verbonden met S2 en vervolgens vertakt S2 naar S3. U neemt een werkstroom op in S2 en stelt de trigger in op **Afsluiten van fase**.  
  
 De werkstroom wordt in alle gevallen niet geactiveerd. U kunt dit probleem omzeilen door een algemene werkstroom toe te voegen en de werkstroom die moet worden geactiveerd daaraan toe te voegen, zodat de werkstroom wordt geactiveerd voor het bedrijfsproces in plaats van voor een fase van het proces. U kunt de trigger voor een algemene werkstroom instellen op Proces afgebroken of Proces voltooid om te zorgen dat de werkstroom wordt geactiveerd wanneer een gebruiker het bedrijfsproces afbreekt of voltooit.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entiteiten die bedrijfsprocesstromen kunnen gebruiken  
 Alle aangepaste entiteiten kunnen bedrijfsprocesstromen gebruiken. De volgende standaardentiteiten kunnen ook bedrijfsprocesstromen gebruiken:  
  
-   Account  
-   Afspraak  
-   Campagne  
-   Campagneactiviteit  
-   Campagnerespons  
-   Concurrent  
-   Contactpersoon  
-   E-mailadres  
-   Recht  
-   Fax  
-   Aanvraag  
-   Factuur  
-   Potentiële klant  
-   Brief  
-   Marketinglijst  
-   Verkoopkans  
-   Telefoongesprek  
-   Product  
-   Prijslijstitem  
-   Prijsopgave  
-   Terugkerende afspraak  
-   Verkoopdocumentatie  
-   Sociale activiteit  
-   Order  
-   Gebruiker  
-   Taak  
-   Team  
  
 Als u een aangepaste entiteit voor bedrijfsprocesstromen wilt inschakelen, schakelt u het selectievakje **Bedrijfsprocesstromen (velden worden gemaakt)** in de entiteitsdefinitie in. Let op: u kunt deze actie niet ongedaan maken.  
  
> [!NOTE]
>  Als u naar de fase van de bedrijfsprocesstroom navigeert die de entiteit `Social Activity` bevat en de knop **Volgende fase** kiest, ziet u de optie **Maken**. Als u **Maken** kiest, wordt het formulier **Sociale activiteit** geladen. Omdat `Social Activity` niet geldig is voor `Create` vanuit de gebruikersinterface van de app, kunt u het formulier echter niet opslaan en ziet u het foutbericht: Onverwachte fout.  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Maximum aantal processen, fasen en stappen  
 Om zeker te zijn van acceptabele prestaties en bruikbaarheid van de gebruikersinterface, zijn er enkele beperkingen waarmee u rekening moet houden wanneer u van plan bent bedrijfsprocesstromen te gebruiken:  
  
-   Er kunnen niet meer dan tien geactiveerde processen voor bedrijfsprocesstroom per entiteit zijn.  
  
-   Elk proces kan maximaal dertig fasen bevatten.  
  
-   Processen met meerdere entiteiten kunnen maximaal vijf entiteiten bevatten.
  
## <a name="business-process-flow-entity-customization-support"></a>Ondersteuning voor aanpassing van entiteit van bedrijfsprocesstroom 

Geïntroduceerd in de update van versie 9.0 van Dynamics 365 (online): entiteiten van bedrijfsprocesstromen kunnen in het systeem worden weergegeven, zodat entiteitsrecordgegevens beschikbaar kunnen worden gemaakt in rasters, weergaven, grafieken en dashboards. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Entiteitsrecords van bedrijfsprocesstromen gebruiken met rasters, weergaven, grafieken en dashboards

Met bedrijfsprocesstromen die als entiteit beschikbaar zijn, kunt u nu geavanceerd zoeken, weergaven, grafieken en dashboards gebruiken die afkomstig zijn uit bedrijfsprocesstroomgegevens voor een opgegeven entiteit, zoals een potentiële klant of verkoopkans. Systeembeheerders en aanpassers kunnen aangepaste rasters, weergaven, grafieken en dashboards van een bedrijfsprocesstroom maken die lijken op rasters, weergaven, grafieken en dashboards die zijn gemaakt met een andere entiteit.

Bedrijfsprocesstromen, zoals **Verkoopproces van potentiële klant naar verkoopkans**, worden als aanpasbare entiteit in Solution Explorer weergegeven.

![Solution Explorer met entiteit voor proces van potentiële klant naar verkoopkans](media/bpf-lead-solution-explorer.png)

Voor toegang tot een standaardweergave van een bedrijfsprocesstroom opent u Solution Explorer, vouwt u **Entiteiten** uit, vouwt u het gewenste proces uit, zoals **Verkoopproces van potentiële klant naar verkoopkans**, selecteert u **Weergaven** en selecteert u vervolgens de gewenste weergave.

Er zijn verscheidene standaardweergaven beschikbaar die u als grafiek kunt bekijken, zoals de weergave **Verkoopproces actieve verkoopkans**. 

![Weergave Verkoopproces actieve verkoopkans](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interactie met de entiteit van de bedrijfsprocesstroom vanuit een werkstroom
Interactie met entiteiten van bedrijfsprocesstromen is ook mogelijk vanuit een werkstroom. U kunt bijvoorbeeld een werkstroom maken voor de entiteitsrecord Bedrijfsprocesstroom om de actieve fase te wijzigen wanneer een veld in de entiteitsrecord Verkoopkans wordt bijgewerkt. Zie [Automate business process flow stages using workflows](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows) (Fasen van bedrijfsprocesstroom automatiseren met werkstromen) voor meer informatie.


### <a name="limitations-of-using-business-process-flow-entities"></a>Beperkingen bij het gebruik van entiteiten van bedrijfsprocesstroom

- Momenteel kunt u geen aangepaste formulieren maken voor entiteiten op basis van een bedrijfsprocesstroom.
- Als een oplossing een entiteit voor een bedrijfsprocesstroom bevat, moet de entiteit van de bedrijfsprocesstroom handmatig worden toegevoegd aan de oplossing voordat u deze kunt exporteren. Anders wordt de entiteit van de bedrijfsprocesstroom niet opgenomen in het oplossingspakket. Meer informatie: [Oplossingsonderdelen toevoegen](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)

### <a name="next-steps"></a>Volgende stappen  
 [Bekijk een korte video (4:49) over bedrijfsprocesstromen](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Een bedrijfsprocesstroom maken](create-business-process-flow.md)   
 [Bedrijfsprocesstromen verbeteren met vertakkingen](enhance-business-process-flows-branching.md) <br/>
 [Technisch document: Inschakeling van proces met Dynamics 365](http://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
