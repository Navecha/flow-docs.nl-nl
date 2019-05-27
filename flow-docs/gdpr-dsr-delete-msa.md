---
title: Verwijderingsverzoeken van betrokkenen in het kader van de AVG met Microsoft Flow voor Microsoft-accounts (MSA) | Microsoft Docs
description: Ontdek hoe u Microsoft Flow kunt gebruiken om te reageren op verwijderingsverzoeken van betrokkenen in het kader van de AVG voor Microsoft-accounts.
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
ms.openlocfilehash: e42da775d5c004bfbe0d6bb8923e6d05aaa5e976
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64454298"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Reageren op verwijderingsverzoeken van betrokkenen in het kader van de AVG

Het **recht op vergetelheid**, het recht om persoonsgegevens te laten verwijderen, is een belangrijke beschermingsmaatregel in de AVG. Het verwijderen van persoonsgegevens omvat het verwijderen van alle persoonsgegevens, behalve gegevens van auditlogboeken.

Gebruikers van Microsoft Flow mogen geautomatiseerde werkstromen maken. Wanneer een gebruiker besluit de persoonsgegevens uit Microsoft Flow te verwijderen, kan de gebruiker de persoonsgegevens beoordelen en besluiten om deze in volledig of gedeeltelijk te verwijderen.

In de volgende tabel ziet u welke persoonsgegevens automatisch worden verwijderd en welke gegevens een MSA-gebruiker (Microsoft-account) moet controleren en verwijderen.

|Vereist dat de MSA-gebruiker beoordeelt en verwijdert|Automatisch verwijderd|
|------|------|
|Activiteit van producten en services|Uitvoeringsgeschiedenis|
|Stromen|Activiteitsfeed|
|Verbindingen||

Microsoft Flow biedt de volgende ervaringen om persoonsgegevens en resources die niet automatisch worden verwijderd voor gebruikers te vinden, te controleren of te wijzigen:

## <a name="manage-delete-requests"></a>Verwijderingsaanvragen beheren

In de onderstaande stappen wordt beschreven hoe u verwijderingsverzoeken kunt uitvoeren in het kader van de AVG.

### <a name="delete-product-and-service-activity"></a>Product- en serviceactiviteit verwijderen

1. Meld u met uw MSA aan bij het [Microsoft-privacydashboard](https://account.microsoft.com/privacy/).
1. Selecteer de koppeling **Activiteitenoverzicht**.

    ![Activiteitenoverzicht](./media/gdpr-dsr-export-msa/activityhistory.png)

1. U kunt zoeken in of bladeren door uw activiteitengeschiedenis voor de verschillende Microsoft-toepassingen en -services die u gebruikt, waaronder Microsoft Flow. Selecteer **Verwijderen** om activiteitsgebeurtenissen van specifieke producten of services te verwijderen.

    ![Gebeurtenis verwijderen](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Binnen enkele momenten wordt het item gewist en uit het privacydashboard verwijderd.

### <a name="list-and-delete-flows"></a>Stromen vermelden en verwijderen

Gebruikers kunnen een lijst opstellen van hun stromen uit [Microsoft Flow](https://flow.microsoft.com) en deze verwijderen door deze stappen uit te voeren:

1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com) en selecteer **Mijn stromen**.

1. Selecteer **...** naast de stroom die u wilt verwijderen en selecteer vervolgens **Verwijderen**.

    ![Gebeurtenis verwijderen](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Verbindingen verwijderen

Connectors gebruiken verbindingen om te communiceren met API's en SaaS-systemen. Verbindingen bevatten verwijzingen naar de gebruiker die ze heeft gemaakt. Gebruikers kunnen deze verwijzingen op elk gewenst moment verwijderen door deze stappen uit te voeren:

1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com), selecteer het tandwielpictogram en selecteer vervolgens **Verbindingen**.

    ![Gebeurtenis verwijderen](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Selecteer de verbinding die u wilt verwijderen, selecteer **...** en selecteer vervolgens **Verwijderen**.

    ![Gebeurtenis verwijderen](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Selecteer het pictogram **Verwijderen** in de bevestigingsprompt.

    ![Gebeurtenis verwijderen](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Als andere stromen gebruik maken van de verbinding die u verwijdert, wordt een melding weergegeven dat een nieuwe verbinding is vereist. Selecteer anders **Verwijderen** om door te gaan.
>
>

## <a name="learn-more"></a>Meer informatie

* Aan de slag met [Microsoft Flow](getting-started.md)
* Meer informatie over [nieuwe functies](release-notes.md) met Microsoft-Flow
