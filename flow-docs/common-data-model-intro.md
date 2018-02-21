---
title: Common Data Service | Microsoft Docs
description: Maak een stroom om gegevens te importeren, gegevens te exporteren of goedkeuringen te bouwen met de Common Data Service.
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: e4e92bfdcf1ea65de272233b2056523641010cf2
ms.sourcegitcommit: f3261717768177e03e825c0dd2e3ba736dc9b94d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2018
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Een stroom maken die gebruikmaakt van de Common Data Service
Verbeter uw bedrijfsefficiëntie met een geïntegreerde weergave van bedrijfsgegevens door een stroom te maken die gebruikmaakt van de [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). U kunt deze beveiligde bedrijfsdatabase die bestaat uit juist opgemaakte standaardbedrijfsentiteiten (zoals Verkoop, Inkoop, Klantenservice en Productiviteit) in uw organisatie implementeren. U kunt de organisatiegegevens opslaan in een of meer [aangepaste entiteiten](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/), die verschillende voordelen bieden via externe gegevensbronnen zoals Microsoft Excel en Salesforce.

Een voorbeeld: u kunt in Microsoft Flow op de volgende manieren gebruikmaken van de Common Data Service:

* U kunt een stroom maken om gegevens te importeren, gegevens te exporteren of een actie uit te voeren op gegevens (zoals het verzenden van een melding). Houd er rekening mee dat deze benadering geen volledige synchronisatieservice is. U kunt gegevens alleen per entiteit naar binnen of naar buiten verplaatsen.
  
    Zie de procedures in dit onderwerp voor gedetailleerde stappen.
* In plaats van [een goedkeuringslus via e-mail te maken](wait-for-approvals.md), maakt u een stroom waarmee de goedkeuringsstatus wordt opgeslagen in een entiteit en bouwt u een aangepaste app waarin gebruikers items kunnen goedkeuren of afwijzen.
  
    Zie het artikel [Een goedkeuringslus bouwen met de Common Data Service](common-data-model-approve.md) voor uitvoerige stappen.

**Vereisten**

* Registreren voor [Microsoft Flow](https://flow.microsoft.com) en [PowerApps](https://web.powerapps.com).
  
    Als u problemen ondervindt, controleert u of [Microsoft Flow](sign-up-sign-in.md) en [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) ondersteuning bieden voor het type account dat u hebt en of aanmelding niet is geblokkeerd door uw organisatie.
* Als u de Common Data Service nog niet eerder hebt gebruikt, gaat u naar [powerapps.com](https://web.powerapps.com/#/entities), opent u het tabblad **Entiteiten** en klikt of tikt u op **Mijn database maken**.

## <a name="sign-in-to-your-environment"></a>Aanmelden bij uw omgeving
1. Open de [Microsoft Flow-portal](https://flow.microsoft.com) en klik of tik op **Aanmelden** in de rechterbovenhoek.
   
    **Opmerking**: mogelijk moet u het menu linksboven openen om de knop **Aanmelden** weer te geven.
   
    ![Aanmelden](./media/common-data-model-intro/signin-flow.png)
2. In het bovenste menu rechts selecteert u de omgeving die u hebt gemaakt in de database in powerapps.com.
   
    **Opmerking**: als u niet dezelfde omgeving selecteert, worden uw entiteiten niet weergegeven.
   
    ![Omgeving selecteren](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Een sjabloon openen
1. Typ of plak **common** in het vak **Sjablonen zoeken** boven in het scherm en druk op Enter.
   
    ![Sjablonen zoeken](./media/common-data-model-intro/template-search.png)
2. Klik of tik in de lijst met sjablonen op de sjabloon waarmee de gegevens uit de bron worden geïmporteerd die u in de entiteit (of het *object*) wilt opnemen.
   
    Tik op klik bijvoorbeeld op de sjabloon waarmee contactgegevens uit Dynamics 365 naar de Common Data Service worden gekopieerd.
   
    ![Een sjabloon kiezen](./media/common-data-model-intro/choose-template.png)
3. Klik of tik op **Deze sjabloon gebruiken**.
   
    ![Sjabloon gebruiken](./media/common-data-model-intro/use-template.png)
4. Als u nog geen koppeling tot stand hebt gebracht vanuit Microsoft Flow met Dynamics 365, klikt of tikt u op **Aanmelden** en geeft u uw referenties op als u hierom wordt gevraagd.
   
    ![Aanmelden bij Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Klik of tik op **Doorgaan**.
   
    ![Accounts bevestigen](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Uw stroom bouwen
1. Geef op de eerste kaart de gebeurtenis op waarmee de stroom wordt geactiveerd.
   
    Stel dat u een stroom bouwt waarmee nieuwe contactpersonen vanuit een Dynamics 365-exemplaar naar de Common Data Service worden gekopieerd. Geef het exemplaar op onder **Wanneer een record wordt gemaakt** door te klikken of te tikken op de pijl-omlaag en vervolgens te klikken of te tikken op een optie in de lijst die wordt weergegeven.
   
    ![Dynamics 365-exemplaar opgeven](./media/common-data-model-intro/specify-instance.png)
2. Typ eventueel een andere naam voor de stroom die u maakt boven in het scherm.
   
    **Opmerking**: als het browservenster niet is gemaximaliseerd, kan de gebruikersinterface er enigszins anders uitzien.
   
    ![De stroom een naam geven](./media/common-data-model-intro/name-flow.png)
3. Klik of tik op **Stroom maken**.
   
    **Opmerking**: als het browservenster niet is gemaximaliseerd, wordt mogelijk alleen het vinkje weergegeven.
   
    ![Stroom maken](./media/common-data-model-intro/create-flow.png)

Wanneer het object nu in het bronsysteem wordt gemaakt, wordt dit geïmporteerd in de Common Data Service. Als u geen geschikte sjabloon kunt vinden, kunt u [een volledig nieuwe stroom bouwen](get-started-logic-flow.md) die boven op de Common Data Service werkt.

U kunt acties uitvoeren op wijzigingen in de database. U kunt bijvoorbeeld een e-mailmelding verzenden wanneer de gegevens worden gewijzigd.

