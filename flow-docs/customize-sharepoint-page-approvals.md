---
title: Beheer goedkeuringen voor SharePoint-pagina met Microsoft Flow | Microsoft Docs
description: Informatie over het beheren van goedkeuringen voor SharePoint-pagina met Microsoft Flow...
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: d5e01a3d2e13cc48107e19e0e2bbea3821437273
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061337"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>Beheer goedkeuringen voor SharePoint-pagina met Microsoft Flow

Beheerders van de SharePoint-site kunt u Microsoft Flow gebruiken om te vereisen nieuwe of bijgewerkte sitepagina's moeten worden goedgekeurd voordat het werd gepubliceerd.

In dit artikel leert u hoe u uw SharePoint-site voor het gebruik van een stroom vereist wijzigingen in de site moeten worden goedgekeurd voordat ze live gaan configureren.

## <a name="configure-sharepoint-for-page-approvals"></a>SharePoint configureren voor pagina goedkeuringen

### <a name="prerequisites"></a>Vereisten 

U moet de beheerder van een SharePoint-site voor het uitvoeren van de activiteiten in dit artikel.

1. Aanmelden bij SharePoint als de beheerder van een site.
1. Selecteer **pagina's** in de navigatiebalk.

    ![Pagina goedkeuringsstroom selecteren](media/customize-sharepoint-page-approvals/pages.png)

1. Selecteer **stroom** en selecteer vervolgens **configureren pagina goedkeuringsstroom**.
    
    ![Pagina goedkeuringsstroom selecteren](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Geef een **Stroomnaam**, ten minste één naam in de **goedkeurders** vak en selecteer vervolgens **maken**.
    
    ![Pagina goedkeuringsstroom selecteren](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Dat is alles! Nu, telkens wanneer een pagina wordt toegevoegd of gewijzigd, een goedkeuringsaanvraag gaat u naar de **goedkeurders** u vermeld in de stroom.

De pagina goedkeuringsstroom is net als bij een andere stroom, wordt deze weergegeven in de **mijn stromen** tabblad.

![Pagina goedkeuringsstroom selecteren](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Een pagina voor goedkeuring verzenden

Nu dat u een goedkeuringsstroom voor pagina hebt gemaakt, wordt iedereen die toegevoegd of gewijzigd van een pagina moet het volgende doen:

 - Breng een wijziging aan in de site (bijvoorbeeld een nieuwe pagina toevoegen) en sla de wijziging.

     ![Pagina voor goedkeuring verzenden](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Wacht totdat iemand goed te keuren van de wijziging.
    
    ![Pagina voor goedkeuring verzenden](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Een pagina goedkeuren

Fiatteurs ontvangt een e-mail wanneer er sprake is van een pagina-aanvraag voor goedkeuring. Ze kunnen de aanvragen rechtstreeks in het e-mailbericht goedkeuren (als hun e-mailclient bruikbare berichten ondersteunt) of open de pagina in de e-mail om te controleren en vervolgens goedkeuren de pagina in SharePoint.

## <a name="customize-page-approval-flows"></a>Goedkeuringsstromen pagina aanpassen

Omdat Microsoft Flow-pagina goedkeuringen achter de schermen gebruiken, is de pagina goedkeuringsstroom beschikbaar voor site-eigenaren te wijzigen en toevoegen van een aangepaste bedrijfslogica in de stroom. Als u wilt de stroom wijzigen, de eigenaar van de site kunt selecteren **stromen** en selecteer vervolgens **Zie uw stromen** in de bibliotheek pagina's te vinden van de pagina goedkeuringsstroom.

## <a name="learn-more"></a>Meer informatie

- [Pagina goedkeuringsstroom](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Pagina goedkeuring configureren](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
