---
title: AVG voor micro soft-accounts (MSA) voor het account van de gegevens van het object Microsoft Flow Microsoft Docs
description: Meer informatie over het gebruik van Microsoft Flow om te reageren op aanvragen voor het sluiten van AVG betrokkenen-gegevens van een micro soft-account.
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
ms.date: 5/25/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 8665148baf4d752f1f384670b296a66bbfca6163
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548002"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>Reageren op aanvragen voor het sluiten van een AVG-gegevens account voor Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Het **recht op** het verwijderen van persoonlijke gegevens is een belang rijke beveiliging in de AVG. Dit recht omvat het verwijderen van alle persoons gegevens, met uitzonde ring van audit logboek gegevens. Wanneer gebruikers besluiten hun micro soft-account (MSA) te sluiten, worden de onderliggende gegevens van de gebruiker ook verwijderd.

Deze resources bevatten persoonlijke gegevens die automatisch worden verwijderd wanneer een gebruiker een MSA sluit:

|Resources met persoons gegevens|
|------|
|Product-en service activiteit|
|uitvoerings geschiedenis|
|Terugloop|
|Activiteitsfeed|
|Gebruikers Details|
|Inbel|

## <a name="account-close-requests"></a>Aanvragen voor account sluiten

In deze stappen wordt beschreven hoe u zelf aanvragen voor het sluiten van accounts voor AVG kunt gebruiken.

1. Meld u aan bij het [micro soft-account sluit Portal](https://go.microsoft.com/fwlink/?LinkId=523898) met uw micro soft-account en selecteer **volgende**.

    > [!NOTE]
    > U wordt gevraagd om bestaande abonnementen te annuleren of om gegevens te exporteren uit bestaande services waarop u zich hebt geabonneerd.
    >
    >

    ![Abonnementen annuleren](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Erken dat u weet wat de gevolgen zijn van het sluiten van uw MSA en selecteer vervolgens **account markeren voor sluiting**.

    Er wordt een melding weer gegeven dat aangeeft dat uw account binnen 30 dagen wordt gesloten. U kunt dit account op elk gewenst moment opnieuw openen tijdens deze periode van 30 dagen.

    ![Account gesloten](./media/gdpr-dsr-delete-msa/accountclosed.png)

    Aan het einde van dit venster van 30 dagen wordt het proces voor het verwijderen van alle Microsoft Flow resources voor deze MSA gestart.

## <a name="learn-more"></a>Meer informatie

* Aan de slag met [Microsoft flow](getting-started.md)
* Meer informatie over [de nieuwe functies](release-notes.md) van Microsoft flow
