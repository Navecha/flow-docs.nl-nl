---
title: Een aangepaste actie maken | MicrosoftDocs
description: Gebruik aangepaste acties wanneer u een reeks opdrachten in het systeem wilt automatiseren. Acties breiden de beschik bare woorden lijst voor ontwikkel aars uit om bedrijfs processen te expresseren.
ms.custom: ''
ms.date: 08/06/2018
ms.reviewer: matp
ms.service: flow
ms.topic: article
author: msftman
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8b00e6e0b3ca2da357eb98d1b6de7756ff5cc75
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546828"
---
# <a name="create-a-custom-action"></a>Een aangepaste actie maken
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Gebruik aangepaste acties wanneer u een reeks opdrachten in het systeem wilt automatiseren. Acties breiden de beschik bare woorden lijst voor ontwikkel aars uit om bedrijfs processen te expresseren. Met kern woorden als Create, update, DELETE en Assign die door het systeem worden aangelegd, gebruikt een actie die kern woorden om meer inzichten-termen te maken, zoals goed keuren, escaleren, route ring of planning. Als de definitie van een bedrijfs proces verandert, kan iemand die geen ontwikkelaar is de aangepaste actie bewerken, zodat de code niet hoeft te worden gewijzigd.  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Een actie maken  
  
> [!IMPORTANT]
>  Als u een actie maakt die moet worden opgenomen als onderdeel van een oplossing die wordt gedistribueerd, maakt u deze in de context van de oplossing. Ga naar **[instellingen](/powerapps/maker/model-driven-apps/advanced-navigation#settings)**  > **oplossingen** en zoek de onbeheerde oplossing waarvan deze actie deel zal uitmaken. Selecteer vervolgens in de menu balk **nieuwe** > **proces**. Dit zorgt ervoor dat het aanpassings voorvoegsel dat is gekoppeld aan de naam van de actie consistent is met andere onderdelen in de oplossing. Nadat u de actie hebt gemaakt, kunt u het voor voegsel niet wijzigen.  
  
 Net als werk stroom processen hebben acties de volgende eigenschappen in het dialoog venster **proces maken** .  
  
 **Proces naam**  
 Nadat u een naam voor het proces hebt opgegeven, wordt er een unieke naam voor gemaakt door spaties of speciale tekens uit de proces naam te verwijderen.  
  
 **Rubriek**  
 Deze eigenschap bepaalt dat dit een actie proces is. U kunt dit niet wijzigen nadat u het proces hebt opgeslagen.  
  
 **Vennootschap**  
 Met actie processen kunt u een entiteit selecteren om context voor de werk stroom op te geven, net als andere typen processen, maar u hebt ook de optie **geen (globaal)** te kiezen. Gebruik deze als voor uw actie niet de context van een specifieke entiteit is vereist. U kunt dit niet wijzigen nadat u het proces hebt opgeslagen.  
  
 **Voert**  
 Gebruik deze eigenschap om te kiezen of u een geheel nieuwe actie wilt maken of een bestaande sjabloon wilt starten.  
 
In tegens telling tot werk stroom processen hoeft u de volgende opties niet in te stellen:  
  
- **Starten wanneer**: acties worden gestart wanneer de code het bericht aanroept dat voor hen is gegenereerd.  
  
- **Bereik**: acties worden altijd uitgevoerd in de context van de aanroepende gebruiker.  
  
- **Uitvoeren op de achtergrond**: acties zijn altijd realtime-werk stromen.  
  
Acties hebben ook iets dat werk stroom processen niet: invoer-en uitvoer argumenten hebben.

> [!NOTE]
> U kunt een aangepaste actie inschakelen vanuit een werk stroom zonder code te schrijven. Meer informatie: [aangepaste acties aanroepen vanuit een werk stroom](invoke-custom-actions-workflow-dialog.md).
 
<a name="edit"></a>   
## <a name="edit-an-action"></a>Een actie bewerken  
 U moet de processen deactiveren voordat u ze kunt bewerken.  
  
 U kunt een actie bewerken die is gemaakt als onderdeel van een onbeheerde oplossing of die is opgenomen in een oplossing die in uw organisatie is geïnstalleerd. Als de oplossing een beheerde oplossing is, kunt u deze mogelijk niet bewerken. De oplossings Uitgever beschikt over de mogelijkheid om de beheerde eigenschappen te bewerken, zodat de actie die met een beheerde oplossing wordt geïnstalleerd, niet kan worden bewerkt.  
  
 Wanneer een actie wordt opgeslagen, wordt een unieke naam gegenereerd op basis van de proces naam. Voor deze unieke naam is het aanpassings voorvoegsel van de oplossings uitgever toegevoegd. Dit is de naam van het bericht dat een ontwikkelaar in de code zal gebruiken.  
  
 Wanneer u een actie bewerkt, hebt u de volgende opties:  
  
 **Proces naam**  
 Nadat het proces is gemaakt en de unieke naam is gegenereerd op basis van de proces naam, kunt u de proces naam bewerken. Mogelijk wilt u een naamgevings Conventie Toep assen om het gemakkelijker te maken om specifieke processen te vinden.  
  
 **Unieke naam**  
 Wanneer een actie wordt opgeslagen, wordt een unieke naam gegenereerd op basis van de proces naam. Deze unieke naam bevat het aanpassings voorvoegsel van de oplossings uitgever die is toegevoegd. Dit is de naam van het bericht dat een ontwikkelaar in de code zal gebruiken. Wijzig deze unieke naam niet als het proces is geactiveerd en de code op dat punt verwacht om de actie aan te roepen met deze naam.  
  
> [!IMPORTANT]
>  Nadat de actie is geactiveerd en code is geschreven om een unieke naam te gebruiken, mag de unieke naam niet worden gewijzigd zonder ook de code te wijzigen waarmee ernaar wordt verwezen.  
  
 **Terugdraaien inschakelen**  
 Over het algemeen worden processen die ondersteuning bieden voor trans acties, ongedaan maken (of terugdraaien) van de gehele bewerking als een deel ervan mislukt. Er zijn enkele uitzonde ringen. Sommige acties die ontwikkel aars kunnen uitvoeren in de code die door de actie wordt geïnitieerd, bieden mogelijk geen ondersteuning voor trans acties. Als de code bijvoorbeeld acties uitvoert in andere systemen die buiten het bereik van de trans actie vallen. Deze kunnen niet worden teruggedraaid door de actie die wordt uitgevoerd in een app. Sommige berichten in het platform bieden geen ondersteuning voor trans acties. Maar alles wat u gewoon kunt doen met de gebruikers interface van de actie, ondersteunt trans acties. Alle acties die deel uitmaken van een real-time werk stroom worden in de trans actie beschouwd, maar met acties kunt u deze optie uit te kiezen.  
  
 Neem contact op met de ontwikkelaar die dit bericht gaat gebruiken om te bepalen of het moet worden gebruikt in een trans actie of niet. Over het algemeen is een actie in trans actie als de acties die door het bedrijfs proces worden uitgevoerd, niet zinvol zijn, tenzij al deze zijn voltooid. Het klassieke voor beeld is het overdragen van fondsen tussen twee Bank rekeningen. Als u de fondsen van het ene account intrekt, moet u ze in de andere aanroepen. Als er een storing optreedt, moeten beide mislukken.  
  
> [!NOTE]
>  U kunt terugdraaien niet inschakelen als een aangepaste actie rechtstreeks vanuit een werk stroom wordt aangeroepen. U kunt terugdraaien inschakelen als een actie wordt geactiveerd door een PowerApps-webservices bericht.  
  
 **Activeren als**  
 Net als bij alle processen kunt u het proces als een sjabloon activeren en dit als een geavanceerd start punt gebruiken voor processen die een vergelijkbaar patroon volgen.  
  
 **Proces argumenten definiëren**  
 In dit gebied geeft u de gegevens op die de actie verwacht te starten en welke gegevens uit de actie worden door gegeven. Meer informatie: [proces argumenten definiëren](#define-process-arguments)  
  
 **Fasen en stappen toevoegen**  
 Net als bij andere processen geeft u op welke acties moeten worden uitgevoerd en wanneer ze moeten worden uitgevoerd. Meer informatie: [fasen en stappen toevoegen](#add-stages-and-steps)

<a name="BKMK_DefineProcessArgs"></a>   
## <a name="define-process-arguments"></a>Proces argumenten definiëren  
 Wanneer een ontwikkelaar een bericht gebruikt, kunnen ze beginnen met bepaalde gegevens die ze in het bericht kunnen door geven. Als u bijvoorbeeld een nieuwe case record wilt maken, kan de waarde van de case-titel worden door gegeven als een invoer argument.  
  
 Wanneer het bericht is voltooid, moet de ontwikkelaar mogelijk bepaalde gegevens door geven die zijn gewijzigd of door het bericht zijn gegenereerd naar een andere bewerking in de code. Deze gegevens zijn het argument uitvoer.  
  
 Invoer-en uitvoer argumenten moeten een naam, een type en enige informatie bevatten over of het argument altijd vereist is. U kunt ook een beschrijving opgeven.  
  
 De naam van het bericht en de informatie over alle proces argumenten vertegenwoordigen de hand tekening voor het bericht. Nadat een actie is geactiveerd en wordt gebruikt in code, mag de hand tekening niet worden gewijzigd. Als deze hand tekening wordt gewijzigd, mislukt de code die gebruikmaakt van het bericht. De enige uitzonde ring hierop kan een van de para meters wijzigen zodat deze niet altijd vereist is.  
  
 U kunt de volg orde van de argumenten wijzigen door ze te sorteren of omhoog of omlaag te verplaatsen, omdat de argumenten worden geïdentificeerd op naam, niet op basis van de volg orde. Als de beschrijving wordt gewijzigd, wordt de code ook niet onderbroken met het bericht.  
  
### <a name="action-process-argument-types"></a>Argument typen actie proces  
 In de volgende tabel worden de argument typen van het actie proces beschreven.  
  
|Voert|Beschrijvingen|  
|----------|-----------------|  
|True|Een `true`-of `false` waarde.|  
|DateTime|Een waarde die datum-en tijd gegevens opslaat.|  
|Komma|Een numerieke waarde met decimale precisie. Wordt gebruikt als nauw keurigheid zeer belang rijk is.|  
|Vennootschap|Een record voor de opgegeven entiteit. Wanneer u entiteit selecteert, wordt de vervolg keuzelijst ingeschakeld en kunt u het entiteits type selecteren.|  
|EntityCollection|Een verzameling entiteit records.|  
|EntityReference|Een object dat de naam, ID en het type van een entiteits record bevat waarmee het uniek wordt geïdentificeerd. Wanneer u EntityReference selecteert, wordt de vervolg keuzelijst ingeschakeld en kunt u het entiteits type selecteren.|  
|Float|Een numerieke waarde met decimale precisie. Wordt gebruikt wanneer gegevens afkomstig zijn uit een meting die niet volledig nauw keurig is.|  
|geheeltallige|Een geheel getal.|  
|financieel|Een waarde die gegevens over een geld hoeveelheid opslaat.|  
|Selectie lijst|Een waarde die een optie voor een Optionset-kenmerk vertegenwoordigt.|  
|tekenreeksexpressie|Een tekst waarde.|  
  
> [!NOTE]
> Waarde voor de argumenten **EntityCollection** kan niet worden ingesteld in de gebruikers interface voor voor waarden of acties. Deze zijn bedoeld voor gebruik door ontwikkel aars in aangepaste code. Meer informatie: [uw eigen acties maken](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Fasen en stappen toevoegen  
 Acties zijn een soort proces dat lijkt op real time-werk stromen. Alle stappen die kunnen worden gebruikt in realtime werk stromen kunnen worden gebruikt in acties. Zie [werk stroom stadiums en stappen](configure-workflow-steps.md)voor informatie over de stappen die kunnen worden gebruikt voor realtime-werk stromen en-acties.  
  
 Naast de stappen die kunnen worden gebruikt voor realtime werk stromen, hebben acties ook de stap **waarde toewijzen** .  In acties kunnen deze alleen worden gebruikt om uitvoer argumenten in te stellen. U kunt de Formulierenassistent gebruiken om uitvoer argumenten in te stellen op specifieke waarden of, meer waarschijnlijk, op waarden van de record waarmee de actie wordt uitgevoerd, records die betrekking hebben op deze record met een veel-op-een-relatie, records die zijn gemaakt in een eerdere stap of waarden die maken deel uit van het proces.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Aangepaste acties vanuit een werk stroom aanroepen](invoke-custom-actions-workflow-dialog.md)   

 
 
