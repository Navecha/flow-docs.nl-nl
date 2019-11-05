---
title: Meer informatie over het automatiseren van terugkerende taken met knop stromen die gebruikers invoer maken | Microsoft Docs
description: Microsoft Flow maakt het eenvoudig om terugkerende taken te automatiseren. Uw stromen kunnen zelfs gebruikers invoer uitvoeren wanneer een terugkerende taak wordt uitgevoerd.
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
ms.date: 02/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a1bc5161bdd0e6a098d57cefafba99d3c89e6c97
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546446"
---
# <a name="introducing-button-flows-with-user-input"></a>Introductie van knop stromen met gebruikers invoer
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Een knop stroom maken om routine taken uit te voeren door simpelweg op een knop te tikken. Pas uw stroom aan door de gebruiker specifieke details te geven die worden gebruikt wanneer de stroom wordt uitgevoerd. In dit onderwerp vindt u instructies voor het maken van een knop stroom die de invoer van de gebruiker uitvoert en de knop stroom wordt uitgevoerd, waarbij u kunt aangeven hoe de gebruikers invoer moet worden opgegeven.

U kunt een knop stroom maken in de Microsoft Flow website of de mobiele app voor Microsoft Flow. Voor dit onderwerp gebruikt u de website.

### <a name="prerequisites"></a>Vereisten
* Een account op de Microsoft Flow-website.

## <a name="open-the-template"></a>De sjabloon openen
1. Meld u aan bij de [Microsoft flow-website](https://flow.microsoft.com), Voer **Visual Studio** in het zoekvak in en klik of tik op het zoek pictogram om alle sjablonen te vinden die betrekking hebben op Visual Studio:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. Selecteer de sjabloon **een bug met prioriteit 2 openen in Visual Studio** :
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. Selecteer **de knop deze sjabloon gebruiken** :
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Deze sjabloon maakt gebruik van Visual Studio Team Services (VSTS) en de Push Notification Services. U moet zich aanmelden bij deze services als u geen verbinding hebt met een van beide. De **aanmeldings** knop wordt alleen weer gegeven als u zich moet aanmelden bij een service.
4. Nadat u zich hebt aangemeld bij alle benodigde services, selecteert u de knop **door gaan** :
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. Beschrijving Wijzig de naam van de stroom door de gewenste naam in het vak boven aan de portal te typen:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>De gebruikers invoer aanpassen
1. Selecteer **bewerken**in de trigger kaart:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Selecteer het pictogram **+** om de pagina uit te breiden zodat u aangepaste invoer velden kunt toevoegen:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Voer de **Invoer titel** en de **invoer beschrijving** in voor elk aangepast veld dat u beschikbaar wilt maken wanneer iemand uw stroom uitvoert.  
   
    In dit voor beeld maakt u twee aangepaste invoer velden (**bug reproduceren-stappen** en **fout Ernst**), zodat iedereen die deze stroom gebruikt, de stappen kan invoeren om de fout te reproduceren en de ernst van de fout te beoordelen:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>De bug aanpassen
1. Tik op de titel balk **een nieuwe werk item maken** :
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. Selecteer de opties die geschikt zijn voor uw VSTS-omgeving en selecteert u **bewerken**:
   
    U kunt bijvoorbeeld verbinding maken met myinstance.visualstudio.com door **myinstance**te typen.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Selecteer **Geavanceerde opties weer geven** om de andere velden voor deze kaart te tonen:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. Plaats de cursor vóór het **fout titel** token en voer ' Ernst: ' in het tekst veld **titel** in.
5. Als de cursor zich nog in het tekst veld Titel bevindt, selecteert u het Ernst token van de **fout** en voert u vervolgens '--' in.  
6. In het tekst veld **Beschrijving** plaatst u de cursor vlak na het **fout beschrijvings** token en drukt u vervolgens op ENTER om een nieuwe regel te starten.
7. Plaats de cursor op de nieuwe regel en selecteer vervolgens het token voor de **fout reproduceren-stappen** :
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>De push melding aanpassen
1. Tik op de titel balk op de kaart **een push melding verzenden** om deze uit te vouwen.
2. Selecteer in de lijst met tokens voor dynamische inhoud de optie **meer weer geven**en voeg vervolgens het **URL** -token toe in het tekst veld voor de **koppeling** .
3. Voeg in het tekst veld **label voor koppeling** het token **id** toe:
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Tik op **stroom maken** in het menu om uw stroom te maken: ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Uw stroom uitvoeren
In deze procedure gebruikt u de mobiele app voor Microsoft Flow voor het uitvoeren van de knop stroom die u zojuist hebt gemaakt. U kunt alle gebruikers invoer opgeven die nodig is voor het maken van een bug met een titel, een beschrijving, reproduceren stappen en een Ernst niveau.  

1. Tik in de mobiele app voor Microsoft Flow op het tabblad **knoppen** en tik vervolgens op de knop **fout rapport maken met stappen** .
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Voer de titel in voor de fout die u wilt rapporteren en tik vervolgens op **volgende**. Bijvoorbeeld:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Voer de beschrijving in van de fout die u wilt rapporteren en tik vervolgens op **volgende**. Bijvoorbeeld:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Voer de stappen in om de fout te reproduceren die u wilt rapporteren en tik vervolgens op **volgende**. Bijvoorbeeld:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Voer de ernst in van de fout die u wilt rapporteren en tik vervolgens op **gereed**:  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    De stroom wordt uitgevoerd.
6. Beschrijving Tik op het tabblad **activiteit** om de resultaten weer te geven.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. Beschrijving Geef de gedetailleerde resultaten van de uitvoering van de stroom weer door op de stap **een nieuwe werk item maken** te tikken.
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>Verschillende invoer typen gebruiken

Uw knop stromen kunnen ook uitgebreide gegevens typen accepteren. Hier volgt een lijst met gegevens invoer typen die door de knop stromen worden geaccepteerd: 

- SMS
- Vervolg keuzelijsten (zoals keuze rondjes)
- E-mail adres
- Bestand (bijvoorbeeld een foto op uw telefoon)
- Selectie vakje ja of Nee
- Telwoord
- Datum (met een kalender kiezer)

Als u deze invoer typen wilt gebruiken, voegt u **hand matig een stroom** trigger toe en voegt u deze typen vervolgens toe aan uw stroom:

![Invoer opties](media/button-flow-with-user-input-tokens/input-options.png)

Daarnaast is het mogelijk dat u een aantal invoer wilt aanwijzen als vereist en andere als optioneel. Het menu actie gebruiken (... aan de rechter kant) op elk invoer veld. Er is een limiet van vijf invoer per knop.

![Optionele tokens selecteren](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>Volgende stappen
* [Knop stromen delen](share-buttons.md)
* [Meer informatie over knop stromen](introduction-to-button-flows.md)  
* [Meer informatie over knop stromen met trigger tokens](introduction-to-button-trigger-tokens.md)  

