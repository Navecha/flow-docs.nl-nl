---
title: Aangepaste bedrijfslogica maken via processen met PowerApps | MicrosoftDocs
description: Lees hier informatie over de verschillende typen bedrijfslogica die u kunt gebruiken in uw app
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b6cf8c2bc5e7499e7eaf5feb367c07a3aa94b3f7
ms.sourcegitcommit: f7985b96afe68b079b7fd4a6d04cd0a042d893e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2018
ms.locfileid: "47188588"
---
# <a name="create-custom-business-logic-through-processes"></a>Aangepaste bedrijfslogica maken met processen

Het definiëren en afdwingen van consistente bedrijfsprocessen is een van de belangrijkste redenen voor het gebruiken van modelgestuurde apps. Consistente processen zorgen ervoor dat gebruikers van het systeem zich op hun werk kunnen concentreren en niet op het onthouden van een set handmatige stappen. Processen kunnen eenvoudig of complex zijn en kunnen in de loop van de tijd veranderen.  
  
PowerApps bevat verschillende soorten processen, die allemaal zijn ontworpen voor een ander doel:  
  
-   Bedrijfsprocesstromen  
  
-   Mobiele taakstromen  
  
-   Werkstromen  
  
-   Acties  
  
 Net als bij processen, kunt u ook bedrijfsregels en aanbevelingen maken. Zie [Maak bedrijfsregels en aanbevelingen om logica in een formulier toe te passen](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form) voor meer informatie.  

> [!NOTE]
>  Het toepassen van processen kan invloed hebben op de licentievereisten voor PowerApps en stromen. Zie [Licentievereisten voor entiteiten](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses) voor meer informatie. 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Wanneer bedrijfsprocesstromen gebruiken  
 Gebruik een bedrijfsprocesstroom als u wilt dat medewerkers dezelfde fasen doorlopen en dezelfde stappen volgen voor interactie met een klant. Gebruik bijvoorbeeld een bedrijfsprocesstroom als u wilt dat iedereen aanvragen voor klantenservice op dezelfde manier verwerkt of om te vereisen dat medewerkers goedkeuring moeten vragen voor een factuur voordat ze een order plaatsen.  
  
 Uw omgeving bevat al enkele kant-en-klare bedrijfsprocesstromen voor algemene verkoop-, service- en marketingtaken die u met weinig of geen wijzigingen kunt gebruiken. Maar u kunt natuurlijk ook uw eigen processtromen maken. Zie het volgende onderwerp voor meer informatie over bedrijfsprocesstromen:  
  
-   [Een bedrijfsprocesstroom maken](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Wanneer werkstromen gebruiken  
 Gebruik werkstromen om bedrijfsprocessen achter de schermen te automatiseren. Werkstromen worden meestal opgestart door systeemgebeurtenissen, zodat de gebruiker niet eens hoeft te weten dat ze worden uitgevoerd. Werkstromen die op de achtergrond worden uitgevoerd, zijn 'asynchroon'. Werkstromen kunnen ook worden geconfigureerd voor handmatig opstarten door gebruikers, bijvoorbeeld als u algemene taken wilt automatiseren, zoals het automatisch verzenden van een bevestigingsmail naar een klant wanneer een order wordt verzonden. Werkstromen die in realtime werken, zijn 'synchroon'. Zie [Werkstroomprocessen](workflow-processes.md) voor meer informatie over werkstromen.  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Wanneer acties gebruiken  
 Gebruik acties als u een reeks opdrachten in het systeem wilt automatiseren. Acties zijn een uitbreiding op het arsenaal waaruit ontwikkelaars kunnen putten om bedrijfsprocessen uit te drukken. De belangrijkste bewerkingen zoals Create, Update, Delete en Assign zijn standaard beschikbaar in het systeem. Gebruik een actie in combinatie met deze bewerkingen voor het maken van meer expressieve bewerkingen zoals Approve, Escalate, Route of Schedule. Als de definitie van een bedrijfsproces wordt gewijzigd, kan iemand die geen ontwikkelaar is de actie bewerken zodat de code niet hoeft te worden gewijzigd.  Zie [Acties](create-actions.md) voor meer informatie over acties.  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-microsoft-flow"></a>Wanneer Microsoft Flow gebruiken  
 Gebruik Microsoft Flow als u geautomatiseerde werkstromen wilt maken die acties uitvoeren tussen uw omgeving en een favoriete app of service, zoals Dynamics 365, Twitter, Dropbox, Google Services, Office 365 en SharePoint. U kunt een stroom activeren op basis van een specifieke actie of aanroepen vanuit uw app. Meer informatie: [Microsoft Flow gebruiken om processen voor services te automatiseren](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Waar kan ik processen maken?  
 Er zijn twee paden om naar het onderdeel Processen te gaan:  
  
- Open [Solution Explorer](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) en ga naar **Onderdelen > Processen.** Dit pad biedt een gemakkelijke toegang als u bezig bent met andere aanpassingswerkzaamheden in de hulpprogramma's voor aanpassing.  

- **[Instellingen](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Processen.** Dit pad biedt de mogelijkheid om weergaven te gebruiken die zijn gedefinieerd voor de entiteit Proces, inclusief eventuele aangepaste weergaven.  
  
 Specifieke bedrijfsprocesstromen kunnen ook worden bewerkt met behulp van de knop **Proces bewerken** op de opdrachtbalk voor het formulier waarop de bedrijfsprocesstroom actief is.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Wie kan processen maken?  
 Alleen gebruikers met de beveiligingsrol Systeembeheerder, Systeemaanpasser of Algemeen directeur-bedrijfsleider kan processen maken die betrekking hebben op de hele omgeving. Gebruikers met andere rollen kunnen processen met een beperkt toegangsniveau maken. Zo kunnen gebruikers met het toegangsniveau Gebruiker werkstromen voor eigen gebruik maken met records waarvan ze eigenaar zijn.  
  
 In de volgende tabel ziet u het toegangsniveau van processen op basis van standaardbeveiligingsrollen.  
  
|||  
|-|-|  
|**Beveiligingsrol**|**Toegangsniveau**|  
|Algemeen directeur-bedrijfsleider|Organisatie|  
|Systeembeheerder|Organisatie|  
|Systeemaanpasser|Organisatie|  
|Adjunct-directeur marketing|Bovenliggend: onderliggende Business Units|  
|Adjunct-directeur verkoop|Bovenliggend: onderliggende Business Units|  
|Servicemanager|Business Unit|  
|Marketingmanager|Business Unit|  
|Verkoopmanager|Business Unit|  
|Planningbeheer|Business Unit|  
|Medewerker van de klantenservice|Gebruiker|  
|Marketingprofessional|Gebruiker|  
|Verkoper|Gebruiker|  
|Planner|Gebruiker|  
  
> [!NOTE]
>  Gebruikers die bevoegd zijn om bedrijfsprocesstromen, realtime-werkstromen of actieprocessen te maken, hebben de bevoegdheid **Bedrijfsprocesstromen activeren** of **Realtime-processen activeren** nodig om die onderdelen te activeren.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Meer informatie over werkstromen en acties  
 Processen kunnen voorwaarden controleren, vertakkingslogica toepassen en acties uitvoeren. Deze acties worden uitgevoerd in een reeks stappen. De volgende tabel beschrijft de beschikbare stappen in werkstroom- en actieprocessen. Zie de onderwerpen voor elk type proces voor meer informatie.  
  
|Stap|Type proces|Beschrijving|  
|----------|------------------|-----------------|  
|**Fase**|Werkstroom, Actie|Fasen maken de logica van een werkstroom gemakkelijker te lezen en beschrijven de werkstroomlogica. Fasen hebben echter geen invloed op de logica of het gedrag van werkstromen. Als een proces bestaat uit fasen, moeten alle stappen in het proces zijn opgenomen in een fase.|  
|**Voorwaarde controleren**|Werkstroom, Actie|Een logische 'if-\<voorwaarde>then'-instructie.<br /><br /> U kunt waarden controleren voor de record waarop de werkstroom wordt uitgevoerd, voor een record die aan deze record is gekoppeld in een N:1-relatie of voor een record die in eerdere stappen is gemaakt. Op basis van deze waarden kunt u extra stappen definiëren wanneer aan de voorwaarde `true` is.|  
|**Voorwaardelijke branche**|Werkstroom, Actie|Een logische 'else-if-then'-instructie; in de editor wordt de tekst 'Otherwise, if \<condition> then:' gebruikt.<br /><br /> Selecteer een controlevoorwaarde die u eerder hebt gedefinieerd en u kunt een voorwaardelijke vertakking toevoegen voor het definiëren van extra stappen wanneer de controlevoorwaarde `false` is.|  
|**Standaardactie**|Werkstroom, Actie|Een logische 'else'-instructie. In de editor wordt de tekst 'Otherwise:' gebruikt.<br /><br /> Selecteer een controlevoorwaarde, voorwaardelijke vertakking, een wachtvoorwaarde of een parallelle wachtvertakking die u eerder hebt gedefinieerd en u kunt een standaardactie gebruiken voor het definiëren van stappen voor alle gevallen die niet voldoen aan de criteria die zijn gedefinieerd in voorwaarde- of vertakkingselementen.|  
|**Wachtvoorwaarde**|Alleen achtergrondwerkstroom|Hiermee kunt u een achtergrondwerkstroom zichzelf laten onderbreken totdat is voldaan aan de criteria die zijn gedefinieerd door de voorwaarde. De werkstroom wordt verder uitgevoerd zodra aan de criteria in de wachtvoorwaarde is voldaan.|  
|**Parallelle wachtbranche**|Alleen achtergrondwerkstroom|Hiermee definieert u een alternatieve wachtvoorwaarde voor een achtergrondwerkstroom met een bijbehorende set extra stappen die alleen worden uitgevoerd als aan het eerste criterium wordt voldaan. U kunt parallelle wachtvertakkingen gebruiken om tijdslimieten in te bouwen in uw werkstroomlogica. U voorkomt zo dat de werkstroom oneindig lang blijft wachten totdat is voldaan aan de criteria die zijn gedefinieerd in een wachtvoorwaarde.|  
|**Waarde toewijzen**|Actie|Hiermee stelt u een waarde in op een variabele of uitvoerparameter in het proces.|  
|**Record maken**|Werkstroom, Actie|Hiermee maakt u een nieuwe record voor een entiteit en worden waarden toegewezen aan kenmerken.|  
|**Record bijwerken**|Werkstroom, Actie|U kunt de record bijwerken waarop de werkstroom wordt uitgevoerd, een record die aan deze record is gekoppeld in een N:1-relatie of een record die in eerdere stappen is gemaakt.|  
|**Record toewijzen**|Werkstroom, Actie|U kunt de record toewijzen waarop de werkstroom wordt uitgevoerd, een record die aan deze record is gekoppeld met een N:1-relatie of een record die in eerdere stappen is gemaakt.|  
|**E-mail verzenden**|Werkstroom, Actie|Hiermee verstuurt u een e-mail. U kunt een nieuw e-mailbericht maken of een e-mailsjabloon gebruiken die is geconfigureerd voor de entiteit van de record waarop de werkstroom wordt uitgevoerd, een entiteit met een N:1-relatie met die entiteit of de entiteit voor een record die in eerdere stappen is gemaakt.|  
|**Onderliggende werkstroom starten**|Werkstroom, Actie|Hiermee start u een werkstroomproces dat is geconfigureerd als een onderliggende werkstroom.|  
|**Status wijzigen**|Werkstroom, Actie|Hiermee wijzigt u de status van de record waarop de werkstroom wordt uitgevoerd, een record die aan deze record is gekoppeld met een N:1-relatie of een record die in eerdere stappen is gemaakt.|  
|**Werkstroom stoppen**|Werkstroom, Actie|Hiermee stopt u de huidige werkstroom of actie. U kunt de status instellen op **Succeeded** of **Canceled** en een statusbericht opgeven.|  
|**Aangepaste stap**|Werkstroom, Actie|Hiermee kunt u de logische elementen uitbreiden die standaard beschikbaar zijn. Stappen kunnen bestaan uit voorwaarden, acties, andere stappen of een combinatie van deze elementen. Ontwikkelaars kunnen aangepaste werkstroomstappen maken. Er zijn standaard geen aangepaste stappen beschikbaar.|

Meer informatie voor ontwikkelaars kunt u lezen in dit onderwerp in de handleiding voor ontwikkelaars: [Automate your business processes in Customer Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/developer/automate-business-processes-customer-engagement
) (Bedrijfsprocessen automatiseren in Customer Engagement).
  

