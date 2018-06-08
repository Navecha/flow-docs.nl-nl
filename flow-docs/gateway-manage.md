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
ms.openlocfilehash: 642cf26110a09404c8bd453f894540963904ebda
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "29057402"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Een on-premises gegevensgateway beheren in Microsoft Flow

U kunt een on-premises gegevensgateway installeren en beheren zodat u verschillende cloud-apps via Microsoft Flow veilig kunt integreren met uw on-premises gegevens en apps.

Met een gateway kunt u verbinding maken met on-premises gegevens via de volgende verbindingen:

* SharePoint
* SQL Server
* Oracle
* Informix
* Bestandssysteem
* DB2

> [!IMPORTANT]
> Microsoft SharePoint-gegevensgateways ondersteunen nu zowel HTTP- als HTTPS-verkeer.


## <a name="prerequisites"></a>Vereisten

* De gebruikersnaam die en het wachtwoord dat u gebruikt om u [aan te melden](sign-up-sign-in.md) bij Microsoft Flow.
* Beheerdersbevoegdheden op een gateway.

  Standaard hebt u deze machtigingen voor elke gateway die u installeert. Een beheerder van een andere gateway kan u deze machtigingen ook verlenen voor die gateway.
* Een licentie die ondersteuning biedt voor gateways. Zie de sectie 'Connectiviteit' van de [pagina met prijzen](https://flow.microsoft.com/pricing/) voor meer informatie.

> [!NOTE]
> U kunt een gateway en een on-premises verbinding alleen maken in uw [standaardomgeving](environments-overview-maker.md).



## <a name="view-your-gateways"></a>Uw gateways weergeven

Selecteer rechtsboven in de hoek van de [Microsoft Flow-website](https://flow.microsoft.com) het tandwielpictogram en selecteer vervolgens **Gateways**.

![Gateway onder beheer][1]

> [!NOTE]
> Als u een gateway hebt gemaakt in PowerApps of toegang tot een dergelijke gateway hebt gekregen, wordt die gateway weergegeven in de lijst **Mijn gateways** in Microsoft Flow.



## <a name="install-a-gateway"></a>Een gateway installeren

1. Download de [wizard voor gatewayinstallatie](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).

1. Voer de wizard uit en geef de referenties op waarmee u zich ook bij Microsoft Flow aanmeldt.

    Als u de gateway hebt geregistreerd en geconfigureerd, wordt deze weergegeven in de lijst **Gateways** in Microsoft Flow.

Zie [Gateways](gateway-reference.md) voor meer informatie.

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
