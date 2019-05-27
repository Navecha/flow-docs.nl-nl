---
title: Stromen starten met bttns | Microsoft Docs
description: Informatie over het starten van stromen met een bttn
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
ms.openlocfilehash: 813ad16dbc9514975daadac456b73d98fc30db79
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64462196"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Uw stromen uitvoeren met fysieke knoppen (bttns) van The Button Corporation (preview)
Activeer uw stromen door op een bttn te drukken (een fysieke knop die is gemaakt door [The Button Corporation](https://my.bt.tn/)). Druk bijvoorbeeld op een bttn die een stroom activeert om de volgende taken uit te voeren:

* contact opnemen met de helpdesk met locatie-informatie
* een e-mailbericht verzenden naar uw team
* uw agenda blokkeren
* voorraden opnieuw bestellen

> [!IMPORTANT]
> U moet uw bttn [registreren](https://my.bt.tn/) voordat u deze in een stroom kunt gebruiken.
> 
> [!TIP]
> Configureer alle bttn-eigenschappen, zoals de naam, de locatie en het e-mailadres, op de [bttn-website](https://my.bt.tn/) voordat u uw flow maakt.
> 
> 

U kunt een stroom ook activeren met behulp van een [fysieke Flic-knop](flic-button-flows.md).

## <a name="prerequisites"></a>Vereisten
* U moet toegang hebben tot [Microsoft Flow](https://flow.microsoft.com).
* Ten minste één [geregistreerde bttn](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Een stroom maken die wordt geactiveerd door een bttn
In dit scenario gebruiken we een helpdesk-sjabloon om een stroom te maken die u kunt activeren door één keer op een [bttn](https://my.bt.tn/) te drukken. Wanneer de stroom wordt uitgevoerd, genereert deze een ondersteuningsaanvraag en wordt deze aanvraag naar de helpdesk gestuurd. De ondersteuningsaanvraag geeft de helpdesk de locatie van de ruimte waar hulp nodig is. In dit scenario ziet u hoe u deze stroom met behulp van een sjabloon kunt maken. U kunt echter ook de lege sjabloon gebruiken, waardoor u volledige controle hebt over alle aspecten van de stroom.

U kunt een van deze sjablonen kiezen om snel stromen voor uw bttn te maken en verbinding te maken met onder andere Zendesk, Google en SharePoint:

![bttn-sjablonen](./media/bttn-button-flows/bttn-templates.png)

Tip: Geef een naam die een in een typisch kantoorgebouw vergaderruimte-uw bttn voor het doel van dit scenario.

De instellingen voor uw bttn moeten eruitzien zoals in dit voorbeeld (van de bttn-website):

![bttn-sjablonen](./media/bttn-button-flows/bttn-config.png)

Nu u bent geregistreerd en uw bttn hebt geconfigureerd, kunt u een stroom gaan maken.

### <a name="sign-in-and-select-a-template"></a>Aanmelden en een sjabloon selecteren
1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com).
   
    ![aanmelden](./media/bttn-button-flows/sign-into-flow.png)
   
    Opmerking: Als alternatief kunt u stromen kunt maken in de mobiele Microsoft Flow-app voor [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), of [Windows Phone](https://aka.ms/flowmobilewindows).
2. Typ **bttn** in het zoekvak en selecteer het zoekpictogram.
   
    ![zoeken](./media/bttn-button-flows/bttn-search-template.png)
   
    Nadat u het zoekpictogram hebt geselecteerd, worden alle sjablonen die u met bttns kunt gebruiken weergegeven.
3. Selecteer de sjabloon **Use Bttn to call technical support for meeting room (Bttn gebruiken technische ondersteuning te vragen voor vergaderruimte)**.
   
    ![sjabloon voor ondersteuning](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Microsoft Flow toestaan om verbinding te maken met uw bttn
1. Meld u aan bij de bttn en de Outlook-services van Office 365 als u hierom wordt gevraagd. Hiermee wordt de knop **Doorgaan** ingeschakeld.
   
    ![referenties](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Wanneer u zich aanmeldt bij de bttn-service, moet u toestaan dat Microsoft Flow uw bttns gebruikt.
   
    **Belangrijke**: Als u geen toestemming Microsoft Flow uw bttns gebruikt geeft, kan u zien of maak er verbinding mee in Microsoft Flow.
   
    ![autoriseren](./media/bttn-button-flows/authorize-bttn.png)
3. Nadat u zich bij beide services hebt aangemeld, selecteert u **Doorgaan**.
   
    ![Doorgaan](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Selecteer de bttn waarmee de stroom wordt geactiveerd
1. In de kaart **Wanneer een bttn wordt ingedrukt** opent u de lijst met bttn-ID's en selecteert u de bttn die u wilt gebruiken.
   
    ![bttn selecteren](./media/bttn-button-flows/bttn-id.png)
   
    De stroom moet er nu uitzien zoals weergegeven in dit voorbeeld.
   
    ![overzicht van stroom](./media/bttn-button-flows/bttn-done.png)
2. Geef uw stroom een naam en selecteer **Stroom maken** om deze op te slaan.
   
    ![stroom opslaan](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Uw stroom testen en de resultaten bevestigen
1. Druk op de knop op uw bttn.
2. Bekijk de uitvoeringsgeschiedenis van uw stroom om te bevestigen dat deze is uitgevoerd.
   
    U kunt de uitvoeringsgeschiedenis controleren op de website van Microsoft Flow of op uw mobiele apparaat.
   
    Opmerking: De uitvoeringsstatus is ingesteld op **met** totdat iemand selecteert **bevestigen** in het verzoek om ondersteuning e-mailbericht.
3. U kunt ook bevestigen dat het e-mailbericht is verzonden naar het ondersteuningsteam.
   
    Als u het scenario hebt gevolgd, lijkt de e-mail met de ondersteuningsaanvraag op het volgende voorbeeld:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Problemen oplossen
* Als de stroom niet is geactiveerd, meldt u zich aan bij de site van The Buttn Corporation en controleert u of de knopactiviteit (knop indrukken) wordt vastgelegd.
* U kunt de uitvoering van de activiteit ook bekijken op de site van Microsoft Flow en controleren of er foutberichten worden weergegeven.

## <a name="more-information"></a>Meer informatie
* [Knopstromen delen](share-buttons.md).
* Leer hoe u [knoptriggertokens](introduction-to-button-trigger-tokens.md) kunt gebruiken om de huidige gegevens te verzenden wanneer uw knopstromen worden uitgevoerd.
* [Installeer de Microsoft Flow-app voor Android](https://aka.ms/flowmobiledocsandroid).
* [Installeer de Microsoft Flow-app voor iOS](https://aka.ms/flowmobiledocsios).

