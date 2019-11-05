---
title: Stromen uitvoeren volgens een schema | Microsoft Docs
description: Automatiseer terugkerende taken door stromen uit te voeren op basis van een schema, bijvoorbeeld elke dag of elk uur.
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
ms.date: 09/14/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b737f416c927e7d7d8a7ea28ec81e268aa59b51d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548831"
---
# <a name="run-flows-on-a-schedule"></a>Stromen uitvoeren volgens een schema
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Een stroom maken waarmee een of meer taken worden uitgevoerd (zoals het verzenden van een rapport per e-mail):

* eenmaal per dag, uur of minuut
* op een datum die u opgeeft
* na een aantal dagen, uren of minuten dat u opgeeft

## <a name="create-a-recurring-flow"></a>Een terugkerende stroom maken
1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com)en selecteer vervolgens **mijn stromen** in de bovenste navigatie balk.
   
    ![De optie mijn stromen](./media/run-scheduled-tasks/create-flow.png)
2. Selecteer **leeg item maken**.
   
    ![Een lege stroom maken](./media/run-scheduled-tasks/create-from-blank.png)
3. Typ **terugkeer patroon**in het vak **alle connectors en triggers doorzoeken** en selecteer vervolgens **schema-terugkeer patroon**.
   
    ![Terugkeer patroon trigger zoeken](./media/run-scheduled-tasks/select-recurrence.png)
4. Geef in het dialoog venster **terugkeer patroon** op hoe vaak u de stroom wilt uitvoeren.
   
    Geef bijvoorbeeld **2** op onder **interval** en **week** onder **frequentie** als u wilt dat de stroom elke twee weken wordt uitgevoerd.
   
    ![Terugkeer patroon opgeven](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Geavanceerde opties opgeven
1. Volg de stappen in de vorige sectie en selecteer vervolgens **Geavanceerde opties weer geven**.
   
    **Opmerking**: deze opties worden gewijzigd op basis van de waarden waarvoor **interval** en **frequentie** zijn ingesteld. Als uw scherm niet overeenkomt met de onderstaande afbeelding, controleert u of het **interval** en de **frequentie** zijn ingesteld op dezelfde waarden die in de afbeelding worden weer gegeven.
2. Selecteer een **tijd zone** om op te geven of de **Start tijd** een lokale tijd zone, UTC (Universal Coordinated Time), enzovoort weerspiegelt.
3. Geef een **begin tijd** op in deze notatie:
   <br>JJJJ-MM-DDTUU: MM: SSZ
4. Als u **dag** onder **frequentie**hebt opgegeven, geeft u het tijdstip van de dag op waarop de stroom moet worden uitgevoerd.
5. Als u **week** onder **frequentie**hebt opgegeven, geeft u de dag of dagen van de week op waarop de stroom moet worden uitgevoerd en de tijd of tijden van de dag waarop de stroom moet worden uitgevoerd.
   
    Configureer bijvoorbeeld de opties zoals weer gegeven om een stroom te starten die niet eerder is dan 12:00 uur (Pacific Time) op maandag, 1 januari 2018, en voer deze elke twee weken uit op dinsdag om 5:30p (Pacific Time).
   
    ![Geavanceerde opties opgeven](./media/run-scheduled-tasks/advanced-options.png)
6. Voeg de actie of acties toe die u de stroom wilt laten uitvoeren, zoals wordt beschreven in [een volledig nieuwe stroom maken](get-started-logic-flow.md) .

## <a name="delay-a-flow"></a>Een stroom vertragen
1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com)en selecteer vervolgens **mijn stromen** in de bovenste navigatie balk.
   
    ![Een lege stroom maken](./media/run-scheduled-tasks/create-flow.png)
2. Selecteer **leeg item maken**.
   
    ![Een lege stroom maken](./media/run-scheduled-tasks/create-from-blank.png)
3. Geef een gebeurtenis [op als een volledig nieuwe stroom maken](get-started-logic-flow.md) beschrijft.
4. Selecteer **nieuwe stap**en selecteer vervolgens **een actie toevoegen**.
   
    ![Optie voor het toevoegen van een actie aan een stroom](./media/run-scheduled-tasks/add-action.png)
5. Voer een van de volgende handelingen uit in de lijst met acties:
   
   * Selecteer **vertraging**, geef een **aantal**op en geef een tijds **eenheid** op, zoals seconde, minuut of uur.
   * Selecteer **vertraging tot**en geef een datum op in deze notatie.<br>JJJJ-MM-DDTUU: MM: SSZ
     
     ![een vertraging toevoegen](./media/run-scheduled-tasks/add-delay.png)
     ![een vertraging opgeven in tijds eenheden](./media/run-scheduled-tasks/delay.png)
     ![een vertraging opgeven tot](./media/run-scheduled-tasks/delay-until.png)

## <a name="learn-more"></a>Meer informatie

Meer informatie over de [Geavanceerde opties](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) en hoe u deze kunt configureren.

