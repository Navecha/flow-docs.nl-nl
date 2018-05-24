---
title: Gegevensgroepen voor Microsoft Flow | Microsoft Docs
description: Inleiding tot gegevensgroepen voor Microsoft PowerApps en Microsoft Flow.
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
ms.openlocfilehash: fd76c12d1879c9b613ba833d9ef2211cd4aab702
ms.sourcegitcommit: f0202f74ba9a2282a670a1751462f598a5ea0ce5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2018
---
# <a name="learn-all-about-data-groups"></a>Meer informatie over gegevensgroepen
## <a name="what-is-a-data-group"></a>Wat is een gegevensgroep?
Gegevensgroepen zijn een eenvoudige manier om services te categoriseren binnen een [Beleid voor preventie van gegevensverlies (DLP)](prevent-data-loss.md). De twee beschikbare groepen zijn de groep **Alleen bedrijfsgegevens** en de groep **Geen bedrijfsgegevens toegestaan**. Organisaties kunnen zelf bepalen welke services in een bepaalde gegevensgroep worden geplaatst. Een goede manier om de services te categoriseren is door ze in groepen te plaatsen, op basis van de gevolgen voor de organisatie. Standaard worden alle services in de gegevensgroep **Geen bedrijfsgegevens toegestaan** geplaatst. U beheert de services in een gegevensgroep wanneer u eigenschappen van een DLP-beleid maakt of beheert in het beheercentrum.

## <a name="how-data-is-shared-between-data-groups"></a>Hoe gegevens worden gedeeld tussen gegevensgroepen
Gegevens kunnen niet worden gedeeld tussen services die zich in verschillende groepen bevinden. Als u bijvoorbeeld SharePoint en Salesforce in de groep **Alleen bedrijfsgegevens** plaatst, en Facebook en Twitter in de groep **Geen bedrijfsgegevens toegestaan**, kunt u geen stroom maken waarmee gegevens worden verplaatst tussen SharePoint en Facebook. Gegevens kunnen niet worden gedeeld tussen services in verschillende groepen. U kunt gegevens echter wel delen tussen de services binnen een specifieke groep. Terugkijkend naar het vorige voorbeeld: omdat SharePoint en Salesforce in dezelfde gegevensgroep zijn geplaatst, kunnen met stromen die uw eindgebruikers maken gegevens tussen SharePoint en Salesforce worden gedeeld. Eindgebruikers kunnen op dezelfde manier stromen en PowerApps maken waarmee gegevens tussen Facebook en Twitter worden gedeeld. Cruciaal is dat services in een specifieke groep gegevens kunnen delen, terwijl services in verschillende groepen geen gegevens kunnen delen.  

Daarnaast moet één gegevensgroep worden aangemerkt als de *standaard* groep. In eerste instantie is de groep **Geen bedrijfsgegevens toegestaan** de *standaard* groep en bevinden alle services zich in deze gegevensgroep. Een beheerder kan de standaard gegevensgroep wijzigen naar de gegevens **Alleen bedrijfsgegevens**. **Opmerking**: elke nieuwe service die wordt toegevoegd aan Flow wordt geplaatst in de aangewezen *standaard* groep. Daarom wordt aanbevolen **Geen bedrijfsgegevens toegestaan** als standaardgroep te houden en services handmatig toe te voegen aan de groep **Alleen bedrijfsgegevens** nadat uw organisatie de gevolgen van het delen van bedrijfsgegevens met de nieuwe service heeft geëvalueerd.

## <a name="add-services-to-a-data-group"></a>Nieuwe services toevoegen aan een gegevensgroep
In deze walkthrough worden SharePoint en Salesforce toegevoegd aan de gegevensgroep **Alleen bedrijfsgegevens** van een beleid voor preventie van gegevensverlies (DLP). 

1. Selecteer de koppeling **+ Toevoegen** binnen het groepsvak **Alleen bedrijfsgegevens** van een DLP-beleid:    
   ![Afbeelding toevoegen](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Selecteer SharePoint en Salesforce en selecteer vervolgens **Services toevoegen** om beide toe te voegen aan de groep Alleen bedrijfsgegevens:    
   ![Afbeelding Services toevoegen](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Selecteer **Beleid opslaan** in het menu bovenaan:  
   ![Beleid opslaan](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Merk op dat SharePoint en Salesforce zich nu in de groep Alleen bedrijfsgegevens bevinden:  
   ![bijgewerkte groep bedrijfsgegevens](./media/introduction-to-data-groups/add-to-data-group-3.png)   

In deze walkthrough hebt u SharePoint en Salesforce toegevoegd aan de gegevensgroep **Alleen bedrijfsgegevens** van een DLP-beleid. Als iemand die onderdeel uitmaakt van de omgeving van het DLP-beleid een app maakt die gegevens deelt tussen SharePoint of Salesforce en een service in de gegevensgroep **Geen bedrijfsgegevens toegestaan**, mag de app niet worden uitgevoerd.

## <a name="remove-services-from-a-data-group"></a>Services verwijderen uit een gegevensgroep
Alle services moeten zich in een van beide gegevensgroepen bevinden. Als u een service uit een specifieke groep wilt verwijderen, voegt u de service gewoon toe aan de andere groep en slaat u het beleid vervolgens op.  

## <a name="change-the-default-data-group"></a>De standaard gegevensgroep wijzigen
In deze walkthrough wordt de standaard gegevensgroep gewijzigd van de gegevensgroep **Geen bedrijfsgegevens toegestaan** naar de gegevensgroep **Alleen bedrijfsgegevens**.  

**Belangrijk**: elke nieuwe service die wordt toegevoegd aan Flow wordt geplaatst in de aangewezen *standaard*groep. Daarom wordt aanbevolen **Geen bedrijfsgegevens toegestaan** als standaardgroep te houden en services handmatig toe te voegen aan de groep **Alleen bedrijfsgegevens**.

1. Selecteer de **...** in de rechterbovenhoek van de gegevensgroep die u wilt aanwijzen als de standaard gegevensgroep:    
   ![standaardgroep wijzigen](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Selecteer **Set as default group** (Instellen als standaardgroep):  
   ![standaardgroep wijzigen](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Selecteer **Beleid opslaan** in het menu bovenaan:  
   ![standaardgroep wijzigen](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. U ziet dat de gegevensgroep nu is ingesteld als de standaard gegevensgroep:  
   ![standaardgroep wijzigen](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Volgende stappen
* [Meer informatie over beleid voor preventie van gegevensverlies (DLP)](prevent-data-loss.md)
* [Meer informatie over omgevingen](environments-overview-admin.md)   

