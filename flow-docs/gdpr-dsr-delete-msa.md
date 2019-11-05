---
title: AVG-aanvragen voor het verwijderen van gegevens voor micro soft-accounts (MSA) Microsoft Flow Microsoft Docs
description: Meer informatie over het gebruik van Microsoft Flow om te reageren op AVG betrokkenen-aanvragen voor het verwijderen van gegevens van micro soft-accounts.
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
ms.openlocfilehash: 379c88842b9724c7bdb6adfed79e2bb11497694d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548059"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Reageren op AVG-aanvragen voor het verwijderen van gegevens
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Het **recht op doorhaling** door het verwijderen van persoonlijke gegevens is een belang rijke beveiliging in de AVG. Het verwijderen van persoonlijke gegevens omvat het verwijderen van alle persoons gegevens, met uitzonde ring van audit logboek gegevens.

Met Microsoft Flow kunnen gebruikers geautomatiseerde werk stromen bouwen. Wanneer een gebruiker besluit hun persoons gegevens te verwijderen uit Microsoft Flow, kan de gebruiker hun persoons gegevens bekijken en bepalen of een deel ervan moet worden verwijderd.

In de volgende tabel ziet u welke persoons gegevens automatisch worden verwijderd en welke gegevens een micro soft-account (MSA) nodig heeft om het te controleren en te verwijderen.

|De MSA-gebruiker moet controleren en verwijderen|Automatisch verwijderd|
|------|------|
|Product-en service activiteit|uitvoerings geschiedenis|
|Terugloop|Activiteitsfeed|
|Inbel||

Microsoft Flow biedt de volgende ervaringen om gebruikers te helpen bij het zoeken, controleren of wijzigen van persoonlijke gegevens en resources die niet automatisch worden verwijderd:

## <a name="manage-delete-requests"></a>Verwijderings aanvragen beheren

In de volgende stappen wordt beschreven hoe u zelf Delete-aanvragen voor AVG kunt uitvoeren.

### <a name="delete-product-and-service-activity"></a>Product-en service activiteit verwijderen

1. Meld u aan bij het [micro soft-privacybeleid](https://account.microsoft.com/privacy/) met uw MSA.
1. Selecteer de koppeling **activiteiten geschiedenis** .

    ![Activiteitsgeschiedenis](./media/gdpr-dsr-export-msa/activityhistory.png)

1. U kunt zoeken naar of bladeren in uw activiteiten geschiedenis voor de verschillende micro soft-toepassingen en-services die u gebruikt, met inbegrip van Microsoft Flow. Selecteer **verwijderen** om specifieke gebeurtenissen voor een product of service activiteit te verwijderen.

    ![Gebeurtenis verwijderen](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Binnen enkele ogen blikken wordt het item verwijderd en verwijderd uit het privacy-dash board.

### <a name="list-and-delete-flows"></a>Stromen weer geven en verwijderen

Een gebruiker kan hun stromen van [Microsoft flow](https://flow.microsoft.com) weer geven en verwijderen door de volgende stappen te follwing:

1. Meld u aan bij de [Microsoft flow](https://flow.microsoft.com)en selecteer vervolgens op **mijn stromen**.

1. Selecteer **...** naast de stroom die u wilt verwijderen en selecteer vervolgens **verwijderen**.

    ![Gebeurtenis verwijderen](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Verbindingen verwijderen

Connectors gebruiken verbindingen om te communiceren met Api's en SaaS-systemen. Verbindingen bevatten verwijzingen naar de gebruiker die ze heeft gemaakt. De gebruiker kan deze verwijzingen op elk gewenst moment verwijderen door de volgende stappen te follwing:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com), selecteer het tandwiel pictogram en selecteer vervolgens **verbindingen**.

    ![Gebeurtenis verwijderen](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Selecteer de verbinding die u wilt verwijderen, selecteer.. **.** en selecteer vervolgens **verwijderen**.

    ![Gebeurtenis verwijderen](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Selecteer het pictogram **verwijderen** op de bevestigings prompt.

    ![Gebeurtenis verwijderen](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Als andere stromen de verbinding gebruiken, wordt u gewaarschuwd dat een nieuwe verbinding vereist is. Selecteer anders **verwijderen** om door te gaan.
>
>

## <a name="learn-more"></a>Meer informatie

* Aan de slag met [Microsoft flow](getting-started.md)
* Meer informatie over [de nieuwe functies](release-notes.md) van Microsoft flow
