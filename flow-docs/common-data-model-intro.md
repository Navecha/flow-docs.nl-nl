---
title: Common Data Service | Microsoft Docs
description: Maak een stroom om gegevens te importeren, gegevens te exporteren of goed keuringen samen te stellen met de Common Data Service.
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
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 60e076dadab17beb15ffaec289ec0a2937924668
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546951"
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Een stroom maken die gebruikmaakt van de Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Verbeter de operationele efficiëntie met een uniforme weer gave van Bedrijfs gegevens door een stroom te maken die gebruikmaakt van de [common data service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). Implementeer deze beveiligde bedrijfs database die een goed opgemaakte standaard bedrijfs entiteiten bevat (zoals verkoop, aankoop, klanten service en productiviteit) in uw organisatie. Sla organisatie gegevens op in een of meer [aangepaste entiteiten](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/). deze bieden diverse voor delen ten opzichte van externe gegevens bronnen, zoals micro soft Excel en Sales Force.

Gebruik bijvoorbeeld de Common Data Service in Microsoft Flow op de volgende belang rijke manieren:

* Een stroom maken om gegevens te importeren, gegevens te exporteren of actie te ondernemen op gegevens (zoals het verzenden van een melding). Houd er rekening mee dat deze benadering geen volledige synchronisatie service is. u kunt er eenvoudigweg gegevens mee verplaatsen in of uit te voeren op basis van een eenheid.
  
    Zie de procedures verderop in dit onderwerp voor gedetailleerde stappen.
* In plaats van [een door e-mail een goedkeurings proces te maken](wait-for-approvals.md), maakt u een stroom die de goedkeurings status opslaat in een entiteit en maakt u een aangepaste app waarmee gebruikers items kunnen goed keuren of afwijzen.
  
    Zie [een goedkeurings proces bouwen met de common data service](common-data-model-approve.md)voor gedetailleerde stappen.

**Vereisten**

* Meld u aan voor [Microsoft flow](https://flow.microsoft.com) en [PowerApps](https://web.powerapps.com).
  
    Als u problemen ondervindt, controleert u of [Microsoft flow](sign-up-sign-in.md) en [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) het type account dat u hebt, ondersteunt en dat uw organisatie de aanmelding niet heeft geblokkeerd.
* Als u de Common Data Service nog niet eerder hebt gebruikt, opent u het tabblad **entiteiten** van [powerapps.com](https://web.powerapps.com/#/entities)en klikt of tikt u op **mijn data base maken**.

## <a name="sign-in-to-your-environment"></a>Aanmelden bij uw omgeving
1. Open de [Microsoft flow Portal](https://flow.microsoft.com)en klik of tik in de rechter bovenhoek op **Aanmelden** .
   
    **Opmerking**: mogelijk moet u het menu linksboven openen om de knop **Aanmelden** weer te geven.
   
    ![Aanmelden](./media/common-data-model-intro/signin-flow.png)
2. In het menu rechtsboven selecteert u de omgeving waarin u de Data Base hebt gemaakt in powerapps.com.
   
    **Opmerking**: als u niet dezelfde omgeving selecteert, worden uw entiteiten niet weer geven.
   
    ![Omgeving selecteren](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Een sjabloon openen
1. Typ of plak in het vak **Zoek sjablonen** boven aan het scherm de tekst **common**en druk op ENTER.
   
    ![Sjablonen zoeken](./media/common-data-model-intro/template-search.png)
2. Klik of tik in de lijst met sjablonen op de sjabloon waarmee gegevens worden geïmporteerd van de bron die u wilt opnemen in de gewenste entiteit (of *object*).
   
    Klik of tik bijvoorbeeld op de sjabloon waarmee de contact gegevens van Dynamics 365 worden gekopieerd naar de Common Data Service.
   
    ![Een sjabloon kiezen](./media/common-data-model-intro/choose-template.png)
3. Klik of tik op **deze sjabloon gebruiken**.
   
    ![Sjabloon gebruiken](./media/common-data-model-intro/use-template.png)
4. Als u nog geen verbinding hebt gemaakt van Microsoft Flow naar Dynamics 365, klikt of tikt u op **Aanmelden**en geeft u uw referenties op als u hierom wordt gevraagd.
   
    ![Aanmelden bij Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Klik of tik op **door gaan**.
   
    ![Accounts bevestigen](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Uw stroom bouwen
1. Geef in de eerste kaart de gebeurtenis op waarmee de stroom wordt geactiveerd.
   
    Stel dat u een stroom bouwt waarmee nieuwe contact personen worden gekopieerd van een exemplaar van Dynamics 365 naar het Common Data Service. Geef onder **Wanneer een record wordt gemaakt**het exemplaar op door te klikken of te tikken op de pijl-omlaag en vervolgens te klikken of tikken op een optie in de lijst die wordt weer gegeven.
   
    ![Exemplaar van Dynamics 365 opgeven](./media/common-data-model-intro/specify-instance.png)
2. Beschrijving Geef boven aan het scherm een andere naam op voor de stroom die u wilt maken.
   
    **Opmerking**: als het browser venster niet is gemaximaliseerd, kan de gebruikers interface er iets anders uitzien.
   
    ![Naam stroom](./media/common-data-model-intro/name-flow.png)
3. Klik of tik op **stroom maken**.
   
    **Opmerking**: als het browser venster niet is gemaximaliseerd, kan alleen het vinkje worden weer gegeven.
   
    ![stroom maken](./media/common-data-model-intro/create-flow.png)

Wanneer het object nu in het bron systeem wordt gemaakt, wordt het in de Common Data Service geïmporteerd. Als u een sjabloon die u nodig hebt niet kunt vinden, kunt u [een volledig nieuwe stroom bouwen](get-started-logic-flow.md) die boven op de common data service.

U kunt acties uitvoeren op wijzigingen in de data base. U kunt bijvoorbeeld een e-mail melding verzenden wanneer gegevens worden gewijzigd.

