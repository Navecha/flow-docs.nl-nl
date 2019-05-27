---
title: Meer informatie over het automatiseren en uitvoeren van terugkerende taken met knopstromen voor het ophalen van gebruikersinvoer | Microsoft Docs
description: Met Microsoft Flow kunt u terugkerende taken eenvoudig automatiseren. U kunt met uw stromen zelfs gebruikersinvoer ophalen bij het uitvoeren van een terugkerende taak.
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
ms.openlocfilehash: 5c1aed64ad5ac8fc1cced9290b376cb54f97e65a
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64992319"
---
# <a name="introducing-button-flows-with-user-input"></a>Inleiding voor knopstromen met gebruikersinvoer
Een knopstroom maken om routinetaken uit te voeren door op een knop te tikken. De stroom aanpassen door de gebruiker de gelegenheid te geven specifieke details op te geven die worden gebruikt als de stroom wordt uitgevoerd. In dit onderwerp wordt u begeleid bij het maken van een knopstroom die invoer van de gebruiker opneemt en vervolgens de knopstroom uitvoert, met de nadruk op het leveren van de invoer van de gebruiker.

U kunt een knopstroom maken in de Microsoft Flow-website of met de mobiele app voor Microsoft-Flow. In dit onderwerp gebruikt u de website.

### <a name="prerequisites"></a>Vereisten
* Een account bij de Microsoft Flow-website.

## <a name="open-the-template"></a>De sjabloon openen
1. Meld u aan bij de [Microsoft Flow-website](https://flow.microsoft.com), voer in het zoekvak **Visual Studio** in en klik of tik vervolgens op het zoekpictogram om naar alle sjablonen te zoeken die gerelateerd zijn aan Visual Studio:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. Selecteer de sjabloon **Een bug met prioriteit 2 openen in Visual Studio**:
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. Selecteer de knop **Deze sjabloon gebruiken**:
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Deze sjabloon maakt gebruik van Visual Studio Team Services (VSTS) en Push Notification Services. U moet zich aanmelden bij een van deze services als u geen verbinding hebt met een van beide. De knop **Aanmelden** wordt alleen weergegeven als u zich moet aanmelden bij een service.
4. Nadat u zich bij alle benodigde services hebt aangemeld, selecteert u de knop **Doorgaan**:
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. (optioneel) Wijzig de naam van de stroom door de gewenste naam in het vak boven aan de portal te typen:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>De gebruikersinvoer aanpassen
1. Selecteer **Bewerken** in de kaart voor de trigger:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Selecteer het pictogram **+** om de pagina uit te breiden zodat u aangepaste invoervelden kunt toevoegen:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Voer **Titel van invoer** en **Beschrijving van invoer** in voor elk aangepast veld dat u beschikbaar wilt stellen als iemand de stroom uitvoert.  
   
    In dit voorbeeld maakt u twee aangepaste invoervelden (**Stappen om fout te reproduceren** en **Ernst van fout**), zodat iedereen die deze stroom gebruikt, de stappen kan invoeren om de fout te reproduceren en de ernst van de fout kan beoordelen:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>De fout aanpassen
1. Tik op de titelbalk **Een nieuw werkitem maken** van de kaart:
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. Selecteer de instellingen die passend zijn voor uw VSTS-omgeving en selecteer vervolgens **Bewerken**:
   
    Maak bijvoorbeeld verbinding met mijninstantie.visualstudio.com door **mijninstantie** te typen.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Selecteer **Geavanceerde opties weergeven** om de andere velden voor deze kaart weer te geven:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. Plaats de cursor voor het token **Titel van fout** en voer vervolgens in het tekstveld **Titel** Ernst in.
5. Selecteer het token **Ernst van fout** terwijl de cursor nog in het tekstveld Titel staat en voer vervolgens ' -- ' in.  
6. Plaats de cursor in het tekstveld **Beschrijving** direct na het token **Beschrijving van de fout** en druk vervolgens op Enter om een nieuwe regel te beginnen.
7. Plaats de cursor op de nieuwe regel en selecteer vervolgens het token **Stappen om fout te reproduceren**:
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>De pushmelding aanpassen
1. Tik op de titelbalk op de kaart **Een pushmelding verzenden** om deze uit te vouwen.
2. Selecteer in de lijst met tokens voor dynamische inhoud **Meer weergeven** en voeg vervolgens in het tekstveld **Koppeling** het token **URL** in.
3. Voeg in het tekstveld **Label voor koppeling** het token **Id** in:
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Tik in het menu op **Stroom maken** om de stroom te maken:  ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>De stroom uitvoeren
In dit scenario voert u met de mobiele app voor Microsoft-Flow de knopstroom uit die u zojuist hebt gemaakt. U geeft de gebruikersinvoer op die nodig is om een fout te maken, dat wil zeggen een titel, een beschrijving, stappen om te reproduceren en een ernstniveau.  

1. Tik in de mobiele app voor Microsoft-Flow op het tabblad **Knoppen** en tik op de knop **Foutenrapport met stappen maken**.
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Voer de titel in voor de fout die u wilt rapporteren en tik vervolgens op **Volgende**. Bijvoorbeeld:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Voer de beschrijving in van de fout die u wilt rapporteren en tik vervolgens op **Volgende**. Bijvoorbeeld:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Voer de stappen in om de fout te reproduceren die u wilt rapporteren en tik vervolgens op **Volgende**. Bijvoorbeeld:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Voer de ernst in van de fout die u wilt rapporteren en tik vervolgens op **Gereed**.  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    De stroom wordt uitgevoerd.
6. (optioneel) Tik op het tabblad **Activiteit** om de resultaten weer te geven.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. (optioneel) Geef de gedetailleerde resultaten van de stroomuitvoering weer door op de stap **Een nieuw werkitem maken** te tikken.
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>Gebruik verschillende invoertypen

Uw knopstromen kunnen ook uitgebreide gegevenstypen accepteren. Hier volgt de lijst met gegevens invoertypen die knopstromen accepteren: 

- Tekst
- Vervolgkeuzelijsten (zoals keuzerondjes)
- E-mailadres
- Bestand (bijvoorbeeld een foto op uw telefoon)
- Ja of Nee selectievakje
- Aantal
- Datum (met een datumkiezer kalender)

Voor het gebruik van deze invoertypen, voeg de **handmatig een stroom activeren** activeren en een van deze typen vervolgens toevoegen aan uw stroom:

![Opties voor invoer](media/button-flow-with-user-input-tokens/input-options.png)

U wilt ook enkele invoer zoals vereist en anderen aanwijzen als optioneel. Gebruik het actiemenu (...) aan de rechterkant) op elke invoerveld. Er is een limiet van vijf invoer per knop.

![Optionele tokens selecteren](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>Volgende stappen
* [Knopstromen delen](share-buttons.md)
* [Meer informatie over knopstromen](introduction-to-button-flows.md)  
* [Meer informatie over knopstromen met triggertokens](introduction-to-button-trigger-tokens.md)  

