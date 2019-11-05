---
title: Acties gebruiken | MicrosoftDocs
description: Met acties kunt u bewerkingen uitvoeren, zoals maken, bijwerken, verwijderen, toewijzen of actie ondernemen. Intern maakt een actie een aangepast bericht
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: eb4fa4040611241dd2bd81706736738ad6774d38
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544585"
---
# <a name="use-actions"></a>Acties gebruiken
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Acties openen een scala aan mogelijkheden voor het opstellen van bedrijfs logica. Met acties kunt u bewerkingen uitvoeren, zoals maken, bijwerken, verwijderen, toewijzen of actie ondernemen. Intern maakt een actie een aangepast bericht. Ontwikkel aars verwijzen naar deze acties als ' berichten '. Elk van deze berichten is gebaseerd op acties die zijn uitgevoerd op een entiteits record. Als het doel van een proces is om een record te maken, vervolgens bij te werken en het vervolgens toe te wijzen, zijn er drie afzonderlijke stappen. Elke stap wordt gedefinieerd door de mogelijkheden van de entiteit, niet noodzakelijkerwijs uw bedrijfs proces.  
  
Acties bieden de mogelijkheid om één term (of een bericht) te definiëren die overeenkomt met een bewerking die u moet uitvoeren voor uw bedrijf. Deze nieuwe berichten worden gestuurd door een proces of gedrag in plaats van wat er met een entiteit kan worden gedaan. Deze berichten kunnen overeenkomen met werk woorden zoals escaleren, converteren, plannen, routeren of goed keuren, wat u nodig hebt. Het toevoegen van deze termen helpt u bij het maken van een rijkere woorden lijst om uw bedrijfs processen te definiëren. U kunt deze uitgebreide vocabulaire van clients of integraties Toep assen in plaats van de actie binnen clients te schrijven. Dit maakt het eenvoudiger omdat u het slagen of mislukken van de hele actie als één eenheid kunt beheren en registreren.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Configureer bare berichten  
 Zodra een actie is gedefinieerd en geactiveerd, kan een ontwikkelaar dit bericht gebruiken, bijvoorbeeld een van de andere berichten die door het platform worden gebruikt. Een belang rijk verschil is dat nu iemand die geen ontwikkelaar is, wijzigingen kan Toep assen op wat er moet gebeuren wanneer dat bericht wordt gebruikt. U kunt de actie zo configureren dat de stappen worden gewijzigd wanneer uw bedrijfs processen worden gewijzigd. Aangepaste code die dit bericht gebruikt, hoeft niet te worden gewijzigd zolang de proces argumenten niet worden gewijzigd.  
  
 Werk stroom processen en-invoeg toepassingen blijven vergelijk bare mogelijkheden bieden voor het definiëren van automatisering. Werk stroom processen bieden nog steeds de mogelijkheid om wijzigingen toe te passen door een niet-ontwikkelaar. Het verschil is echter in de manier waarop de bedrijfs processen zijn samengesteld en hoe een ontwikkelaar hun code kan schrijven. Een actie is een bericht dat op hetzelfde niveau werkt als een van de berichten die door het platform worden gegeven. Ontwikkel aars kunnen invoeg toepassingen voor acties registreren.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Algemene berichten 
 
 In tegens telling tot Common Data Service werk stromen of [-invoeg toepassingen](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in), hoeft een actie niet aan een specifieke entiteit te zijn gekoppeld. U kunt algemene acties definiëren die zelf kunnen worden aangeroepen.

## <a name="next-steps"></a>Volgende stappen

[Een aangepaste actie maken](create-actions.md)  
  

