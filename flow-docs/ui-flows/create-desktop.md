---
title: Meer informatie over het maken van gebruikers interface voor het bureau blad | Microsoft Docs
description: Meer informatie over het maken van bureaublad GEBRUIKERSINTERFACE-flows voor Windows-toepassingen.
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
ms.openlocfilehash: e03b23387f5c3837b9b3f7e9ce023f8c31ce79a3
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589803"
---
# <a name="create-and-test-desktop-ui-flows"></a>UI-stromen van het bureau blad maken en testen

[Dit onderwerp bevat voorlopige documentatie en kan worden gewijzigd.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]


Maak bureaublad GEBRUIKERSINTERFACE-flows om Windows-bureaublad toepassingen te automatiseren. 

Raadpleeg de [bekende problemen](create-desktop.md#known-issues-and-solutions) verderop in dit onderwerp voor meer informatie over problemen die u kunt uitvoeren in, tijdelijke oplossingen voor deze problemen en scenario's die niet worden ondersteund in deze preview-versie.


> [!TIP]
> U kunt andere Windows-bureau blad-apps automatiseren door een vergelijkbaar patroon te volgen.

## <a name="create-a-desktop-ui-flow"></a>Een UI-stroom voor het bureau blad maken

In de volgende stappen wordt uitgelegd hoe u de reken machine-app kunt automatiseren om twee getallen te totaliseren en vervolgens het resultaat op te slaan voor later gebruik. 

1. Zorg ervoor dat het [apparaat klaar is](setup.md) voor het maken van UI-stromen. <!--Todo: link to the prereqs section-->

1. Gebruik de [chroom versie van micro soft Edge](https://www.microsoftedgeinsider.com) of Google Chrome om [energie automatisering](https://flow.microsoft.com)te openen en meld u vervolgens aan met een e-mail account voor werk of school.

1. Selecteer **mijn stromen** > **UI-stromen (preview)**  > **Nieuw**.

   ![Nieuwe UI-flow maken](../media/create-windows-ui-flow/create-new.png "Nieuwe UI-flow maken")

1. Kies **bureau blad-app** en selecteer **volgende**.

   ![Bureau blad selecteren](../media/create-windows-ui-flow/select-desktop.png "Bureau blad selecteren") 

1. Voer een naam in voor de gebruikers interface stroom in het veld **stroom naam** en selecteer **volgende**.

   ![Bureau blad selecteren](../media/create-windows-ui-flow/give-a-name.png "Bureau blad selecteren") 

1. Selecteer **volgende** onderaan om het optionele scherm voor het **instellen van ingangen** over te slaan omdat we geen invoer in dit overzicht gebruiken.

1. Selecteer de kaart **app opnemen** om deze uit te vouwen.

   ![Record-app selecteren](../media/create-windows-ui-flow/select-record-app.png "Record-app selecteren")

1. Selecteer **starten recorder**.

   ![Start recorder selecteren](../media/create-windows-ui-flow/select-launch-recorder.png "Start recorder selecteren")

   Het besturings element recorder wordt boven aan het scherm weer gegeven.

   ![De recorder-Control](../media/create-windows-ui-flow/recorder-control.png "De recorder-Control")

1. De rekenmachine-app starten.

     >[!TIP]
     >Wanneer de muis aanwijzer over besturings elementen in de app wordt geleid, ziet u dat elk besturings element in een blauw kader wordt gemarkeerd. Wacht altijd op het blauwe hooglicht voordat u een besturings element selecteert.
     >
     >Als de blauwe markering niet rond het element wordt weer gegeven, wordt deze mogelijk niet juist opgenomen.

1. Selecteer **record** in het besturings element voor recorder.
1. Selecteer het eerste getal, selecteer **+** , selecteer het tweede nummer en selecteer vervolgens **=** .

    ![De reken machine-app](../media/create-windows-ui-flow/app-to-record.png "De reken machine-app")

1. Selecteer **gereed** op het besturings element voor recorder nadat u de acties hebt voltooid die u wilt opnemen.

1. Sluit de app die u hebt vastgelegd.

1. Selecteer de kaart die begint met het uitvoeren van <app name> script om scherm opnamen van de vastgelegde stappen weer te geven.

     >[!TIP]
     >Selecteer **...**  > **verwijderen** om eventuele extra stappen te verwijderen die u wilt verwijderen.

    ![Opgenomen stappen weer geven](../media/create-windows-ui-flow/show-recorded-steps.png "Opgenomen stappen weer geven")

1. Selecteer **volgende**. 

1. Selecteer **volgende** om de optionele stap voor het **instellen van uitvoer** over te slaan omdat we geen uitvoer in dit overzicht gebruiken.

## <a name="test-your-ui-flow"></a>Uw gebruikers interface stroom testen

Het is altijd een goed idee om uw gebruikers interface-flow te testen. Als u dit wilt doen, selecteert u de knop **nu testen** en bekijkt u de uitvoering van de werk stroom van de gebruikers interface.
    
 >[!IMPORTANT]
 >Voor de beste resultaten moet u niet communiceren met uw apparaat voor de duur van het afspelen.

1. Selecteer **opslaan en sluiten** om uw stroom op te slaan en de functie gebruikers interface stromen af te sluiten.


## <a name="known-issues-and-solutions"></a>Bekende problemen en oplossingen

- Open en Maximaliseer de apps die u wilt opnemen voordat *u begint* met de opname.

- U kunt een [ **sluitings** actie](edit-desktop.md#add-a-manual-action) toevoegen aan het einde van de gebruikers interface stroom, omdat er door de interface stromen een nieuw exemplaar van de toepassingen wordt gestart bij elke test of uitvoering.

- Selecteer **...**  > **verwijderen** op de kaart met vastgelegde acties om onnodige/dubbele acties te verwijderen. Er kunnen dubbele acties worden gemaakt, afhankelijk van het type en de snelheid van de opname. 

- De rechter muisknop wordt mogelijk niet correct afgespeeld. In dat geval kunt u tijdens het opnemen op links klikken om gebruikers interface stromen te richten op het element van de gebruikers interface van de doel groep en vervolgens met de rechter muisknop te klikken.

- Als de interface-flows geen Windows-toepassingen meer records of afspeelt na de installatie van een nieuwe versie, verwijdert u de vorige versie en installeert u vervolgens een nieuwe versie.


### <a name="unsupported-application-types"></a>Niet-ondersteunde toepassings typen

-   Interacties in Windows (Verkenner, opstart menu, taak balk, enzovoort).

-   Webbrowsers (Chrome, IE, Edge, Edge chroom, Firefox, Mozilla, enzovoort).
    Raadpleeg in plaats daarvan [een webgebruikersinterface flow maken](edit-web.md) om websites te automatiseren.

-   Java-toepassingen.

-   Klik eenmaal op toepassingen.

-   Toepassingen met een webweergave, zoals elektroden-toepassingen.

-   Microsoft Office 2016 en eerder. 

-   Microsoft Office Online.

### <a name="unsupported-configurations"></a>Niet-ondersteunde configuraties

-   Meerdere schermen.

-   Vastleggen via een virtuele-machine-client (Extern bureaublad, Citrix, enz.), met de gebruikers interface stromen-app die wordt uitgevoerd op het hostapparaat of op de virtuele machine. Geen wordt ondersteund.

-   Meerdere exemplaren van een toepassing waarbij de titels van het hoofd venster identiek zijn.

-   Toepassings Vensters met identieke titels, bijvoorbeeld micro soft Outlook met meerdere **Naamloos – Message (HTML)** nieuwe e-mail vensters tegelijk.

-   Gelijktijdige opname sessies op een bepaald apparaat.

-   Gelijktijdige afspeel sessies op een bepaald apparaat. Als er sprake is van gelijktijdige uitvoeringen van de gebruikers interface, heeft het eerste de voor keur en mislukt de volgende totdat de eerste is voltooid.

-   Afspelen op een apparaat met een andere toetsenbord indeling dan het apparaat waarop het is opgenomen.

-   Vastleggen op een apparaat of Windows-sessie terwijl de browser met Microsoft Flow zich op een ander apparaat of Windows-sessie bevindt.

### <a name="unsupported-action-types-and-behaviors"></a>Niet-ondersteunde actie typen en-gedrag

De volgende acties worden niet vastgelegd:

-   Dubbel klik.

-   Muis verplaatsen.

-   Muis aanwijzer.

-   Klik en sleep.

-   Aanraken of pen invoer.

-   Open de app vóór de opname.

-   Gesloten app voordat afspelen wordt gestart.

## <a name="unreliable-behaviors-and-workarounds-for-microsoft-office-desktop"></a>Onbetrouwbaar gedrag en tijdelijke oplossingen voor Microsoft Office (Desktop)
- Maak het lint vast voordat u begint met afspelen om problemen te voor komen die zich kunnen voordoen als het lint tijdens het afspelen is ingesteld op automatisch verbergen.
- Selecteer geen items door te klikken en te slepen. Gebruik bijvoorbeeld niet Shift-klikken om cellen in micro soft Excel te selecteren en selecteer tekst niet in micro soft Word of micro soft power point door de muis te slepen.
- Sommige elementen werken mogelijk niet correct in UI-stromen (preview) voor micro soft Word-en micro soft power point-desktop toepassingen. U kunt bijvoorbeeld de opties in het menu bestand, bijvoorbeeld vanaf een lege regel of met de rechter muisknop klikken op besturings elementen zoals het toevoegen van een alinea in micro soft Word of het wijzigen van de indeling van dia's in micro soft power point, niet werken.

## <a name="next-steps"></a>Volgende stappen

- Meer informatie over [het activeren van de gebruikers interface stroom](run-ui-flow.md) die u zojuist hebt gemaakt.

- Als u meer wilt doen met UI-stromen, kunt u ook de gebruikers interface stromen uitproberen met [invoer-en uitvoer](inputs-outputs-web.md) parameters.

