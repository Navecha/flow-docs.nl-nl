---
ms.openlocfilehash: bb5f08b2606b889a19de0167ef2825cd3428d069
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64463408"
---
In een vorig onderwerp hebt u gezien hoe u een goedkeuringsproces maakt voor tweets die zijn opgeslagen in een SharePoint-lijst.  In dit onderwerp ziet u hoe de ervaring eruitziet wanneer een goedkeurder een nieuwe goedkeuringsaanvraag ontvangt. 

## <a name="create-and-process-a-request"></a>Een aanvraag maken en verwerken
Eerst voegen we een item toe aan onze SharePoint-lijst. Vervolgens kunnen we een goedkeuringsaanvraag voor dit item verwerken.

1. Open de SharePoint-lijst **Contoso-tweets**, die is geconfigureerd in een vorig onderwerp.  Selecteer **Nieuw** om een nieuwe tweet te maken. 
   
    ![SharePoint-lijst](./media/learning-approval-request/sharepoint-list-home.png)
2. Voeg de volgende waarden toe aan de velden en selecteer **Opslaan**.
   
   * **Titel** - Aanbiedingen
   * **Inhoud tweet**: Bekijk de nieuwe productlijn van Contoso Flooring #ohsocontoso
   * **Datum tweet**: de datum van vandaag
     
     ![SharePoint - nieuw item](./media/learning-approval-request/sharepoint-new-tweet.png)
3. Selecteer in **Microsoft Flow** de optie **Mijn stromen**. 
4. Selecteer de stroom **Lijstitems op Twitter plaatsen na goedkeuring** die is geconfigureerd in het vorige onderwerp en selecteer de actieve stroom onder **UITVOERINGSGESCHIEDENIS**.
   
    ![Uitvoeringsgeschiedenis](./media/learning-approval-request/run-history.png)
5. Selecteer de trigger **Wanneer een nieuw item is gemaakt**. Controleer of de gegevens voor het lijstitem dat u zojuist hebt gemaakt, worden weergegeven.
   
    ![Stroomtrigger](./media/learning-approval-request/approval-flow.png)
6. Open in **Outlook** de geautomatiseerde goedkeuringse-mail in het Postvak IN en selecteer **Goedkeuren**. 
   
    ![Outlook-aanvraag](./media/learning-approval-request/outlook-mail.png)
7. Bekijk in het **Goedkeuringscentrum** de details van de aanvraag, voeg een opmerking toe en selecteer **Bevestigen**. 
   
    ![Goedkeuringscentrum](./media/learning-approval-request/approval-center.png)
8. Vernieuw in **SharePoint** de lijst **Contoso-tweets** en controleer of **Goedkeurigsstatus** is ingesteld op **Ja** en de ingevoerde opmerking wordt weergegeven. 
   
    ![SharePoint - lijst vernieuwen](./media/learning-approval-request/sharepoint-list-approved.png)

In dit onderwerp hebt u de ervaring gezien vanuit het perspectief van de goedkeurder: van het ontvangen van een e-mail met een goedkeuringsaanvraag tot het verwerken van de aanvraag in het Goedkeuringscentrum.

