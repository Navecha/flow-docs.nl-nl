---
title: Gebruikers interface stromen uitvoeren vanuit andere stromen | Microsoft Docs
description: Gebruikers interface stromen uitvoeren vanuit andere stromen
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 275ef331d37ff83d8890b4b6ddd750dc038dd099
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589756"
---
# <a name="run-ui-flows"></a>UI-stromen uitvoeren

[Dit onderwerp bevat voorlopige documentatie en kan worden gewijzigd.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Nadat u een UI-stroom hebt gemaakt en getest, kunt u deze uitvoeren vanuit een gebeurtenis, planning of knop. Als u dit mogelijk wilt maken, voegt u de gebruikers interface stroom toe aan een [geautomatiseerde stroom](../get-started-logic-flow.md), een [knop stroom](../introduction-to-button-flows.md), een [Geplande stroom](../run-scheduled-tasks.md)of een [bedrijfs proces stroom](../business-process-flows-overview.md).

## <a name="prerequisites"></a>Vereisten

- U hebt de [on-premises gegevens gateway](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409) nodig voor uw apparaat om de UI-stroom te laten door lopen met automatisch starten.
   
   De gateway is een veilige beveiligde verbinding tussen energie automatisering en uw apparaat (waar uw UI-stroom wordt uitgevoerd). Energie automatisering maakt gebruik van de gateway om toegang te krijgen tot uw on-premises apparaat, zodat de gebruikers interface van een gebeurtenis, schema of knop kan worden geactiveerd.
- Een werk-of school account. 

   >[!IMPORTANT]
   >U moet hetzelfde werk-of school account gebruiken om de gateway in te stellen, om u aan te melden bij energie automatisering en om u aan te melden bij uw Windows-apparaat.
   

## <a name="run-your-ui-flow-from-an-event-button-schedule-or-business-process-flow"></a>De werk stroom van de gebruikers interface uitvoeren vanuit een gebeurtenis, knop, planning of bedrijfsproces stroom

In dit voor beeld gebruiken we een automatische stroom om een UI-stroom te activeren wanneer er een nieuwe e-mail binnenkomt.

1. Navigeer naar [energie automatisering](https://flow.microsoft.com/).
1. Selecteer **mijn stromen** in de linkernavigatiebalk.
1. Selecteer **Nieuw**en selecteer vervolgens **automatisch-uit leeg**.

   >[!TIP]
   >U kunt elk ander type stroom kiezen dat aan uw behoeften voldoet.

1. Geef uw stroom een naam in het vak **stroom naam** .
1. Zoek naar ' nieuwe e-mail ' en selecteer vervolgens **wanneer er een nieuwe e-mail binnenkomt (v3)** in de lijst met triggers. 
    
   ![Een trigger selecteren](../media/run-ui-flow/2d4ec17d239169a46905cef1829fa3a1.png "Een trigger selecteren")

1. Selecteer **maken**en selecteer vervolgens **nieuwe stap**.

1. Zoek naar **UI-stromen**en selecteer vervolgens **een UI-stroom voor bureau blad uitvoeren** uit de lijst met **acties**. 

   ![Zoek actie](../media/run-ui-flow/search-action.png "Zoek actie")

1. Geef de gateway gegevens en de referenties van het apparaat op. 

   U moet dit eenmaal doen per apparaat:

    - **Verbindings naam**: Kies een naam voor de stroom verbinding van het apparaat. Dit kan een andere zijn dan de naam van de gateway.
    - **Gebruikers naam**: Geef het werk-of school account van uw apparaat op.
    - **Verificatie type**: Selecteer Windows.
    - **Wacht woord**: het wacht woord van uw werk-of school account.
    - **Gateway**: Selecteer de gateway die u tijdens de installatie hebt gemaakt.

      ![Verbindings instellingen](../media/run-ui-flow/connection-settings.png "Verbindings instellingen")

      >[!TIP]
      >Als uw gateway niet wordt weer geven, moet u mogelijk een andere verbinding selecteren. Als u dit wilt doen, selecteert u **...** in de rechter bovenhoek van de kaart **een UI-flow uitvoeren voor Desktop (preview-versie)** en selecteert u vervolgens de verbinding die u wilt gebruiken vanuit **Mijn verbindingen**.

      ![Een nieuwe verbinding selecteren](../media/run-ui-flow/select-new-connection.png "Een nieuwe verbinding selecteren")

1. Selecteer de gebruikers interface stroom die u eerder hebt gemaakt.

   ![UI-stroom selecteren](../media/run-ui-flow/select-ui-flow.png "UI-stroom selecteren")

1. Selecteer **Opslaan** om uw geautomatiseerde stroom op te slaan.

1. Test uw stroom door een e-mail te verzenden om deze te activeren. U ziet dat de door u genoteerde stappen worden weer gegeven in de werk stroom van de gebruikers interface. 

![Geslaagde uitvoering die een UI-stroom aanroept](../media/run-ui-flow/successful-run.png "Geslaagde uitvoering die een UI-stroom aanroept")

>[!TIP]
>Communiceer niet met uw apparaat terwijl de stroom wordt uitgevoerd.

## <a name="use-inputs-and-outputs"></a>Invoer en uitvoer gebruiken

Wanneer u invoer en uitvoer binnen een UI-flow definieert, kunt u gegevens van en naar deze invoer door geven.

1. Wanneer u een UI-stroom aan een stroom toevoegt, ziet u de lijst met invoer gegevens die in de gebruikers interface stroom zijn gedefinieerd.

   ![Invoer van de UI-stroom](../media/run-ui-flow/inputs.png "Invoer van de UI-stroom")

1. U kunt elk invoer veld in de UI-stroom vullen met waarden uit de vorige stappen in de stroom. Als u dit wilt doen, selecteert u het invoer veld en selecteert u vervolgens een invoer van de token kiezer.


1. U kunt ook uitvoer van uw UI-stroom gebruiken als invoer voor acties die later in de stroom worden weer gegeven. Als u dit wilt doen, selecteert u het invoer veld en selecteert u vervolgens een invoer van de token kiezer.

## <a name="limitations-and-known-issues"></a>Beperkingen en bekende problemen

- Gateway clusters worden niet ondersteund.
- Omdat niet-Amerikaanse (QWERTY) toetsen borden niet worden ondersteund in deze Realease, resulteert het afspelen van een invoer stap waarbij de sleutel reeks is vastgelegd op basis van een niet-Amerikaans (QWERTY) toetsen bord, als gevolg van belang rijke streken in de VS (QWERTY).

## <a name="learn-more"></a>Meer informatie

 - De [on-premises gegevens gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-app)installeren.
 - [Gebruik de on-premises gegevens gateway-app](https://docs.microsoft.com/flow/gateway-manage) -documentatie.
 - [Problemen met](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) de on-premises gegevens gateway oplossen.
