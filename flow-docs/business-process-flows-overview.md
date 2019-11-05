---
title: Overzicht van bedrijfs proces stromen | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 230c35947c4e499c5e26fc37bb87828ec787a469
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545522"
---
# <a name="business-process-flows-overview"></a>Overzicht van bedrijfs proces stromen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

U kunt ervoor zorgen dat mensen gegevens consistent invoeren en dezelfde stappen volgen telkens wanneer ze met een klant samen werken door een bedrijfs proces stroom te maken. U kunt bijvoorbeeld een bedrijfsproces stroom maken zodat iedereen de service aanvragen van de klant op dezelfde manier afhandelt, of om te vereisen dat mensen goed keuring voor een factuur krijgen voordat ze een bestelling indienen. Bedrijfs proces stromen gebruiken dezelfde onderliggende technologie als andere processen, maar de mogelijkheden die ze bieden, verschillen van andere functies die gebruikmaken van processen. Zie [een bedrijfs proces stroom maken](create-business-process-flow.md)voor meer informatie over het maken of bewerken van een bedrijfsproces stroom.  
  
 [Bekijk een korte video (4:49) over bedrijfs proces stromen.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Waarom bedrijfs proces stromen gebruiken?  
Bedrijfs proces stromen bieden een hand leiding voor mensen die hun werk doen. Ze bieden een gestroomlijnde gebruikers ervaring waarmee gebruikers worden geleid door de processen die hun organisatie heeft gedefinieerd voor interacties die moeten worden uitgebreid tot een conclusie van wat u moet doen. Deze gebruikers ervaring kan zodanig worden aangepast dat mensen met verschillende beveiligings rollen een ervaring kunnen hebben die het werk dat ze doen, het beste kan doen.  
  
 Bedrijfs proces stromen gebruiken om een reeks stappen te definiëren die gebruikers moeten volgen om ze naar een gewenst resultaat te brengen. Deze stappen bieden een visuele indicator waarmee wordt aangegeven waar deze zich in het bedrijfs proces bevinden. Bedrijfs proces stromen verminderen de behoefte aan trainingen, omdat nieuwe gebruikers zich niet hoeven te concentreren op de entiteit die ze moeten gebruiken. Ze kunnen deze hand leiding laten door de processen. U kunt bedrijfsproces stromen zo configureren dat algemene verkoop methoden worden ondersteund waarmee uw verkoop groepen betere resultaten kunnen krijgen. In het geval van service groepen kunnen bedrijfsproces stromen nieuwe mede werkers helpen om sneller en te voor komen dat er fouten ontstaan waardoor klanten ontevreden kunnen raken.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>Wat kunnen bedrijfs proces stromen doen?  
 Met bedrijfs proces stromen definieert u een reeks *fasen* en *stappen* die vervolgens worden weer gegeven in een besturings element boven aan het formulier.  
  
 ![Bedrijfs proces met fasen](media/business-process-stages.png "Bedrijfs proces met fasen")  
  
 Elke fase bevat een groep stappen. Elke stap vertegenwoordigt een veld waarin gegevens kunnen worden ingevoerd. Personen gaan naar de volgende fase met behulp van de knop **volgende fase** . U kunt een stap verplicht maken zodat mensen gegevens voor het bijbehorende veld moeten invoeren voordat ze kunnen door gaan naar de volgende fase. Dit wordt meestal ' fase-beperking ' genoemd.  
  
 Bedrijfs proces stromen worden relatief eenvoudig vergeleken met andere typen processen, omdat ze geen voorwaardelijke bedrijfs logica of automatisering bieden, behalve de gestroomlijnde ervaring voor het invoeren van gegevens en het bewaken van vermelding in fasen. Wanneer u deze echter combineert met andere processen en aanpassingen, kunnen ze een belang rijke rol spelen bij het opslaan van mensen tijd, het verminderen van de trainings kosten en het verhogen van de gebruikers acceptatie.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Bedrijfs proces stromen geïntegreerd met andere aanpassingen  
 Wanneer u of uw gebruiker gegevens invoert met behulp van bedrijfsproces stromen, worden de gegevens wijzigingen ook toegepast op formulier velden, zodat de automatisering die wordt verschaft door bedrijfs regels of formulier scripts onmiddellijk kan worden toegepast. Stappen kunnen worden toegevoegd die waarden instellen voor velden die niet aanwezig zijn in het formulier en deze velden worden toegevoegd aan het `Xrm.Page`-object model dat wordt gebruikt voor formulier scripts. Werk stromen die worden geïnitieerd door wijzigingen in velden die zijn opgenomen in een bedrijfs proces stroom worden toegepast wanneer de gegevens in het formulier worden opgeslagen. Als de automatisering door een realtime werk stroom wordt toegepast, worden de wijzigingen onmiddellijk zichtbaar voor de gebruiker wanneer de gegevens in het formulier worden vernieuwd nadat de record is opgeslagen.  
  
 Hoewel het besturings element voor bedrijfs processen in het formulier geen directe programmeer baarheid aan de client zijde biedt, worden wijzigingen die worden toegepast door bedrijfs regels of formulier scripts, automatisch toegepast op stroom besturings elementen voor bedrijfs processen. Als u een veld in een formulier verbergt, wordt dat veld ook verborgen in de stroom regeling voor bedrijfs processen. Als u een waarde instelt met behulp van bedrijfs regels of formulier scripts, wordt die waarde ingesteld in de bedrijfs proces stroom.  
  
### <a name="concurrent-process-flows"></a>Gelijktijdige proces stromen  
 Met gelijktijdige bedrijfs proces stromen kunnen aanpassingen meerdere bedrijfs processen configureren en deze koppelen aan dezelfde begin record. Gebruikers kunnen scha kelen tussen meerdere bedrijfs processen die gelijktijdig worden uitgevoerd, en hun werk in het stadium hervatten in het proces waarin ze zich bevonden.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Bedrijfs proces stromen voor systeem  
 De volgende bedrijfs proces stromen zijn opgenomen. Als u wilt weten hoe bedrijfsproces stromen werken, raadpleegt u deze processen voor bedrijfsproces stromen:  
  
-   Verkoop proces van lead naar verkoop kans  
  
-   Verkoop proces verkoop kansen  
  
-   Telefoon-naar-case proces  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Meerdere entiteiten in bedrijfs proces stromen  
 U kunt een bedrijfsproces stroom voor één entiteit gebruiken of meerdere entiteiten beslaan. U kunt bijvoorbeeld een proces hebben dat begint met een verkoop kans, vervolgens door gaan naar een offerte, een bestelling en vervolgens een factuur voordat u de opportuniteit gaat afsluiten.  
  
 U kunt bedrijfs proces stromen ontwerpen waarmee de records voor Maxi maal vijf verschillende entiteiten in één proces worden gecombineerd, zodat gebruikers die de app gebruiken zich kunnen concentreren op de stroom van hun proces in plaats van op welke entiteit ze werken. Ze kunnen eenvoudiger navigeren tussen gerelateerde entiteits records.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Er zijn meerdere bedrijfs proces stromen beschikbaar per entiteit  
 Niet elke gebruiker in een organisatie kan hetzelfde proces volgen en er kunnen verschillende voor waarden zijn die vereisen dat een ander proces wordt toegepast. U kunt Maxi maal tien actieve bedrijfsproces stromen per entiteit hebben om de juiste processen te bieden voor verschillende situaties.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Bepalen welke bedrijfs proces stroom wordt toegepast  
 U kunt bedrijfsproces stromen koppelen aan beveiligings rollen zodat alleen personen met deze beveiligings rollen ze kunnen zien of gebruiken. U kunt ook de volg orde van de bedrijfs proces stromen instellen, zodat u kunt bepalen welke bedrijfs proces stroom standaard wordt ingesteld. Dit werkt op dezelfde manier als meerdere formulieren voor een entiteit worden gedefinieerd.  
  
 Wanneer iemand een nieuwe entiteits record maakt, wordt de lijst met beschik bare actieve bedrijfs proces definities gefilterd op de beveiligingsrol van de gebruiker. De eerste geactiveerde bedrijfs proces definitie die beschikbaar is voor de beveiligingsrol van de gebruiker op basis van de lijst proces volgorde, wordt standaard toegepast. Als er meer dan één actieve bedrijfs proces definities beschikbaar zijn, kunnen gebruikers een andere laden vanuit het dialoog venster switch process. Wanneer de processen worden overgeschakeld, wordt de huidige weer gegeven op de achtergrond en vervangen door het geselecteerde proces, maar de status wordt behouden en kan worden omgedraaid. Aan elke record kunnen meerdere proces instanties zijn gekoppeld (elk voor een andere stroom definitie van een bedrijfs proces, tot een totaal van 10). Bij het laden van formulieren wordt slechts één proces stroom van het bedrijf weer gegeven. Wanneer een gebruiker een ander proces toepast, wordt dat proces mogelijk alleen voor de desbetreffende gebruiker standaard geladen.  
  
 Om ervoor te zorgen dat een bedrijfs proces standaard wordt geladen voor alle gebruikers (gedrag gelijk aan het ' vastmaken ' van het proces), kan een aangepast client-API-script (WebResource) worden toegevoegd aan de formulier belasting die specifiek een bestaand exemplaar van een bedrijfs proces op basis van het bedrijf laadt proces definitie-ID. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Overwegingen voor bedrijfs proces stroom  
 U kunt alleen bedrijfsproces stromen definiëren voor de entiteiten die ze ondersteunen. U moet ook rekening houden met de limieten voor het aantal processen, fasen en stappen dat kan worden toegevoegd.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Bedrijfs proces stromen die een werk stroom aanroepen  
 U kunt werk stromen op aanvraag aanroepen vanuit een bedrijfs proces stroom. U kunt dit configureren op basis van de nieuwe bedrijfsproces stroom ontwerper door een werk stroom onderdeel naar een proces fase of naar het gedeelte algemene werk stromen te slepen. Zie voor meer informatie over het gebruik van werk stromen in de stroom van bedrijfs processen [blog: automatisering van bedrijfs processen in Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Wanneer u een werk stroom opneemt die u wilt activeren bij het afsluiten van een fase in uw bedrijfs proces stroom, en die fase de laatste fase in de stroom is, geeft de ontwerper de indruk dat de werk stroom wordt geactiveerd wanneer die fase is voltooid. De werk stroom wordt echter niet geactiveerd omdat er geen fase overgang plaatsvindt. U ontvangt geen waarschuwing of fout waardoor u de werk stroom niet in het stadium kunt opnemen. Wanneer een gebruiker werkt met de stroom van het bedrijfs proces, wordt het volt ooien of afbreken van het proces niet in een fase overgang veroorzaakt, waardoor de werk stroom niet wordt geactiveerd. Bekijk de volgende voor beelden:  
  
-   U maakt een bedrijfsproces stroom met twee fasen, S1 verbindt met S2 met een werk stroom in fase S2 en stelt de trigger in op **fase afsluiten**.  
  
-   U maakt een bedrijfsproces stroom met drie fasen, S1 verbinding maken met S2 en vervolgens de vertakkingen tot S3. U neemt een werk stroom op S2 op en stelt de trigger in op **fase afsluiten**.  
  
 De werk stroom wordt in geen van beide gevallen geactiveerd. U kunt dit probleem omzeilen door een algemene werk stroom toe te voegen en de werk stroom die u wilt activeren, toe te voegen, zodat de werk stroom wordt geactiveerd voor het bedrijfs proces in plaats van een fase van het proces. U kunt de trigger instellen voor een globale werk stroom voor het afgebroken of voltooide proces om ervoor te zorgen dat de werk stroom wordt geactiveerd wanneer een gebruiker het bedrijfs proces verlaat of voltooit.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entiteiten die bedrijfs proces stromen kunnen gebruiken  
 Alle aangepaste entiteiten kunnen bedrijfsproces stromen gebruiken. De volgende standaard entiteiten kunnen ook bedrijfs proces stromen gebruiken:  
  
-   Account  
-   Viel  
-   Marketing  
-   Campagne activiteit  
-   Campagne respons  
-   Concurrenten  
-   Overzicht  
-   E-mail  
-   Toewijzing  
-   Faxtaken  
-   Casu  
-   Betalen  
-   Verantwoordelijkheid  
-   Letters  
-   Marketing lijst  
-   Mogelijkheid  
-   Telefoon oproep  
-   voortplant  
-   Prijslijst item  
-   Aanhalings teken  
-   Terugkerende afspraak  
-   Verkoop documentatie  
-   Sociale activiteit  
-   Ter  
-   Gebruiker  
-   Takenreeksuitvoeringsengine  
-   Stellen  
  
 Als u een aangepaste entiteit wilt inschakelen voor bedrijfs proces stromen, selecteert u het selectie vakje **bedrijfs proces stromen (velden worden gemaakt)** in de definitie van de entiteit. U kunt deze actie niet ongedaan maken.  
  
> [!NOTE]
>  Als u navigeert naar de stroom fase bedrijfs proces dat de `Social Activity` entiteit bevat en de knop **volgende fase** kiest, ziet u de optie **maken** . Wanneer u **maken**kiest, wordt het formulier **sociale activiteiten** geladen. Omdat `Social Activity` echter niet geldig is voor `Create` van de gebruikers interface van de app, kunt u het formulier niet opslaan en ziet u het fout bericht: onverwachte fout.  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Maximum aantal processen, fasen en stappen  
 Om te zorgen voor voldoende prestaties en de bruikbaarheid van de gebruikers interface, moet u rekening houden met enkele beperkingen wanneer u van plan bent om bedrijfs proces stromen te gebruiken:  
  
-   Er kunnen niet meer dan tien geactiveerde processen voor bedrijfsproces stromen per entiteit zijn.  
  
-   Elk proces kan niet meer dan 30 fasen bevatten.  
  
-   Processen met meerdere entiteiten kunnen niet meer dan vijf entiteiten bevatten.
  
## <a name="business-process-flow-entity-customization-support"></a>Ondersteuning voor entiteits aanpassingen van bedrijfsproces stroom 

In het geval van de Dynamics 365 (online), update van versie 9,0, kunnen bedrijfs proces stroom-entiteiten worden weer gegeven in het systeem zodat entiteits record gegevens beschikbaar kunnen worden gemaakt in rasters, weer gaven, grafieken en dash boards. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Entiteits records voor bedrijfs processen gebruiken met rasters, weer gaven, grafieken en dash boards

Met bedrijfs processen die beschikbaar zijn als een entiteit, kunt u nu geavanceerde zoek bewerkingen, weer gaven, grafieken en dash boards gebruiken die zijn gebrond op basis van bedrijfs proces stroom gegevens voor een bepaalde entiteit, zoals een lead of een verkoop kans. Systeem beheerders en aanpassingen kunnen aangepaste bedrijfsproces stroom rasters, weer gaven, grafieken en dash boards maken die vergelijkbaar zijn met die welke zijn gemaakt met een andere entiteit.

Bedrijfs proces stromen, zoals het **verkoop proces van leads naar verkoop kansen**, worden weer gegeven als een aanpas bare entiteit in Solution Explorer.

![Solution Explorer met de entiteit proces van potentiële klant](media/bpf-lead-solution-explorer.png)

Als u toegang wilt krijgen tot een standaard weer gave voor bedrijfs processen, opent u Solution Explorer, vouwt u **entiteiten** uit > vouwt u het proces uit dat u wilt uitvoeren, zoals **lead to sales verkoop process**, selecteert u **views**en selecteert u de gewenste weer gave.

Er zijn verschillende standaard weergaven beschikbaar die u kunt weer geven als een grafiek, zoals de weer gave van het **actieve verkoop kansen verkoopproces** . 

![Weer gave van het verkoop proces van actieve verkoop kansen](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interactie met de entiteit bedrijfs proces stroom vanuit een werk stroom
U kunt ook communiceren met Business proces flow-entiteiten vanuit een werk stroom. U kunt bijvoorbeeld een werk stroom maken voor de entiteits record van de bedrijfs proces stroom om de actieve fase te wijzigen wanneer een veld in de entiteits record van de verkoop kans wordt bijgewerkt. Zie voor meer informatie over hoe u dit doet, [bedrijfsproces stroom fasen automatiseren met werk stromen](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows).


### <a name="limitations-of-using-business-process-flow-entities"></a>Beperkingen bij het gebruik van bedrijfs proces stroom-entiteiten

- Op dit moment kunt u geen aangepaste formulieren voor entiteiten maken op basis van een bedrijfs proces stroom.
- Als een oplossing een entiteit voor een bedrijfs proces stroom bevat, moet de entiteit bedrijfs proces stroom hand matig worden toegevoegd aan de oplossing voordat u deze exporteert. Anders wordt de entiteit bedrijfs proces stroom niet opgenomen in het oplossings pakket. Meer informatie: [oplossings onderdelen toevoegen](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)

### <a name="next-steps"></a>Volgende stappen  
 [Bekijk een korte video (4:49) over stromen voor bedrijfs processen](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Een bedrijfs proces stroom  maken](create-business-process-flow.md)  
 [Zakelijke proces stromen verbeteren met vertakkingen](enhance-business-process-flows-branching.md) <br/>
 [Technisch document: proces activering met Dynamics 365](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
