---
title: Aanvragen van betrokkenen voor het sluiten van accounts in het kader van de AVG met Microsoft Flow voor Microsoft-accounts (MSA) | Microsoft Docs
description: Ontdek hoe u Microsoft Flow kunt gebruiken om te reageren op aanvragen van betrokkenen voor het sluiten van accounts in het kader van de AVG voor Microsoft-accounts.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 6480fe6a7e6ca26a7dbad3952b6608a9e0a880ae
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035066"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>Reageren op AVG-verzoeken van betrokkenen voor het sluiten van accounts in Microsoft Flow

Het **recht op vergetelheid**, het recht om persoonsgegevens te laten verwijderen, is een belangrijke beschermingsmaatregel in de AVG. Dit recht omvat het verwijderen van alle persoonsgegevens, behalve gegevens van auditlogboeken. Wanneer gebruikers besluiten hun Microsoft-Account (MSA) sluiten, wordt de onderliggende gegevens van de gebruiker ook verwijderd.

Deze resources bevatten persoonsgegevens die automatisch worden verwijderd wanneer een gebruiker een MSA sluit:

|Resources met persoonsgegevens|
|------|
|Activiteit van producten en services|
|Uitvoeringsgeschiedenis|
|Stromen|
|Activiteitsfeed|
|Gebruikersdetails|
|Verbindingen|

## <a name="account-close-requests"></a>Aanvragen voor het sluiten van accounts

In de onderstaande stappen wordt beschreven hoe u aanvragen voor het sluiten van accounts kunt uitvoeren in het kader van de AVG.

1. Meld u aan bij de [portal voor het sluiten van Microsoft-accounts](http://go.microsoft.com/fwlink/?LinkId=523898) met uw Microsoft-account en selecteer vervolgens **Volgende**.

    > [!NOTE]
    > U krijgt een herinnering dat u bestaande abonnementen moet annuleren of gegevens uit bestaande services waarop u bent geabonneerd moet exporteren.
    >
    >

    ![Abonnementen annuleren](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Bevestig dat u begrijpt welke invloed het sluiten van uw MSA heeft en selecteer vervolgens **Account markeren voor sluiting**.

    Er wordt een melding weergegeven om aan te geven dat uw account over 30 dagen wordt gesloten. U kunt dit account tijdens deze periode van 30 dagen op elk gewenst moment opnieuw openen.

    ![Account gesloten](./media/gdpr-dsr-delete-msa/accountclosed.png)

    Aan het eind van deze periode van 30 dagen wordt het proces voor het verwijderen van alle Microsoft Flow-resources voor dit MSA gestart.

## <a name="learn-more"></a>Meer informatie

* Aan de slag met [Microsoft Flow](getting-started.md)
* Meer informatie over [nieuwe functies](release-notes.md) met Microsoft-Flow
