---
title: Stromen starten met bttns | Microsoft Docs
description: Meer informatie over het starten van uw stromen met een BTTN
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
ms.date: 05/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5835593c7bd020cdfce5f463a7fc198907c4ba6c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545669"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Voer uw stromen uit met fysieke knoppen (bttns) van de knop Corporation (preview-versie)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Activeer uw stromen door op een BTTN te drukken (een fysieke knop die door [het knop bedrijf](https://my.bt.tn/)is gemaakt). U kunt bijvoorbeeld drukken op een BTTN die een stroom activeert om de volgende taken uit te voeren:

* Neem contact op met de Help Desk met locatie-informatie
* Hiermee wordt een e-mail bericht naar uw team verzonden
* Hiermee wordt uw agenda geblokkeerd
* Bestel benodigdheden

> [!IMPORTANT]
> U moet uw BTTN [registreren](https://my.bt.tn/) voordat u deze in een stroom kunt gebruiken.
> 
> [!TIP]
> Configureer alle BTTN-eigenschappen, zoals de naam, locatie en het e-mail adres op de [BTTN-website](https://my.bt.tn/) voordat u de stroom maakt.
> 
> 

U kunt ook een stroom activeren met behulp van een [fysieke Flic-knop](flic-button-flows.md).

## <a name="prerequisites"></a>Vereisten
* Toegang tot [Microsoft flow](https://flow.microsoft.com).
* Ten minste één [geregistreerde BTTN](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Een stroom maken die wordt geactiveerd vanuit een BTTN
In dit overzicht gebruiken we een Help Desk-sjabloon om een stroom te maken die u kunt activeren met één druk op een [BTTN](https://my.bt.tn/). Wanneer de stroom wordt uitgevoerd, wordt er een ondersteunings aanvraag gegenereerd en vervolgens naar de Help Desk verzonden. De ondersteunings aanvraag biedt de Help Desk de locatie van de kamer waar Help is nodig. In dit scenario ziet u hoe u deze stroom maakt op basis van een sjabloon, maar u kunt de lege sjabloon gebruiken, waarmee u volledige controle hebt over alle aspecten van uw stroom.

U kunt elk van de volgende sjablonen gebruiken om snel stromen te maken voor uw BTTN en verbinding met Zendesk, Google en share point tot stand te brengen, onder andere:

![BTTN-sjablonen](./media/bttn-button-flows/bttn-templates.png)

Tip: voor de doel einden van dit overzicht geeft u uw BTTN een naam die een Vergader ruimte vertegenwoordigt in een typische kantoor gebouw.

De instellingen voor uw BTTN moeten lijken op dit voor beeld (van de BTTN-website):

![BTTN-sjablonen](./media/bttn-button-flows/bttn-config.png)

Nu u uw BTTN hebt geregistreerd en geconfigureerd, kunt u aan de slag gaan met het maken van de stroom.

### <a name="sign-in-and-select-a-template"></a>Aanmelden en een sjabloon selecteren
1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com).
   
    ![Aanmelden](./media/bttn-button-flows/sign-into-flow.png)
   
    Opmerking: als alternatief kunt u stromen maken in de mobiele app van Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [IOS](https://aka.ms/flowmobiledocsios)of [Windows Phone](https://aka.ms/flowmobilewindows).
2. Voer **BTTN** in het zoekvak in en selecteer vervolgens het zoek pictogram.
   
    ![Opdracht](./media/bttn-button-flows/bttn-search-template.png)
   
    Nadat u het zoek pictogram hebt geselecteerd, worden alle sjablonen weer gegeven die u met bttns kunt gebruiken.
3. Selecteer de sjabloon **BTTN gebruiken om technische ondersteuning te bellen voor Vergader ruimte** .
   
    ![ondersteunings sjabloon](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Microsoft Flow toestemming geven om verbinding te maken met uw BTTN
1. Meld u aan bij de BTTN en de Office 365 Outlook-services, zodat de knop **door gaan** wordt ingeschakeld.
   
    ![aanmeldings](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Wanneer u zich aanmeldt bij de BTTN-service, moet u Microsoft Flow autoriseren om uw bttns te gebruiken.
   
    **Belang rijk**: als u Microsoft flow niet autoriseert om uw bttns te gebruiken, kunt u deze niet zien of er verbinding mee maken via Microsoft flow.
   
    ![autoriseren](./media/bttn-button-flows/authorize-bttn.png)
3. Nadat u zich hebt aangemeld bij beide services, selecteert u **door gaan**.
   
    ![Doen](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Selecteer de BTTN die de stroom activeert
1. Open in de kaart **Wanneer een BTTN wordt ingedrukt** de lijst met BTTN-id's en selecteer vervolgens de BTTN die u wilt gebruiken.
   
    ![BTTN selecteren](./media/bttn-button-flows/bttn-id.png)
   
    De stroom moet er nu uitzien als in dit voor beeld.
   
    ![overzicht van flow](./media/bttn-button-flows/bttn-done.png)
2. Geef uw stroom een naam en selecteer **stroom maken** om deze op te slaan.
   
    ![stroom opslaan](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Uw stroom testen en de resultaten bevestigen
1. Druk op de knop op uw BTTN.
2. Bekijk de uitvoerings geschiedenis van de stroom om te controleren of deze correct is uitgevoerd.
   
    U kunt de uitvoerings geschiedenis controleren op de Microsoft Flow website of op uw mobiele apparaat.
   
    Opmerking: de uitvoerings status wordt ingesteld op **actief** totdat iemand **bevestigen** selecteert in het e-mail bericht voor ondersteuning.
3. U kunt ook controleren of het e-mail bericht is verzonden naar het ondersteunings team.
   
    Als u de e-mail hebt gevolgd, ziet de ondersteunings-e-mail er ongeveer uit als in dit voor beeld:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Meer
* Als uw stroom niet is geactiveerd, meldt u zich aan bij de site van de button Corporation en bevestigt u of de knop activiteit (druk persen) wordt vastgelegd.
* U kunt ook inzoomen op de uitvoerings activiteit op de Microsoft Flow-site en controleren op fout berichten.

## <a name="more-information"></a>Meer informatie
* [Knop stromen delen](share-buttons.md).
* Leer hoe u [knop trigger tokens](introduction-to-button-trigger-tokens.md) kunt gebruiken om de huidige gegevens te verzenden wanneer uw knop stromen worden uitgevoerd.
* [Installeer de Microsoft flow-app voor Android](https://aka.ms/flowmobiledocsandroid).
* [Installeer de Microsoft flow-app voor IOS](https://aka.ms/flowmobiledocsios).

