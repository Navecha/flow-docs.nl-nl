---
title: Acties voor werkstromen configureren in PowerApps | Microsoft Docs
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
author: Mattp123
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
caps.latest.revision: 19
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c1b8686000b7723f2d942f3c6c5ebe685d98429d
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64458757"
---
# <a name="configure-custom-actions-from-a-workflow"></a>Aangepaste acties in een werkstroom configureren

U kunt een aangepaste actie inschakelen vanuit een werkstroom zonder code te schrijven. Meer informatie: [Aangepaste acties op basis van een werkstroom aanroepen](invoke-custom-actions-workflow-dialog.md).  
  
 U kunt ook een actie maken zodat een ontwikkelaar deze kan gebruiken in code of mogelijk moet u een actie aanpassen die eerder is gedefinieerd. Net als bij werkstroomprocessen moet u rekening houden met het volgende:  
  
-   Wat moet de actie doen?  
  
-   Onder welke voorwaarden moet de actie worden uitgevoerd?  
  
 
In tegenstelling tot werkstroomprocessen hoeft u de volgende opties niet in te stellen:  
  
- **Starten wanneer**: Acties starten wanneer code het bericht aanroept dat voor de acties is gegenereerd.  
  
- **Bereik**: Acties worden altijd uitgevoerd in de context van de aanroepende gebruiker.  
  
- **Op de achtergrond uitvoeren**: Acties zijn altijd realtime-werkstromen.  
  
Acties hebben ook iets dat werkstroomprocessen niet hebben: invoer- en uitvoerargumenten. Meer informatie: [Procesargumenten definiëren](configure-actions.md#BKMK_DefineProcessArgs)  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Een actie maken  
  
> [!IMPORTANT]
>  Als u een actie maakt die deel gaat uitmaken van een oplossing die wordt gedistribueerd, moet u de actie in de context van de oplossing maken. Ga naar **[Instellingen](/powerapps/maker/model-driven-apps/advanced-navigation#settings)** > **Oplossingen** en zoek de onbeheerde oplossing waarvan deze actie deel gaat uitmaken. Selecteer vervolgens **Nieuw** > **Verwerken** op de menubalk. Dit zorgt ervoor dat het aanpassingsvoorvoegsel dat is gekoppeld aan de naam van de actie, consistent is met andere onderdelen in de oplossing. Nadat u de actie hebt gemaakt, kunt u het voorvoegsel niet meer wijzigen.  
  
 Acties hebben, net als werkstroomprocessen, de volgende eigenschappen in het dialoogvenster **Proces maken**.  
  
 **Procesnaam**  
 Nadat u een naam voor het proces hebt ingevoerd, wordt hiervoor een unieke naam gemaakt door eventuele spaties of speciale tekens uit de procesnaam te verwijderen.  
  
 **Categorie**  
 Deze eigenschap bepaalt dat dit een actieproces is. U kunt dit niet meer wijzigen nadat u het proces hebt opgeslagen.  
  
 **Entiteit**  
 Met actieprocessen kunt u een entiteit selecteren die context biedt voor de werkstroom, net als andere typen processen, maar hebt u ook de mogelijkheid om **Geen (algemeen)** te kiezen. Gebruik deze optie als voor uw actie niet de context van een bepaalde entiteit vereist is. U kunt dit niet meer wijzigen nadat u het proces hebt opgeslagen.  
  
 **Type**  
 Gebruik deze eigenschap om te kiezen of u een volledig nieuwe actie wilt maken of vanuit een bestaande sjabloon wilt starten.  
  
<a name="edit"></a>   
## <a name="edit-an-action"></a>Een actie bewerken  
 U moet processen deactiveren voordat u ze kunt bewerken.  
  
 U kunt een actie bewerken die is gemaakt als onderdeel van een niet-beheerde oplossing of die in een oplossing is opgenomen die is geïnstalleerd in uw organisatie. Als de oplossing een beheerde oplossing is, is het misschien niet mogelijk om deze te bewerken. De oplossingsuitgever heeft de mogelijkheid de beheerde eigenschappen te bewerken, zodat de actie die is geïnstalleerd met een beheerde oplossing niet kan worden bewerkt.  
  
 Wanneer een actie wordt opgeslagen, wordt er een unieke naam gegenereerd op basis van de procesnaam. Deze unieke naam bevat het aanpassingsvoorvoegsel dat door de oplossingsuitgever is toegevoegd. Dit is de naam van het bericht dat door een ontwikkelaar in code wordt gebruikt.  
  
 Tijdens het bewerken van een actie hebt u de volgende opties:  
  
 **Procesnaam**  
 Nadat het proces is gemaakt en de unieke naam is gegenereerd van de procesnaam, kunt u de procesnaam bewerken. Het is raadzaam om een naamconventie toe te passen om het zoeken naar specifieke processen eenvoudiger te maken.  
  
 **Unieke naam**  
 Wanneer een actie wordt opgeslagen, wordt er een unieke naam gegenereerd op basis van de procesnaam. Deze unieke naam bevat het aanpassingsvoorvoegsel dat door de oplossingsuitgever is toegevoegd. Dit is de naam van het bericht dat door een ontwikkelaar in code wordt gebruikt. Wijzig deze unieke naam niet als het proces is geactiveerd en er code is die verwacht dat de actie met deze naam wordt aangeroepen.  
  
> [!IMPORTANT]
>  Nadat de actie is geactiveerd en code is geschreven voor het gebruiken van een unieke naam, mag de unieke naam niet meer worden gewijzigd zonder ook de code te wijzigen die ernaar verwijst.  
  
 **Terugdraaien inschakelen**  
 Over het algemeen zullen processen die transacties ondersteunen de gehele bewerking ‘ongedaan maken' (of terugdraaien) als een deel hiervan mislukt. Hierop zijn enkele uitzonderingen. Sommige acties die ontwikkelaars in code plaatsen die door een actie wordt gestart, bieden mogelijk geen ondersteuning voor transacties. Dit is bijvoorbeeld het geval als de code acties uitvoert in andere systemen die buiten het bereik van de transactie vallen. Deze acties kunnen niet worden teruggedraaid door de actie die in een app wordt uitgevoerd. Bepaalde berichten op het platform bieden geen ondersteuning voor transacties. Maar alles wat u kunt doen via de gebruikersinterface van de actie, is geschikt voor gebruik met transacties. Alle acties die deel uitmaken van een realtime-werkstroom, worden als in transactie beschouwd, maar met acties hebt u de mogelijkheid om dit uit te schakelen.  
  
 Neem contact op met de ontwikkelaar die dit bericht gaat gebruiken om te bepalen of dit wel of niet in transactie moet zijn. Over het algemeen dient een actie in transactie te zijn als de acties die worden uitgevoerd door het bedrijfsproces niet zinvol zijn, tenzij deze allemaal met succes zijn voltooid. Het klassieke voorbeeld is het overbrengen van fondsen van de ene naar de andere bankrekening. Als u fondsen van de ene rekening haalt, moet u deze op de andere storten. Als een van beide niet lukt, moeten beide geen doorgang vinden.  
  
> [!NOTE]
>  U kunt terugdraaien niet inschakelen als een aangepaste actie rechtstreeks vanuit de werkstroom wordt aangeroepen. U kunt terugdraaien inschakelen als een actie wordt geactiveerd door een bericht van PowerApps-webservices.  
  
 **Activeren als**  
 U kunt het proces, net als alle processen, als sjabloon activeren en gebruiken als een geavanceerd beginpunt voor processen die een vergelijkbaar patroon volgen.  
  
 **Procesargumenten definiëren**  
 In dit gebied moet u gegevens opgeven die de actie verwacht te starten en welke gegevens zullen worden doorgegeven vanuit de actie. Meer informatie: [Procesargumenten definiëren](configure-actions.md#BKMK_DefineProcessArgs)  
  
 **Fasen, voorwaarden en acties toevoegen**  
 Net als bij andere processen geeft u op welke acties moeten worden uitgevoerd en wanneer dit moet gebeuren. Meer informatie: [Fasen, voorwaarden en acties toevoegen](configure-actions.md#BKMK_AddStagesConditionsAndActions)

<a name="BKMK_DefineProcessArgs"></a>   
### <a name="define-process-arguments"></a>Procesargumenten definiëren  
 Als een ontwikkelaar een bericht gebruikt, kan er worden begonnen met enkele gegevens die aan het bericht kunnen worden doorgegeven. Voor het maken van een nieuwe caserecord kan er bijvoorbeeld sprake zijn van een casetitelwaarde die als invoerargument wordt ingegeven.  
  
 Wanneer het bericht is voltooid, moet de ontwikkelaar wellicht bepaalde gegevens die zijn gewijzigd of die door het bericht zijn gegenereerd aan een andere bewerking in de code doorgeven. Deze gegevens zijn het uitvoerargument.  
  
 Zowel het invoer- als het uitvoerargument moet de beschikking hebben over een naam, een type en de informatie of het argument altijd vereist is. U kunt ook een beschrijving opgeven.  
  
 De naam van het bericht en de informatie over alle procesargumenten vormen de ‘handtekening’ van het bericht. Nadat een actie is geactiveerd en in code wordt gebruikt, mag u de handtekening niet meer wijzigen. Als deze handtekening wordt gewijzigd, mislukt code die gebruikmaakt van het bericht. De enige uitzondering hierop kan zijn wanneer u een van de parameters wijzigt, zodat het argument niet altijd nodig is.  
  
 U kunt de volgorde van de argumenten wijzigen door deze te sorteren of ze omhoog of omlaag te verplaatsen, omdat de argumenten worden geïdentificeerd op basis van de naam, niet de volgorde. Door wijzigingen in de beschrijving zal eveneens geen code worden verbroken die van het bericht gebruikmaakt.  
  
#### <a name="action-process-argument-types"></a>Typen procesargumenten voor acties  
 In de volgende tabel zijn de typen procesargumenten voor acties beschreven.  
  
|Type|Beschrijving|  
|----------|-----------------|  
|Booleaans|Een waarde `true` of `false`.|  
|DateTime|Een waarde waarmee datum- en tijdgegevens worden opgeslagen.|  
|Decimal|Een numerieke waarde met decimale precisie. Dit type wordt gebruikt wanneer precisie erg belangrijk is.|  
|Entity|Een record voor de opgegeven entiteit. Wanneer u dit type selecteert, wordt de vervolgkeuzelijst ingeschakeld waarin u het type entiteit kunt selecteren.|  
|EntityCollection|Een verzameling entiteitsrecords.|  
|EntityReference|Een object met de naam, de id en het type entiteitsrecord dat een unieke identificatie vormt. Wanneer u EntityReference selecteert, wordt de vervolgkeuzelijst ingeschakeld waarin u het type entiteit kunt selecteren.|  
|Float|Een numerieke waarde met decimale precisie. Dit type wordt gebruikt wanneer gegevens afkomstig zijn van een meting die niet helemaal nauwkeurig is.|  
|Integer|Een geheel getal.|  
|Money|Een waarde waarin gegevens over een geldbedrag worden opgeslagen.|  
|Picklist|Een waarde die een optie voor een OptionSet-kenmerk vertegenwoordigt.|  
|String|Een tekstwaarde.|  
  
> [!NOTE]
> Waarden voor **EntityCollection** kunnen niet worden ingesteld in de gebruikersinterface voor voorwaarden of acties. Deze worden door ontwikkelaars in aangepaste code voor gebruik beschikbaar gesteld. Meer informatie: [Uw eigen acties maken](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Fasen en stappen toevoegen  
 Acties zijn een type proces dat erg vergelijkbaar is met realtime-werkstromen. Alle stappen die kunnen worden gebruikt in realtime-werkstromen kunnen worden gebruikt in acties. Zie [Fasen en stappen voor werkstromen](configure-workflow-steps.md) voor meer informatie over de stappen die kunnen worden gebruikt voor zowel realtime-werkstromen als acties.  
  
 Naast de stappen die kunnen worden gebruikt voor realtime werkstromen, kunnen acties ook de stap **Waarde toewijzen** hebben.  In acties kunnen deze alleen worden gebruikt om uitvoerargumenten in te stellen. U kunt de Formulierenassistent gebruiken om uitvoerargumenten in te stellen op specifieke waarden of, wat waarschijnlijker is, op waarden uit de record waarop de actie wordt uitgevoerd, records gerelateerd aan die record met een veel-op-een-relatie, records die in een eerdere stap zijn gemaakt of waarden die deel uitmaken van het proces zelf.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Acties](actions.md)  

 [Aangepaste acties op basis van een werkstroom aanroepen](invoke-custom-actions-workflow-dialog.md)   
 [Realtime-werkstromen en acties controleren](monitor-manage-processes.md#BKMK_MonitorSyncWorkflows)
 
 
