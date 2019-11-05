---
title: Eenvoudig goedkeurings werk stromen automatiseren. | Microsoft Docs
description: Automatiseer goedkeurings werk stromen die kunnen worden geïntegreerd met share point, Dynamics CRM, Sales Force, OneDrive voor bedrijven, Zendesk of WordPress.
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
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c46ac3dc65b6e1a3970bd0b9b4ef17df5bef16f8
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548700"
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Een goedkeurings werk stroom met Microsoft Flow maken en testen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Met Microsoft Flow kunt u de goed keuring van documenten of processen in verschillende services beheren, waaronder share point, Dynamics 365, Sales Force, OneDrive voor bedrijven, Zendesk of WordPress.

Als u een goedkeurings werk stroom wilt maken, voegt u de actie **goed keuringen-een goed keuring starten** aan een stroom toe. Nadat u deze actie hebt toegevoegd, kan uw stroom de goed keuring van documenten of processen beheren. U kunt bijvoorbeeld goedkeurings stromen voor documenten maken die facturen, werk orders of verkoop offertes goed keuren. U kunt ook goedkeurings stromen voor processen maken die vakantie aanvragen, overwerk werk of reis plannen goed keuren.

Goed keurders kunnen reageren op aanvragen vanuit hun postvak in, [het goedkeurings centrum](https://flow.microsoft.com/manage/approvals/received/) op de Microsoft flow-website of de Microsoft flow-app.

## <a name="create-an-approval-flow"></a>Een goedkeurings stroom maken
Hier volgt een overzicht van de stroom die we gaan maken en testen:

   ![overzicht van flow](./media/modern-approvals/create-flow-overview.png)

De stroom voert de volgende stappen uit:

1. Wordt gestart wanneer iemand een vakantie aanvraag maakt in een share point online-lijst.
2. Voegt de vakantie aanvraag toe aan het goedkeurings centrum en stuurt deze vervolgens per e-mail naar de goed keurder.
3. Hiermee wordt een e-mail met de beslissing van de fiatteur verzonden naar de persoon die vakantie heeft aangevraagd.
4. Werkt de share point online-lijst bij met de beslissings opmerkingen van de fiatteur.

## <a name="prerequisites"></a>Vereisten
Als u deze procedure wilt uitvoeren, moet u toegang hebben tot:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Deze kolommen maken in uw share point online-lijst:

   ![Share point online-lijst kolommen](./media/modern-approvals/sharepoint-list-fields.png)

Noteer de naam en de URL van de share point online-lijst. U hebt deze items later nodig bij het configureren van de trigger **share point-wanneer een item is gemaakt** .

## <a name="create-your-flow-from-the-blank-template"></a>Uw stroom maken op basis van de lege sjabloon
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Een trigger toevoegen

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

Het **site adres** en de **lijst naam** zijn de items die u eerder in dit overzicht hebt genoteerd.

![Share point-info](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Een profiel actie toevoegen

1. Selecteer **nieuwe stap**en selecteer vervolgens **een actie toevoegen**.
   
    ![Nieuwe stap](./media/modern-approvals/select-sharepoint-add-action.png)
2. Geef het **profiel** op in het zoekvak **een actie kiezen** .
   
    ![Profiel zoeken](./media/modern-approvals/search-for-profile.png)
3. Zoek en selecteer de actie **Office 365-gebruikers-mijn profiel ophalen** .
   
    ![Office-gebruikers selecteren](./media/modern-approvals/select-my-profile.png)
4. Geef een naam op voor uw stroom en selecteer **stroom maken** om het werk dat we tot nu toe hebben gedaan, op te slaan.
   
    ![stroom opslaan](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Een goedkeurings actie toevoegen

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Met deze actie wordt de goedkeurings aanvraag verzonden naar het e-mail adres in het vak **toegewezen aan** .
>
>

## <a name="add-a-condition"></a>Een voor waarde toevoegen

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Een e-mail actie voor goed keuringen toevoegen

Volg deze stappen om een e-mail bericht te verzenden als de vakantie aanvraag is goedgekeurd:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![goedgekeurde e-mail sjabloon configureren](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Een bijwerk actie voor goedgekeurde aanvragen toevoegen

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> **Site adres**, **lijst naam**, **id**en **titel** zijn vereist.
>
>

![artikel configuratie bijwerken](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Een e-mail actie voor afwijzingen toevoegen

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![configuratie voor geweigerde aanvragen](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Update-actie voor geweigerde aanvragen toevoegen

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > **Site adres**, **lijst naam**, **id**en **titel** zijn vereist.
   >
   >

![artikel kaart bijwerken](./media/modern-approvals/configure-update-item-no.png)

1. Selecteer **stroom bijwerken** om het werk dat we hebben uitgevoerd, op te slaan.
   
    ![Update-actie selecteren](./media/modern-approvals/update.png)

Als u de volgende stap hebt gevolgd, moet uw stroom eruitzien als deze scherm afbeelding:

![overzicht van flow](./media/modern-approvals/completed-flow.png)

Nu u de stroom hebt gemaakt, is het tijd om te testen!

## <a name="request-an-approval"></a>Een goed keuring aanvragen

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]


## <a name="create-long-running-approvals"></a>Langlopende goed keuringen maken

Als uw stroom waarschijnlijk langer dan 30 dagen wordt uitgevoerd, kunt u overwegen uw goed keuringen op te slaan in Common Data Service. Dit maakt het mogelijk om stromen te maken die reageren op Reacties op goedkeurings aanvragen, zelfs nadat de oorspronkelijke stroom een time-out heeft uitgevoerd. Hiervoor gebruikt u twee stromen, een om een goedkeurings aanvraag te verzenden en de andere om bedrijfs logica uit te voeren op de antwoorden op de goedkeurings aanvraag, op basis van de actie **een goed keuring maken (v2)** . Meer informatie over [langlopende goed keuringen](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/long-lived-approvals-other-approval-improvements).

>[!TIP]
> Als u moderne e-mailclients gebruikt, hoeft u zich niet af te vragen als een aanvraag nog vereist is omdat Microsoft Flow de e-mail automatisch bijwerkt om aan te geven dat de goed keuring is voltooid.

## <a name="cancel-an-approval-requests"></a>Een goedkeurings aanvraag annuleren

Soms wilt u mogelijk een goedkeurings aanvraag annuleren die u hebt verzonden. Mogelijk hebt u een fout gemaakt in de aanvraag of is deze niet meer relevant. In beide gevallen kan de persoon die de aanvraag heeft verzonden deze annuleren door de volgende stappen uit te voeren:

1. De goed keuring selecteren
1. Selecteer **goed keuring annuleren** in het zijvenster.

>[!TIP]
>U kunt altijd het tabblad **geschiedenis** selecteren om de goedkeurings aanvragen weer te geven die u hebt geannuleerd.

>[!NOTE]
> De annulerings functie wordt ondersteund bij de actie **een goed keuring maken (v2)** .

## <a name="request-approvals-from-guest-users"></a>Goed keuringen aanvragen bij gast gebruikers

U kunt aanvragen voor goed keuring verzenden naar personen buiten uw organisatie. Gebruik hiervoor Azure Active Directory-gast gebruikers (Azure AD) door [gebruikers uit andere tenants als gasten uit te nodigen](https://docs.microsoft.com/azure/active-directory/b2b/add-user-without-invite).

Wanneer u een rol toewijst aan een gast, krijgt de gast de benodigde machtiging om deel te nemen aan het goedkeurings proces.

Nu u de stroom hebt gemaakt en getest, moet u ervoor zorgen dat anderen weten hoe ze deze kunnen gebruiken.

## <a name="learn-more"></a>Meer informatie

* [In behandeling zijnde goedkeurings aanvragen](approve-reject-requests.md) weer geven en beheren
* [Sequentiële goedkeurings stromen maken.](sequential-modern-approvals.md)
* [Parallelle goedkeurings stromen maken.](parallel-modern-approvals.md)
* Installeer de mobiele app voor Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [IOS](https://aka.ms/flowmobiledocsios)of [Windows Phone](https://aka.ms/flowmobilewindows).
