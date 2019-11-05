---
title: Invoer en uitvoer gebruiken in de gebruikers interface van het bureau blad | Microsoft Docs
description: Invoer en uitvoer gebruiken in de gebruikers interface van het bureau blad.
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
ms.openlocfilehash: 88bea3b8a038c01360fc5f3e61dbf30599b5deba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589766"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Invoer en uitvoer gebruiken in de gebruikers interface van het bureau blad

[Dit onderwerp bevat voorlopige documentatie en kan worden gewijzigd.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs"></a>Invoer opgeven

Met invoer kunt u informatie door geven van een externe bron, zoals een Data Base of een ondersteunde connector, voor de verouderde software die door de gebruikers interface wordt geautomatiseerd.

U kunt bijvoorbeeld klant gegevens uit een share point-lijst gebruiken als bron voor invoer in uw verouderde boekhoud software.

### <a name="define-inputs-in-the-ui-flows-wizard"></a>Invoer opgeven in de wizard gebruikers interface stromen

1. Selecteer nieuwe invoer

   ![](../media/inputs-outputs-desktop/2eb6313a0e966f1fbfc352445b89ee39.png)

1. Voeg een naam, een voorbeeld gegevens en een beschrijving toe aan uw invoer.

    - Voorbeeld gegevens worden gebruikt tijdens het opnemen of testen.

    - De beschrijving is handig voor het onderscheiden van de invoer die u hebt gemaakt.

   ![](../media/inputs-outputs-desktop/e33d206bf2158228277a276261c49785.png)

1.  Zodra de invoer is gemaakt, kunt u op Volgende klikken om ze te gebruiken in een opname.

### <a name="use-inputs-to-pass-information-to-the-application"></a>Invoer gebruiken om informatie door te geven aan de toepassing

1. Tijdens het opnemen kunt u een invoer in een app gebruiken door **invoer gebruiken**te selecteren.

1. In de lijst kunt u kiezen uit drie opties:

    - Selecteer een van de invoer waarden die u hebt gedefinieerd in gebruikers interface stromen **invoer velden instellen** stap.

    - Een eerder gedefinieerde uitvoer gebruiken (Zie de sectie outputs). Dit is handig voor het door geven van gegevens tussen verschillende toepassingen binnen dezelfde UI-stroom.

    - Maak een nieuwe invoer tijdens het opnemen. U vindt deze terug in de stap voor het **instellen van invoer velden** in UI-stromen.

   ![](../media/inputs-outputs-desktop/de36baa0f85d5a19304e1606de25aa3e.png)

1. Selecteer de locatie waar u de invoer wilt gebruiken. De door u gedefinieerde voorbeeld waarde wordt automatisch gebruikt. In het onderstaande voor beeld is ' Hallo wereld ' de voorbeeld waarde voor de invoer naam ' mijn invoer ' en deze wordt toegevoegd aan de pagina in micro soft Word.  
    
    ![](../media/inputs-outputs-desktop/d6b74dc86f38c51cf1daa0582ff0cc33.png)

1. Vouw in Power de stappen voor het automatiseren van **records en bewerkingen**, acties uit die gebruikmaken van invoer om weer te geven welke is geselecteerd.

   ![](../media/inputs-outputs-desktop/340aa71942b618431b0455b632f76f52.png)

1. Wanneer u de gebruikers interface-stroom wilt activeren, kunt u de invoer waarde wijzigen in. Zie invoer & uitvoer gebruiken voor meer informatie.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Uitvoer gebruiken om informatie uit de app te halen

Met uitvoer kunt u gegevens van de verouderde software door geven die door de gebruikers interface worden geautomatiseerd naar een externe bestemming, zoals een Data Base of een [ondersteunde connector](https://flow.microsoft.com/connectors/).

U kunt bijvoorbeeld klant gegevens ophalen uit uw verouderde boekhoud software en toevoegen aan een share point-lijst.

Outputs kunnen alleen worden gemaakt wanneer u de gebruikers interface-stroom vastlegt.

1. Bij een opname selecteert u in de knop uitvoer ophalen

   ![](../media/inputs-outputs-desktop/13f8dfca19c0ed04ca2a0f87bf7055ea.png)

1. Selecteer de knop tekst selecteren (dit is het enige type uitvoer dat nu beschikbaar is)

   ![](../media/inputs-outputs-desktop/2845b73ee807a5be747c1dc494570ab7.png)

1. Klik op een element van de gebruikers interface om de bijbehorende tekst voor de uitvoer te selecteren. De waarde wordt automatisch vastgelegd.

   ![](../media/inputs-outputs-desktop/7df19b56aadcd0aef207c7372a04b3c6.png)

   ![](../media/inputs-outputs-desktop/af55a0bf39d805b154a783eff3de131b.png)

1. Definieer de naam en de beschrijving van de uitvoer.

   ![](../media/inputs-outputs-desktop/a083579ee011dfb76aa21fac116796a3.png)

1. Selecteer **opslaan.** 

Uw uitvoer is nu beschikbaar in het toegewezen gebied van de wizard

   ![](../media/inputs-outputs-desktop/b9f396de0b5893c5a3152b592911f67a.png)

Elke uitvoer heeft:

-  Een uitvoer naam zoals gedefinieerd tijdens de registratie
-  Een beschrijving: dit veld kan erg nuttig zijn wanneer u tijdens een registratie veel uitvoer definieert en u deze eenvoudig wilt identificeren.
-  Een actie naam: de actie waarbij de uitvoer is gedefinieerd in de gebruikers interface stroom

## <a name="delete-an-output-from-a-ui-flow"></a>Een uitvoer van een UI-stroom verwijderen

Als u geen uitvoer meer nodig hebt, kunt u deze verwijderen door terug te gaan naar de bijbehorende actie en de uitvoer naam in de dynamische waarde te verwijderen.

## <a name="test-your-ui-flow"></a>Uw gebruikers interface stroom testen

Door UI-stromen te testen kunt u uw wijzigingen en het juiste afspeel gedrag valideren.

1. Beschrijving Voer een nieuwe waarde in het invoer veld in. 
    
    ![](../media/inputs-outputs-desktop/0b4aef639c4ab30b93413e1e7a5e662d.png)

1. Klik op **nu testen** om te zien of de verouderde software geautomatiseerd is. U ziet dat de door u genoteerde stappen worden weer gegeven in de UI-automatisering van de werk stroom. **Maak geen interactie met uw apparaat voor de duur van het afspelen.**

1. Zodra het afspelen is voltooid, ziet u de uitvoerings status van de gebruikers interface-flow:

    - Voor elke actie, een status die aangeeft dat de test goed werkte en de bijbehorende invoer.

    - De waarde van de uitvoer die voor deze test is verkregen.

    - Als er een fout is gegenereerd, kunt u zien welke stap problematisch was met een scherm opname van het moment dat de fout optrad.

   ![](../media/inputs-outputs-desktop/85056d7942d12a5408005f5b683d432b.png)

## <a name="learn-more"></a>Meer informatie

- Meer informatie over [het activeren van de gebruikers interface stroom](run-ui-flow.md) die u zojuist hebt gemaakt.

- Als u meer wilt doen met UI-stromen, kunt u ook de gebruikers interface stromen uitproberen met [invoer-en uitvoer](inputs-outputs-web.md) parameters.


