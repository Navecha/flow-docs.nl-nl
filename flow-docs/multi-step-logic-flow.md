---
title: Een geavanceerde optie en meerdere acties toevoegen | Microsoft Docs
description: Breid een stroom uit met een geavanceerde optie, zoals e-mail instellen op hoge prioriteit, en voeg nog een actie toe voor dezelfde gebeurtenis.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/20/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 668e69b1c8f1781cf5720443af8e48409f43d322
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548616"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Meerdere acties en geavanceerde opties toevoegen aan een stroom
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Pas een stroom aan door een of meer geavanceerde opties en meerdere acties voor dezelfde trigger toe te voegen. Voeg bijvoorbeeld een geavanceerde optie toe waarmee een e-mail bericht met hoge prioriteit wordt verzonden. Naast het verzenden van e-mail wanneer een item wordt toegevoegd aan een share point-lijst, maakt u een bestand in Dropbox dat dezelfde informatie bevat.

## <a name="prerequisites"></a>Vereisten
* [Een stroom maken](get-started-logic-flow.md)

## <a name="add-another-action"></a>Nog een actie toevoegen
In deze procedure voegt u een actie toe in het midden van de stroom. Met deze actie wordt een bestand in uw Dropbox opgeslagen en wordt het item in de lijst gearchiveerd.

1. Selecteer in [flow.Microsoft.com](https://flow.microsoft.com) **mijn stromen** in de bovenste navigatie balk.
2. Selecteer de stroom die u wilt bewerken in de lijst met stromen.
3. Selecteer **nieuwe stap**en selecteer vervolgens **een actie toevoegen**.
   
    ![Samengevouwen toevoegen](./media/multi-step-logic-flow/add-action.png)
4. Zoek in de lijst met mogelijke acties naar **bestand maken**en selecteer vervolgens **Dropbox-bestand maken**.
   
    ![Zoek bestand maken](./media/multi-step-logic-flow/create-file-search.png)
5. Geef uw Dropbox-referenties op als u hierom wordt gevraagd.
6. Selecteer het mappictogram aan de rechter kant van het vak **pad naar map** .
7. Zoek en selecteer de map waarin u het nieuwe bestand wilt plaatsen.
   
    ![Zoek bestand maken](./media/multi-step-logic-flow/create-file-folder.png)
8. Voer de naam van het nieuwe bestand in het vak **Bestands naam** in. Zorg ervoor dat u een extensie, zoals. txt, toevoegt aan de bestands naam. Hier gaan we de **Tweet** in de naam van het bestand gebruiken om ervoor te zorgen dat de bestanden uniek zijn. U moet mogelijk **meer weer geven** selecteren om het **Tweet** -token te vinden.
9. Voeg de tekst toe die u wilt dat het bestand bevat door te typen in het vak **Bestands inhoud** . U kunt ook tokens toevoegen aan het vak **Bestands inhoud** .
   
    ![bestands naam en-inhoud](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Als u het bestand een naam geeft die overeenkomt met de naam van een bestaand bestand (in de geselecteerde map), wordt het bestaande bestand overschreven.
   > 
   > 
10. Selecteer **Update stroom**, die zich in het menu boven aan het scherm bevindt.
11. Stuur een tweet met het tref woord dat u hebt opgegeven.
    
     Binnen een minuut wordt een bestand gemaakt in uw Dropbox-account.

## <a name="reorder-or-delete-an-action"></a>Een actie opnieuw ordenen of verwijderen
* Als u e-mail wilt ontvangen nadat het bestand in Dropbox is gemaakt, verplaatst u de Dropbox-actie door de titel balk boven de e-mail actie te slepen. Release de Dropbox-actie via de pijl tussen de trigger (**Wanneer een nieuwe tweet wordt gepost**) en de e-mail actie. (De cursor geeft aan of de actie correct wordt geplaatst.)
  
  > [!NOTE]
  > U kunt een stap niet vóór de andere plaatsen als u uitvoer uit die stap gebruikt.
  > 
  > 
  
    ![Het menu verwijderen](./media/multi-step-logic-flow/draggingaction.png)
* Als u een actie wilt verwijderen, selecteert u het weglatings teken (...) aan de rechter kant van de titel balk voor de actie die u wilt verwijderen, selecteert u **verwijderen**en selecteert u vervolgens **OK**.
  
    ![Het menu verwijderen](./media/multi-step-logic-flow/deletemenu.png)
  
     **Opmerking:** U kunt een actie niet verwijderen als u overal in de stroom een wille keurige uitvoer wilt gebruiken. Verwijder eerst die uitvoer uit de velden en vervolgens kunt u de actie verwijderen.


## <a name="copy-and-paste-actions"></a>Acties kopiëren en plakken

Als u acties wilt dupliceren tijdens het ontwerpen van een stroom, kunt u deze kopiëren en plakken. Als u bijvoorbeeld een voor waarde bouwt en soort gelijke acties in de **If ja** -zijde en de **als geen** zijde, in plaats van beide acties te maken, kunt u de eerste actie op één zijde samen stellen en deze vervolgens naar de andere kant kopiëren.


### <a name="to-copy-an-action"></a>Een actie kopiëren
1. Selecteer het actie menu (de... in de rechter bovenhoek van de actie).
1. Selecteer **kopiëren naar het klem bord**. 
1. Selecteer **nieuwe stap** waar u wilt dat uw actie gaat. 

     U ziet het tabblad **mijn klem bord** , waarmee u alle acties kunt kiezen die u hebt gekopieerd.
1. Selecteer het item dat u wilt plakken.

## <a name="add-advanced-options"></a>Geavanceerde opties toevoegen
Begin met een stroom met een actie een **E-mail verzenden** .

1. Selecteer **Geavanceerde opties weer geven**onder aan de kaart **een e-mail verzenden** .
   
     Vervolgens ziet u de geavanceerde opties voor het verzenden van een e-mail.
   
    ![Share point-triggers](./media/multi-step-logic-flow/advanced.png)
2. Selecteer **hoog** in de lijst **urgentie** en selecteer vervolgens **Geavanceerde opties verbergen** om de geavanceerde opties te verbergen.
3. Selecteer **Update stroom**, die zich in het menu boven aan het scherm bevindt.
   
     Met deze stap worden uw wijzigingen opgeslagen.

