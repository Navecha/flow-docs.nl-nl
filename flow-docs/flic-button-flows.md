---
title: Stromen starten met Flic-knoppen | Microsoft Docs
description: Met de knoppen van Flic van de werk balk kunt u eenvoudig stromen op de knop starten.
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
ms.date: 05/19/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e6430f78ad2eccecc5af7f6606bb56e1a7eb4599
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544811"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Voer uw stromen uit door op de slimme knop Flic (preview) te drukken
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Activeer uw stromen door te drukken op een fysieke knop, ook wel een Flic genoemd, vanuit shortcut Labs. Druk bijvoorbeeld op een Flic om uw werk uren bij te houden, uw agenda te blok keren, bezoekers bij een gebeurtenis te tellen of geografische locaties op te slaan.

> [!IMPORTANT]
> Configureer alle Flic-eigenschappen met behulp van de mobiele app van Flic voor [Android](https://play.google.com/store/apps/details?id=io.flic.app) of [IOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) voordat u uw stroom maakt.
> 
> 

## <a name="prerequisites"></a>Vereisten
Als u Flics met Microsoft Flow wilt gebruiken, hebt u het volgende nodig:

* Toegang tot [Microsoft flow](https://flow.microsoft.com).
* De mobiele app voor [Android](https://play.google.com/store/apps/details?id=io.flic.app) of [IOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) van Flic is gedownload en deze wordt gebruikt om een of meer Flics te koppelen.

## <a name="configure-flic-properties"></a>Eigenschappen van Flic configureren
Gebruik de mobiele app van Flic om de gebeurtenissen van de Flic te Program meren. De gebeurtenissen zijn:

* Klik (één kort ingedrukt)
* dubbel klik (twee snelle persen)
* bewaren (één lang ingedrukt)

In deze scherm afbeelding ziet u een voor beeld van wat uw Flic-configuratie proces kan zijn:

![Flics configureren](./media/flic-button-flows/configure-flic-actions.png)

Nadat u een Flic-gebeurtenis aan Microsoft Flow hebt gekoppeld, kunt u die Flic selecteren als trigger voor uw stromen. Verderop in dit overzicht kunt u triggers selecteren.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Een stroom maken die wordt geactiveerd door een Flic
In dit scenario gebruiken we een Flic om een stroom uit te voeren die de tijd registreert die een consultant op elke client doorbrengt. De consultant drukt één keer op de Flic en drukt deze opnieuw, net vóór vertrek van de client. Bij elke pers van de Flic wordt een uitvoering van de stroom gestart waarmee de verbinding tot stand is gebracht. De stroom slaat de huidige tijd op in Google spread sheets en verzendt vervolgens een e-mail melding. Het e-mail bericht bevat details over de uitvoering van de stroom.

Opmerking: Zorg ervoor dat u de mobiele Flic-app hebt gebruikt om te koppelen en configureer ten minste één **Klik** actie om Microsoft flow te activeren. In deze scherm afbeelding heb ik de **Klik** actie geconfigureerd om Microsoft flow te activeren. Verderop in dit scenario wordt de stroom geconfigureerd om te activeren wanneer de Flic eenmaal wordt ingedrukt (geklikt).

   ![Flic-configuratie](./media/flic-button-flows/flic-configured-for-flow.png)

Laten we beginnen met het maken van onze stroom.

### <a name="start-with-a-template"></a>Beginnen met een sjabloon
1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com).
   
    ![Aanmelden](./media/flic-button-flows/sign-into-flow.png)
2. Voer **Flic** in het zoekvak in en selecteer vervolgens het zoek pictogram.
   
    ![Flic zoeken](./media/flic-button-flows/search-flic.png)
3. Selecteer de sjabloon **uw werk tijden met Flic slimme knop bijhouden** .
   
    ![sjabloon selecteren](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Een werk blad maken in Google spread sheets
1. Controleer de details van de sjabloon en houd er rekening mee dat voor deze sjabloon een werk blad in Google spread sheets is vereist.
   
   ![Details van sjabloon controleren](./media/flic-button-flows/flic-template-details.png)
2. In Google spread sheets maakt u een werk blad dat een blad bevat met kolommen met de naam **Click type** en **Time Stamp**.
   
      Tip: u kunt kolommen in Google spread sheets een naam geven door de kolom naam boven aan de kolom in te voeren. Uw blad moet er nu als volgt uitzien:
   
   ![Google-spread sheet](./media/flic-button-flows/flic-google-sheet.png)
   
   Opmerking: u kunt dit blad later in dit overzicht gebruiken.

### <a name="add-the-flic-trigger-to-your-flow"></a>De trigger Flic toevoegen aan uw stroom
1. Meld u aan bij de services van de sjabloon en selecteer vervolgens **door gaan**.
   
     **Door gaan** is ingeschakeld nadat u zich hebt aangemeld bij alle vereiste services voor de sjabloon.
   
    ![referenties opgeven](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Voer **Flic** in het zoekvak in en selecteer het **Flic-wanneer een Flic wordt ingedrukt** .
   
    ![zoeken naar Flic-trigger](./media/flic-button-flows/flic-search-trigger.png)
3. Selecteer de Flic die u wilt gebruiken in de lijst met **Flic-knoppen** op de kaart **Flic-wanneer een Flic wordt ingedrukt** .
4. Selecteer **klikken** in de lijst **gebeurtenissen** om aan te geven dat u de stroom wilt activeren wanneer de Flic eenmaal wordt ingedrukt.
   
    ![Flic-actie selecteren](./media/flic-button-flows/select-flic.png)
   
   U kunt **eventueel een wille keurige** selecteren om aan te geven dat elke Flic-gebeurtenis (klikken, dubbel klikken of vasthouden) de stroom activeert.
   
   **Dubbel klik** geeft aan dat de stroom wordt geactiveerd wanneer de Flic snel twee keer wordt ingedrukt. **Hold** geeft aan dat een lange pers op de Flic de stroom activeert.
   
   U kunt andere stromen maken en deze activeren met behulp van de andere gebeurtenissen in de lijst met **gebeurtenissen** . U kunt bijvoorbeeld de gebeurtenis voor **dubbel klikken** gebruiken om de tijd vast te leggen waarop u een-client verlaat.

### <a name="configure-the-sheet"></a>Het blad configureren
   Op de kaart **rij invoegen** :

1. Selecteer het werk blad dat u eerder hebt gemaakt in de lijst met **bestanden** .
2. Selecteer het blad in de lijst met **werk bladen** .
   
   Opmerking: er worden twee extra vakken weer gegeven op de kaart **rij invoegen** nadat u het blad hebt geselecteerd. Deze vakken vertegenwoordigen de twee kolommen in het blad dat u eerder hebt gemaakt.
3. Selecteer het vak **Click type** en selecteer vervolgens het token **type Klik** .
4. Selecteer het vak **tijds tempel** en selecteer vervolgens het token **Klik tijd** .
   
    ![Google spread sheet-gegevens configureren](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>Controleren of de e-mail instellingen juist zijn
1. Bevestig de kaart **Ik wil een e-mail melding verzenden** als deze scherm afbeelding.
   
    ![e-mail melding bevestigen](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Sla de stroom op en test deze
1. Geef uw stroom een naam en sla deze op.
   
    ![uw stroom opslaan](./media/flic-button-flows/save.png)

Als u klaar bent, drukt u op de Flic zodra de stroom wordt geactiveerd. De stroom registreert vervolgens het type Klik en de huidige tijd in het werk blad en stuurt vervolgens een e-mail bericht naar u.

1. Druk eenmaal op uw Flic.
2. Open uw werk blad in Google spread sheets. U ziet dat de **Click type** en de **Time Stamp** -kolommen worden gevuld met respectievelijk ' Klik ' en de tijd.
   
    ![resultaten van de uitvoering bekijken](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. U kunt ook de resultaten van de uitvoering van de Microsoft Flow website of van de mobiele app van Microsoft Flow weer geven. Hier volgt een scherm opname van mijn test uitvoering.
   
    ![uw stroom opslaan](./media/flic-button-flows/flic-test-run-results-portal.png)
4. Hier ziet u de hoofd tekst van de meldings-e-mail die ik heb ontvangen van de uitvoering van de stroom.
   
    ![uw stroom opslaan](./media/flic-button-flows/flic-email-body.png)

Voor extra tegoed kunt u de stroom uitbreiden om automatisch uw locatie (breedte graad en lengte graad) vast te leggen wanneer de Flic wordt ingedrukt.

## <a name="more-information"></a>Meer informatie
* [Knop stromen delen](share-buttons.md).
* Leer hoe u [knop trigger tokens](introduction-to-button-trigger-tokens.md) kunt gebruiken om de huidige gegevens te verzenden wanneer uw knop stromen worden uitgevoerd.
* Installeer de mobiele app voor Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [IOS](https://aka.ms/flowmobiledocsios)of [Windows Phone](https://aka.ms/flowmobilewindows).

