---
title: Stomen uitvoeren op basis van een schema | Microsoft Docs
description: U kunt terugkerende taken automatiseren door stromen op basis van een schema uit te voeren, bijvoorbeeld elke dag of elk uur.
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
ms.date: 09/14/2017
ms.author: stepsic
ms.openlocfilehash: 1c36abb44be31795e7d458628cc7ec7483187f49
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="run-flows-on-a-schedule"></a>Stromen op basis van een schema uitvoeren
Een stroom maken waarmee een of meer taken worden uitgevoerd (zoals het verzenden van een rapport per e-mail):

* eenmaal per dag, elk uur of elke minuut
* op een datum die u opgeeft
* na een aantal dagen, uren of minuten dat u opgeeft

## <a name="create-a-recurring-flow"></a>Een terugkerende stroom maken
1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com) en selecteer vervolgens **Mijn stromen** in de bovenste navigatiebalk.
   
    ![De optie Mijn stromen](./media/run-tasks-on-a-schedule/create-flow.png)
2. Selecteer **Maken van lege**.
   
    ![Een volledig nieuwe stroom maken](./media/run-tasks-on-a-schedule/create-from-blank.png)
3. Typ **Terugkeerpatroon** in het vak **Alle connectors en triggers doorzoeken** en selecteer vervolgens **Schema: terugkeerpatroon**.
   
    ![Trigger voor terugkeerpatroon vinden](./media/run-tasks-on-a-schedule/select-recurrence.png)
4. Geef in het dialoogvenster **Terugkeerpatroon** op hoe vaak de stroom moet worden uitgevoerd.
   
    Geef bijvoorbeeld **2** op bij **Interval** en **Week** bij **Frequentie** als u de stroom elke twee weken wilt uitvoeren.
   
    ![Terugkeerpatroon opgeven](./media/run-tasks-on-a-schedule/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Geavanceerde opties opgeven
1. Volg de stappen in de vorige sectie en selecteer vervolgens **Geavanceerde opties weergeven**.
   
    **Opmerking**: Deze opties veranderen op basis van de waarden voor **Interval** en **Frequentie**. Als uw scherm niet overeenkomt met de onderstaande afbeelding, controleert u of **Interval** en **Frequentie** zijn ingesteld op dezelfde waarden als in de afbeelding.
2. Selecteer een **tijdzone** om op te geven of de **begintijd** uit een lokale tijdzone komt, een UTC-tijd (Universal Coordinated Time) is, enzovoort.
3. Geef een **begintijd** op in deze notatie:
   <br>JJJJ-MM-DDTHH:MM:SSZ
4. Als u **Dag** hebt gekozen bij **Frequentie**, geeft u de tijd van de dag op wanneer de stroom moet worden uitgevoerd.
5. Als u **Week** hebt opgegeven bij **Frequentie**, geeft u de dag of dagen van de week op waarop de stroom moet worden uitgevoerd en de tijd of tijden van de dag waarop de stroom moet worden uitgevoerd.
   
    Neem bijvoorbeeld de weergegeven opties over om in te stellen dat een stroom niet eerder start dan twaalf uur 's middags (Pacific-tijd) op maandag 1 januari 2018 en elke twee weken op dinsdag om 17:30 (Pacific-tijd) wordt uitgevoerd.
   
    ![Geavanceerde opties opgeven](./media/run-tasks-on-a-schedule/advanced-options.png)
6. Voeg de acties toe die met de stroom moeten worden uitgevoerd, zoals u kunt lezen in [Een volledig nieuwe stroom maken](get-started-logic-flow.md).

## <a name="delay-a-flow"></a>Een stroom vertragen
1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com) en selecteer vervolgens **Mijn stromen** in de bovenste navigatiebalk.
   
    ![Een volledig nieuwe stroom maken](./media/run-tasks-on-a-schedule/create-flow.png)
2. Selecteer **Maken van lege**.
   
    ![Een volledig nieuwe stroom maken](./media/run-tasks-on-a-schedule/create-from-blank.png)
3. Geef een gebeurtenis op, zoals wordt beschreven in [Een volledig nieuwe stroom maken](get-started-logic-flow.md).
4. Selecteer de knop **Nieuwe stap** en vervolgens **Een actie toevoegen**.
   
    ![Optie voor het toevoegen van een actie aan een stroom](./media/run-tasks-on-a-schedule/add-action.png)
5. Ga op een van de volgende manieren te werk in de lijst met acties:
   
   * Selecteer **Vertraging**, en geef een waarde op voor **Aantal** en **Eenheid**, zoals seconde, minuut of uur.
   * Selecteer **Uitstellen tot** en geef een datum op in deze notatie.<br>JJJJ-MM-DDTHH:MM:SSZ
     
     ![Een vertraging toevoegen](./media/run-tasks-on-a-schedule/add-delay.png)
     ![Een vertraging opgeven in tijdseenheden](./media/run-tasks-on-a-schedule/delay.png)
     ![Vertraging tot een bepaald moment opgeven](./media/run-tasks-on-a-schedule/delay-until.png)

