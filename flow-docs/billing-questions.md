---
title: Vragen over facturering en meting | Microsoft Docs
description: Antwoorden op veelgestelde vragen over facturering en meting in Microsoft Flow
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
ms.date: 08/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 69fecb42ba2b89f7a3f5b7541f62a4ee984832ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546201"
---
# <a name="billing-and-metering-questions"></a>Vragen over facturering en meting
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

In dit artikel vindt u antwoorden op veelgestelde vragen over facturering en meting in Microsoft Flow.

>[!NOTE]
> PowerApps en Microsoft Flow gebruiken een [Nieuw licentie model](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) dat wordt gestart op 1 oktober 2019. 

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Waar kan ik zien welke prijs plannen er beschikbaar zijn?

Zie de [pagina met prijzen](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>Waar kan ik zien wat mijn plan is?

Zie de [pagina met prijzen](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>Hoe kan ik switch-plannen?

Selecteer in het bovenste navigatie menu **meer informatie** > **prijzen**en selecteer vervolgens het plan dat u wilt overschakelen.

![Meer informatie > prijzen](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Hoe kan ik weet ik hoeveel ik heb gebruikt?

Als u een gratis abonnement of proef abonnement hebt, klikt of tikt u op het tandwiel pictogram in de bovenste navigatie balk om uw huidige gebruik op basis van uw abonnement weer te geven. 

![Knop instellingen](./media/billing-questions/settings.png)

Als u een betaald abonnement hebt, worden uitvoeringen gegroepeerd op alle gebruikers in uw organisatie. We werken aan functies om beschik bare quota en gebruik beschikbaar te maken binnen een organisatie.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>Wat gebeurt er als mijn gebruik de limieten overschrijdt?

Microsoft Flow beperkt uw stroom uitvoeringen.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Waar vind ik meer informatie over de gebruiks limieten?

Op de [pagina met prijzen](https://flow.microsoft.com/pricing/)raadpleegt u de sectie **Veelgestelde vragen** .

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>Wat gebeurt er als ik de uitvoering te vaak probeer uit te voeren?

Uw abonnement bepaalt hoe vaak uw stromen worden uitgevoerd. Uw stromen kunnen bijvoorbeeld om de 15 minuten worden uitgevoerd als u zich op het gratis abonnement bevindt. Als een stroom minder dan 15 minuten na de laatste uitvoering wordt geactiveerd, wordt deze in de wachtrij geplaatst tot 15 minuten zijn verstreken.

## <a name="what-counts-as-a-run"></a>Wat is het aantal uitvoer?

Wanneer een stroom wordt geactiveerd, hetzij door een automatische trigger of door deze hand matig te starten, wordt dit beschouwd als een run. Controleren op nieuwe gegevens wordt niet geteld als uitvoeringen.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Zijn er verschillen tussen micro soft-accounts en werk-of school accounts voor facturering?

Klikt. Als u zich aanmeldt met een micro soft-account (zoals een account dat eindigt op @outlook.com of @gmail.com), kunt u alleen het gratis abonnement gebruiken. Als u wilt profiteren van de functies in het betaalde abonnement, meldt u zich aan met een werk-of school-e-mail adres.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Ik probeer een upgrade uit te voeren, maar mijn account komt niet in aanmerking.

Als u een upgrade wilt uitvoeren, gebruikt u een werk-of school account of maakt u een [proef account voor Office 365](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Waarom is er geen uitvoering meer meer wanneer mijn stroom slechts enkele keren is uitgevoerd?

Bepaalde stromen kunnen vaker worden uitgevoerd dan u verwacht. U kunt bijvoorbeeld een stroom maken die u een push melding stuurt wanneer uw manager u een e-mail stuurt. Deze stroom moet worden uitgevoerd elke keer dat u een e-mail ontvangt (van iedereen), omdat de stroom moet controleren of de e-mail afkomstig is van uw manager. Deze actie telt als een uitvoering.

U kunt dit probleem omzeilen door alle filters te plaatsen die u nodig hebt in de trigger. Vouw in het voor beeld van een push melding het menu **Geavanceerde opties** uit en geef het e-mail adres van uw manager op in het veld **van** .

## <a name="other-limits-and-caveats"></a>Andere beperkingen en voor behoud

* Elk account kan zoveel zijn als:
  * 250 stromen.
  * 15 aangepaste connectors.
  * 20 verbindingen per API en 100 verbindingen totaal.
* U kunt alleen een gateway in de standaard omgeving installeren.
* Bepaalde externe connectors, zoals Twitter, implementeren beperking van de verbinding om de kwaliteit van de service te bepalen. Uw stromen mislukken wanneer beperking van kracht is. Als uw stromen mislukken, controleert u de details van de uitvoering die is mislukt in de uitvoerings geschiedenis van de stroom.
