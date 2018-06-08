---
title: Stromen starten met Flic-knoppen | Microsoft Docs
description: U kunt eenvoudig stromen starten met fysieke Flic-knoppen van Shortcut Labs.
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
ms.openlocfilehash: 518834103c1a17ef2f5af218eae43ccab4e5fda2
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440835"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Stromen starten door op een slimme Flic-knop te drukken (preview)
Activeer uw stromen door op een fysieke knop, ook wel een Flic, van Shortcut Labs te drukken. Druk bijvoorbeeld op een Flic om de werkuren bij te houden, uw agenda te blokkeren, bezoekers van een evenement te tellen of om geografische locaties op te slaan.

> [!IMPORTANT]
> Configureer alle Flic-eigenschappen door de mobiele app van Flic voor [Android](https://play.google.com/store/apps/details?id=io.flic.app) of [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) te gebruiken voordat u de stroom maakt.
> 
> 

## <a name="prerequisites"></a>Vereisten
Voor het gebruik van Flics met Microsoft Flow zijn de volgende vereisten van toepassing:

* U moet toegang hebben tot [Microsoft Flow](https://flow.microsoft.com).
* U moet de mobiele app van Flic voor [Android](https://play.google.com/store/apps/details?id=io.flic.app) of [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) downloaden en een of meer Flics met de app koppelen.

## <a name="configure-flic-properties"></a>Flic-eigenschappen configureren
Gebruik de mobiele app van Flic om de gebeurtenissen van de Flic te programmeren. De gebeurtenissen zijn:

* klikken (één keer snel drukken)
* dubbelklikken (twee keer snel drukken)
* ingedrukt houden (één keer lang ingedrukt houden)

Deze schermopname bevat een voorbeeld van een Flic-configuratieproces:

![Flics configureren](./media/flic-button-flows/configure-flic-actions.png)

Zodra u een Flic-gebeurtenis aan Microsoft Flow hebt gekoppeld, kunt u die Flic selecteren als een trigger voor uw stromen. Verderop in dit scenario zult u triggers selecteren.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Een stroom maken die wordt geactiveerd door een Flic
In dit scenario wordt er een stroom met de Flic uitgevoerd die registreert hoeveel tijd een consultant bij een klant doorbrengt. De consultant drukt bij aankomst één keer op de Flic en vlak voor vertrek nogmaals. Telkens wanneer op de Flic wordt gedrukt, wordt de gekoppelde stroom uitgevoerd. Zodra de stroom wordt gestart, wordt de huidige tijd opgeslagen in Google Spreadsheets en wordt er vervolgens een e-mailmelding verzonden. De e-mail bevat informatie over de stroomuitvoering.

Opmerking: zorg ervoor dat u minimaal één **klikactie** met de mobiele Flic-app hebt gekoppeld en geconfigureerd om Microsoft Flow te activeren. In deze schermopname is de **klikactie** geconfigureerd om Microsoft Flow te openen. Verderop in dit scenario zullen we de stroom zodanig configureren dat deze wordt geactiveerd wanneer de Flic één keer wordt ingedrukt (klikken).

   ![flic configureren](./media/flic-button-flows/flic-configured-for-flow.png)

Laten we de stroom maken.

### <a name="start-with-a-template"></a>Begin met een sjabloon
1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com).
   
    ![aanmelden](./media/flic-button-flows/sign-into-flow.png)
2. Typ **flic** in het zoekvak en selecteer het zoekpictogram.
   
    ![flic zoeken](./media/flic-button-flows/search-flic.png)
3. Selecteer de sjabloon **Track your working hours with Flic smart button**.
   
    ![sjabloon selecteren](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Een spreadsheet in Google Spreadsheets maken
1. Controleer de details van de sjabloon. Zoals u kunt zien, is voor deze sjabloon een spreadsheet in Google Spreadsheets vereist.
   
   ![de sjabloondetails controleren](./media/flic-button-flows/flic-template-details.png)
2. Maak een spreadsheet in Google Spreadsheets met de kolommen **ClickType** en **TimeStamp**.
   
      Tip: u kunt de kolommen in Google Spreadsheets een naam geven door boven aan de kolom een kolomnaam in te voeren. Uw sheet moet overeenkomen met deze schermopname:
   
   ![Google-spreadsheet](./media/flic-button-flows/flic-google-sheet.png)
   
   Opmerking: u hebt deze sheet later in dit scenario nog nodig.

### <a name="add-the-flic-trigger-to-your-flow"></a>De Flic-trigger toevoegen aan uw stroom
1. Meld u aan bij de services van de sjabloon en selecteer vervolgens **Doorgaan**.
   
     **Doorgaan** wordt ingeschakeld zodra u zich hebt aangemeld bij alle vereiste services voor de sjabloon.
   
    ![referenties opgeven](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Typ **flic** in het zoekvak en selecteer vervolgens de trigger **Flic - When a Flic is pressed**.
   
    ![flic-trigger zoeken](./media/flic-button-flows/flic-search-trigger.png)
3. Selecteer in de lijst **Flic button** op de kaart **Flic - When a Flic is pressed** de Flic die u wilt gebruiken.
4. Selecteer **klikken** in de lijst **Gebeurtenissen** om aan te geven dat u de stroom wilt activeren wanneer er één keer op de Flic wordt gedrukt.
   
    ![flic-actie selecteren](./media/flic-button-flows/select-flic.png)
   
   U kunt eventueel **any** selecteren om aan te geven dat de stroom voor elke Flic-gebeurtenis (klikken, dubbelklikken of ingedrukt houden) wordt geactiveerd.
   
   **Dubbelklikken** geeft aan dat de stroom wordt geactiveerd wanneer er snel twee keer op de Flic wordt gedrukt. **Ingedrukt houden** geeft aan dat de Flic ingedrukt moet worden gehouden om de stroom te activeren.
   
   U kunt naar wens andere stromen maken en deze activeren met de andere gebeurtenissen in de lijst **Gebeurtenissen**. U kunt bijvoorbeeld de gebeurtenis **dubbelklikken** gebruiken om te registreren op welk tijdstip u bij een klant vertrekt.

### <a name="configure-the-sheet"></a>De sheet configureren
   Op de kaart **Rij invoegen**:

1. Selecteer de spreadsheet die u eerder op basis van de lijst **Bestand** hebt gemaakt.
2. Selecteer de sheet in de lijst **Werkblad**.
   
   Opmerking: er worden twee extra vakken op de kaart **Rij invoegen** weergegeven nadat u deze sheet hebt geselecteerd. Deze vakken vertegenwoordigen de twee kolommen in de sheet die u eerder hebt gemaakt.
3. Selecteer het vak **ClickType** en selecteer vervolgens het token **Click type**.
4. Selecteer het vak **Timestamp** en selecteer vervolgens het token **Click time**.
   
    ![Google Spreadsheets-gegevens configureren](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>Controleren of de e-mailinstellingen juist zijn
1. Controleer of de kaart **Ik wil een e-mailmelding ontvangen** eruitziet als deze schermopname.
   
    ![e-mailmelding bevestigen](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>De stroom opslaan en testen
1. Geef de stroom een naam en sla deze vervolgens op.
   
    ![de stroom opslaan](./media/flic-button-flows/save.png)

Als u de stappen hebt gevolgd, wordt de stroom geactiveerd wanneer u één keer op de Flic drukt. Vervolgens worden het type klik en de huidige tijd in de sheet geregistreerd en ontvangt u vervolgens een e-mail.

1. Druk één keer op uw Flic.
2. Open de sheet in Google Spreadsheets. Als het goed is, bevatten de kolommen **ClickType** en **Timestamp** respectievelijk de 'klik' en de tijd.
   
    ![resultaten van de uitvoering weergeven](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. U kunt de resultaten van de stroomuitvoering ook bekijken op de Microsoft Flow-website of in de mobiele app van Microsoft Flow. Hier volgt een schermopname van mijn testuitvoering.
   
    ![de stroom opslaan](./media/flic-button-flows/flic-test-run-results-portal.png)
4. De hoofdtekst van de e-mailmelding die ik naar aanleiding van de uitgevoerde stroom heb ontvangen, ziet er als volgt uit.
   
    ![de stroom opslaan](./media/flic-button-flows/flic-email-body.png)

U kunt overwegen om de stroom zodanig uit te breiden dat ook automatisch uw locatie (breedtegraad en lengtegraad) wordt geregistreerd wanneer op de Flic wordt gedrukt.

## <a name="more-information"></a>Meer informatie
* [Knopstromen delen](share-buttons.md).
* Leer hoe u [knoptriggertokens](introduction-to-button-trigger-tokens.md) kunt gebruiken om de huidige gegevens te verzenden wanneer uw knopstromen worden uitgevoerd.
* Installeer de mobiele app voor Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) of [Windows Phone](https://aka.ms/flowmobilewindows).

