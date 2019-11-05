---
title: Meer informatie over het beheren van on-premises gegevens gateways | Microsoft Docs
description: Een on-premises gegevens gateway in Microsoft Flow weer geven en installeren.
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
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3991e739178f86bbea3ae1b68b9d3337c42b4727
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547670"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Een on-premises gegevens gateway beheren in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Een on-premises gegevens gateway installeren en beheren om verschillende Cloud-apps veilig te integreren met uw on-premises gegevens en apps via Microsoft Flow.

Met een gateway kunt u verbinding maken met on-premises gegevens via deze verbindingen:

* Apache Impala
* Aangepaste connectors die u maakt
* DB2
* Bestands systeem
* Http met Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* Point
* SQL Server
* Teradata (preview-versie)

> [!IMPORTANT]
> Micro soft share point-gegevens gateways bieden nu ondersteuning voor HTTP-en HTTPS-verkeer.

## <a name="prerequisites"></a>Vereisten

* De gebruikers naam en het wacht woord die u hebt gebruikt om u te [registreren](sign-up-sign-in.md) voor Microsoft flow.
* Beheerders machtigingen op een gateway.

  U hebt deze machtigingen standaard voor elke gateway die u installeert. Een beheerder van een andere gateway kan u ook deze machtigingen voor die gateway verlenen.
* Een licentie die ondersteuning biedt voor gateways. Zie de sectie ' connectiviteit ' van de [pagina met prijzen](https://flow.microsoft.com/pricing/)voor meer informatie.

> [!NOTE]
> U kunt een gateway en een on-premises verbinding alleen in uw [standaard omgeving](environments-overview-maker.md)maken.

## <a name="install-a-gateway"></a>Een gateway installeren

Als u een gateway wilt installeren, volgt u de stappen in [een on-premises gegevens gateway installeren](/data-integration/gateway/service-gateway-install). Installeer de gateway in de standaard modus omdat de _on-premises gegevens gateway (persoonlijke modus)_ alleen beschikbaar is voor Power bi.

## <a name="view-your-gateways"></a>Uw gateways weer geven

Selecteer in de rechter bovenhoek van de [Microsoft flow website](https://flow.microsoft.com)het tandwiel pictogram en selecteer vervolgens **gateways**.

![Gateway onder beheren][1]

> [!NOTE]
> Als u toegang tot een gateway in PowerApps hebt gemaakt of gekregen, wordt die gateway weer gegeven in de lijst **mijn gateways** in Microsoft flow.

## <a name="cluster-your-gateways"></a>Uw gateways clusteren

U kunt [clusters met een hoge Beschik baarheid van on-premises gegevens gateways](/data-integration/gateway/service-gateway-high-availability-clusters) maken om afzonderlijke toegangs punten te voor komen bij het openen van on-premises gegevens bronnen.

Microsoft Flow maakt standaard gebruik van de primaire gateway in het cluster. Als de primaire gateway niet beschikbaar is, wordt de service overgeschakeld naar de volgende gateway in het cluster, enzovoort.

Zodra u een gateway cluster hebt ingesteld, kunt u toestaan dat verkeer over alle gateways in het cluster wordt gedistribueerd.

Volg deze stappen om uw verkeer over uw gateways te verdelen:

1. Selecteer **gegevens** op de navigatie balk aan de linkerkant.
1. Selecteer **gateways**.
1. Selecteer een van uw gateways.
1. Selecteer **distributie aanvragen op alle actieve gateways in dit cluster**.
1. Selecteer **Toep assen** om uw wijzigingen op te slaan.

Zie [gateways begrijpen](gateway-reference.md)voor meer informatie.

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
