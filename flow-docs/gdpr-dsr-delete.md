---
title: 'Microsoft Flow: AVG-verzoeken van betrokkenen - verwijdering | Microsoft Docs'
description: Ontdek hoe u Microsoft Flow kunt gebruiken om te reageren op AVG-verzoeken van betrokkenen voor het verwijderen van gegevens.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: 70206e0ed6c2b59d0dfffa0c4608ba47e0fac1dc
ms.sourcegitcommit: ca875127f607034d7ef6a3fe270fc48e4f7eeee6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/20/2018
ms.locfileid: "39175127"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Reageren op AVG-verzoeken van betrokkenen voor het verwijderen van gegevens in Microsoft Flow

Het recht op vergetelheid, het recht om persoonsgegevens uit de klantgegevens van een organisatie te laten verwijderen, is een belangrijke beschermingsmaatregel in de AVG. Het verwijderen van persoonsgegevens omvat het verwijderen van alle persoonsgegevens en door het systeem gegenereerde logboeken, behalve gegevens van auditlogboeken.

Met Microsoft-Flow kunnen gebruikers automatiseringswerkstromen creëren die een belangrijk onderdeel vormen van de dagelijkse werkzaamheden van uw organisatie. Wanneer een gebruiker uw organisatie verlaat, moet een beheerder handmatig controleren en bepalen of bepaalde gegevens en resources die de gebruiker heeft gemaakt, al dan niet moeten worden verwijderd. Er zijn andere persoonsgegevens die automatisch worden verwijderd wanneer het account van de gebruiker wordt verwijderd uit Azure Active Directory.

In de volgende tabel ziet u welke persoonsgegevens automatisch worden verwijderd en welke gegevens een beheerder handmatig moet controleren en verwijderen:

|Moet handmatig worden gecontroleerd en verwijderd|Automatisch verwijderd wanneer de gebruiker wordt verwijderd uit Azure Active Directory|
|------|------|
|Omgeving*|Door het systeem gegenereerde logboeken|
|Omgevingsmachtigingen**|Uitvoeringsgeschiedenis|
|Stromen|Activiteitsfeed|
|Stroommachtigingen|Gateway |
|Gebruikersdetails|Gatewaymachtigingen|
|Verbindingen*||
|Verbindingsmachtigingen||
|Aangepaste connector*||
|Machtigingen voor aangepaste connectors||

*Elk van deze resources bevat Gemaakt door- en Gewijzigd door-records die persoonsgegevens bevatten. Deze records worden uit veiligheidsoverwegingen bewaard totdat de resource wordt verwijderd.

**In omgevingen met een Common Data Service For Apps-database worden omgevingsmachtigingen (bijvoorbeeld welke gebruikers zijn toegewezen aan de rollen Omgevingsmaker en Beheerder) opgeslagen als records in de Common Data Service-database. Zie [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Verzoeken van betrokkenen uitvoeren op basis van klantgegevens van Common Data Service) voor informatie over het reageren op verzoeken van betrokkenen voor gebruikers die gebruikmaken van Common Data Service.

Voor de gegevens en resources die handmatig moeten worden bekeken, biedt Microsoft Flow de volgende ervaringen om persoonsgegevens voor een specifieke gebruiker te vinden of te wijzigen:

* **Webtoegang:** aanmelden bij het [PowerApps-beheercentrum](https://admin.powerapps.com/) of het [Microsoft Flow-beheercentrum](https://admin.flow.microsoft.com/)

* **PowerShell-toegang:**  [PowerApps Admin PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871804) 

Hier volgt de uitsplitsing van ervaringen die een beheerder ter beschikking staan voor het verwijderen van elk type persoonsgegevens binnen elk type resource:

|Resources met persoonsgegevens|Webtoegang|PowerShell-toegang|Geautomatiseerde verwijdering|
|-----|----|----|----|
|Door het systeem gegenereerde logboeken|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|||
|Omgeving|Microsoft Flow-beheercentrum|PowerApps-cmdlets||
|Omgevingsmachtigingen*|Microsoft Flow-beheercentrum|PowerApps-cmdlets||
|Uitvoeringsgeschiedenis||| Verwijderd via een bewaarbeleid van 28 dagen|
|Activiteitsfeed |||Verwijderd via een bewaarbeleid van 28 dagen|
|Gebruikerstaken|| ||
|Stromen|Microsoft Flow Maker Portal**|||
|Stroommachtigingen|Microsoft Flow Maker Portal|||
|Gebruikersdetails||PowerApps-cmdlets||
|Verbindingen|Microsoft Flow Maker Portal| ||
|Verbindingsmachtigingen|Microsoft Flow Maker Portal| ||
|Aangepaste connector|Microsoft Flow Maker Portal| ||
|Machtigingen voor aangepaste connectors|Microsoft Flow Maker Portal| ||
|Goedkeuringsgeschiedenis|Microsoft PowerApps Maker Portal*|||

*Sinds de introductie van de Common Data Service for Apps worden, als er binnen de omgeving een database wordt gemaakt, omgevingsmachtigingen en modelgestuurde app-machtigingen als records in het database-exemplaar van Common Data Service for Apps opgeslagen. Zie [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Verzoeken van betrokkenen uitvoeren op basis van klantgegevens van Common Data Service) voor informatie over het reageren op verzoeken van betrokkenen voor gebruikers die gebruikmaken van Common Data Service.

\*\*Een beheerder heeft alleen toegang tot deze bronnen vanuit Microsoft Flow Maker Portal als de beheerder toegang toegewezen heeft gekregen vanuit het Microsoft Flow Admin Center.

## <a name="manage-delete-requests"></a>Verwijderingsaanvragen beheren

In de onderstaande stappen wordt beschreven hoe beheerfuncties bestaan voor het uitvoeren van verwijderingsaanvragen in het kader van de AVG. Deze stappen moeten worden uitgevoerd in de onderstaande volgorde.

> [!IMPORTANT]
> Volg deze stappen in de aangegeven volgorde, om beschadiging van gegevens te voorkomen.
>
>

## <a name="list-and-re-assign-flows"></a>Stromen weergeven en opnieuw toewijzen

Met deze stappen worden bestaande stromen voor een vertrekkende gebruiker gekopieerd. Als u de kopieën een nieuwe eigenaar toewijst, kunnen deze stromen bestaande bedrijfsprocessen blijven ondersteunen. Het kopiëren van deze stromen is belangrijk voor het verwijderen van koppelingen naar de vertrekkende gebruiker en er moeten nieuwe verbindingen tot stand worden gebracht zodat de stroom verbinding kan maken met andere API's en SaaS-toepassingen.

1. Meld u aan bij het [Microsoft-Flow-beheercentrum](https://admin.flow.microsoft.com/) en selecteer de omgeving die stromen bevat waarvan de verwijderde gebruiker eigenaar is.

    ![Omgevingen bekijken](./media/gdpr-dsr-delete/view-environments.png)

1. Selecteer **Resources** > **Stromen** en selecteer vervolgens de titel voor de stroom die u opnieuw wilt toewijzen.

    ![Stromen bekijken](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Selecteer **Delen beheren**.

    ![Delen beheren](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. Voeg uzelf als eigenaar toe in het deelvenster **Delen** dat aan de rechterkant wordt weergegeven en selecteer **Opslaan**.

    ![Stroom delen](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com/), selecteer **Mijn stromen** en selecteer **Teamstromen**.

1. Selecteer het beletselteken **(...)** voor de stroom die u wilt kopiëren en selecteer **Opslaan als**.

    ![Stroom opslaan als](./media/gdpr-dsr-delete/flow-save-as.png)

1. Configureer de vereiste verbindingen en selecteer **Doorgaan**.

1. Geef een nieuwe naam op en selecteer **Opslaan**.

    ![Kopie van de stroom maken](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Deze nieuwe versie van de stroom wordt weergegeven in **Mijn stromen**, waar u deze desgewenst kunt delen met extra gebruikers.

    ![Teamstromen](./media/gdpr-dsr-delete/team-flows.png)

1. Verwijder de oorspronkelijke stroom door het beletselteken **(...)** te selecteren, **Verwijderen** te selecteren en vervolgens nogmaals **Verwijderen** te selecteren als dit wordt gevraagd. In deze stap worden ook onderliggende persoonlijke id's verwijderd die zijn opgenomen in systeemafhankelijkheden tussen de gebruiker en Microsoft Flow.

    ![Bevestiging voor verwijderen stroom](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Schakel de kopie van de stroom in door **Mijn stromen** te openen en de schakeloptie op **Aan** te zetten.

    ![Stroom inschakelen](./media/gdpr-dsr-delete/toggle-on.png)

1. De kopie voert nu dezelfde werkstroomlogica uit als de oorspronkelijke versie.

## <a name="delete-approval-history-from-microsoft-flow"></a>Goedkeuringsgeschiedenis verwijderen uit Microsoft Flow

 Goedkeuringsgegevens voor Microsoft-Flow worden opgeslagen in de huidige of de vorige versie van de Common Data Service for Apps. Een goedkeuring bevat persoonsgegevens in de vorm van goedkeuringstoewijzingen en commentaar in een goedkeuringsantwoord. Beheerders hebben toegang tot die gegevens met de volgende stappen:

1. Meld u aan bij [PowerApps](https://web.powerapps.com/).

1. Selecteer **Gegevens** en vervolgens **Entiteiten**.

1. Selecteer het beletselteken **(...)** voor de entiteit **Stroomgoedkeuring** en open vervolgens de gegevens in Microsoft Excel.

1. In Microsoft Excel kunt u goedkeuringsgegevens naar behoefte zoeken, filteren en vervolgens verwijderen.

Zie [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Verzoeken van betrokkenen uitvoeren op basis van klantgegevens van Common Data Service) voor meer informatie over het reageren op verzoeken van betrokkenen voor gebruikers die gebruikmaken van Common Data Service.


## <a name="delete-connections-created-by-a-user"></a>Door een gebruiker gemaakte verbindingen verwijderen

Verbindingen worden in combinatie met connectors gebruikt om verbinding te maken met andere API's en SaaS-systemen.  Verbindingen bevatten verwijzingen naar de gebruiker die ze heeft gemaakt en kunnen dus worden verwijderd om verwijzingen naar de gebruiker te verwijderen.

PowerApps Maker PowerShell-cmdlets

Een gebruiker kan al zijn/haar verbindingen verwijderen met behulp van de functie Remove-Connection van de [PowerApps Maker PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-Connection | Remove-Connection
```

PowerApps Admin PowerShell-cmdlets

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```
## <a name="delete-the-users-permissions-to-shared-connections"></a>De machtigingen van de gebruiker voor gedeelde verbindingen verwijderen

PowerApps Maker PowerShell-cmdlets

Een gebruiker kan al zijn/haar verbindingsroltoewijzingen voor gedeelde verbindingen verwijderen met de functie Remove-ConnectionRoleAssignment in de [PowerApps Maker PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

PowerApps Admin PowerShell-cmdlets

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> Eigenaarsroltoewijzingen kunnen niet worden verwijderd zonder de verbindingsresource te verwijderen.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Door de gebruiker gemaakte aangepaste connectors verwijderen

Aangepaste connectors vormen een aanvulling op de bestaande meegeleverde connectors, en maken verbinding mogelijk met andere API's, SaaS- en speciaal ontwikkelde systemen. Aangepaste verbindingen bevatten wel verwijzingen naar de gebruiker die ze heeft gemaakt en kunnen dus worden verwijderd om verwijzingen naar de gebruiker te verwijderen.

PowerApps Maker PowerShell-cmdlets

Een gebruiker kan al zijn/haar aangepaste verbindingen verwijderen met behulp van de functie Remove-Connector in de [PowerApps Maker PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

PowerApps Admin PowerShell-cmdlets
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>De machtigingen van de gebruiker voor gedeelde aangepaste verbindingen verwijderen

PowerApps Maker PowerShell-cmdlets

Een gebruiker kan al zijn/haar connectorroltoewijzingen voor gedeelde aangepaste connectors verwijderen met de functie Remove-ConnectorRoleAssignment in de [PowerApps Maker PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

PowerApps Admin PowerShell-cmdlets
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> Eigenaarsroltoewijzingen kunnen niet worden verwijderd zonder de verbindingsresource te verwijderen.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Alle door de gebruiker gemaakte omgevingen verwijderen of opnieuw toewijzen

Als beheerder moet u twee beslissingen nemen bij de verwerking van een verwijderingsverzoek van betrokkenen voor een gebruiker voor elk van de omgevingen die door de gebruiker zijn gemaakt:

1. Als u vaststelt dat de omgeving niet door iemand anders in uw organisatie wordt gebruikt, kunt u de omgeving verwijderen.
1. Als u vaststelt dat de omgeving nog steeds nodig is, kunt u ervoor kiezen de omgeving niet te verwijderen en uzelf (of een andere gebruiker in uw organisatie) toe te voegen als omgevingsbeheerder.
> [!IMPORTANT]
> Door een omgeving te verwijderen worden alle resources in de omgeving definitief verwijderd, inclusief alle apps, stromen, verbindingen enzovoort. Vergeet dus niet de inhoud van een omgeving te bekijken voordat u deze verwijdert.
>
>

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Toegang verlenen tot de omgevingen van een gebruiker vanuit het Microsoft Flow-beheercentrum

Een beheerder kan beheerderstoegang verlenen tot een omgeving die is gemaakt door een specifieke gebruiker vanuit het [Microsoft Flow-beheercentrum](https://admin.flow.microsoft.com/). Navigeer naar [Omgevingen gebruiken in Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin) voor meer informatie over het beheren van omgevingen.

## <a name="delete-the-users-permissions-to-all-other-environments"></a>De machtigingen van de gebruiker voor alle andere omgevingen verwijderen

Gebruikers kunnen machtigingen (zoals Omgevingsbeheerder, Omgevingsmaker, enzovoort) krijgen toegewezen in een omgeving, die in de Microsoft Flow-service worden opgeslagen als 'roltoewijzing'.

Sinds de introductie van de Common Data Service for Apps worden, als er binnen de omgeving een database wordt gemaakt, deze roltoewijzingen als records in de database-instance van Common Data Service for Apps opgeslagen.

Navigeer naar [Omgevingen gebruiken in Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin) voor meer informatie over het verwijderen van de machtiging van een gebruiker in een omgeving.

## <a name="delete-gateway-settings"></a>Gateway-instellingen verwijderen
Informatie over het reageren op verwijderingsverzoeken van een betrokkene voor on-premises gegevensgateways vindt u [hier](https://docs.microsoft.com/en-us/power-bi/service-gateway-onprem#tenant-level-administration).

## <a name="delete-user-details"></a>Gebruikersgegevens verwijderen
Details van de gebruikers bieden een koppeling tussen een gebruiker en een specifieke tenant. Voordat u deze opdracht gaat uitvoeren, moet u ervoor zorgen dat alle stromen voor deze gebruiker opnieuw zijn toegewezen en/of verwijderd. Zodra die stap is voltooid, kan een beheerder gebruikersdetails verwijderen door de cmdlet **Remove-AdminFlowUserDetails** aan te roepen en uit te voeren in de Object-id voor de gebruiker.


PowerApps Admin PowerShell-cmdlets
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> Als een gebruiker nog steeds de eigenaar is van afzonderlijke stromen of teamstromen, retourneert deze opdracht een fout. U kunt dit oplossen door alle resterende stromen of teamstromen voor deze gebruiker te verwijderen en de opdracht opnieuw uit te voeren.
>
>
## <a name="delete-the-user-from-azure-active-directory"></a>De gebruiker verwijderen uit Azure Active Directory
Zodra de bovenstaande stappen zijn voltooid, bestaat de laatste stap uit het verwijderen van het account van de gebruiker voor Azure Active Directory. Voer hiervoor de stappen uit die worden beschreven in de Azure-documentatie over aanvragen van betrokkenen in het kader van de AVG. U vindt deze in de [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

## <a name="delete-the-user-from-unmanaged-tenant"></a>De gebruiker uit de onbeheerde tenant verwijderen
In het geval u lid bent van een onbeheerde tenant, moet u de actie **Account sluiten** uitvoeren in de [portal voor privacy op het werk en op school](https://go.microsoft.com/fwlink/?linkid=873123).

Als u wilt bepalen of u een gebruiker van een beheerde of onbeheerde tenant bent, voert u de volgende acties uit:
1. Open de volgende URL in een browser en zorg ervoor dat u uw e-mailadres in de URL vervangt:[ https://login.windows.net/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.windows.net/common/userrealm/foobar@contoso.com?api-version=2.1).
1. Als u lid bent van een **onbeheerde tenant**, ziet u een `"IsViral": true` in het antwoord.

    {

     Login: foobar@unmanagedcontoso.com,

    DomainName: unmanagedcontoso.com,

    IsViral: **true**,
    
    }

1. Anders maakt u deel uit van een beheerde tenant.

