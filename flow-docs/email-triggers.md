---
title: Voer stromen uit op basis van e-maileigenschappen. | Microsoft Docs
description: Start een stroom op basis van eigenschappen zoals het onderwerp, de afzender of de ontvanger van een e-mailbericht.
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
ms.date: 06/08/2017
ms.author: deonhe
ms.openlocfilehash: 395cb9bc1d58e50e5ac8ebac9afaed544f3261ec
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440007"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>Activeer een stroom op basis van e-maileigenschappen.
Gebruik de trigger **Wanneer er een nieuwe e-mail binnenkomt** om een stroom te maken die wordt uitgevoerd wanneer één of meer van deze e-maileigenschappen overeenkomen met criteria die u opgeeft:

| Eigenschap | Wanneer gebruiken |
| --- | --- |
| Map |Activeer een stroom wanneer e-mailberichten in een specifieke map binnenkomen. Deze eigenschap is handig als u regels hebt die e-mailberichten naar verschillende mappen sturen. |
| Aan |Activeer een stroom die is gebaseerd op het adres waarnaar een e-mailbericht is verzonden. Deze eigenschap is handig als u e-mailberichten ontvangt die zijn verzonden naar verschillende e-mailadressen in hetzelfde postvak. |
| Van |Activeer een stroom op basis van het e-mailadres van de afzender. |
| Urgentie |Activeer een stroom op basis van de urgentie waarmee e-mailberichten zijn verzonden. E-mailberichten kunnen worden verzonden met een hoge, normale of lage urgentie. |
| Heeft bijlage |Activeer een stroom op basis van de aanwezigheid van bijlagen bij binnenkomende e-mailberichten. |
| Onderwerpfilter |Zoek op de aanwezigheid van specifieke woorden in het onderwerp van een e-mailbericht. Uw stroom voert *acties* uit op basis van de resultaten van uw zoekopdracht. |

> [!IMPORTANT]
> Elk [Microsoft Flow-abonnement](https://flow.microsoft.com/pricing/) heeft een uitvoeringsquotum. Controleer altijd en indien mogelijk de eigenschappen van de stroomtrigger. Zo voorkomt u onnodig gebruik van uw uitvoeringsquotum. Als u een eigenschap in een voorwaarde controleert, houd er dan rekening mee dat elke uitvoeringsbewerking wordt meegeteld voor het quotum van uw abonnement, zelfs als er niet wordt voldaan aan de filtervoorwaarde die u hebt gedefinieerd. Als u bijvoorbeeld het *van*-adres van een e-mail in een voorwaarde controleert, wordt elke uitvoeringsbewerking meegeteld voor het quotum van uw abonnement, zelfs als u geen informatie over het *van*-adres nodig hebt.
> 
> 

In de onderstaande scenario’s controleren we alle eigenschappen in de trigger **Wanneer er een nieuwe e-mail binnenkomt**. U vindt meer informatie in de [veelgestelde vragen over facturering](billing-questions.md#what-counts-as-a-run) en de pagina [prijzen](https://ms.flow.microsoft.com/pricing/).

## <a name="prerequisites"></a>Vereisten
* Een account met toegang tot [Microsoft Flow](https://flow.microsoft.com).
* Een Office 365 Outlook-account.
* De mobiele app voor Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) of [Windows Phone](https://aka.ms/flowmobilewindows).
* Verbindingen met Office 365 Outlook en de service voor pushberichten.

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>Een stroom activeren op basis van het onderwerp van een e-mail.
In dit scenario maken we een stroom die een pushmelding naar uw mobiele telefoon verzendt als het onderwerp van een nieuw e-mailbericht het woord 'loterij' bevat. Uw stroom markeert deze e-mailberichten vervolgens als *gelezen*.

Opmerking: In dit scenario wordt een pushmelding verzoden, maar u kunt ook andere gratis acties gebruiken die aansluiten op uw werkstroom. U kunt de inhoud van de e-mail bijvoorbeeld opslaan in een andere opslagplaats, zoals Google Spreadsheets of een Microsoft Excel-bestand dat u opslaat in Dropbox.

Laten we beginnen:

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Voer in het vak **Onderwerpfilter** de tekst in die de stroom gebruikt voor het filteren van binnenkomende e-mailberichten.
   
     In dit voorbeeld ben ik geïnteresseerd in e-mailberichten met het woord 'loterij' in het onderwerp.
   
    ![geavanceerde opties](./media/email-triggers/email-triggers-subject-text.png)

[!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Voer de details in voor de mobiele melding die u wilt ontvangen wanneer er een e-mailbericht binnenkomt dat overeenkomt met de **Onderwerpfilter** die u eerder hebt opgegeven.
   
    ![details van melding](./media/email-triggers/email-triggers-4.png)

[!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Geef uw stroom een naam en sla deze op door **Stroom maken** boven aan de pagina te selecteren.
   
    ![stroom opslaan](./media/email-triggers/email-triggers-subject-notification.png)

Gefeliciteerd, u ontvangt een pushmelding elke keer dat u een e-mail ontvangt met het woord 'loterij' in het onderwerp.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>Een stroom activeren op basis van de afzender van een e-mail
In dit scenario maken we een stroom die een pushmelding naar uw mobiele telefoon verzendt als er een nieuw e-mailbericht binnenkomt van een specifieke afzender (e-mailadres). Uw stroom markeert deze e-mailberichten ook als *gelezen*.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Voer het e-mailadres van de afzender in bij **Van**.
   
     De stroom voert de actie uit op e-mailberichten de vanaf dit adres zijn verzonden.
   
    ![e-maileigenschap](./media/email-triggers/email-triggers-from.png)

[!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Geef de details op voor de mobiele melding die u wilt ontvangen wanneer er een bericht binnenkomt van het e-mailadres dat u eerder hebt ingevoerd.
   
    ![details van melding](./media/email-triggers/email-triggers-sender-notification.png)

[!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Geef uw stroom een naam en sla deze op door **Stroom maken** boven aan de pagina te selecteren.
   
    ![stroom opslaan](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>Een stroom activeren wanneer e-mailberichten in een specifieke map binnenkomen
Als u regels hebt waarmee e-mailberichten naar andere mappen worden verzonden op basis van bepaalde eigenschappen, zoals het adres, is dit type stroom erg handig.

Laten we beginnen:

> [!NOTE]
> Als u nog geen regel hebt die e-mails doorstuurt naar een andere map dan uw postvak in, maakt u deze. Bevestig dat de regel werkt door een testbericht te verzenden.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Selecteer de map waarnaar bepaalde e-mailberichten volgens uw regel worden verzonden. Als u alle e-mailmappen wilt weergeven, selecteert u eerst het pictogram **Kiezer weergeven** aan de rechterkant van het vak **Map** op de kaart **Wanneer er een nieuwe e-mail binnenkomt**.
   
    ![map selecteren](./media/email-triggers/email-triggers-2.png)

[!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Voer de details in voor de mobiele melding die u wilt ontvangen wanneer er een e-mailbericht binnenkomt in de map die u eerder hebt opgegeven. Als u dit nog niet hebt gedaan, voert u de referenties voor de meldingenservice in.
   
    ![details van melding](./media/email-triggers/email-triggers-folder-notification.png)

[!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Geef uw stroom een naam en sla deze op door **Stroom maken** boven aan de pagina te selecteren.
   
    ![stroom opslaan](./media/email-triggers/email-triggers-7.png)

Test de stroom door een e-mailbericht te verzenden en te kijken of deze wordt doorgestuurd naar de map die u eerder in dit scenario hebt geselecteerd.

