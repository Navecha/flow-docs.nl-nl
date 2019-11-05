---
title: Stromen uitvoeren op basis van e-mail eigenschappen | Microsoft Docs
description: Start een stroom op basis van eigenschappen zoals het onderwerp, het adres van de afzender of het adres van de ontvanger van een e-mail bericht.
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b1dcb98d5bb99c9eaf2843ec75a8bdfaf03fa913
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544941"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>Een stroom activeren op basis van e-mail eigenschappen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Gebruik de trigger **Wanneer een nieuwe e-mail binnenkomt** om een stroom te maken die wordt uitgevoerd wanneer een of meer van de volgende e-mail eigenschappen overeenkomen met de criteria die u opgeeft:

| Eigenschap | Wanneer gebruiken |
| --- | --- |
| Map |Activeer een stroom wanneer e-mail berichten in een specifieke map binnenkomen. Deze eigenschap kan handig zijn als u regels hebt die e-mail berichten naar andere mappen routeren. |
| Aan |Activeer een stroom op basis van het adres waarnaar een e-mail bericht is verzonden. Deze eigenschap kan handig zijn als u e-mail berichten ontvangt die zijn verzonden naar verschillende e-mail adressen in hetzelfde postvak in. |
| Van |Activeer een stroom op basis van het e-mail adres van de afzender. |
| Relevantie |Activeer een stroom op basis van de urgentie waarmee e-mail berichten zijn verzonden. E-mail kan worden verzonden met een hoge, normale of lage urgentie. |
| Heeft bijlage |Activeer een stroom op basis van de aanwezigheid van bijlagen in binnenkomende e-mail berichten. |
| Onderwerps filter |Zoek naar de aanwezigheid van specifieke woorden in het onderwerp van een e-mail. De stroom voert vervolgens *acties* uit die zijn gebaseerd op de resultaten van uw zoek opdracht. |

> [!IMPORTANT]
> Elk [Microsoft flow plan](https://flow.microsoft.com/pricing/) bevat een uitvoerings quotum. Controleer, indien mogelijk, altijd de eigenschappen in de trigger van de stroom. Zo voor komt u dat het gebruik van uw uitvoerings quota onnodig is. Als u een eigenschap in een voor waarde controleert, worden elk uitgevoerd op basis van het uitvoer quotum van uw abonnement, zelfs als de filter voorwaarde die u hebt gedefinieerd, niet aan de criteria voldoet. 

Als u bijvoorbeeld een e-mail adres *van* een e-mail in een voor waarde controleert, telt elke uitvoering op basis van het uitvoer quotum van uw abonnement, zelfs als het niet *van* het adres is dat u interesseert.
> 
> 

In de volgende scenario's controleren we alle eigenschappen in de trigger **wanneer er een nieuwe e-mail binnenkomt** . Ga voor meer informatie naar de [Veelgestelde vragen over facturering](billing-questions.md#what-counts-as-a-run) en de pagina met [prijzen](https://ms.flow.microsoft.com/pricing/) .

## <a name="prerequisites"></a>Vereisten
* Een account met toegang tot [Microsoft flow](https://flow.microsoft.com)
* Een Office 365 Outlook-account
* De mobiele app Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [IOS](https://aka.ms/flowmobiledocsios)of [Windows Phone](https://aka.ms/flowmobilewindows)
* Verbindingen met Office, Outlook en de Push Notification Service

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>Een stroom activeren op basis van het onderwerp van een e-mail
In dit scenario maken we een stroom die een push melding naar uw mobiele telefoon verzendt als het onderwerp van een nieuwe e-mail het woord ' loterij ' bevat. Uw stroom markeert deze e-mail berichten vervolgens als *gelezen*.

>[!NOTE]
>Hoewel deze walkthrough een push melding verstuurt, kunt u een andere actie gebruiken die aansluit bij uw werk stroom behoeften. U kunt bijvoorbeeld de e-mail inhoud opslaan in een andere opslag plaats, zoals Google Sheets of een micro soft Excel-bestand dat is opgeslagen op Dropbox.

Ga nu aan de slag:

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Voer in het vak **onderwerps filter** de tekst in die door uw stroom wordt gebruikt voor het filteren van binnenkomende e-mail berichten.
   
     In dit voor beeld zijn we geïnteresseerd in een e-mail bericht met het woord ' loterij ' in het onderwerp.
   
    ![Geavanceerde opties](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Voer de details in voor de mobiele melding die u wilt ontvangen wanneer u een e-mail ontvangt die overeenkomt met het **onderwerps filter** dat u eerder hebt opgegeven.
   
    ![Details van melding](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Geef uw stroom een naam. Sla het vervolgens op door **stroom maken** boven aan de pagina te selecteren.
   
    ![stroom opslaan](./media/email-triggers/email-triggers-subject-notification.png)

Voltooid! U ontvangt nu een push melding telkens wanneer u een e-mail bericht ontvangt met het woord ' loterij ' in het onderwerp.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>Een stroom activeren op basis van de afzender van een e-mail bericht
In dit scenario maken we een stroom die een push melding naar uw mobiele telefoon verzendt als er een nieuw e-mail bericht binnenkomt van een specifieke afzender (e-mail adres). De stroom markeert deze e-mail berichten ook als *gelezen*.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Voer in het vak **van** het e-mail adres van de afzender in. 
   
     Uw stroom onderneemt actie bij alle e-mail berichten die vanaf dit adres worden verzonden.
   
    ![E-mail eigenschap](./media/email-triggers/email-triggers-from.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Voer de details in voor de mobiele melding die u wilt ontvangen wanneer er een bericht binnenkomt van het e-mail adres dat u eerder hebt ingevoerd.
   
    ![Details van melding](./media/email-triggers/email-triggers-sender-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Geef uw stroom een naam en sla deze op door **stroom maken** te selecteren bovenaan de pagina.
   
    ![stroom opslaan](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>Een stroom activeren wanneer e-mail berichten in een specifieke map binnenkomen
Als u regels hebt die e-mail berichten naar andere mappen sturen op basis van bepaalde eigenschappen, zoals het adres, kunt u dit type stroom.

Laten we aan de slag:

> [!NOTE]
> Als u nog geen regel hebt die e-mail naar een andere map dan uw postvak in stuurt, maakt u een dergelijke regel en bevestigt u dat deze werkt door een test bericht te verzenden.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Selecteer de map waarnaar u specifieke e-mails wilt door sturen. Als u alle e-mail mappen wilt weer geven, selecteert u eerst het pictogram **kiezer weer geven** aan de rechter kant van het vak **map** op de kaart **wanneer er een nieuwe e-mail binnenkomt** .
   
    ![Map selecteren](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Voer de details in voor de mobiele melding die u wilt ontvangen wanneer er een e-mail bericht binnenkomt in de map die u eerder hebt geselecteerd. Als u dit nog niet hebt gedaan, voert u de referenties voor de service meldingen in.
   
    ![Details van melding](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Geef uw stroom een naam en sla deze op door **stroom maken** te selecteren bovenaan de pagina.
   
    ![stroom opslaan](./media/email-triggers/email-triggers-7.png)

Test de stroom door een e-mail bericht te verzenden dat wordt doorgestuurd naar de map die u eerder in dit overzicht hebt geselecteerd.

