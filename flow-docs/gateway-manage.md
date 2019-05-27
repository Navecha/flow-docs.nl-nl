---
title: Meer informatie over het beheren van on-premises gegevensgateways | Microsoft Docs
description: Een on-premises gegevensgateway in Microsoft Flow weergeven en installeren
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
ms.date: 02/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b8b14f720736a60b04cbd9ae23dec5c0524ff03c
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "65054071"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Een on-premises gegevensgateway beheren in Microsoft Flow

U kunt een on-premises gegevensgateway installeren en beheren zodat u verschillende cloud-apps via Microsoft Flow veilig kunt integreren met uw on-premises gegevens en apps.

Met een gateway kunt u verbinding maken met on-premises gegevens via de volgende verbindingen:

* Apache Impala
* Aangepaste connectors die u maakt
* DB2
* Bestandssysteem
* HTTP met Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (preview)

> [!IMPORTANT]
> Microsoft SharePoint-gegevensgateways ondersteunen nu zowel HTTP- als HTTPS-verkeer.

## <a name="prerequisites"></a>Vereisten

* De gebruikersnaam die en het wachtwoord dat u gebruikt om u [aan te melden](sign-up-sign-in.md) bij Microsoft Flow.
* Beheerdersbevoegdheden op een gateway.

  Standaard hebt u deze machtigingen voor elke gateway die u installeert. Een beheerder van een andere gateway kan u deze machtigingen ook verlenen voor die gateway.
* Een licentie die ondersteuning biedt voor gateways. Zie de sectie 'Connectiviteit' van de [pagina met prijzen](https://flow.microsoft.com/pricing/) voor meer informatie.

> [!NOTE]
> U kunt een gateway en een on-premises verbinding alleen maken in uw [standaardomgeving](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Een gateway installeren

1. Download de [wizard voor gatewayinstallatie](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).

1. Voer de wizard uit en geef de referenties op waarmee u zich ook bij Microsoft Flow aanmeldt.

    Als u de gateway hebt geregistreerd en geconfigureerd, wordt deze weergegeven in de lijst **Gateways** in Microsoft Flow.

## <a name="view-your-gateways"></a>Uw gateways weergeven

Selecteer rechtsboven in de hoek van de [Microsoft Flow-website](https://flow.microsoft.com) het tandwielpictogram en selecteer vervolgens **Gateways**.

![Gateway onder beheer][1]

> [!NOTE]
> Als u een gateway hebt gemaakt in PowerApps of toegang tot een dergelijke gateway hebt gekregen, wordt die gateway weergegeven in de lijst **Mijn gateways** in Microsoft Flow.


## <a name="cluster-your-gateways"></a>Uw gateways van cluster

U kunt maken *clusters met hoge beschikbaarheid van on-premises data gateway installaties* om te voorkomen dat single point of failure bij het openen van on-premises gegevensbronnen. 

Microsoft Flow maakt standaard gebruik van de primaire gateway in het cluster. Als de primaire gateway niet beschikbaar is, wordt de service schakelt over naar de volgende gateway in het cluster, enzovoort.

Wanneer u een gateway-cluster hebt ingesteld, kunt u verkeer wordt verdeeld over alle gateways in het cluster. 

Volg deze stappen voor het verkeer verdelen over uw gateways:

1. Selecteer **gegevens** op de navigatiebalk aan de linkerkant.
1. Selecteer **Gateways**.
1. Selecteer een van uw gateways.
1. Selecteer **aanvragen verdelen over alle actieve gateways in dit cluster**.
1. Selecteer **toepassen** uw wijzigingen op te slaan.


Zie [Gateways](gateway-reference.md) voor meer informatie.

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
