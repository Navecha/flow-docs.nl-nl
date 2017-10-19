---
title: Meer informatie over het beheren van on-premises gegevensgateways | Microsoft Docs
description: Een on-premises gegevensgateway in Microsoft Flow weergeven en installeren
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: deonhe
ms.openlocfilehash: 41f5d40ca2ad5fcce3a7967beef7104dd532b1d8
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
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
> Microsoft SharePoint-gegevensgateways ondersteunen wel HTTP-verkeer, maar geen HTTPS-verkeer.
> 
> 

## <a name="prerequisites"></a>Vereisten
* De gebruikersnaam die en het wachtwoord dat u gebruikt om u [aan te melden](sign-up-sign-in.md) bij Microsoft Flow.
* Beheerdersbevoegdheden op een gateway.
  
  Hebt u deze machtigingen standaard voor elke gateway die u installeert en een beheerder van een andere gateway kan u deze machtigingen verlenen voor die gateway.
* Een licentie die ondersteuning biedt voor gateways. Zie de sectie 'Connectiviteit' van de [pagina met prijzen](https://flow.microsoft.com/pricing/) voor meer informatie.
* U kunt een gateway en een on-premises verbinding alleen maken in uw [standaardomgeving](environments-overview-maker.md).

## <a name="view-your-gateways"></a>Uw gateways weergeven
Klik of tik in de rechterbovenhoek van de [Microsoft Flow-website](https://flow.microsoft.com) op het tandwielpictogram en klik of tik vervolgens op **Gateways**.

![Gateway onder beheer][1]

**Opmerking**: als u een gateway hebt gemaakt in PowerApps of toegang tot een dergelijke gateway hebt gekregen, wordt die gateway weergegeven in de lijst **Mijn gateways** in Microsoft Flow.

## <a name="install-a-gateway"></a>Een gateway installeren
1. Download de [wizard voor gatewayinstallatie](http://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).
   
    U kunt deze wizard ook downloaden door op het tandwielpictogram in de rechterbovenhoek van de [Microsoft Flow-website](https://flow.microsoft.com) te klikken of tikken, op **Gateways** te klikken of tikken en vervolgens op **Gateway maken** te klikken of tikken.
   
    ![Installatie van de gateway][2]
2. Voer de wizard uit en geef de referenties op waarmee u zich ook bij Microsoft Flow aanmeldt.
   
    Als u de gateway hebt geregistreerd en geconfigureerd, wordt deze weergegeven in de lijst **Mijn gateways** in Microsoft Flow.

Zie [Gateways](gateway-reference.md) voor meer informatie.

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
[2]: ./media/manage-gateway/list-gateways.png
