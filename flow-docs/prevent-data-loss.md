---
title: Inleiding tot beleid voor preventie van gegevens verlies (DLP). | Microsoft Docs
description: Inleiding tot beleid voor preventie van gegevens verlies voor Microsoft Flow.
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
ms.date: 04/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 46f646fb81fcf7043ff612a240528fed72638048
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548529"
---
# <a name="data-loss-prevention-dlp-policies"></a>Beleid voor preventie van gegevens verlies (DLP)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Dit document bevat informatie over het beleid voor preventie van gegevens verlies, waarmee u uw bedrijfs gegevens kunt beveiligen met een lijst van connectors die u definieert.

## <a name="whats-a-data-loss-prevention-policy"></a>Wat is beleid voor preventie van gegevens verlies?

De gegevens van een organisatie zijn essentieel voor het slagen. De gegevens moeten direct beschikbaar zijn voor de besluit vorming, maar moeten worden beveiligd zodat ze niet worden gedeeld met doel groepen die geen toegang mogen hebben. Microsoft Flow biedt u de mogelijkheid om een beleid te maken en af te dwingen dat bepaalt welke Consumer-connectors toegang hebben tot en delen van zakelijke gegevens om deze gegevens te beveiligen. Deze beleids regels die definiëren hoe gegevens kunnen worden gedeeld, worden het beleid voor preventie van gegevens verlies (DLP) genoemd.

## <a name="why-create-a-dlp-policy"></a>Waarom een DLP-beleid maken?

U maakt DLP-beleid om duidelijk te definiëren welke Consumer-connectors toegang hebben tot uw zakelijke gegevens en deze kunnen delen. Een organisatie die bijvoorbeeld Microsoft Flow gebruikt, wil niet dat de zakelijke gegevens in share point automatisch worden gepubliceerd naar de Twitter-feed. U kunt dit voor komen door een DLP-beleid te maken waarmee share point-gegevens worden geblokkeerd voor gebruik als de bron voor tweets.

## <a name="benefits-of-a-dlp-policy"></a>Voor delen van een DLP-beleid

* Zorgt ervoor dat gegevens in de hele organisatie op een uniforme manier worden beheerd.
* Hiermee voor komt u dat belang rijke Bedrijfs gegevens per ongeluk worden gepubliceerd naar connectors zoals sites voor sociale media.

## <a name="managing-dlp-policies"></a>DLP-beleid beheren

### <a name="prerequisites-for-managing-dlp-policies"></a>Vereisten voor het beheren van het DLP-beleid

* De machtigingen voor de omgevings beheerder of Tenant beheerder.

    Meer informatie over machtigingen vindt u in het [artikel omgevingen](environments-overview-admin.md).
* Een [Microsoft flow P2-licentie](billing-questions.md).

## <a name="create-a-dlp-policy"></a>Een DLP-beleid maken

### <a name="prerequisites-for-creating-dlp-policies"></a>Vereisten voor het maken van DLP-beleid

Als u een DLP-beleid wilt maken, moet u machtigingen hebben voor ten minste één omgeving.

Volg deze stappen om een DLP-beleid te maken waarmee wordt voor komen dat gegevens in de share point-site van uw bedrijf worden gepubliceerd naar Twitter:

1. Meld u aan bij het [Microsoft flow-beheer centrum](https://admin.flow.microsoft.com) (beheer centrum).

1. Selecteer het tabblad gegevens beleid en selecteer vervolgens de koppeling **Nieuw beleid** :

    ![Aanmelden](./media/prevent-data-loss/create-policy-1.png)
1. Selecteer het tabblad **gegevens groepen** .

1. Voer de naam van het DLP-beleid in als *beveiligde gegevens toegang voor contoso* in het label **naam gegevens beleid** boven aan de pagina:

    ![Aanmelden](./media/prevent-data-loss/create-policy-2.png)

1. Selecteer de [omgeving](environments-overview-admin.md) op het tabblad **omgevingen** .

    > [!NOTE]
    > Als omgevings beheerder kunt u beleids regels maken die alleen van toepassing zijn op één omgeving. Als Tenant beheerder kunt u beleids regels maken die van toepassing zijn op een wille keurige combi natie van omgevingen:
    >
    >

    ![Omgeving selecteren](./media/prevent-data-loss/create-policy-3.png)

1. Selecteer het tabblad **gegevens groepen** :

    ![gegevens groepen selecteren](./media/prevent-data-loss/create-policy-4.png)

1. Selecteer de koppeling **toevoegen** die zich in de groep **alleen zakelijke gegevens** bevindt:

    ![Selecteer toevoegen](./media/prevent-data-loss/create-policy-5.png)

1. Selecteer de **share point-** en **Sales Force** -connectors op de pagina **connectors toevoegen** :

   ![connectors selecteren](./media/prevent-data-loss/create-policy-6.png)

1. Selecteer de knop **connectors toevoegen** om de connectors toe te voegen die zakelijke gegevens kunnen delen.

1. Selecteer **beleid opslaan** in de rechter bovenhoek van het scherm.

1. Na enkele ogen blikken wordt uw nieuwe DLP-beleid weer gegeven in de lijst met beleids regels voor preventie van gegevens verlies:

    ![DLP-lijst](./media/prevent-data-loss/create-policy-9.png)

1. **Optioneel** Een e-mail bericht of andere communicatie naar uw team verzenden, zodat u wordt gewaarschuwd dat er nu een nieuw DLP-beleid beschikbaar is.

Gefeliciteerd, u hebt nu een DLP-beleid gemaakt waarmee de app gegevens kan delen tussen share point en Sales Force en het delen van gegevens met andere services blokkeert.

> [!NOTE]
> Als u een service toevoegt aan één gegevens groep, wordt deze automatisch uit de andere gegevens groep verwijderd. Als Twitter zich momenteel in de gegevens groep **alleen zakelijke gegevens** bevindt en u niet wilt toestaan dat bedrijfs gegevens worden gedeeld met Twitter, moet u de Twitter-service gewoon toevoegen aan de gegevens groep **geen zakelijke gegevens toegestaan** . Hiermee wordt Twitter verwijderd uit de gegevens groep met alleen zakelijke gegevens.
>
>

## <a name="data-sharing-violations"></a>Schendingen van gegevens deling

Ervan uitgaande dat u het hierboven beschreven DLP-beleid hebt gemaakt, als een gebruiker een stroom maakt die gegevens deelt tussen Sales Force (in de gegevens groep **alleen zakelijke gegevens** ) en Twitter (in de gegevens groep **geen zakelijke gegevens toegestaan** ), wordt de gebruiker Er wordt op de hoogte gebracht dat de stroom is **onderbroken** vanwege een conflict met het beleid voor preventie van gegevens verlies dat u hebt gemaakt.

![stroom maken](./media/prevent-data-loss/10.png)

Als uw gebruikers contact met u opnemen over onderbroken stromen, kunt u het volgende overwegen:

1. Als er in dit voor beeld een geldige zakelijke reden is om zakelijke gegevens te delen tussen share point en Twitter, kunt u het DLP-beleid bewerken.

1. Vraag de gebruiker om de stroom te bewerken om te voldoen aan het DLP-beleid.

1. Vraag de gebruiker om de stroom in de onderbroken status te laten totdat er een beslissing wordt genomen over het delen van gegevens tussen deze twee entiteiten.

## <a name="find-a-dlp-policy"></a>Een DLP-beleid zoeken

### <a name="admins"></a>Beheerders

Beheerders kunnen de zoek functie van het beheer centrum gebruiken om een specifiek DLP-beleid te vinden.

> [!NOTE]
> Beheerders moeten alle DLP-beleids regels publiceren zodat gebruikers in de organisatie zich bewust zijn van de beleids regels voordat ze stromen maken.
>
>

### <a name="makers"></a>Makers

Als u geen beheerders machtigingen hebt en u meer wilt weten over het DLP-beleid in uw organisatie, neemt u contact op met de beheerder. Meer informatie vindt u in het artikel van de [Maker-omgeving](environments-overview-maker.md) .

> [!NOTE]
> Alleen beheerders kunnen DLP-beleid bewerken of verwijderen.
>
>

## <a name="edit-a-dlp-policy"></a>Een DLP-beleid bewerken

1. Start het [beheer centrum](https://admin.flow.microsoft.com).

1. Selecteer in het beheer centrum dat wordt gestart de koppeling **gegevens beleid** aan de linkerkant.

    ![gegevens beleid selecteren](./media/prevent-data-loss/2.png)

1. Zoek in de lijst met bestaand DLP-beleid en selecteer de knop Bewerken naast het beleid dat u wilt bewerken.

1. Breng de benodigde wijzigingen aan in het beleid. U kunt bijvoorbeeld de omgeving of de services in de gegevens groepen wijzigen.

1. Selecteer **beleid opslaan** om uw wijzigingen op te slaan.

> [!NOTE]
> DLP-beleid dat is gemaakt door Tenant beheerders kan worden weer gegeven door omgevings beheerders, maar kan niet worden bewerkt door omgevings beheerders.
>
>

## <a name="delete-a-dlp-policy"></a>Een DLP-beleid verwijderen

1. Start het [beheer centrum](https://admin.flow.microsoft.com).

1. Selecteer het tabblad **gegevens beleid** aan de linkerkant.

    ![tabblad gegevens beleid selecteren](./media/prevent-data-loss/2.png)

1. Zoek in de lijst met bestaande DLP-beleids regels en selecteer vervolgens de knop verwijderen naast het beleid dat u wilt verwijderen:

    ![Selecteer de knop verwijderen](./media/prevent-data-loss/3-delete.png)

1. Bevestig dat u het beleid echt wilt verwijderen door de knop **verwijderen** te selecteren:

    ![Bevestig dat u het beleid echt wilt verwijderen](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>DLP-beleids machtigingen

Alleen Tenant-en omgevings beheerders kunnen DLP-beleid maken en wijzigen. Meer informatie over machtigingen vindt u in het artikel [omgevingen](environments-overview-admin.md) .


## <a name="custom-and-http-connectors"></a>Aangepaste en HTTP-connectors

Aangepaste en HTTP-connectors moeten worden toegevoegd aan DLPs met behulp van een Microsoft Flow sjabloon of een Power shell.

> [!TIP]
> U kunt geen downgrade uitvoeren van schema versie 2018-11-01. HTTP-ondersteuning kan niet uit een beleid worden verwijderd. Als u HTTP-ondersteuning probeert te verwijderen, is het DLP-beleid mogelijk beschadigd. Als er nog een DLP-beleid wordt bijgewerkt ter ondersteuning van HTTP-connectors, kunnen de huidige stromen die gebruikmaken van deze HTTP-mogelijkheden, worden afgesloten.

Hier vindt u de HTTP-Connect oren die u aan een beleid kunt toevoegen:

- HTTP (en HTTP + Swagger)
- HTTP-webhook
- HTTP-aanvraag

## <a name="add-connectors-custom-and-http-connectors-with-templates"></a>Aangepaste en HTTP-connectors voor connectors toevoegen met sjablonen

Als u een aangepaste connector wilt toevoegen aan een beleid met behulp van een [sjabloon](https://flow.microsoft.com/galleries/public/templates/ae9683086770420e902c043e5ed4b363/), voert u de naam van het beleid, de groep waaraan u de connector wilt toevoegen en de naam, id en type van de connector. Voer de stroom opnieuw uit om de aangepaste connector toe te voegen aan het beleid en de opgegeven groep.

Als u de HTTP-connectors via de [sjabloon](https://flow.microsoft.com/galleries/public/templates/834eb1366aa54335a5f979014a9e0477/)wilt toevoegen aan een bestaand beleid, voert u de naam in van het beleid waaraan u deze wilt toevoegen en voert u vervolgens de stroom uit.

## <a name="add-custom-and-http-connectors-with-powershell"></a>Aangepaste en HTTP-connectors toevoegen met Power shell

Als u ondersteuning wilt toevoegen voor aangepaste connectors en/of HTTP-connectors met behulp van de Power shell, [downloadt](https://docs.microsoft.com/powerapps/administrator/powerapps-powershell) en importeert u de nieuwste PowerApps Power shell-scripts en gebruikt u vervolgens de volgende cmdlets: New-AdminDlpPolicy, set-AdminDlpPolicy, Add-CustomConnectorToPolicy ' en ' Remove-CustomConnectorFromPolicy ' om het beleid te wijzigen. Gebruik de cmdlet Get-Help-detailed als referentie.


> [!IMPORTANT]
> Gebruik de schema versie 2018-11-01 bij het maken of bijwerken van een DLP-beleid om HTTP-connectors op te stellen. Het toevoegen van HTTP-ondersteuning via de sjabloon of Power Shell heeft alleen invloed op het opgegeven beleid. Nieuwe beleids regels die zijn gemaakt via het beheer centrum bevatten geen HTTP-connectors.



## <a name="next-steps"></a>Volgende stappen

* [Meer informatie over omgevingen](environments-overview-admin.md)
* [Meer informatie over Microsoft Flow](getting-started.md)
* [Meer informatie over het beheer centrum](admin-center-introduction.md)
* [Meer informatie over gegevens integratie](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)
