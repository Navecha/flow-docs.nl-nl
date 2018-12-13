---
title: Aangepaste acties vanuit een werkstroom aanroepen | MicrosoftDocs
description: Meer informatie over het aanroepen van een aangepaste actie vanuit een werkstroom
ms.custom: ''
ms.date: 11/22/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 1fd5d39e-3dc8-4d1a-8b4b-ccaa303f4bbb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e4dbedbd8157f2dd1814bbbbd080a6b366c04938
ms.sourcegitcommit: a505b0aac796960d57fccee92eb18c6566ac9c35
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/06/2018
ms.locfileid: "53006973"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Aangepaste acties vanuit een werkstroom aanroepen

Werkstromen hebben talloze mogelijkheden voor de ondersteuning bedrijfsscenario's. Elementaire gegevensbewerkingsacties aanroepen voor een record, zoals Maken, Bijwerken en Verwijderen, vanuit een werkstroom zorgt voor een oplossing voor een groot aantal bedrijfsscenario's. Als u de mogelijkheden van de werkstromen koppelt aan de kracht van de aangepaste acties die rechtstreeks vanuit de werkstroom worden aangeroepen, voegt u echter een geheel nieuwe serie bedrijfsscenario's aan uw toepassing toe zonder code te hoeven schrijven.  
  
 Bekijk het scenario waarin een aangepaste actie wordt aangeroepen vanuit een werkstroom. Er wordt een aangepaste actie aangeroepen voor het aanvragen van goedkeuring van de manager wanneer de korting voor een specifieke verkoopkans groter is dan 20%.  
  
<a name="action"></a>   
## <a name="dynamics-365-customer-engagement-example-create-a-custom-action-using-the-opportunity-entity"></a>Voorbeeld van Dynamics 365 Customer Engagement: Een aangepaste actie maken met de entiteit Verkoopkans
  
1. Selecteer in [Oplossingsverkenner](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) **Processen**.  
  
2.  Kies op de navigatiebalk **Nieuw**. Geef een naam op voor het proces en kies de categorie **Actie**.  
  
 Voor het aanvragen van goedkeuring voor de korting gebruiken wij een aangepaste actie met de naam **Goedkeuringsproces**. Er is een invoerparameter toegevoegd **SpecialNotes** en een stap **E-mailbericht verzenden** voor het maken van een nieuw bericht en het verzenden van een aanvraag voor goedkeuring van de manager, zoals hier wordt weergegeven.  
  
 ![Een stap toevoegen &#45; e-mailbericht verzenden](media/enable-custom-action-approval-proces-sadd-email.png "Een stap toevoegen - e-mailbericht verzenden")  
  
 Kies voor het configureren van het e-mailbericht **Eigenschappen instellen**. Wanneer het formulier wordt geopend, gebruikt u de **Formulierassistent** om opmerkingen en andere informatie aan het e-mailbericht toe te voegen, zoals is gemarkeerd op de schermafbeelding. Plaats voor het toevoegen van de speciale notities de cursor op de locatie waar u ze in het bericht wilt weergeven en kies daarna in de **Formulierassistent** onder **Zoeken naar** **Argumenten** in de eerste vervolgkeuzelijst en kies **SpecialNotes** in de tweede vervolgkeuzelijst. Kies vervolgens **OK**.  
  
 ![E-mailbericht instellen](media/enable-custom-action-approval-process-setup-email.png "E-mailbericht instellen")  
  
 Voordat u de actie vanuit een werkstroom kunt aanroepen, moet u deze activeren. Nadat u de actie hebt geactiveerd, kunt u de eigenschappen ervan bekijken door **Eigenschappen weergeven** te kiezen.  
  
 ![Aangepaste actie activeren &#45; goedkeuringsproces](media/enable-custom-action-approval-process-activate-action.png "Aangepaste actie activeren - goedkeuringsproces")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Een aangepaste actie vanuit een werkstroom aanroepen  
  
1. Selecteer in [Oplossingsverkenner](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) **Processen**.   
  
2.  Kies op de navigatiebalk **Nieuw**. Geef een naam op voor het proces en kies de categorie **Werkstroom**.  
  
 We hebben een werkstroom gemaakt waarmee de aangepaste actie **Goedkeuringsproces** steeds wordt aangeroepen wanneer de goedkeuring van de manager vereist is voor een korting van meer dan 20% op een verkoopkans.  
  
 ![Actie-eigenschappen instellen vanuit de werkstroom](media/enable-custom-action-from-workflow.png "Actie eigenschappen van werkstroom instellen")  
  
 U kunt de invoereigenschappen van de actie instellen door **Eigenschappen instellen** te kiezen. We hebben in de speciale notities een naam van het account toegevoegd dat betrekking heeft op de verkoopkans. Kies in de **Formulierassistent** onder **Zoeken naar** **Account** in de eerste vervolgkeuzelijst, kies **Accountnaam** in de tweede vervolgkeuzelijst en kies vervolgens **OK**. De eigenschap **Doel** is vereist en wordt door het systeem gevuld. De **{Opportunity(Opportunity)}** in de eigenschap **Doel** is de dezelfde verkoopkans als die waarop de aanroepende werkstroom wordt uitgevoerd. U kunt ook een specifieke verkoopkans voor de eigenschap Doel kiezen met behulp van opzoeken.  
  
 ![Invoerparameters voor actie ApprovalProcess instellen](media/enable-customaction-workflow-set-properties.png "Invoerparameters voor actie ApprovalProcess instellen")  
  



