---
title: Gegevens groepen voor Microsoft Flow | Microsoft Docs
description: Inleiding tot gegevens groepen voor Microsoft PowerApps en Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/26/2016
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 030e0563ce9adaa7c1c5c44f1446859e3152a398
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547452"
---
# <a name="learn-all-about-data-groups"></a>Meer informatie over gegevens groepen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-is-a-data-group"></a>Wat is een gegevens groep?
Gegevens groepen zijn een eenvoudige manier om services te categoriseren binnen een [beleid voor preventie van gegevens verlies (DLP)](prevent-data-loss.md). De twee beschik bare gegevens groepen zijn de groep **alleen zakelijke gegevens** en de groep **geen zakelijke gegevens toegestaan** . Organisaties kunnen bepalen welke services in een bepaalde gegevens groep worden geplaatst. Een goede manier om services te categoriseren is door ze in groepen te plaatsen, op basis van de impact op de organisatie. Standaard worden alle services in de gegevens groep **geen zakelijke gegevens toegestaan** geplaatst. U beheert de services in een gegevens groep wanneer u de eigenschappen van een DLP-beleid maakt of wijzigt vanuit het beheer centrum.

## <a name="how-data-is-shared-between-data-groups"></a>Hoe gegevens worden gedeeld tussen gegevens groepen
Gegevens kunnen niet worden gedeeld tussen services die zich in verschillende groepen bevinden. Als u bijvoorbeeld share point en Sales Force in de groep **alleen zakelijke gegevens** plaatst en Facebook en Twitter in de groep **geen zakelijke gegevens toegestaan** plaatst, kunt u geen stroom maken waarmee gegevens tussen share point en Facebook worden verplaatst. Terwijl gegevens niet kunnen worden gedeeld tussen services in verschillende groepen, kunt u gegevens delen tussen de services binnen een specifieke groep. Het vorige voor beeld wordt weer gegeven, omdat share point en Sales Force in dezelfde gegevens groep zijn geplaatst, stromen die uw eind gebruikers maken gegevens kunnen delen tussen share point en Sales Force. Eind gebruikers kunnen ook stromen en PowerApps maken die gegevens delen tussen Facebook en Twitter. Het sleutel punt is dat services in een specifieke groep gegevens kunnen delen, terwijl Services in verschillende groepen geen gegevens kunnen delen.  

Daarnaast moet één gegevens groep worden aangewezen als de *standaard* groep. In eerste instantie is de groep **geen zakelijke gegevens toegestaan** de *standaard* groep en alle services bevinden zich in de gegevens groep. Een beheerder kan de standaard gegevens groep wijzigen in de gegevens groep **alleen zakelijke gegevens** . **Houd er rekening mee** dat nieuwe services die worden toegevoegd aan flow, worden geplaatst in de aangewezen *standaard* groep. Daarom raden we u aan om de **geen bedrijfs gegevens toegestaan** als standaard groep te houden en services hand matig toe te voegen aan de groep **alleen zakelijke gegevens** nadat uw organisatie de gevolgen heeft geëvalueerd van het toestaan van Bedrijfs gegevens die worden gedeeld met de nieuwe service.

## <a name="add-services-to-a-data-group"></a>Services toevoegen aan een gegevens groep
In dit overzicht worden share point en Sales Force toegevoegd aan de gegevens groep **alleen zakelijke gegevens** van een beleid voor preventie van gegevens verlies (DLP). 

1. Selecteer de koppeling **+ toevoegen** in het groepsvak **alleen zakelijke gegevens** van een DLP-beleid:    
   afbeelding ![toevoegen](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Selecteer share point en Sales Force en selecteer vervolgens **Services toevoegen** om beide toe te voegen aan de groep alleen zakelijke gegevens:    
   ![installatie kopie van services toevoegen](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Selecteer **beleid opslaan** in het menu bovenaan:  
   beleid ![opslaan](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. U ziet dat zowel share point als Sales Force nu wordt weer gegeven in de groep alleen zakelijke gegevens:  
   ![bijgewerkte groep met zakelijke gegevens](./media/introduction-to-data-groups/add-to-data-group-3.png)   

In deze hand leiding hebt u share point en Sales Force toegevoegd aan de gegevens groep **alleen zakelijke gegevens** van een DLP-beleid. Als een persoon die deel uitmaakt van de omgeving van het DLP-beleid een app maakt die gegevens deelt tussen share point of Sales Force en een service in de gegevens groep **geen zakelijke gegevens toegestaan** , kan de app niet worden uitgevoerd.

## <a name="remove-services-from-a-data-group"></a>Services verwijderen uit een gegevens groep
Aangezien alle services in een van de beschik bare gegevens groepen moeten worden verwijderd, moet u de service gewoon toevoegen aan een andere groep en vervolgens het beleid opslaan.  

## <a name="change-the-default-data-group"></a>De standaard gegevens groep wijzigen
In dit overzicht wordt de standaard gegevens groep gewijzigd van de gegevens groep **geen zakelijke gegevens toegestaan** in de gegevens groep **alleen zakelijke gegevens** .  

**Belang rijk** dat nieuwe services die aan de stroom worden toegevoegd, worden geplaatst in de aangewezen *standaard* groep. Daarom raden we u aan om ervoor te zorgen dat **er geen zakelijke gegevens worden toegestaan** als standaard groep en hand matig Services toe te voegen aan de groep **alleen zakelijke gegevens** .

1. Selecteer de. **.** . bevindt zich in de rechter bovenhoek van de gegevens groep die u wilt aanwijzen als de standaard gegevens groep:    
   ![standaard groep wijzigen](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Selecteer **instellen als standaard groep**:  
   ![standaard groep wijzigen](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Selecteer **beleid opslaan** in het menu bovenaan:  
   ![standaard groep wijzigen](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. U ziet dat de gegevens groep nu is ingesteld als de standaard gegevens groep:  
   ![standaard groep wijzigen](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Volgende stappen
* [Meer informatie over beleid voor preventie van gegevens verlies (DLP)](prevent-data-loss.md)
* [Meer informatie over omgevingen](environments-overview-admin.md)   

