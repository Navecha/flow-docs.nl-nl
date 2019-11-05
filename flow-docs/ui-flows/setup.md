---
title: GEBRUIKERSINTERFACE stromen instellen op uw apparaat | Microsoft Docs
description: GEBRUIKERSINTERFACE stromen instellen op uw apparaat
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
ms.openlocfilehash: 9e5029189df9807ba727efbe377392f87ef20884
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589683"
---
# <a name="set-up-ui-flows"></a>UI-stromen instellen

[Dit onderwerp bevat voorlopige documentatie en kan worden gewijzigd.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Voordat u het apparaat kunt gebruiken om UI-stromen te maken, moet u ervoor zorgen dat het voldoet aan de vereisten die hier worden beschreven.

> [!TIP]
> Voordat u een UI-stroom maakt, controleert u de [lijst met connectors](https://flow.microsoft.com/connectors/) om te zien of de toepassing die u wilt automatiseren al een connector heeft. Als dit het geval is, kunt u overwegen een stroom te maken in plaats van een UI-stroom. U kunt ook uw [eigen connector](https://docs.microsoft.com/connectors/custom-connectors/)bouwen.

## <a name="prerequisites"></a>Vereisten

- Een geautomatiseerd [of](https://flow.microsoft.com/pricing/) [proef](https://flow.microsoft.com/manage/) abonnement.

- Een werk-of school account om u aan te melden bij zowel energie automatisering als uw Windows-apparaat.

- Een apparaat met Windows 10, Windows Server 2016 of Windows Server 2019.
- Een aan de VS (QWERTY) toetsen bord gekoppeld.

- De [volgende versie van micro soft Edge](https://www.microsoftedgeinsider.com) of Google Chrome.

- Een [omgeving](https://docs.microsoft.com/power-platform/admin/environments-overview) met een [common data service-data base](https://docs.microsoft.com/power-platform/admin/create-database).

> [!IMPORTANT]
> UI-stromen worden momenteel geïmplementeerd in verschillende regio's. Als u de preview-functie niet ziet of geen nieuwe UI-stromen kunt maken, probeer het dan later opnieuw.


## <a name="limitations"></a>Hardwarebeperkingen

Gebruikers interface-stromen (preview) zijn beschikbaar in het Engels.

Het volgende wordt niet ondersteund:

-   UI-stromen van bureau blad

    -   Meerdere monitors
    -   Virtuele machines
    -   Dubbel klikken, muis aanwijzen, aanraken/pen invoer
    -   Interacties in Windows (Verkenner, opstart menu, taak balk, enz.)

-   Web-UI-stromen

    -   Met de rechter muisknop
    -   Informatie over gebruikers sessies (bijvoorbeeld cookies) wordt niet opnieuw gebruikt tijdens het afspelen. U moet het script bewerken om aanmeldings gegevens in te sluiten wanneer dit door websites wordt vereist.

U vindt specifieke beperkingen die zijn opgenomen in de documentatie voor elk onderdeel.

## <a name="get-your-device-ready"></a>Uw apparaat voorbereiden

Installeer de volgende onderdelen om UI-stromen te maken en uit te voeren:

|  | **Naam**                             | **Belasting**  |                                                        
|---|--------------------------------------|----------------------------------------------------------------------|
|   | [De gebruikers interface stromen-app](https://go.microsoft.com/fwlink/?linkid=2102613)                         | Bureau blad-Windows-toepassingen opnemen                                  |          |
|   | Browser uitbreiding gebruikers interface stromen           | Registreer en test Windows-toepassingen op het bureau blad. Webtoepassingen opnemen. |                                                                                              |
|   | Webstationr                            | Desktop-Windows-toepassingen testen en uitvoeren                            |                                                                                              |
|   | [Selenium IDE](https://go.microsoft.com/fwlink/?linkid=2107665) | Webtoepassingen opnemen en afspelen                                 |  |
|   | [#B0](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409)                              | Wordt gebruikt om gebeurtenissen, geplande stromen of knop stromen in te scha kelen om verbinding te maken met, uw gebruikers interface-stromen te activeren (in uw organisatie uit te voeren) en deze uit te voeren.              |  | 

## <a name="install-the-ui-flows-app"></a>De gebruikers interface-flows-app installeren

Het installatie programma van de gebruikers interface bevat alle onderdelen die nodig zijn voor het vastleggen, bewerken en testen van UI-stromen voor het bureau blad. 

>[!IMPORTANT]
>Het installatie programma van de gebruikers interface plaatst het onderdeel Webstation en de browser extensie van de gebruikers interface. Beide zijn nodig voor het registreren, testen en uitvoeren van de UI-stromen voor het bureau blad.

Voer de volgende stappen uit om de gebruikers interface-flows-app te installeren:

1. [Down load het installatie programma voor de gebruikers interface-app](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Open het bestand **Setup. micro soft. flow. UIflow. exe** . Dit bestand is waarschijnlijk in de map **down loads** nadat u het hebt gedownload in de vorige stap.
1. Volg de instructies in het installatie programma voor de **UI-flow (preview-versie)** om de installatie te volt ooien.

## <a name="activate-the-ui-flows-browser-extension"></a>De browser uitbreiding van de gebruikers interface-flow activeren 

Zodra het installatie programma voor de gebruikers interface stroom is voltooid, wordt u door de browser gevraagd om de extensie te activeren.

- Selecteer in micro soft Edge (chroom) elk waarschuwings pictogram in de rechter bovenhoek van de browser en selecteer vervolgens **uitbrei ding inschakelen**.
-   Op Google Chrome selecteert u **uitbrei ding inschakelen** wanneer u hierom wordt gevraagd.  


## <a name="install-selenium-ide"></a>Selenium IDE installeren

De Selenium IDE is een open source-hulp programma waarmee u menselijke interacties kunt vastleggen en afspelen op websites.

Met UI flows kunt u Selenium IDE-scripts uitvoeren vanuit automatische energie en blijven ze veilig opgeslagen (met de juiste IT-governance) in Common Data Service.

Voer de volgende stappen uit om Selenium IDE te installeren:

1. [Down load en installeer](https://go.microsoft.com/fwlink/?linkid=2107665) de Selenium IDE voor de volgende versie van micro soft Edge of Google Chrome.

1. Onder micro soft Edge (Chrome) selecteert u **uitbrei dingen uit andere winkels toestaan**en selecteert **u vervolgens toevoegen aan Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>De on-premises gegevens gateway installeren

U hebt de gateway nodig om de werk stroom van de gebruikers interface van een [gebeurtenis, schema of knop stroom](../getting-started.md/#types-of-flows)te activeren.

>[!TIP]
>De gateway is niet vereist als u alleen uw gebruikers interface-stromen op uw apparaat wilt maken, bewerken en testen.

[Installeer de on-premises gegevens gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install)als u deze nodig hebt.

## <a name="uninstall-ui-flows"></a>Gebruikers interface-stromen verwijderen

1. Open het menu **start** > **instellingen** > **apps**.
1. Zoek naar **UI-stromen (preview)** en selecteer deze.
1. Selecteer **verwijderen**.

## <a name="next-steps"></a>Volgende stappen

- Meer informatie over het [maken van gebruikers interface voor het bureau blad](create-desktop.md).
- Meer informatie over het [maken van Web-UI-stromen](create-web.md).
- Meer informatie over het uitvoeren van [UI-stromen](run-ui-flow.md).
- Meer informatie over het [beheren van UI-stromen](manage.md).
- Meer informatie over de [on-premises gateway](../gateway-reference.md/#use-a-gateway)

