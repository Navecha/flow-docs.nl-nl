---
title: Inleiding tot beleid voor preventie van gegevensverlies (DLP). | Microsoft Docs
description: Inleiding tot beleid voor preventie van gegevensverlies voor Microsoft Flow.
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
ms.date: 02/28/2018
ms.author: deonhe
ms.openlocfilehash: 7dbf6296383551d82d22682121210f1cd339b65e
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "29563083"
---
# <a name="data-loss-prevention-dlp-policies"></a>Beleid voor preventie van gegevensverlies (DLP)

In dit document vindt u een inleiding tot het beleid voor preventie van gegevensverlies. Als u een dergelijk beleid gebruikt, kunt u voorkomen dat uw bedrijfsgegevens worden gedeeld met de lijst met connectors die u definieert.

## <a name="whats-a-data-loss-prevention-policy"></a>Wat is beleid voor preventie van gegevensverlies?

De gegevens van een organisatie zijn essentieel voor het succes. De gegevens moeten direct beschikbaar zijn voor de besluitvorming, maar moeten worden beveiligd, zodat ze niet worden gedeeld met doelgroepen die geen toegang mogen hebben. Voor het beveiligen van deze gegevens biedt Microsoft Flow de mogelijkheid om beleidsregels te maken en af te dwingen op basis waarvan wordt bepaald welke consumentconnectors toegang kunnen krijgen tot uw zakelijke gegevens en welke connectors deze gegevens mogen delen. Deze beleidsregels waarin wordt gedefinieerd hoe gegevens kunnen worden gedeeld, worden beleid voor preventie van gegevensverlies (DLP) genoemd.

## <a name="why-create-a-dlp-policy"></a>Waarom maakt u een DLP-beleid?

U maakt een DLP-beleid om duidelijk te definiëren welke consumentconnectors toegang kunnen krijgen tot uw zakelijke gegevens en deze gegevens mogen delen. Mogelijk wil een organisatie die gebruikmaakt van Microsoft Flow niet dat de zakelijke gegevens in SharePoint automatisch worden gepubliceerd naar de Twitter-feed. Om dit te voorkomen, maakt u een DLP-beleid waarmee het gebruik van SharePoint-gegevens als bron voor tweets wordt geblokkeerd.

## <a name="benefits-of-a-dlp-policy"></a>Voordelen van een DLP-beleid

* Zorgt ervoor dat gegevens in de hele organisatie op een uniforme wijze worden beheerd.
* Voorkomt dat belangrijke zakelijke gegevens per ongeluk wordt gepubliceerd naar connectors zoals socialemediasites.

## <a name="managing-dlp-policies"></a>DLP-beleid beheren

### <a name="prerequisites-for-managing-dlp-policies"></a>Vereisten voor het beheren van een DLP-beleid

* Machtigingen voor omgevingsbeheerders of tenantbeheerders.

    In het [artikel over omgevingen](environments-overview-admin.md) vindt u meer informatie over machtigingen.
* Een [Microsoft Flow P2-licentie](billing-questions.md).

## <a name="create-a-dlp-policy"></a>Een DLP-beleid maken

### <a name="prerequisites-for-creating-dlp-policies"></a>Vereisten voor het maken van een DLP-beleid

Als u een DLP-beleid wilt maken, moet u machtigingen hebben voor ten minste één omgeving.

Volg de onderstaande stappen om een DLP-beleid te maken waarmee wordt voorkomen dat gegevens op de SharePoint-site van uw bedrijf worden gepubliceerd naar Twitter:

1. Meld u aan bij het [Microsoft Flow-beheercentrum](https://admin.flow.microsoft.com).

1. Selecteer het tabblad Gegevensbeleid en selecteer vervolgens de koppeling **Nieuw beleid**:

    ![Aanmelden](./media/prevent-data-loss/create-policy-1.png)
1. Selecteer het tabblad **Gegevensgroepen**.

1. Voer de naam in voor het DLP-beleid als *Beveiligde gegevenstoegang voor Contoso* in het label **Naam gegevensbeleid** boven aan de pagina:

    ![Aanmelden](./media/prevent-data-loss/create-policy-2.png)

1. Selecteer de [omgeving](environments-overview-admin.md) op het tabblad **Omgevingen**.

    > [!NOTE]
    > Als omgevingsbeheerder kunt u alleen beleidsregels maken die betrekking hebben op één omgeving. Als tenantbeheerder kunt u beleidsregels maken die betrekking hebben op meerdere omgevingen:
    >
    >

    ![Omgeving selecteren](./media/prevent-data-loss/create-policy-3.png)

1. Selecteer het tabblad **Gegevensgroepen**:

    ![Gegevensgroepen selecteren](./media/prevent-data-loss/create-policy-4.png)

1. Selecteer de koppeling **Toevoegen** binnen het groepsvak **Alleen bedrijfsgegevens**:

    ![Toevoegen selecteren](./media/prevent-data-loss/create-policy-5.png)

1. Selecteer de **SharePoint**- en **Salesforce**-connectors op de pagina **Connectors toevoegen**:

   ![Connectors selecteren](./media/prevent-data-loss/create-policy-6.png)

1. Selecteer de knop **Connectors toevoegen** om de connectors toe te voegen die zakelijke gegevens mogen delen.

1. Selecteer **Beleid opslaan** in de rechterbovenhoek van het scherm.

1. Na enkele ogenblikken wordt uw nieuwe DLP-beleid weergegeven in de lijst met beleidsregels voor preventie van gegevensverlies:

    ![DLP-lijst](./media/prevent-data-loss/create-policy-9.png)

1. **Optioneel**: verzendt een e-mail of ander bericht naar uw team waarin u hen erop attent maakt dat er een nieuw DLP-beleid beschikbaar is.

U hebt nu een DLP-beleid gemaakt waarmee de app gegevens mag delen tussen SharePoint en Saleforce en waarmee het delen van gegevens met andere services wordt geblokkeerd.

> [!NOTE]
> Als u een service toevoegt aan een gegevensgroep, wordt deze automatisch uit de andere gegevensgroep verwijderd. Als Twitter zich bijvoorbeeld momenteel bevindt in de gegevensgroep met **alleen zakelijke gegevens**, en u niet wilt dat zakelijke gegevens met Twitter worden gedeeld, voegt u de Twitter-service toe aan de gegevensgroep waarin **geen zakelijke gegevens zijn toegestaan**. Hiermee wordt Twitter verwijderd uit de gegevensgroep met alleen zakelijke gegevens.
>
>

## <a name="data-sharing-violations"></a>Fouten bij het delen van gegevens

Als u het hierboven beschreven DLP-beleid hebt gemaakt, ontvangt een gebruiker die een stroom maakt waarmee de gegevens worden gedeeld tussen Salesforce (in de gegevensgroep met **alleen zakelijke gegevens**) en Twitter (in de gegevensgroep waarin **geen zakelijke gegevens zijn toegestaan**) de melding dat de stroom tijdelijk is **onderbroken** vanwege een conflict met het beleid voor preventie van gegevensverlies.

![Stroom maken](./media/prevent-data-loss/10.png)

Als uw gebruikers contact met u opnemen over de onderbroken stromen, kunt u het volgende overwegen:

1. Voor dit voorbeeld geldt dat u het DLP-beleid kunt bewerken wanneer er een geldige zakelijke reden is om zakelijke gegevens te delen tussen SharePoint en Twitter.

1. Vraag de gebruiker om de stroom te bewerken zodat de stroom voldoet aan het DLP-beleid.

1. Vraag de gebruiker de onderbroken status van stroom te handhaven totdat er een beslissing is genomen over het delen van gegevens tussen deze twee entiteiten.

## <a name="find-a-dlp-policy"></a>Een DLP-beleid vinden

### <a name="admins"></a>Beheerders

Beheerders kunnen de zoekfunctie gebruiken in het Beheercentrum om specifiek DLP-beleid te vinden.

> [!NOTE]
> Beheerders moeten alle DLP-beleidsregels publiceren zodat gebruikers in de organisatie zich bewust zijn van de beleidsregels voordat ze stromen maken.
>
>

### <a name="makers"></a>Makers

Als u geen beheerdersmachtigingen hebt en graag meer wilt weten over DLP-beleidsregels in uw organisatie, neemt u contact op met de beheerder. Ook in het [artikel over makersomgevingen](environments-overview-maker.md) vindt u meer informatie.

> [!NOTE]
> Alleen beheerders mogen een DLP-beleid bewerken of verwijderen.
>
>

## <a name="edit-a-dlp-policy"></a>Een DLP-beleid bewerken

1. Start het [beheercentrum](https://admin.flow.microsoft.com).

1. Selecteer in het beheercentrum dat wordt gestart de koppeling **Gegevensbeleid** aan de linkerkant.

    ![Gegevensbeleid selecteren](./media/prevent-data-loss/2.png)

1. Zoek in de lijst met bestaande DLP-beleidsregels en selecteer de knop Bewerken naast het beleid dat u wilt bewerken.

1. Breng de gewenste wijzigingen in het beleid aan. U kunt bijvoorbeeld de omgeving of de services in de gegevensgroepen wijzigen.

1. Selecteer **Beleid opslaan** om uw wijzigingen op te slaan.

> [!NOTE]
> DLP-beleidsregels die zijn gemaakt door tenantbeheerders kunnen worden bekeken door omgevingsbeheerders, maar kunnen niet worden bewerkt door deze omgevingsbeheerders.
>
>

## <a name="delete-a-dlp-policy"></a>Een DLP-beleid verwijderen

1. Start het [beheercentrum](https://admin.flow.microsoft.com).

1. Selecteer het tabblad **Gegevensbeleid** aan de linkerkant.

    ![Tabblad Gegevensbeleid selecteren](./media/prevent-data-loss/2.png)

1. Zoek in de lijst met bestaande DLP-beleidsregels en selecteer de knop Verwijderen naast het beleid dat u wilt verwijderen.

    ![De knop Verwijderen selecteren](./media/prevent-data-loss/3-delete.png)

1. Bevestig dat u het beleid echt verwijderen door de knop **Verwijderen** te selecteren:

    ![Bevestigen dat u het beleid daadwerkelijk wilt verwijderen](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>Machtigingen voor DLP-beleid

Alleen tenant- en omgevingsbeheerders kunnen DLP-beleid maken en wijzigen. In het artikel over [omgevingen](environments-overview-admin.md) vindt u meer informatie over machtigingen.

## <a name="next-steps"></a>Volgende stappen

* [Meer informatie over omgevingen](environments-overview-admin.md)
* [Meer informatie over Microsoft Flow](getting-started.md)
* [Meer informatie over het beheercentrum](admin-center-introduction.md)
* [Meer informatie over gegevensintegratie](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)
