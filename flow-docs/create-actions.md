---
title: Een aangepaste actie maken | MicrosoftDocs
description: Gebruik aangepaste acties als u een reeks opdrachten in het systeem wilt automatiseren. Acties vormen een uitbreiding op het vocabulaire dat beschikbaar is voor ontwikkelaars om bedrijfsprocessen uit te drukken.
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
ms.openlocfilehash: f1b51a48d7355684d2c6883bbf0db12853f686eb
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690233"
---
# <a name="create-a-custom-action"></a>Een aangepaste actie maken

Gebruik aangepaste acties als u een reeks opdrachten in het systeem wilt automatiseren. Acties vormen een uitbreiding op het vocabulaire dat beschikbaar is voor ontwikkelaars om bedrijfsprocessen uit te drukken. De belangrijkste bewerkingen zoals Maken, Bijwerken, Verwijderen en Toewijzen die door het systeem worden opgegeven, worden gebruikt voor het maken van meer expressieve bewerkingen, zoals Goedkeuren, Escaleren, Routeren of Plannen. Als de definitie van een bedrijfsproces wordt gewijzigd, kan iemand die geen ontwikkelaar is de aangepaste actie bewerken zodat de code niet hoeft te worden gewijzigd.  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Een actie maken  
  
> [!IMPORTANT]
>  Als u een actie maakt die deel gaat uitmaken van een oplossing die wordt gedistribueerd, kunt u deze in de context van de oplossing maken. Ga naar **[Instellingen](/powerapps/maker/model-driven-apps/advanced-navigation#settings)** > **Oplossingen** en ga naar de onbeheerde oplossing waarvan deze actie deel gaat uitmaken. Selecteer vervolgens in de menubalk **Nieuw** > **Verwerken**. Dit zorgt ervoor dat het aanpassingsvoorvoegsel dat is gekoppeld aan de naam van de actie consistent is met andere onderdelen in de oplossing. Nadat u de actie hebt gemaakt, kunt u het voorvoegsel niet meer wijzigen.  
  
 Acties hebben, net als werkstroomprocessen, de volgende eigenschappen in het dialoogvenster **Proces maken**.  
  
 **Procesnaam**  
 Nadat u een naam voor het proces hebt ingevoerd, wordt hiervoor een unieke naam gemaakt door eventuele spaties of speciale tekens uit de procesnaam te verwijderen.  
  
 **Categorie**  
 Deze eigenschap bepaalt dat dit een actieproces is. U kunt dit niet wijzigen nadat u het proces hebt opgeslagen.  
  
 **Entiteit**  
 Met actieprocessen kunt u een entiteit selecteren die context biedt voor de werkstroom, net als andere typen processen, maar u hebt ook de mogelijkheid om **Geen (wereldwijd)** te kiezen. Gebruik deze optie als voor uw actie niet de context van een bepaalde entiteit vereist is. U kunt dit niet wijzigen nadat u het proces hebt opgeslagen.  
  
 **Type**  
 Gebruik deze eigenschap om te kiezen of u een volledig nieuwe actie wilt maken of u vanuit een bestaande sjabloon wilt starten.  
 
In tegenstelling tot werkstroomprocessen hoeft u de volgende opties niet in te stellen:  
  
- **Starten wanneer**: acties starten wanneer de code het bericht aanroept dat ervoor wordt gegenereerd.  
  
- **Bereik**: acties worden altijd uitgevoerd in de context van de aanroepende gebruiker.  
  
- **Op de achtergrond uitvoeren**: acties zijn altijd realtime werkstromen.  
  
Acties hebben iets dat werkstroomprocessen niet hebben: invoer- en uitvoerargumenten.

> [!NOTE]
> U kunt een aangepaste actie inschakelen vanuit een werkstroom zonder code te schrijven. Meer informatie: [Aangepaste acties aanroepen vanuit een werkstroom](invoke-custom-actions-workflow-dialog.md).
 
<a name="edit"></a>   
## <a name="edit-an-action"></a>Een actie bewerken  
 U moet processen deactiveren voordat u ze kunt bewerken.  
  
 U kunt een actie bewerken die is gemaakt als onderdeel van een niet-beheerde oplossing of in een oplossing is opgenomen die is geïnstalleerd in uw organisatie. Als de oplossing een beheerde oplossing is, is het misschien niet mogelijk om deze te bewerken. De oplossingsuitgever heeft de mogelijkheid voor het bewerken van de beheerde eigenschappen, zodat de actie die is geïnstalleerd met een beheerde oplossing niet kan worden bewerkt.  
  
 Wanneer een actie wordt opgeslagen, wordt een unieke naam gegenereerd op basis van de procesnaam. Deze unieke naam heeft het aanpassingsvoorvoegsel dat van de kant van de oplossingsuitgever is toegevoegd. Dit is de naam van het bericht dat door een ontwikkelaar in de code wordt gebruikt.  
  
 Tijdens het bewerken van een actie hebt u de volgende opties:  
  
 **Procesnaam**  
 Nadat het proces wordt gemaakt en de unieke naam van de procesnaam wordt gegenereerd, kunt u de procesnaam bewerken. Het is raadzaam om een naamconventie toe te passen om het zoeken naar specifieke processen eenvoudiger te maken.  
  
 **Unieke naam**  
 Wanneer een actie wordt opgeslagen, wordt een unieke naam gegenereerd op basis van de procesnaam. Deze unieke naam heeft een aanpassingsvoorvoegsel dat van de kant van de oplossingsuitgever is toegevoegd. Dit is de naam van het bericht dat door een ontwikkelaar in de code wordt gebruikt. Wijzig deze unieke naam niet als het proces is geactiveerd en de code is ingesteld welke de actie via deze naam gaat aanroepen.  
  
> [!IMPORTANT]
>  Nadat de actie is geactiveerd en de code wordt geschreven voor het gebruiken van een unieke naam, mag de unieke naam niet worden gewijzigd zonder de code te wijzigen die ernaar verwijst.  
  
 **Terugdraaien inschakelen**  
 Over het algemeen zullen processen die ondersteuning bieden aan transacties de gehele bewerking ‘ongedaan maken' (of terugdraaien) als een deel hiervan mislukt. Hierop zijn enkele uitzonderingen. Sommige acties die ontwikkelaars in code plaatsen die door de actie wordt gestart, bieden mogelijk geen ondersteuning voor transacties. Als bijvoorbeeld de code acties uitvoert in andere systemen die buiten het bereik vallen van de transactie. Deze kunnen niet worden teruggedraaid door de actie die in een app wordt uitgevoerd. Bepaalde berichten in het platform bieden geen ondersteuning voor transacties. Maar alles wat u alleen via de gebruikersinterface van de actie kunt doen, ondersteunt transacties. Alle acties die deel uitmaken van een realtime werkstroom, worden als in transactie beschouwd, maar met acties hebt u de mogelijkheid om hieraan geen gevolg te geven.  
  
 U dient contact op te nemen met de ontwikkelaar die dit bericht gebruikt om te bepalen of deze wel of niet in transactie moet zijn. Over het algemeen dient een actie in transactie te zijn als de acties die worden uitgevoerd door het bedrijfsproces niet zinvol zijn, tenzij deze allemaal met succes zijn voltooid. Het klassieke voorbeeld is het overbrengen van fondsen van de ene naar de andere bankrekening. Als u fondsen van de ene rekening haalt, moet u ze op de andere storten. Als een van beide niet lukt, moeten beide geen doorgang vinden.  
  
> [!NOTE]
>  U kunt Terugdraaien niet inschakelen als een aangepaste actie rechtstreeks vanuit de werkstroom wordt aangeroepen. U kunt Terugdraaien inschakelen als een actie wordt geactiveerd door een bericht van PowerApps-webservices.  
  
 **Activeren als**  
 U kunt het proces, net als alle processen, als sjabloon activeren en gebruiken als een geavanceerd beginpunt voor processen die een vergelijkbaar patroon volgen.  
  
 **Procesargumenten definiëren**  
 In dit gebied moet u gegevens opgeven die de actie verwacht te starten en welke gegevens zullen worden doorgegeven vanuit de actie. Meer informatie: [Procesargumenten definiëren](#define-process-arguments)  
  
 **Fasen en stappen toevoegen**  
 Net als bij andere processen geeft u op welke acties moeten worden uitgevoerd en wanneer deze moeten worden uitgevoerd. Meer informatie: [Fasen en stappen toevoegen](#add-stages-and-steps)

<a name="BKMK_DefineProcessArgs"></a>   
## <a name="define-process-arguments"></a>Procesargumenten definiëren  
 Als een ontwikkelaar gebruikmaakt van een bericht, kan deze beginnen met enkele gegevens die in het bericht kunnen worden doorgegeven. Voor het maken van een nieuw caserecord kan er bijvoorbeeld sprake zijn van een casetitelwaarde die als invoerargument wordt ingegeven.  
  
 Wanneer het bericht is voltooid, moet de ontwikkelaar wellicht bepaalde gegevens die zijn gewijzigd of die door het bericht zijn gegenereerd aan een andere bewerking in de code doorgeven. Deze gegevens zijn het uitvoerargument.  
  
 Zowel het invoer- als het uitvoerargument moet de beschikking hebben over een naam, een type en de informatie of het argument altijd is vereist. U kunt ook een beschrijving opgeven.  
  
 De naam van het bericht en de informatie over alle procesargumenten vormen de ‘handtekening’ van het bericht. Wanneer een actie is geactiveerd en in de code wordt gebruikt, mag u de handtekening niet wijzigen. Als deze handtekening wordt gewijzigd, zal code die gebruikmaakt van het bericht niet werken. De enige uitzondering hierop kan zijn wanneer u een van de parameters wijzigt, zodat het argument niet altijd nodig is.  
  
 U kunt de volgorde van de argumenten wijzigen door deze te sorteren of ze omhoog of omlaag te verplaatsen, omdat de argumenten worden geïdentificeerd op basis van de naam, niet van de volgorde. Door wijzigingen in de beschrijving zal eveneens geen code worden gebroken die van het gericht gebruikmaakt.  
  
### <a name="action-process-argument-types"></a>Typen procesargumenten voor acties  
 In de volgende tabel zijn de typen procesargumenten voor acties beschreven.  
  
|Type|Beschrijving|  
|----------|-----------------|  
|Booleaans|Een waarde `true` of `false`.|  
|DateTime|Een waarde waarmee de datum- en tijdinformatie wordt opgeslagen.|  
|Decimaal|Een numerieke waarde met een decimale precisie. Dit wordt gebruikt wanneer de precisie erg belangrijk is.|  
|Entiteit|Een record voor de opgegeven entiteit. Wanneer u Entiteit selecteert, wordt de vervolgkeuzelijst ingeschakeld waarin u het entiteitstype kunt selecteren.|  
|EntityCollection|Een verzameling entiteitsrecords.|  
|EntityReference|Een object met de naam, de id en het type entiteitsrecord dat een unieke identificatie vormt. Wanneer u EntityReference selecteert, wordt de vervolgkeuzelijst ingeschakeld waarin u het entiteitstype kunt selecteren.|  
|Float|Een numerieke waarde met een decimale precisie. Dit wordt gebruikt wanneer gegevens afkomstig zijn van een meting die niet helemaal nauwkeurig is.|  
|Geheel getal|Een geheel getal.|  
|Geld|Een waarde waarmee gegevens over een hoeveelheid geld wordt opgeslagen.|  
|Picklist|Een waarde die een optie weergeeft voor een OptieSet-kenmerk.|  
|Tekenreeks|Een tekstwaarde.|  
  
> [!NOTE]
> **EntityCollection**-argumentwaarden kunnen niet worden ingesteld in de gebruikersinterface voor voorwaarden of acties. Deze worden door ontwikkelaars in aangepaste code voor gebruik beschikbaar gesteld. Meer informatie: [Uw eigen acties maken](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Fasen en stappen toevoegen  
 Acties zijn een type proces dat zeer goed vergelijkbaar is met realtime werkstromen. Alle stappen die kunnen worden gebruikt in realtime werkstromen kunnen worden gebruikt in acties. Zie voor meer informatie over de stappen die kunnen worden gebruikt voor zowel realtime werkstromen als acties [Fasen en stappen voor werkstromen](configure-workflow-steps.md).  
  
 Naast de stappen die kunnen worden gebruikt voor realtime werkstromen, kunnen acties ook de stap **Waarde toewijzen** hebben.  In acties kunnen deze alleen worden gebruikt om uitvoerargumenten in te stellen. U kunt de Formulierenassistent gebruiken om uitvoerargumenten in te stellen op specifieke waarden of, wat waarschijnlijker is, op waarden uit de record waartegen de actie wordt uitgevoerd, records gerelateerd aan dat record met een veel-op-een-relatie, records die in een eerdere stap zijn gemaakt, of waarden die onderdeel uitmaken van het proces zelf.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Aangepaste acties vanuit een werkstroom aanroepen](invoke-custom-actions-workflow-dialog.md)   

 
 
