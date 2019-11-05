---
title: Aangepaste bedrijfs logica maken via processen met PowerApps | MicrosoftDocs
description: Meer informatie over de verschillende typen bedrijfs logica die u kunt gebruiken in uw app
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
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
ms.openlocfilehash: b3072cc5897b8a2ef5a2a92ec3a07a0e31b57898
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545334"
---
# <a name="create-custom-business-logic-through-processes"></a>Aangepaste bedrijfs logica maken via processen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Het definiëren en afdwingen van consistente bedrijfs processen is een van de belangrijkste redenen voor het gebruik van op modellen gebaseerde apps. Consistente processen zorgen ervoor dat mensen die het systeem gebruiken zich kunnen concentreren op hun werk en niet op het onthouden van het uitvoeren van een set hand matige stappen. Processen kunnen eenvoudig of complex zijn en kunnen worden gewijzigd in de loop van de tijd.  
  
PowerApps bevat verschillende typen processen, die elk zijn ontworpen voor een ander doel:  
  
-   Bedrijfs proces stromen  
  
-   Mobiele taak stromen  
  
-   stroom  
  
-   Regelen  
  
 Net als bij processen kunt u ook bedrijfs regels en aanbevelingen maken. Zie [bedrijfs regels en aanbevelingen maken voor het Toep assen van logica in een formulier](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form) voor meer informatie.  

> [!NOTE]
>  Het gebruik van processen kan invloed hebben op de licentie vereisten voor PowerApps en stromen. Zie voor meer informatie [entiteits licentie vereisten](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Wanneer bedrijfs proces stromen worden gebruikt  
 Gebruik een bedrijfs proces stroom wanneer u wilt dat de mede werkers in dezelfde fasen door lopen en volg dezelfde stappen om met een klant te communiceren. U kunt bijvoorbeeld een bedrijfsproces stroom gebruiken als u wilt dat iedereen de verzoeken van de klanten service op dezelfde manier afhandelt, of als u wilt dat mede werkers goed keuring voor een factuur krijgen voordat ze een bestelling indienen.  
  
 Uw omgeving bevat verschillende kant-en-klare bedrijfs proces stromen voor veelvoorkomende verkoop-, service-en marketing taken die u kunt gebruiken met weinig of geen wijzigingen vereist. U kunt ook uw eigen maken. Zie het volgende onderwerp voor meer informatie over bedrijfsproces stromen:  
  
-   [Een bedrijfs proces stroom maken](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Wanneer moet u werk stromen gebruiken?  
 Gebruik werk stromen voor het automatiseren van bedrijfs processen achter de schermen. Werk stromen worden meestal geïnitieerd door systeem gebeurtenissen, zodat de gebruiker niet hoeft te weten dat ze worden uitgevoerd. Werk stromen die op de achtergrond worden uitgevoerd, zijn asynchroon. Werk stromen kunnen ook worden geconfigureerd voor personen om deze hand matig te initiëren. Wanneer u veelvoorkomende taken wilt automatiseren, zoals het automatisch verzenden van een bevestigings-e-mail naar een klant wanneer een order wordt verzonden. Werk stromen die in realtime worden gebruikt, zijn ' synchroon '. Zie [werk stroom processen](workflow-processes.md) voor meer informatie over werk stromen  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Wanneer moet u acties gebruiken?  
 Gebruik acties wanneer u een reeks opdrachten in het systeem wilt automatiseren. Acties breiden de beschik bare woorden lijst voor ontwikkel aars uit om bedrijfs processen te expresseren. Met kern woorden als Create, update, DELETE en Assign die door het systeem worden aangelegd, gebruikt een actie die kern woorden om meer inzichten-termen te maken, zoals goed keuren, escaleren, route ring of planning. Als de definitie van een bedrijfs proces verandert, kan iemand die geen ontwikkelaar is de actie bewerken zodat de code niet hoeft te worden gewijzigd.  Zie [acties](create-actions.md) voor meer informatie over acties  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-microsoft-flow"></a>Wanneer moet ik Microsoft Flow gebruiken?  
 Gebruik Microsoft Flow wanneer u geautomatiseerde werk stromen wilt maken die acties uitvoeren tussen uw omgeving en uw favoriete app of service, zoals Dynamics 365, Twitter, Dropbox, Google services, Office 365 en share point. U kunt een stroom activeren op basis van een specifieke actie of vanuit uw app aanroepen. Meer informatie: [Microsoft flow gebruiken om processen in Services te automatiseren](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Waar ga ik naar processen maken?  
 Er zijn twee paden om naar processen te navigeren:  
  
- Open [Solution Explorer](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) en ga naar **onderdelen > processen.** Dit pad biedt handige toegang wanneer u andere aanpassingen doorwerkt in de aanpassings hulpprogramma's.  

- **[Instellingen](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > processen.** Met dit pad kunt u weer gaven gebruiken die zijn gedefinieerd voor de entiteit proces, inclusief eventuele aangepaste weer gaven.  
  
 Afzonderlijke bedrijfs proces stromen kunnen ook worden bewerkt met behulp van de knop **proces bewerken** in de opdracht balk van het formulier waarin de bedrijfs proces stroom actief is.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Wie kan processen maken?  
 Alleen personen met de beveiligingsrol systeem beheerder, systeemaanpasser of CEO-Business Manager kunnen processen maken die van toepassing zijn op de hele omgeving. Personen met andere rollen kunnen processen met beperkte toegangs niveau maken. Personen met het toegangs niveau gebruiker kunnen bijvoorbeeld werk stromen maken voor hun eigen gebruik met records waarvan ze eigenaar zijn.  
  
 De volgende tabel toont het toegangs niveau van processen op basis van standaard beveiligings rollen.  
  
|||  
|-|-|  
|**Beveiligingsrol**|**Toegangs niveau**|  
|CEO-Business Manager|Organisatie|  
|Systeem beheerder|Organisatie|  
|Systeemaanpasser|Organisatie|  
|Vice president marketing|Bovenliggend item: onderliggende Business Units|  
|Adjunct-directeur van verkoop|Bovenliggend item: onderliggende Business Units|  
|Service Manager|Bedrijfs eenheid|  
|Marketing Manager|Bedrijfs eenheid|  
|Verkoop Manager|Bedrijfs eenheid|  
|Plannings Manager|Bedrijfs eenheid|  
|Mede werker van de klanten service|Gebruiker|  
|Marketing Professional|Gebruiker|  
|Verkoper|Gebruiker|  
|Scheduler|Gebruiker|  
  
> [!NOTE]
>  Hoewel mensen mogelijk een bedrijfsproces stroom, realtime werk stroom of actie processen kunnen maken, moeten ze de **bedrijfs proces stromen activeren** of **realtime-** proces bevoegdheden activeren om ze te activeren.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Meer informatie over werk stromen en acties  
 Processen kunnen voor waarden controleren, vertakkings logica Toep assen en acties uitvoeren. Ze voeren deze acties uit in een reeks stappen. In de volgende tabel worden de beschik bare stappen in werk stroom-en actie processen beschreven. Zie de onderwerpen voor elk type proces voor meer informatie.  
  
|Wizardstap|Proces type|Beschrijvingen|  
|----------|------------------|-----------------|  
|**Budgetplanningfase**|Werk stroom, actie|Met fasen wordt de werk stroom logica eenvoudiger te lezen en wordt de werk stroom logica uitgelegd. De stappen zijn echter niet van invloed op de logica of het gedrag van werk stromen. Als een proces fasen heeft, moeten alle stappen in het proces deel uitmaken van een fase.|  
|**Controle voorwaarde**|Werk stroom, actie|Een logische ' If-\<condition >-instructie.<br /><br /> U kunt waarden controleren voor de record waarop de werk stroom wordt uitgevoerd, een van de records die zijn gekoppeld aan deze record in een N:1-relatie of records die zijn gemaakt door eerdere stappen. Op basis van deze waarden kunt u extra stappen definiëren wanneer de voor waarde is `true`.|  
|**Voorwaardelijke vertakking**|Werk stroom, actie|Een logische ' Else-If-then '-instructie, de editor gebruikt de tekst ' anders als \<voor waarde > dan: '<br /><br /> Selecteer een voor waarde die u eerder hebt gedefinieerd en u kunt een voorwaardelijke tak toevoegen om extra stappen te definiëren wanneer de controle voorwaarde `false`retourneert.|  
|**Standaard actie**|Werk stroom, actie|Een logische else-instructie. de editor gebruikt de tekst "anderszins:"<br /><br /> Selecteer een controle voorwaarde, voorwaardelijke vertakking, wacht voorwaarde of parallelle wait-vertakking die u eerder hebt gedefinieerd. u kunt een standaard actie gebruiken om de stappen te definiëren voor alle cases die niet overeenkomen met de criteria die zijn gedefinieerd in voor waarde of vertakkings elementen.|  
|**Wacht voorwaarde**|Alleen achtergrond werk stroom|Hiermee kan een werk stroom op de achtergrond zichzelf onderbreken totdat aan de criteria die zijn gedefinieerd door de voor waarde is voldaan. De werk stroom wordt automatisch opnieuw gestart wanneer aan de criteria in de wacht voorwaarde is voldaan.|  
|**Parallelle wait-vertakking**|Alleen achtergrond werk stroom|Definieert een alternatieve wacht tijd voor een werk stroom op de achtergrond met een bijbehorende set extra stappen die alleen worden uitgevoerd wanneer aan het eerste criterium wordt voldaan. U kunt parallelle wachtende vertakkingen gebruiken om tijds limieten in uw werk stroom logica te maken. Ze helpen te voor komen dat de werk stroom oneindig wacht totdat aan de criteria die zijn gedefinieerd in een wacht voorwaarde is voldaan.|  
|**Waarde toewijzen**|Optreden|Hiermee stelt u een waarde in voor een variabele of uitvoer parameter in het proces.|  
|**Record maken**|Werk stroom, actie|Hiermee wordt een nieuwe record voor een entiteit gemaakt en worden waarden aan kenmerken toegewezen.|  
|**Record bijwerken**|Werk stroom, actie|U kunt de record waarop de werk stroom wordt uitgevoerd, bijwerken naar een van de records die zijn gekoppeld aan deze record in een N:1-relatie, of records die zijn gemaakt door eerdere stappen.|  
|**Record toewijzen**|Werk stroom, actie|U kunt de record waarop de werk stroom wordt uitgevoerd, toewijzen aan een van de records die zijn gekoppeld aan deze record met een N:1-relatie, of records die zijn gemaakt door eerdere stappen.|  
|**E-mail verzenden**|Werk stroom, actie|Hiermee verzendt u een e-mail bericht. U kunt ervoor kiezen om een nieuw e-mail bericht te maken of een e-mail sjabloon te gebruiken die is geconfigureerd voor de entiteit van de record waarop de werk stroom wordt uitgevoerd, of entiteiten die een N:1-relatie hebben met de entiteit, of de entiteit voor records die door eerdere stappen zijn gemaakt.|  
|**Onderliggend werk stroom starten**|Werk stroom, actie|Start een werk stroom proces dat is geconfigureerd als een onderliggende werk stroom.|  
|**Status wijzigen**|Werk stroom, actie|Wijzigt de status van de record waarop het proces wordt uitgevoerd, een van de records die aan deze record zijn gekoppeld met een N:1-relatie of records die zijn gemaakt door eerdere stappen.|  
|**Werk stroom stoppen**|Werk stroom, actie|Hiermee wordt de huidige werk stroom of actie gestopt. U kunt de status **geslaagd** of **geannuleerd** instellen en een status bericht opgeven.|  
|**Aangepaste stap**|Werk stroom, actie|Voorziet in uitbrei dingen van de logische elementen die standaard beschikbaar zijn. De stappen kunnen voor waarden, acties, andere stappen of een combi natie van deze elementen bevatten. Ontwikkel aars kunnen aangepaste werk stroom stappen maken. Standaard zijn er geen aangepaste stappen beschikbaar.|

  

