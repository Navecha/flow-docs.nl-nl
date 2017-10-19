---
title: Overzicht van de omgeving voor beheerders | Microsoft Docs
description: Omgevingen gebruiken, maken en beheren in Microsoft Flow
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: f1c50e5d16d5b9fbbd3e6db3128947b0554e9a85
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="using-environments-within-microsoft-flow"></a>Omgevingen gebruiken in Microsoft Flow
## <a name="benefits"></a>Voordelen
Omgevingen zijn een nieuwe functie in Microsoft Flow en bevatten de volgende voordelen: 

* **Gegevenslocatie**: omgevingen kunnen in verschillende regio's worden gemaakt en zijn gebonden aan die geografische locatie. Wanneer u een stroom in een omgeving maakt, wordt de stroom gerouteerd naar alle datacenters op die geografische locatie. Dit biedt tevens prestatievoordelen. 
  
    Maak en gebruik de omgeving in de regio Europa als uw gebruikers zich in Europa bevinden. Als uw gebruikers zich in de Verenigde Staten bevinden, maak en gebruik de omgeving dan in de Verenigde Staten. 
  
    Als u de omgeving verwijdert, worden ook alle stromen binnen die omgeving verwijderd. Dit geldt voor alle items die u in de omgeving maakt, inclusief verbindingen, gateways, PowerApps en meer.
* **Preventie van gegevensverlies**: als beheerder wilt u niet dat stromen die gegevens van een interne locatie krijgen (zoals *OneDrive voor Bedrijven*) deze gegevens vervolgens in de openbaarheid publiceren (bijvoorbeeld op *Twitter*). Met behulp van Preventie van gegevensverlies bepaalt u welke services kunnen worden gebruikt in een beleid voor uitsluitend zakelijke gegevens. 
  
    Een voorbeeld: u kunt services van *SharePoint* en *OneDrive voor Bedrijven* toevoegen aan een beleid voor uitsluitend zakelijke gegevens. Alle stromen die in deze omgeving worden gemaakt, kunnen deze services van *SharePoint* en *OneDrive voor Bedrijven* gebruiken. Alleen services die u toevoegt, zijn beschikbaar. 
  
  > [!NOTE]
  > Preventie van gegevensverlies is beschikbaar bij SKU’s van bepaalde licenties, waaronder de P2-licentie. 
  > 
  > 
* **Isolatiegrens voor alle resources**: alle stromen, gateways, verbindingen, aangepaste connectors enzovoort bevinden zich in die specifieke omgeving. Ze bestaan niet in andere omgevingen. 
* **Common Data Service**: u wilt een stroom maken die ergens gegevens invoegt. Uw opties zijn:
  
  * Gegevens invoegen in een Excel-bestand en het Excel-bestand opslaan in een cloudopslagaccount zoals OneDrive.
  * Uw eigen SQL-database maken en uw gegevens erin opslaan.
  * Gebruik de Common Data Service voor het opslaan van uw gegevens.
    
    Elke omgeving kan nul of één databaseopslag voor uw stromen hebben in de Common Data Service. Toegang tot de Common Data Service is afhankelijk van de licentie die u koopt. De toegang is niet inbegrepen in de gratis licentie.

## <a name="limitations"></a>Beperkingen
Hoewel omgevingen veel voordelen bieden, brengen zij ook nieuwe beperkingen met zich mee. Het feit dat omgevingen een isolatiegrens vormen, betekent dat u nooit resources kunt hebben die verwijzen naar andere resources *in andere* omgevingen. Een voorbeeld: het is niet mogelijk een aangepaste connector in een omgeving te maken en een stroom te maken die zowel die aangepaste connector als een gateway in een andere omgeving gebruikt.

Het is dus belangrijk dat omgevingen alleen worden gemaakt wanneer ze nodig zijn. Het maken van te veel omgevingen maakt het voor gebruikers in uw organisatie lastig om resources te delen.

## <a name="use-the-default-environment"></a>De standaardomgeving gebruiken
De omgeving **Default** is beschikbaar voor elke gebruiker en wordt gedeeld door alle gebruikers. Elke gebruiker kan stromen maken in deze omgeving.

> [!TIP]
> Als u een Preview-gebruiker bent, bevinden alle bestaande stromen zich in de standaardomgeving. Een *Preview-gebruiker* is iemand die Microsoft Flow gebruikte voordat dit algemeen beschikbaar werd. 
> 
> 

## <a name="use-the-administrator-center"></a>Het beheercentrum gebruiken
Beheerders gebruiken het beheercentrum om omgevingen te maken, gebruikers toe te voegen aan deze omgevingen en om andere soortgelijke taken uit te voeren. Er zijn twee manieren om het beheercentrum te openen:

#### <a name="option-1-select-settings"></a>Optie 1: selecteer Instellingen
1. Meld u aan bij [flow.microsoft.com](https://flow.microsoft.com).
2. Selecteer het tandrad van Instellingen en kies **Beheercentrum** in de lijst:  
   ![Instellingen en Beheerdersportal](./media/environments-overview-admin/settings.png)
3. Het beheercentrum wordt geopend.

#### <a name="option-2-open-adminflowmicrosoftcom"></a>Optie 2: open admin.flow.microsoft.com
Ga naar [admin.flow.microsoft.com](https://admin.flow.microsoft.com) en meld u aan met uw werkaccount. Het beheercentrum wordt geopend.

## <a name="create-an-environment"></a>Een omgeving maken
1. Selecteer in het [Beheercentrum van Microsoft Flow](https://admin.flow.microsoft.com) de optie **Omgevingen**. Alle bestaande omgevingen worden weergegeven:  
   ![](./media/environments-overview-admin/environments-list.png)
2. Selecteer **Nieuwe omgeving**. Voer de volgende gegevens in:
   
   | Eigenschap | Beschrijving |
   | --- | --- |
   | Naam van omgeving |Voer de naam van uw omgeving in, zoals `Human Resources`, of `Europe flows`. |
   | Regio |Kies de locatie voor het hosten van uw omgeving. Gebruik voor de beste prestaties de regio die het dichtst bij uw gebruikers ligt. Een voorbeeld: als de Flow-gebruikers zich in Londen bevinden, kies dan de regio Europa. Als uw Flow-gebruikers zich in New York bevinden, kiest u de regio Verenigde Staten. |
3. Selecteer **Een omgeving maken**. Uw nieuwe omgeving wordt weergegeven. 

Vervolgens voegt u gebruikers toe aan de omgeving.

## <a name="manage-your-existing-environments"></a>Uw bestaande omgevingen beheren
1. Ga naar het [Beheercentrum van Microsoft Flow](https://admin.flow.microsoft.com) en selecteer de optie **Omgevingen**.  
   ![](./media/environments-overview-admin/select-environments.png)  
2. Selecteer een omgeving om de eigenschappen daarvan te openen. 
3. Bij **Details** ziet u aanvullende informatie over de omgeving, waaronder wie de omgeving heeft gemaakt, de geografische locatie en andere eigenschappen:  
   ![](./media/environments-overview-admin/open-environment.png)
4. Selecteer **Security**. Bij **Environment roles** zijn er twee opties: **Admin** en **Maker**:  
   
    ![](./media/environments-overview-admin/environment-roles.png)
   
    Een **Maker** kan nieuwe bronnen maken in een omgeving, zoals stromen, gegevensverbindingen en gateways. 
   
   > [!NOTE]
   > Een gebruiker hoeft geen **Maker** te zijn om resources te *bewerken* in een omgeving, alleen om *netto nieuwe* resources te maken. De maker van elke resource kan bepalen wie die resource kan bewerken, en de maker kan machtigingen verlenen aan gebruikers die geen Makers in de omgeving zijn.
   > 
   > 
   
    Een **beheerder** kan beleid voor preventie van gegevensverlies maken en ook beheertaken uitvoeren, zoals omgevingen maken, gebruikers toevoegen aan een omgeving en beheer/makermachtigingen toewijzen.  
   
   1. Selecteer de rol **Environment Maker** en selecteer vervolgens **Users**:  
      ![](./media/environments-overview-admin/add-environment-maker.png)
   2. Voer een naam, e-mailadres of gebruikersgroep in waaraan u de rol Maker wilt toewijzen. Zodra u begint te typen, worden met intellisense de gebruikers/groepen weergegeven die overeenkomen met de tekst. 
   3. Selecteer **Save** om het toevoegen van gebruikers te voltooien. 
5. Selecteer binnen **Beveiliging** de optie **Gebruikersrollen**:  
    ![](./media/environments-overview-admin/security-user-roles.png)
   
    Alle eventueel bestaande rollen worden vermeld, waaronder de opties om de rol te bewerken of verwijderen. 
   
    Selecteer **Nieuwe rol** om een nieuwe rol te maken. 
6. Selecteer binnen **Beveiliging** de optie **Machtigingensets**:  
    ![](./media/environments-overview-admin/security-permission-set.png)
   
    Alle eventueel bestaande machtigingensets worden vermeld, waaronder de opties om de rol te bewerken of verwijderen. 
   
    Selecteer **Nieuwe machtigingenset** om een nieuwe te maken. 
7. In **Database** kunt u ervoor kiezen een database te maken voor het opslaan van uw gegevens. Deze database maakt deel uit van de Common Data Service.

## <a name="commonly-asked-questions"></a>Veelgestelde vragen
##### <a name="can-i-migrate-a-microsoft-flow-in-my-us-environment-to-a-europe-environment"></a>Kan ik een stroom van Microsoft Flow in mijn Amerikaanse omgeving migreren naar een Europese omgeving?
Nee, stromen kunnen niet worden verplaatst tussen omgevingen. Maak de stroom in de andere omgeving opnieuw.

##### <a name="which-license-includes-the-common-data-service"></a>In welke licentie is de Common Data Service opgenomen?
Alleen Microsoft PowerApps Plan 2 heeft rechten om databases te maken met de Common Data Service. Alle betaalde abonnementen (Microsoft Flow Plan 1 en 2, en Microsoft PowerApps Plan 1 en 2) hebben de rechten om de Common Data Service te gebruiken.

Via [Flow-prijzen](https://flow.microsoft.com/pricing/) kunt u een abonnement kiezen dat aan uw behoeften voldoet.  

In [Vragen over facturering](billing-questions.md) vindt u bovendien enkele veelgestelde vragen. 

##### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>Kan de Common Data Service buiten een omgeving worden gebruikt?
Nee. Voor de Common Data Service is een omgeving vereist. [Meer informatie](common-data-model-intro.md) hierover.

##### <a name="what-regions-include-microsoft-flow"></a>In welke regio's is Microsoft Flow beschikbaar?
Microsoft Flow ondersteunt de meeste regio's die Office 365 ondersteunt. Zie [Overzicht van de regio's](regions-overview.md) voor meer informatie.

##### <a name="what-is-needed-to-create-my-own-custom-environment"></a>Wat heb ik nodig om mijn eigen aangepaste omgeving te maken?
Alle gebruikers met de licentie voor Microsoft Flow Plan 2 kunnen naast de standaardomgeving hun eigen omgevingen maken. Alle Microsoft Flow-gebruikers, waaronder gebruikers van Office 365 en Gratis, kunnen de omgevingen gebruiken die zijn gemaakt door beheerders van Plan 2, maar zij kunnen niet hun eigen omgevingen maken. 

