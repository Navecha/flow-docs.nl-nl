---
title: Klassieke Common Data Service-werk stromen vervangen door Microsoft Flow | Microsoft Docs
description: Beschrijft Microsoft Flow mogelijkheden en aanbevolen patronen om flow te gebruiken in plaats van een klassieke werk stroom.
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
ms.service: flow
ms.topic: article
ms.date: 08/27/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c824f726df991aba9aa1290eb117cf87113041a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548506"
---
# <a name="replace-classic-common-data-service-workflows-with-flows"></a>Klassieke Common Data Service-werk stromen vervangen door stromen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

In dit onderwerp worden Microsoft Flow mogelijkheden vergeleken met de klassieke werk stroom.

Microsoft Flow heeft aanzienlijke voor delen ten opzichte van het klassieke werk stroom model; u kunt het beste Microsoft Flow gebruiken om uw processen te automatiseren in plaats van de klassieke werk stroom. 

Maak stromen in plaats van klassieke Common Data Service werk stromen om nieuwe automatiserings processen te bouwen. Daarnaast moet u uw bestaande klassieke werk stroom processen bekijken en overwegen om deze te vervangen door stromen.

## <a name="feature-capability-comparison"></a>Vergelijking functie functies

Deze tabel bevat een overzicht van de mogelijkheden van Microsoft Flow en klassieke werk stromen. 

*We voegen voortdurend nieuwe mogelijkheden toe aan Microsoft Flow, zodat deze in pari en nog beter zijn dan de klassieke werk stroom mogelijkheden. De informatie in deze tabel wordt bijgewerkt als Microsoft Flow toename mogelijkheden. Probeer het regel matig opnieuw. Zie [Wat is er nieuw en gepland voor Microsoft flow](https://docs.microsoft.com/business-applications-release-notes/April19/microsoft-flow/planned-features) in de release opmerkingen van april 2019 voor informatie over aanstaande stroom mogelijkheden waarmee u de klassieke werk stroom kunt vervangen door flow.*

<table>
<tr>
<th colspan="2">Voorzieningen</th>
<th>Microsoft Flow</th>
<th>Klassieke werk stroom</th>
</tr>
<tr>
<td rowspan="5">Model</td>
<td>Voorwaardelijke vertakking</td>
<td>Klikt</td>
<td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Lussen
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Voor waarden wachten op velden
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Parallelle vertakking
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Out-of-Box-connectors naar externe systemen (activeren en acties uitvoeren in externe services)
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Samengesteld
                    
                </td>
                <td>
                    
   Dynamische inhoud
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Toegang tot voorafgaande installatie kopieën van gebeurtenis gegevens
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Onderliggende werk stromen uitvoeren
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Common Data Service acties uitvoeren (inclusief aangepast)
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Aangepaste werk stroom activiteiten uitvoeren
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Stappen groeperen om uit te voeren in een trans actie
                    
                </td>
                <td>
                    
   Ja (wijzigings sets)
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Goedkeurings werk stromen
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Uitvoering
                    
                </td>
                <td>
                    
   Activeren bij veld wijzigingen
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Voorwaardelijk activeren voor veld waarden (bijvoorbeeld op een bepaalde datum in een datum veld)
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Activeren op meerdere Common Data Service entiteits gebeurtenissen
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Op aanvraag uitvoeren
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Run-as-bereiken    <br/>
   (bijvoorbeeld organisatie, bedrijfs eenheid, gebruiker)
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Uitvoeren volgens een planning
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Synchroon uitvoeren (realtime)
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td rowspan="2">
                    
   Transactie
                    
                </td>
                <td>
                    
   Controle
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Analyses uitvoeren
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
            </tr>
            <tr>
                <td rowspan="3">
                    
   Ontwerpen en portabiliteit
                    
                </td>
                <td>
                    
   Ondersteuning voor oplossingen
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Modern Designer
                    
                </td>
                <td>
                    
   Klikt
                    
                </td>
                <td>
                    
   Geen
                    
                </td>
            </tr>
            <tr>
<td>AI-ondersteuning voor ontwerpen</td>
<td>Klikt</td>
<td>Geen</td>
</tr>
</table>

## <a name="example-scenario-replace-workflow-with-a-flow"></a>Voorbeeld scenario: werk stroom vervangen door een stroom

Stel dat u een verkoop scenario hebt waarin u een offerte voor een klant hebt geplaatst en nu moet goed keuring aanvragen van uw beheer team voordat u de offerte naar de klant verzendt. Met klassieke werk stromen zou dit niet eenvoudig kunnen zijn, en de meeste oplossingen hiervoor hebben een ontwikkelaar nodig om aangepaste werk stroom activiteiten te schrijven om offerte regel items op te halen.

Met stromen is dit eenvoudiger te bouwen zoals gedemonstreerd in de stapsgewijze instructies voor een aantal Microsoft Flow mogelijkheden om het scenario te ondersteunen. Dit omvat:

-   Een stroom maken die op aanvraag wordt uitgevoerd

-   Ophalen van een lijst met records die zijn gerelateerd aan een Common Data Service entiteit

-   Een lijst met records door lopen

-   Goedkeurings aanvragen verzenden

De verkoop medewerker toestaan om de goedkeurings aanvraag op aanvraag te activeren:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com/) en maak een stroom in een oplossing. Meer informatie: [een stroom maken in een oplossing](create-flow-solution.md). 

1. Selecteer in de lijst met triggers **common data service (huidige omgeving): wanneer een record wordt geselecteerd** en **aanhalings tekens** selecteren als de entiteit. Met deze trigger kan een stroom op aanvraag op een record of lijst met records worden uitgevoerd.

1. Wanneer de trigger is geconfigureerd, voegt u acties toe om uit te voeren in onze stroom. Hiermee wordt de goed keurder voorzien van de samenvattings gegevens die nodig zijn om de geciteerde items en waarden te identificeren. Begin met het toevoegen van de **common data service (huidige omgeving): records weer geven** . Omdat we afzonderlijke regel items van een offerte willen ophalen, stelt u de entiteit in op **offerte regels**. Om ervoor te zorgen dat alleen deze prijsopgave regel items worden weer gegeven die horen bij de offerte waarvoor de stroom is geactiveerd, geeft u een OData-filter criterium op. Typ *\_quoteid_value EQ* in het veld **filter query** en selecteer vervolgens *quote* in de lijst met dynamische waarden die worden weer gegeven.

    ![Uw stroom definiëren](media/define-flow-1.png "Uw stroom definiëren")

1. Als we offerte regel items wilt samenvatten voor de goed keuring, voegt u de actie **variabele initialiseren** toe. Stel het veld **naam** in op *offerte regel overzicht* en het **type** teken reeks (in de vervolg keuzelijst) en laat het veld **waarde** leeg.

1. Voeg de actie toevoegen **aan teken reeks variabele** toe en selecteer vervolgens de samenvattings variabele voor de *offerte lijn* die u eerder hebt gemaakt. In het veld **waarde** selecteert u *hoeveelheid, naam, prijs per eenheid, totaal bedrag en hand matige hoeveelheid* in de lijst met dynamische waarden. De Microsoft Flow Designer geeft aan dat deze waarden afkomstig zijn uit een lijst met offerte regel items en voegt deze actie toe aan een lus **Apply to each** om ervoor te zorgen dat de gegevens van elk regel item aan deze samen vatting worden toegevoegd.

    ![Uw stroom definiëren](media/define-flow-2.png "Uw stroom definiëren")

1. Als u goed keuring wilt aanvragen voor het offerte overzicht dat we hebben gemaakt, voegt u de **goed keuring toe – starten en wachten op een goedkeurings** actie. Selecteer een goedkeurings type (bijvoorbeeld goed keuren/afwijzen), geef een **titel** op voor de goedkeurings aanvraag (bijvoorbeeld de naam van de offerte waarvoor goed keuring is aangevraagd, uit de lijst met dynamische waarden wordt gekozen), voer het e-mail adres in voor de persoon die de prijs opgave moet controleren en goed keuren in het veld **toegewezen aan** . Voeg in het veld Details de *samenvattings variabele offerte lijn* toe, samen met andere informatie die mogelijk relevant is met de kiezer voor dynamische waarden (bijvoorbeeld totaal bedrag).

1. Als u wilt bepalen wat er gebeurt wanneer een goed keuring wordt geaccepteerd of afgewezen, voegt u de **voorwaarde** actie toe. Selecteer *resultaat* in de lijst met dynamische waarden van het eerste veld in de voor waarde, *bevat* in de vervolg keuzelijst in het tweede veld en voer *accepteren* in het derde veld van de voor waarde in. Voeg ten slotte acties toe op basis van het resultaat van de goed keuring (bijvoorbeeld een e-mail melding verzenden).

    ![Uw stroom definiëren](media/define-flow-3.png "Uw stroom definiëren")

We hebben nu de goedkeurings structuur gemaakt, zodat de goed keurder alle informatie heeft die nodig is om een beslissing te nemen over de volgende stappen. Hier volgt een volledig voor beeld van een stroom op aanvraag om goed keuring aan te vragen:

![Werk stroom structuur goed keuren](media/approval-flow-structure.png "Werk stroom structuur goed keuren")

Wanneer u deze stroom op basis van uw offerte uitvoert, worden offerte regel items voor die offerte weer gegeven en wordt een goedkeurings aanvraag verzonden waarmee de fiatteur kan reageren op Microsoft Flow, of de op te halen e-mail berichten. Hieronder ziet u een voor beeld van de weer gave:

![Stroom in actie](media/flow-in-action.png "Stroom in actie")

## <a name="recommended-patterns"></a>Aanbevolen patronen


-   **Werk stromen met complexe else-als voorwaardelijke logica**  
    
    In plaats van voor waarden te gebruiken, raden we u aan in plaats daarvan de [Schakel actie](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-switch-statement#add-switch-statement) te gebruiken.

-   **Werk stromen die worden uitgevoerd vanuit de invoeg toepassing/code**  
    
    Het is raadzaam om de stroom opnieuw te ontwerpen om te beginnen met triggers.

    -   Gebruik Common Data Service triggers om stromen uit te voeren op basis van gebeurtenissen.

    -   Voor het uitvoeren van stromen op basis van gebeurtenissen in een externe service, maakt gebruik van meer dan 260 out-of-Box-connectors.

    -   Voor scenario's waarbij een connector die u nodig hebt, niet beschikbaar is, kunt u eenvoudig uw eigen aangepaste connector maken [om aangepaste connectors te maken](https://docs.microsoft.com/connectors/custom-connectors/define-blank).

    -   Als er sprake is van scenario's waarin u uw stroom niet kunt activeren met behulp van Common Data Service connector, een van de out-of-Box-connectors of het maken van een aangepaste connector, maakt u gebruik van de [trigger wanneer een HTTP-aanvraag wordt ontvangen](https://docs.microsoft.com/azure/connectors/connectors-native-reqres#use-the-http-request-trigger) om de stroom aan te roepen

-   **Werk stromen die recursief worden uitgevoerd**  
    
    Gebruik in plaats daarvan de [do-until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) of [Toep assen op elke](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#foreach-loop) lus in stromen

-   **Werk stromen die een lijst met records nodig hebben**  
    
    Gebruik de actie **records weer geven** . Wanneer u deze actie gebruikt, definieert u de filter criteria voor records met de OData-syntaxis om de actie te optimaliseren door het aantal records dat u wilt ophalen, te minimaliseren.

-   **Werk stromen die in de slaap stand worden uitgevoerd volgens een planning**  
    
    Gebruik de trigger voor **terugkeer patroon** om op gezette tijden bedrijfs logica uit te voeren.

-   **Werk stromen waarvoor uitvoeringen zijn beheerd om ervoor te zorgen dat activiteiten in één trans actie worden uitgevoerd**  
    
    [Gebruik de [Actieset](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/automated-flows-support-change-sets-common-data-service) om ervoor te zorgen dat alle acties in de groep worden uitgevoerd als één, atomische eenheid waarin alles slaagt of mislukt als een Group. Als een van de acties in een wijzigingsset is mislukt, worden wijzigingen die zijn aangebracht door voltooide bewerkingen teruggedraaid.

-   **Werk stroom uitvoeringen controleren op fouten**  
    
    In Microsoft Flow gebruikt u de **instelling uitvoeren-na** voor een actie om deze te configureren om te worden uitgevoerd wanneer de vorige actie mislukt. U kunt bijvoorbeeld een Microsoft Flow mobiele melding verzenden wanneer de actie **een record bijwerken** mislukt of er een time-out optreedt.

## <a name="faqs"></a>Faq's


-   **Ik heb een Dynamics 365-licentie. Kan ik Microsoft Flow gebruiken?**

    Elke Dynamics 365-gebruiker heeft recht op het gebruik van Microsoft Flow. Bekijk onze licentie gegevens: <https://flow.microsoft.com/pricing/>

-   **Hoe vaak kan mijn stromen worden geactiveerd?**

    -   Dynamics 365 (of Common Data Service) stromen worden bijna in realtime uitgevoerd na de trigger, omdat ze webhooks gebruiken (geen polling vereist)

    -   Net als bij directe API-toegang zijn er beperkingen/limieten in het systeem, dat hier volledig is gedocumenteerd: <https://docs.microsoft.com/flow/limits-and-config>

    -   Met name een limiet van 100.000-acties per 5 minuten, per stroom, en één lus in een stroom kan niet meer dan 100.000 items tegelijk verwerken

    -   Maximum van 6GB van door Voer per 5 minuten

-   **Hoe lang kan één stroom worden uitgevoerd?**  
    
    Er wordt een time-out voor één stroom uitgevoerd na 30 dagen.

-   **Hoe kan ik mijn stromen verplaatsen tussen omgevingen?**  
    
    Net als bij klassieke werk stromen kunt u stromen maken in oplossingen ter ondersteuning van de volledige levens cyclus van toepassingen voor processen.

-   **Worden Microsoft Flow afhankelijkheden bijgehouden in Common Data Service?**  
    
    Net als andere onderdelen in een oplossing worden alle afhankelijkheden voor stromen in oplossingen bijgehouden in Common Data Service.

-   **Hoe zit het met synchrone werk stromen?** 
 
    U moet de behoefte aan synchrone werk stromen opnieuw evalueren om te bepalen of de doel stelling of delen van de werk stroom kunnen worden gemaakt met behulp van een stroom. Met name zien we van onze telemetrie dat synchrone werk stromen een belang rijke bijdrage leveren aan de prestaties van de algemene eind gebruiker. Voor veel toepassingen is het beter om deze acties uit te splitsen als asynchroon, zodat de gebruiker de activiteit kan voortzetten terwijl Microsoft Flow de actie blijft volt ooien.

-   **Met Microsoft Flow worden mijn gegevens binnen de regio bewaard (dat wil zeggen, dezelfde regio als mijn Dynamics 365 of Common Data Service omgeving)?**  
    
    Ja, Microsoft Flow maakt altijd gebruik van dezelfde regio als Common Data Service.

-   **Moet ik wijzigingen in de proxy/firewall aanbrengen?**  
    
    Raadpleeg de [Naslag informatie over de IP-adres configuratie](limits-and-config.md#ip-address-configuration) om te bepalen of u wijzigingen in de proxy/firewall moet aanbrengen.
