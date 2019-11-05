---
title: Deel uw knoppen met anderen. | Microsoft Docs
description: Deel uw knoppen met anderen, zodat ze uw knoppen kunnen gebruiken en Bespaar tijd.
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
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 098ebf9d8e02ede22a7914a2458375eb3641544a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548414"
---
# <a name="share-button-flows-in-microsoft-flow"></a>Knop stromen delen in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
In de mobiele app van Microsoft Flow kunt u [knop stromen](introduction-to-button-flows.md) (knoppen) delen met andere gebruikers of groepen in uw organisatie. Wanneer u een knop deelt, kan de persoon of groep met wie u deelt uw knop uitvoeren, op dezelfde manier als waarop ze hun eigen knoppen uitvoeren. U kunt ook [een koppeling delen](share-buttons.md#re-share-a-button) met knoppen die een andere persoon met u heeft gedeeld. U kunt het delen van uw knoppen op elk gewenst moment [beëindigen](share-buttons.md#stop-sharing-a-button) .

> De scherm afbeeldingen in dit document zijn afkomstig van een Android-apparaat. Als u een iPhone gebruikt, worden de afbeeldingen mogelijk anders weer gegeven, maar de functionaliteit is hetzelfde.
> 
> 

Volg [deze stappen](share-buttons.md#use-shared-buttons) om een knop te gebruiken die iemand met u heeft gedeeld.

## <a name="prerequisites"></a>Vereisten
Als u knoppen wilt delen, hebt u het volgende nodig:

* Een account met toegang tot [Microsoft flow](https://flow.microsoft.com).
* Een stroom om te delen.
* Een mobiel apparaat met de mobiele app Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [IOS](https://aka.ms/flowmobiledocsios)of [Windows Phone](https://aka.ms/flowmobilewindows).
* Een groep of gebruiker binnen uw organisatie met wie u de knop wilt delen.

## <a name="share-a-button"></a>Een knop delen
U kunt een knop delen via het tabblad **knoppen** van de mobiele app van Microsoft flow.

1. Tik op het kleine pictogram naast de knop die u wilt delen.
   
    ![knop delen](./media/share-buttons/share-button-flows-buttons-tab.png)
2. Tik op **anderen uitnodigen** op de pagina **knop gebruikers** .
   
    ![knop delen](./media/share-buttons/share-button-flows-button-users.png)
3. Zoek naar en selecteer de groep of persoon met wie u de knop wilt delen.
   
    ![knop delen](./media/share-buttons/share-button-flows-invite-others-select.png)
4. Tik op de pagina **anderen uitnodigen** op **verzenden** .
   
    ![knop delen](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Tik op **gereed** op de pagina waarop wordt aangegeven dat de bewerking voor het delen van de knop is voltooid.
   
    ![knop delen](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Gebruikers moeten hun eigen verbindingen gebruiken
> [!NOTE]
> Wanneer u een knop deelt, kunt u personen met wie u de knop hebt gedeeld, toestaan om alle verbindingen te gebruiken die door de knop worden gebruikt. U kunt er ook voor zorgen dat ze hun eigen verbindingen gebruiken. Als u toestaat dat anderen uw verbindingen gebruiken, hebben ze geen toegang tot de referenties in uw verbinding of kunnen ze niet opnieuw worden gebruikt in een andere stroom.
> 
> 

Volg deze stappen om te vereisen dat personen met wie u uw knoppen hebt gedeeld, hun eigen verbindingen gebruiken.

1. Selecteer **verbindingen beheren** op het scherm dat direct na het delen van een knop wordt weer gegeven.
2. Selecteer **bewerken** op de knop die u wilt beheren.
3. Selecteer de **door de gebruiker** of uw e-mail adres gegeven.
   
    Uw keuze geeft aan welke verbindingen moeten worden gebruikt op de knop gedeeld.
   
    ![knop delen](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    U kunt uw keuze op elk gewenst moment weer geven of wijzigen. Hiertoe selecteert u het tabblad **stromen** > de stroom die u hebt gedeeld > **gebruikers en verbindingen** > het tabblad **verbindingen** > **bewerken** op de knop die u wilt beheren.
   
    ![knop delen](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>De lijst met knop gebruikers weer geven
U kunt alle groepen of gebruikers met wie een knop wordt gedeeld weer geven door de volgende stappen uit te voeren op het tabblad **knoppen** :

1. Tik op het kleine pictogram naast de knop waarin u geïnteresseerd bent.
2. Bekijk op de pagina **knop gebruikers** alle groepen of gebruikers met wie de knop wordt gedeeld.
   
    ![knop gebruikers weer geven](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Stoppen met delen van een knop
U kunt het delen van een knop beëindigen door de volgende stappen uit te voeren op het tabblad **knoppen** :

1. Tik op het kleine pictogram naast de knop die u niet meer wilt delen.
2. Op de pagina **knop gebruikers** tikt u op de gebruiker of groep met wie u wilt stoppen met het delen van de knop.
   
    ![knop delen stoppen](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Tik op **gebruiker verwijderen** wanneer de pagina van de gebruiker wordt weer gegeven.
   
    ![knop delen stoppen](./media/share-buttons/share-button-flows-remove-user.png)
4. Wacht tot de bewerking verwijderen is voltooid. U ziet dat de lijst met **knop gebruikers** wordt vernieuwd en de gebruiker of groep die u hebt verwijderd, wordt niet meer weer gegeven.
   
    ![knop delen stoppen](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>De uitvoerings geschiedenis controleren
Alle uitvoerings geschiedenis, inclusief de uitvoeringen die zijn gestart door iemand met wie een knop wordt gedeeld, wordt alleen weer gegeven op het tabblad **activiteit** van de Microsoft flow mobiele app van de knop.

## <a name="use-shared-buttons"></a>Gedeelde knoppen gebruiken
Voordat u een knop kunt uitvoeren die iemand met u heeft gedeeld, moet u deze toevoegen aan het tabblad **knoppen** op de pagina **knoppen toevoegen** .

1. Tik op **meer ophalen** (of de **nieuwe knoppen zijn beschikbaar** banner als deze wordt weer gegeven) op het tabblad **knoppen** .
   
    ![nieuwe knop gedeeld met mij](./media/share-buttons/share-button-flows-banner.png)
2. Tik op de knop die u wilt gebruiken.
   
    De knop getikt wordt direct toegevoegd aan het tabblad **knoppen** van de app Microsoft flow. U kunt de knop vervolgens op het tabblad **knoppen** gebruiken, net als elke andere knop die daar wordt vermeld.
   
    ![nieuwe knop gedeeld met mij](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Een knop opnieuw delen
U kunt een koppeling delen naar een knop die met u is gedeeld.

1. Selecteer **...** naast de knop die u wilt delen.
2. Selecteer de **koppeling knop delen**.
   
    ![knop koppeling opnieuw delen](./media/share-buttons/re-share-button.png)
3. Selecteer de app die u wilt gebruiken om de knop te delen en volg de stappen om de knop te verzenden naar de persoon met wie u wilt delen.

## <a name="stop-using-a-shared-button"></a>Een gedeelde knop niet meer gebruiken
Als u een knop die met u is gedeeld niet meer wilt gebruiken, verwijdert u deze uit het tabblad **knoppen** door de volgende stappen uit te voeren:

1. Tik op het tabblad **knoppen** op **...** naast de knop die u niet meer wilt gebruiken.
   
    ![knop verwijderen](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Tik op **verwijderen** in het menu dat wordt weer gegeven.

Dat is alles. De knop wordt niet meer weer gegeven op het tabblad **knoppen** van de app Microsoft flow.

> [!NOTE]
> Nadat u een gedeelde knop hebt verwijderd, kunt u deze opnieuw toevoegen door **meer ophalen** te selecteren op het tabblad **knoppen** .
> 
> 

