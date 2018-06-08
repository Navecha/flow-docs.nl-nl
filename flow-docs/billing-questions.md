---
title: Vragen over facturering en betaling naar gebruik | Microsoft Docs
description: Antwoorden op veelgestelde vragen over facturering en betaling naar gebruik in Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/21/2017
ms.author: deonhe
ms.openlocfilehash: 302dc02e24b23b68e842ead001beb77b08e12aeb
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "27763190"
---
# <a name="billing-and-metering-questions"></a>Vragen over facturering en betaling naar gebruik

In dit artikel vindt u antwoorden op veelgestelde vragen over facturering en betaling naar gebruik in Microsoft Flow.

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Waar vind ik welke prijsstellingen beschikbaar zijn?

Zie de [pagina met prijzen](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>Waar vind ik wat mijn abonnement is?

Zie de [pagina met prijzen](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>Hoe verander ik van abonnement?

Selecteer **Meer** > **prijzen** in de bovenste navigatiemenu en selecteer vervolgens het plan waarnaar u wilt overschakelen.

![Meer > Prijzen](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Hoe weet ik hoeveel ik heb gebruikt?

Als u een gratis abonnement of proefabonnement hebt, klikt of tikt u op het tandwielpictogram in de bovenste navigatiebalk om uw huidige gebruik ten opzichte van uw abonnement weer te geven. 

![De knop Instellingen](./media/billing-questions/settings.png)

Als u een betaald abonnement hebt, worden uitvoeringsbewerkingen voor alle gebruikers in uw organisatie gegroepeerd. We werken aan functies om de beschikbare quota en het gebruik voor een volledige organisatie zichtbaar te maken.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>Wat gebeurt er als mijn gebruik de limiet overschrijdt?

Microsoft Flow beperkt uw stroomuitvoeringen.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Waar vind ik meer informatie over de gebruikslimieten?

Zie de sectie **Veelgestelde vragen** op de [pagina met prijzen](https://flow.microsoft.com/pricing/).

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>Wat gebeurt er als ik uitvoeringsbewerkingen te vaak probeer uit te voeren?

Uw abonnement bepaalt hoe vaak uw stromen worden uitgevoerd. Als u een gratis abonnement hebt, worden uw stromen bijvoorbeeld slechts één keer per vijftien minuten uitgevoerd. Als een stroom minder dan vijftien minuten nadat deze de laatste keer is uitgevoerd, opnieuw wordt geactiveerd, wordt de stroom in de wachtrij geplaatst tot de 15 minuten zijn verstreken.

## <a name="what-counts-as-a-run"></a>Wat wordt tot een uitvoeringsbewerking gerekend?

Wanneer een stroom wordt geactiveerd, of dit nu door een automatische trigger plaatsvindt of handmatig wordt gestart, wordt dit als een uitvoeringsbewerking geteld. Controleren op nieuwe gegevens wordt niet gerekend als een uitvoeringsbewerking.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Zijn er voor facturering verschillen tussen Microsoft-accounts en werk- of schoolaccounts?

Ja. Als u zich met een Microsoft-account aanmeldt (zoals een account dat eindigt op @outlook.com of @gmail.com), kunt u alleen het gratis abonnement gebruiken. Als u de mogelijkheden van het betaalde abonnement wilt gebruiken, meldt u zich aan met een e-mailadres van een werk- of schoolaccount.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Ik probeer een upgrade uit te voeren, maar ik krijg bericht dat mijn account hiervoor niet in aanmerking komt

Als u wilt bijwerken, gebruikt u een account voor werk of school of maakt u een [Office 365-proefaccount](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/) aan.

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Waarom heb ik geen uitvoeringsbewerkingen meer terwijl ik mijn stroom slechts een paar keer heb uitgevoerd?

Bepaalde stromen worden mogelijk vaker uitgevoerd dan u verwacht. U kunt bijvoorbeeld een stroom maken die u telkens een pushmelding stuurt als uw manager u een e-mailbericht stuurt. Deze stroom moet telkens worden uitgevoerd als u een e-mailbericht (van wie dan ook) ontvangt, omdat de stroom moet controleren of het e-mailadres van uw manager afkomstig is. Deze actie wordt geteld als een uitvoeringsbewerking.

U kunt dit probleem omzeilen door alle filters die u nodig hebt in de trigger op te nemen. Vouw in het voorbeeld van de pushmelding het menu **Geavanceerde opties** uit en geef het e-mailadres van uw manager op in het veld **Van**.

## <a name="other-limits-and-caveats"></a>Andere limieten en voorbehouden

* Per account zijn de volgende aantallen toegestaan:
  * 250 stromen.
  * Vijftien aangepaste connectors.
  * 20 verbindingen per API en totaal 100 verbindingen.
* Een gateway kunt u alleen in de standaardomgeving installeren.
* Bepaalde externe connectors, zoals Twitter, implementeren bandbreedtebeperking van de verbinding om QoS (Quality-of-Service) te beheren. Wanneer bandbreedtebeperking van kracht is, mislukken uw stromen. Als uw stromen mislukken, moet u de details van de mislukte uitvoering controleren in de uitvoeringsgeschiedenis van de stroom.