---
title: Overzicht van de omgeving voor beheerders | Microsoft Docs
description: Omgevingen in Microsoft Flow gebruiken, maken en beheren
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: sunayv
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: eb3e1050d22b8f672f47214952428b86186ba145
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547964"
---
# <a name="using-environments-within-microsoft-flow"></a>Omgevingen binnen Microsoft Flow gebruiken
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

## <a name="benefits"></a>Verleend

Omgevingen bieden de volgende voor delen:

* **Gegevens locatie**: omgevingen kunnen in verschillende regio's worden gemaakt en zijn gebonden aan die geografische locatie. Wanneer u een stroom in een omgeving maakt, wordt die stroom gerouteerd naar alle data centers op die geografische locatie. Dit biedt ook een prestatie voordelen.

    Als uw gebruikers zich in Europa bevinden, maakt en gebruikt u de omgeving in de regio Europa. Als uw gebruikers zich in de Verenigde Staten bevinden, maakt en gebruikt u de omgeving in de Verenigde Staten 

    > [!IMPORTANT]
    > Als u de omgeving verwijdert, worden alle stromen in die omgeving ook verwijderd. Dit geldt voor alle items die u in die omgeving maakt, inclusief verbindingen, gateways, PowerApps en meer.
* **Preventie van gegevens verlies**: als beheerder wilt u niet dat stromen die gegevens ophalen van een interne locatie (zoals *OneDrive voor bedrijven* of een share point-lijst met salaris informatie) en vervolgens die gegevens openbaar boeken (bijvoorbeeld naar  *Twitter*). Gebruik preventie van gegevens verlies om te bepalen welke Services gegevens kunnen delen binnen uw Microsoft Flow-implementatie.

    U kunt bijvoorbeeld de services *share point* en *OneDrive voor bedrijven* toevoegen aan een beleid voor alleen zakelijke gegevens. Alle stromen die in deze omgeving worden gemaakt, kunnen gebruikmaken van *share point* en *OneDrive voor bedrijven* -Services. Ze kunnen echter geen gegevens delen met andere services die niet zijn opgenomen in het beleid voor alleen zakelijke gegevens.

  > [!NOTE]
  > Preventie van gegevens verlies is beschikbaar bij sommige licentie-sku's, inclusief de P2-licentie.

* **Isolatie grens voor alle resources**: alle stromen, gateways, verbindingen, aangepaste connectors, enzovoort bevinden zich in een specifieke omgeving. Ze bestaan niet in andere omgevingen.
* **Common data service**: Hier vindt u de opties als u een stroom wilt maken waarmee gegevens in een service worden ingevoegd:

  * Gegevens invoegen in een Excel-bestand en het Excel-bestand opslaan in een account voor Cloud opslag, zoals OneDrive.
  * Maak een SQL Database en sla uw gegevens vervolgens op.
  * Gebruik de Common Data Service om uw gegevens op te slaan.

    Elke omgeving kan een maximum van één Data Base voor uw stromen hebben in de Common Data Service. De toegang tot de Common Data Service is afhankelijk van de licentie die u hebt aangeschaft. de Common Data Service is niet opgenomen in de gratis licentie.

## <a name="limitations"></a>Hardwarebeperkingen

Hoewel omgevingen veel voor delen bieden, worden er ook nieuwe beperkingen geïntroduceerd. Het feit dat omgevingen een isolatie grens vormen, betekent dat u nooit resources kunt hebben die verwijzen naar resources *in verschillende* omgevingen. U kunt bijvoorbeeld geen aangepaste connector in de ene omgeving maken en vervolgens een stroom maken die die aangepaste connector in een andere omgeving gebruikt.

## <a name="use-the-default-environment"></a>De standaard omgeving gebruiken

De **standaard** omgeving wordt gedeeld door alle gebruikers en elke gebruiker kan stromen maken in de **standaard** omgeving.

> [!TIP]
> Als u een preview-gebruiker bent, worden alle bestaande stromen opgeslagen in de standaard omgeving. Een *Preview-gebruiker* is iemand die Microsoft flow heeft gebruikt vóór de release van de algemene beschik BAARHEID (ga).

## <a name="the-admin-center"></a>Het beheer centrum

Beheerders gebruiken het beheer centrum om omgevingen te maken en te beheren. Dit zijn de twee manieren om het beheer centrum te openen:

### <a name="option-1-select-settings"></a>Optie 1: instellingen selecteren

1. Meld u aan bij [flow.Microsoft.com](https://flow.microsoft.com).
1. Selecteer het vistuig instellingen en kies **beheer centrum** in de lijst:

   ![Instellingen en beheerders Portal](./media/environments-overview-admin/settings.png)
1. Het beheer centrum wordt geopend.

### <a name="option-2-open-adminflowmicrosoftcom"></a>Optie 2: open admin.flow.microsoft.com

Ga naar [admin.flow.Microsoft.com](https://admin.flow.microsoft.com)en meld u aan met uw werk account.

## <a name="create-an-environment"></a>Een omgeving maken

1. Selecteer in het [Microsoft flow-beheer centrum](https://admin.flow.microsoft.com)de optie **omgevingen**. U ziet alle bestaande omgevingen: ![omgevingen](./media/environments-overview-admin/environments-list.png)
2. Selecteer **nieuwe omgeving** en geef de vereiste gegevens op:


   |     Eigenschap     |                                                 Beschrijvingen                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Omgevings naam |              Voer de naam van uw omgeving in, zoals `Human Resources`, of `Europe flows`.              |
   |      Deel      | Kies de locatie waar u uw omgeving wilt hosten. Gebruik een regio die het dichtst bij uw gebruikers ligt voor de beste prestaties. |
   | Omgevings type |                  Kies een omgevings type op basis van uw licentie: productie of proef versie.                   |

     ![Omgevings instellingen](./media/environments-overview-admin/new-environment-dialog.png)
3. Klik op **omgeving maken**.
4. U hebt nu de mogelijkheid om een **Data Base te maken** of **overs Laan**.
5. Als u ervoor kiest om een **Data Base te maken**, wordt u gevraagd een **valuta** en **taal** voor de Data Base op te vragen. Daarnaast kunt u er ook voor kiezen om voor beeld-apps en-gegevens te implementeren.

   ![configuratie-instellingen van de data base](./media/environments-overview-admin/create-database-dialog2.png)


U kunt nu gebruikers toevoegen aan de omgeving.

## <a name="manage-your-existing-environments"></a>Uw bestaande omgevingen beheren

1. Selecteer in het [Microsoft flow-beheer centrum](https://admin.flow.microsoft.com)de optie **omgevingen**:

   ![menu-item omgevingen](./media/environments-overview-admin/select-environments.png)
1. Selecteer een omgeving om de eigenschappen ervan te openen.
1. Op het tabblad **Details** kunt u aanvullende informatie weer geven over een omgeving, waaronder wie de omgeving heeft gemaakt, de geografische locatie en meer:

   ![tabblad Details](./media/environments-overview-admin/open-environment.png)
1. Selecteer **beveiliging**.

    Als u in de vorige stappen geen **Data Base maken** hebt geselecteerd **, zijn er**twee opties: **omgevings beheerder** en **omgevings Maker**:

    ![de beheerders rollen](./media/environments-overview-admin/environment-roles.png)

    Een **Maker** kan nieuwe resources maken, zoals stromen, gegevens verbindingen en gateways in een omgeving.

   > [!NOTE]
   > Een gebruiker hoeft geen **Maker** te zijn om resources te *bewerken* in een omgeving. Elke maker bepaalt wie hun resources kan bewerken door machtigingen te verlenen aan gebruikers die geen omgevings makers zijn.
   > 
   > 

    Een **beheerder** kan beleid voor preventie van gegevens verlies maken en andere beheer taken uitvoeren, zoals omgevingen maken, gebruikers toevoegen aan omgevingen en bevoegdheden voor beheerders/Maker toewijzen.

   1. Selecteer de rol **omgevings Maker** en selecteer vervolgens **gebruikers**: rol ![Maker](./media/environments-overview-admin/add-environment-maker.png)
   1. Voer een naam, e-mail adres of gebruikers groep in die u de rol **Maker** wilt geven.
   1. Selecteer **Opslaan**.

1. In **beveiliging**selecteert u **gebruikers rollen**:

    ![Gebruikers rollen](./media/environments-overview-admin/security-user-roles.png)

    Alle bestaande rollen worden weer gegeven, met inbegrip van de opties om de rol te bewerken of te verwijderen.

    Selecteer **nieuwe rol** om een nieuwe rol te maken.
1. Selecteer in **beveiliging** **machtigingen sets**:

    ![machtigings instelling](./media/environments-overview-admin/security-permission-set.png)

    U ziet alle bestaande machtigingen sets en opties voor het bewerken of verwijderen van rollen.

    Selecteer **nieuwe machtigingenset** om een nieuwe machtigingenset te maken.
1. Als u ervoor hebt gekozen om **Data Base te maken**om uw gegevens op te slaan, maakt deze data base deel uit van de common data service. Wanneer u op het tabblad **beveiliging** klikt, wordt u gevraagd om naar het **Dynamics 365-exemplaar beheer centrum** te gaan waar op rollen gebaseerde beveiliging kan worden toegepast.
![Dynamics-beveiligings instellingen](./media/environments-overview-admin/Security-Link-D365.png)

1. Selecteer de gebruiker in de lijst met gebruikers in de omgeving/het exemplaar.
  ![Dynamics-beveiligings instellingen](./media/environments-overview-admin/D365-Select-User.png)

1. Wijs de rol aan de gebruiker toe.

   ![rol toewijzen aan gebruiker](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> Gebruikers of groepen die aan deze omgevings rollen zijn toegewezen, krijgen niet automatisch toegang tot de data base van de omgeving (als deze bestaat) en moeten ze afzonderlijk toegang krijgen door een Data Base-eigenaar. 
>
>

### <a name="database-security"></a>Database beveiliging
De mogelijkheid om een database schema te maken en te wijzigen en te verbinden met de gegevens die zijn opgeslagen in een Data Base die is ingericht in uw omgeving, wordt bepaald door de gebruikers rollen en machtigingen sets van de data base. U kunt de gebruikers rollen en machtigingen sets voor de data base van uw omgeving beheren in de sectie **gebruikers rollen** en **machtigingen sets** van het tabblad **beveiliging** . 

   ![rol toewijzen aan gebruiker](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="can-i-move-a-flow-between-environments"></a>Kan ik een stroom verplaatsen tussen omgevingen?

Ja, stromen kunnen vanuit de ene omgeving worden geëxporteerd en in een andere omgeving worden geïmporteerd.

### <a name="which-license-includes-the-common-data-service"></a>Welke licentie bevat de Common Data Service?

Alleen Microsoft PowerApps abonnement 2 bevat rechten voor het maken van data bases met de Common Data Service. Alle betaalde abonnementen (Microsoft Flow plannen 1 en 2 en Microsoft PowerApps plannen 1 en 2) hebben echter de rechten om de Common Data Service te gebruiken.

Kies een abonnement dat geschikt is voor u door de pagina met [Microsoft flow prijzen](https://flow.microsoft.com/pricing/) te bezoeken.

Raadpleeg het document over [facturerings vragen](billing-questions.md) voor antwoorden op veelgestelde vragen over facturering.

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>Kan de Common Data Service worden gebruikt buiten een omgeving?

Geen. Voor de Common Data Service is een omgeving vereist. [Meer](common-data-model-intro.md) informatie hierover.

### <a name="what-regions-include-microsoft-flow"></a>Welke regio's bevatten Microsoft Flow?

Microsoft Flow ondersteunt de meeste regio's die door Office 365 worden ondersteund, raadpleegt u [het overzicht van regio's](regions-overview.md) voor meer informatie.

### <a name="whats-needed-to-create-my-own-custom-environment"></a>Wat is er nodig om mijn eigen aangepaste omgeving te maken?

Alle gebruikers met de licentie voor Microsoft Flow abonnement 2 kunnen hun eigen omgevingen maken. Alle Microsoft Flow gebruikers kunnen omgevingen gebruiken die zijn gemaakt door beheerders van abonnement 2, maar ze kunnen geen eigen omgevingen maken.
