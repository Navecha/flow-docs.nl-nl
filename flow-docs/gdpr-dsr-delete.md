---
title: AVG-aanvragen voor het verwijderen van gegevens Microsoft Flow | Microsoft Docs
description: Meer informatie over het gebruik van Microsoft Flow om te reageren op AVG betrokkenen-aanvragen voor het verwijderen van gegevens.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 53e33d1c202b05854401573ca16040f17eb138c9
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548076"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Reageren op AVG-aanvragen voor het verwijderen van gegevens voor Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Het "recht op doorhaling" door het verwijderen van persoonlijke gegevens uit de klant gegevens van een organisatie is een belang rijke beveiliging in de AVG. Het verwijderen van persoonlijke gegevens omvat het verwijderen van alle persoonlijke gegevens en door het systeem gegenereerde logboeken, met uitzonde ring van audit logboek gegevens.

Met Microsoft Flow kunnen gebruikers automatiserings werk stromen bouwen die een belang rijk onderdeel vormen van de dagelijkse werkzaamheden van uw organisatie. Wanneer een gebruiker uw organisatie verlaat, moet een beheerder hand matig controleren en bepalen of bepaalde gegevens en resources die de gebruiker heeft gemaakt, moeten worden verwijderd. Er zijn andere persoonlijke gegevens die automatisch worden verwijderd wanneer het account van de gebruiker wordt verwijderd uit Azure Active Directory.

In de volgende tabel ziet u welke persoons gegevens automatisch worden verwijderd en welke gegevens een beheerder nodig heeft om hand matig te controleren en te verwijderen:

|Vereist hand matig controleren en verwijderen|Automatisch verwijderd wanneer de gebruiker wordt verwijderd uit Azure Active Directory|
|------|------|
|Variabelen|Door het systeem gegenereerde logboeken|
|Omgevings machtigingen * *|uitvoerings geschiedenis|
|Terugloop|Activiteitsfeed|
|Stroom machtigingen|#B0 |
|Gebruikers Details|Gateway machtigingen|
|Inbel||
|Verbindings machtigingen||
|Aangepaste connector *||
|Machtigingen voor aangepaste connectors||

\* Elk van deze resources bevat de records ' gemaakt door ' en ' gewijzigd door ' die persoonlijke gegevens bevatten. Uit veiligheids overwegingen worden deze records bewaard totdat de resource wordt verwijderd.

\* * Voor omgevingen die een Common Data Service-Data Base bevatten, worden omgevings machtigingen (bijvoorbeeld welke gebruikers zijn toegewezen aan de omgevings maker en beheerders rollen) opgeslagen als records in de Common Data Service-data base. Zie [DSRs uitvoeren op basis van common data service klant gegevens](https://go.microsoft.com/fwlink/?linkid=872251)voor hulp bij het reageren op DSRs voor gebruikers die de common data service gebruiken.

Voor de gegevens en resources die hand matig moeten worden gecontroleerd, biedt Microsoft Flow de volgende ervaringen om persoons gegevens voor een specifieke gebruiker te zoeken of te wijzigen:

* **Website toegang:** Meld u aan bij het [PowerApps-beheer centrum](https://admin.powerapps.com/)of het [Microsoft flow-beheer centrum](https://admin.flow.microsoft.com/)

* **Power shell-toegang:**  [PowerApps admin Power shell cmdlets](https://go.microsoft.com/fwlink/?linkid=871804) 

Hier volgt een overzicht van de ervaringen die een beheerder beschikbaar kan hebben voor het verwijderen van elk type persoons gegevens binnen elk soort resource:

|Resources met persoons gegevens|Website toegang|Power shell-toegang|Automatisch verwijderen|
|-----|----|----|----|
|Door het systeem gegenereerde logboeken|[Office 365 service Trust-Portal](https://servicetrust.microsoft.com/)|||
|Variabelen|Microsoft Flow-beheer centrum|PowerApps-cmdlets||
|Omgevings machtigingen *|Microsoft Flow-beheer centrum|PowerApps-cmdlets||
|uitvoerings geschiedenis||| Verwijderd tot 28 dagen Bewaar beleid|
|Activiteitsfeed |||Verwijderd tot 28 dagen Bewaar beleid|
|Gebruikers taken|| ||
|Terugloop|Microsoft Flow Maker-Portal * *|||
|Stroom machtigingen|Microsoft Flow Maker-Portal|||
|Gebruikers Details||PowerApps-cmdlets||
|Inbel|Microsoft Flow Maker-Portal| ||
|Verbindings machtigingen|Microsoft Flow Maker-Portal| ||
|Aangepaste connector|Microsoft Flow Maker-Portal| ||
|Machtigingen voor aangepaste connectors|Microsoft Flow Maker-Portal| ||
|Goedkeurings geschiedenis|Microsoft PowerApps Maker-Portal *|||

\* Met de introductie van de Common Data Service, als er een Data Base wordt gemaakt binnen de omgeving, worden omgevings machtigingen en op modellen gebaseerde app-machtigingen opgeslagen als records in de Common Data Service-data base-instantie. Zie [DSRs uitvoeren op basis van common data service klant gegevens](https://go.microsoft.com/fwlink/?linkid=872251)voor hulp bij het reageren op DSRs voor gebruikers die de common data service gebruiken.

\*\* een beheerder alleen toegang heeft tot deze resources vanuit de portal van Microsoft Flow Maker als aan de beheerder toegang is toegewezen vanuit het Microsoft Flow-beheer centrum.

## <a name="manage-delete-requests"></a>Verwijderings aanvragen beheren

In de volgende stappen wordt beschreven hoe beheer functies bestaan voor het verwerken van aanvragen voor het verwijderen van AVG. Deze stappen moeten worden uitgevoerd in de onderstaande volg orde.

> [!IMPORTANT]
> Volg deze stappen in de aangegeven volg orde om gegevens beschadiging te voor komen.
>
>

## <a name="list-and-re-assign-flows"></a>Stromen weer geven en opnieuw toewijzen

Met deze stappen worden bestaande stromen voor een afgeleide gebruiker gekopieerd. Als u een nieuw eigendom toewijst aan de kopieën, kunnen deze stromen bestaande bedrijfs processen blijven ondersteunen. Het is belang rijk om deze stromen te kopiëren om persoonlijke id-koppelingen te verwijderen voor de ontsluitende gebruiker en er moeten nieuwe verbindingen tot stand worden gebracht voor de stroom om verbinding te maken met andere Api's en SaaS-toepassingen.

1. Meld u aan bij het [Microsoft flow-beheer centrum](https://admin.flow.microsoft.com/)en selecteer vervolgens de omgeving die stromen bevat waarvan de verwijderde gebruiker eigenaar is.

    ![omgevingen weer geven](./media/gdpr-dsr-delete/view-environments.png)

1. Selecteer **resources**, > **stromen**en selecteer vervolgens de titel voor de stroom die u opnieuw wilt toewijzen.

    ![Stromen weer geven](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Selecteer **delen beheren**.

    ![Delen beheren](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. Voeg uzelf toe aan de rechter kant van het deel venster **delen** , en selecteer vervolgens **Opslaan**.

    ![Stroom delen](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com/), selecteer **mijn stromen**en selecteer vervolgens **team stromen**.

1. Selecteer het beletsel teken **(...)** voor de stroom die u wilt kopiëren en selecteer vervolgens **Opslaan als**.

    ![Stroom opslaan als](./media/gdpr-dsr-delete/flow-save-as.png)

1. Configureer verbindingen als vereist en selecteer vervolgens **door gaan**.

1. Geef een nieuwe naam op en selecteer vervolgens **Opslaan**.

    ![Een kopie van de stroom maken](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Deze nieuwe versie van de stroom wordt weer gegeven in **mijn stromen**, waar u deze kunt delen met aanvullende gebruikers als u wilt.

    ![Team stromen](./media/gdpr-dsr-delete/team-flows.png)

1. Verwijder de oorspronkelijke stroom door het beletsel teken **(...)** te selecteren, **verwijderen**te selecteren en vervolgens opnieuw **verwijderen** te selecteren wanneer u hierom wordt gevraagd. Met deze stap worden ook onderliggende persoonlijke id's verwijderd die zijn opgenomen in systeem afhankelijkheden tussen de gebruiker en Microsoft Flow.

    ![Stroom bevestiging verwijderen](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Schakel de kopie van de stroom in door **mijn stromen** te openen en vervolgens de wissel knop in **te scha**kelen.

    ![Stroom inschakelen](./media/gdpr-dsr-delete/toggle-on.png)

1. De kopie voert nu dezelfde werk stroom logica uit als de oorspronkelijke versie.

## <a name="delete-approval-history-from-microsoft-flow"></a>Goedkeurings geschiedenis verwijderen uit Microsoft Flow

 Goedkeurings gegevens voor Microsoft Flow worden opgeslagen in de huidige of vorige versie van Common Data Service. Binnen een goed keuring bestaan persoonlijke gegevens in de vorm van goedkeurings toewijzingen en opmerkingen die zijn opgenomen in een goedkeurings antwoord. Beheerders hebben toegang tot deze gegevens door de volgende stappen uit te voeren:

1. Meld u aan bij [PowerApps](https://web.powerapps.com/).

1. Selecteer **gegevens**en selecteer vervolgens **entiteiten**.

1. Selecteer het beletsel teken **(...)** voor de entiteit **stroom goedkeuring** en open vervolgens de gegevens in micro soft Excel.

1. In micro soft Excel kunt u de goedkeurings gegevens naar behoefte zoeken, filteren en vervolgens verwijderen.

Zie het [uitvoeren van DSRs op basis van common data service klant gegevens](https://go.microsoft.com/fwlink/?linkid=872251)voor meer informatie over hoe u kunt reageren op DSRs voor gebruikers die de common data service gebruiken.


## <a name="delete-connections-created-by-a-user"></a>Verbindingen verwijderen die door een gebruiker zijn gemaakt

Verbindingen worden gebruikt in combi natie met connectors om verbinding te maken met andere Api's en SaaS-systemen.  Verbindingen bevatten verwijzingen naar de gebruiker die ze heeft gemaakt en kunnen daarom worden verwijderd om alle verwijzingen naar de gebruiker te verwijderen.

PowerApps Maker Power shell-cmdlets

Een gebruiker kan al zijn of haar verbindingen verwijderen met behulp van de functie Remove-Connection van de [PowerApps Maker Power shell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-AdminPowerAppConnection | Remove-Connection
```

Power shell-cmdlets voor PowerApps-beheer

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminPowerAppConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```

## <a name="delete-the-users-permissions-to-shared-connections"></a>De machtigingen van de gebruiker voor gedeelde verbindingen verwijderen

PowerApps Maker Power shell-cmdlets

Een gebruiker kan al hun roltoewijzingen voor gedeelde verbindingen verwijderen-ConnectionRoleAssignment functie in de [PowerApps Maker Power shell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

Power shell-cmdlets voor PowerApps-beheer

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> Roltoewijzingen voor roltoewijzingen kunnen niet worden verwijderd zonder de verbindings resource te verwijderen.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Aangepaste connectors verwijderen die door de gebruiker zijn gemaakt

Aangepaste connectors vormen een aanvulling op de bestaande out-of-Box connectors en bieden connectiviteit met andere Api's, SaaS en speciaal ontwikkelde systemen. Aangepaste connectors bevatten verwijzingen naar de gebruiker die ze heeft gemaakt en kunnen daarom worden verwijderd om verwijzingen naar de gebruiker te verwijderen.

PowerApps Maker Power shell-cmdlets

Een gebruiker kan al zijn of haar aangepaste connectors verwijderen de functie Remove-connector in de [Power shell-cmdlets van PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

Power shell-cmdlets voor PowerApps-beheer
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>De machtigingen van de gebruiker voor gedeelde aangepaste connectors verwijderen

PowerApps Maker Power shell-cmdlets

Een gebruiker kan al zijn/haar connector roltoewijzingen voor gedeelde aangepaste connector verwijderen met de functie Remove-ConnectorRoleAssignment in de [Power shell-cmdlets van PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

Power shell-cmdlets voor PowerApps-beheer
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> Roltoewijzingen voor roltoewijzingen kunnen niet worden verwijderd zonder de verbindings resource te verwijderen.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Alle door de gebruiker gemaakte omgevingen verwijderen of opnieuw toewijzen

Als beheerder moet u twee beslissingen nemen bij het verwerken van een DSR-aanvraag voor het verwijderen van een gebruiker voor elk van de omgevingen die door de gebruiker zijn gemaakt:

1. Als u vaststelt dat de omgeving niet door iemand anders in uw organisatie wordt gebruikt, kunt u ervoor kiezen om de omgeving te verwijderen
1. Als u vaststelt dat de omgeving nog steeds vereist is, kunt u ervoor kiezen om de omgeving niet te verwijderen en uzelf (of een andere gebruiker in uw organisatie) toe te voegen als een omgevings beheerder.
> [!IMPORTANT]
> Als u een omgeving verwijdert, worden alle resources in de omgeving definitief verwijderd, inclusief alle apps, stromen, verbindingen, enzovoort. Controleer daarom de inhoud van een omgeving voordat u het verwijderen.
>
>

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Toegang verlenen tot de omgevingen van een gebruiker vanuit het Microsoft Flow-beheer centrum

Een beheerder kan beheerders toegang verlenen tot een omgeving die is gemaakt door een specifieke gebruiker vanuit het [Microsoft flow-beheer centrum](https://admin.flow.microsoft.com/). Ga voor meer informatie over het beheren van omgevingen naar het [gebruik van omgevingen binnen Microsoft flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-the-users-permissions-to-all-other-environments"></a>De machtigingen van de gebruiker voor alle andere omgevingen verwijderen

Aan gebruikers kunnen machtigingen worden toegewezen (zoals omgevings beheerder, omgevings Maker, enzovoort) in een omgeving, die wordt opgeslagen in de Microsoft Flow-service als een functie toewijzing.

Met de introductie van de Common Data Service, als er een data base in de omgeving wordt gemaakt, worden deze roltoewijzingen opgeslagen als records in de Common Data Service-data base-instantie.

Voor meer informatie over het verwijderen van de machtiging van een gebruiker in een omgeving, navigeert u naar het [gebruik van omgevingen binnen Microsoft flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-gateway-settings"></a>Gateway-instellingen verwijderen

Reageren op aanvragen voor het verwijderen van gegevens over on-premises gegevens gateways vindt u [hier](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

## <a name="delete-user-details"></a>Gebruikers gegevens verwijderen

Gebruikers gegevens bieden een koppeling tussen een gebruiker en een specifieke Tenant. Voordat u deze opdracht uitvoert, moet u ervoor zorgen dat alle stromen voor deze gebruiker opnieuw zijn toegewezen en/of verwijderd. Als de beheerder eenmaal is voltooid, kan de gebruiker de gebruikers gegevens verwijderen door de cmdlet **Remove-AdminFlowUserDetails** aan te roepen en de object-id voor de gebruiker door te geven.

Power shell-cmdlets voor PowerApps-beheer
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> Als een gebruiker nog steeds eigenaar is van afzonderlijke of team stromen, retourneert deze opdracht een fout. Verwijder alle resterende stromen of team stromen voor deze gebruiker en voer de opdracht opnieuw uit om het probleem op te lossen.
>
>

## <a name="delete-the-user-from-azure-active-directory"></a>De gebruiker uit Azure Active Directory verwijderen

Zodra de bovenstaande stappen zijn voltooid, is de laatste stap het verwijderen van het account van de gebruiker voor Azure Active Directory door de stappen te volgen die worden beschreven in de AVG-documentatie voor Azure data subject-aanvraag die u kunt vinden op de [Office 365 service Trust-Portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

## <a name="delete-the-user-from-unmanaged-tenant"></a>De gebruiker uit een niet-beheerde Tenant verwijderen

Als u lid bent van een niet-beheerde Tenant, moet u een actie voor het sluiten van het **account** uitvoeren vanuit de portal voor [werk-en school-privacy](https://go.microsoft.com/fwlink/?linkid=873123).

Voer de volgende acties uit om te bepalen of u een gebruiker bent van een beheerde of onbeheerde Tenant:

1. Open de volgende URL in een browser, waarbij u ervoor zorgt dat uw e-mail adres wordt vervangen door de URL:[https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1).
1. Als u lid bent van een niet- **beheerde Tenant** , ziet u een `"IsViral": true` in het antwoord.

    {

     "Aanmelden": "foobar@unmanagedcontoso.com",

    "Domein naam": "unmanagedcontoso.com",

    "IsViral": **True**,
    
    }

1. Anders maakt u deel uit van een beheerde Tenant.
