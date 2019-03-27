---
title: Acties gebruiken | MicrosoftDocs
description: U kunt met acties bewerkingen uitvoeren als Maken, Bijwerken, Verwijderen, Toewijzen of Actie uitvoeren. Intern zorgt een actie voor een aangepast bericht
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cf5c0e488f1d01c514f509b9d2a8afae265cf487
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2019
ms.locfileid: "58352867"
---
# <a name="use-actions"></a>Acties gebruiken

Met Acties opent u een scala aan mogelijkheden voor het opstellen van bedrijfslogica. U kunt met acties bewerkingen uitvoeren als Maken, Bijwerken, Verwijderen, Toewijzen of Actie uitvoeren. Intern zorgt een actie voor een aangepast bericht. Ontwikkelaars verwijzen naar deze acties als 'berichten'. Elk van deze berichten is gebaseerd op acties die worden ondernomen tegen een entiteitsrecord. Als het proces is bedoeld om een record te maken, deze bij te werken, en vervolgens toe te wijzen, zijn er drie afzonderlijke stappen. Elke stap wordt gedefinieerd door de functionaliteit van de entiteit – niet per se uw bedrijfsprocessen.  
  
Acties bieden de mogelijkheid om een eenmalige bewerking (of bericht) te definiëren die (dat) overeenkomt met een bewerking die u moet uitvoeren voor uw bedrijf. Deze nieuwe berichten worden aangedreven door een proces of gedrag in plaats van wat er met een entiteit kan worden gedaan. Deze berichten kunnen overeenkomen met termen, zoals Escaleren, Converteren, Plannen, Routeren of Goedkeuren: alles wat u nodig hebt. Met de toevoeging van deze termen krijgt u een uitgebreidere woordenlijst waarmee u uw bedrijfsprocessen soepel kunt definiëren. U kunt deze uitgebreidere woordenlijst toepassen vanuit clients of integraties in plaats van dat u de actie binnen clients moet schrijven. Dit is tevens eenvoudiger, omdat u het slagen of mislukken van de gehele actie als één eenheid kunt beheren en vastleggen.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Configureerbare berichten  
 Wanneer een actie is gedefinieerd en geactiveerd, kan een ontwikkelaar dat bericht gebruiken, net als alle andere berichten die door het platform worden geleverd. Een belangrijk verschil is echter dat nu iemand die geen ontwikkelaar is wijzigingen kan aanbrengen in wat moet worden uitgevoerd wanneer dat bericht wordt gebruikt. U kunt de actie zo configureren dat de stappen worden aangepast op basis van wijzigingen in uw zakelijke processen. Aangepaste code die gebruikmaakt van dat bericht hoeft niet te worden gewijzigd zolang de procesargumenten niet worden gewijzigd.  
  
 Werkstroomprocessen en invoegtoepassingen blijven vergelijkbare functionaliteit bieden voor het definiëren van automatisering. Werkstroomprocessen bieden nog steeds een niet-ontwikkelaar de mogelijkheid om wijzigingen aan te brengen. Maar het verschil zit in de wijze waarop de bedrijfsprocessen zijn samengesteld en een ontwikkelaar code kan schrijven. Een actie is een bericht dat op hetzelfde niveau werkt als berichten die door het platform worden geleverd. Ontwikkelaars kunnen invoegtoepassingen registreren voor acties.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Globale berichten 
 
 In tegenstelling tot Common Data Service-werkstromen of [invoegtoepassingen](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in) hoeft een actie niet aan een specifieke entiteit te zijn gekoppeld. U kunt 'globale' acties definiëren die afzonderlijk kunnen worden aangeroepen.

## <a name="next-steps"></a>Volgende stappen

[Een aangepaste actie maken](create-actions.md)  
  

