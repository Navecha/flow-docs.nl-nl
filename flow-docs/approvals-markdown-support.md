---
title: Prijs verlaging gebruiken om Microsoft Flow goed keuringen op te maken | Microsoft Docs
description: Meer informatie over het gebruik van korting om Microsoft Flow goedkeurings aanvragen in te delen.
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: kfile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/23/2018
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b82ac7c53c8c018b5e61011e4c1d8b9cdabe9747
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545302"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Prijs verlaging gebruiken in Microsoft Flow goedkeurings aanvragen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

In dit artikel leert u hoe u de syntaxis voor [korting](https://en.wikipedia.org/wiki/Markdown) kunt gebruiken om uitgebreide opmaak en tabellen toe te voegen aan uw goedkeurings aanvragen.

## <a name="headers"></a>koppen

Structureer uw opmerkingen met behulp van kopteksten. Headers segmenteert meer opmerkingen, waardoor ze gemakkelijker te lezen zijn.

Start een regel met een hash-teken `#` een kop in te stellen. Organiseer uw opmerkingen met subkoppen door een regel te beginnen met extra hash-tekens, bijvoorbeeld `####`. Er worden Maxi maal zes niveaus van koppen ondersteund.

**Hierbij**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Daardoor**

![Stroom exporteren](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Alinea's en regel einden

Uw tekst gemakkelijker te lezen maken door deze te splitsen met alinea's of regel einden. Voer twee spaties vóór het regel einde in om een nieuwe alinea te beginnen of Voer twee regel einden opeenvolgend in om een nieuwe alinea te beginnen.   
   
**Hierbij**

Voeg regels toe tussen uw tekst met de Enter-toets.
Hiermee wordt uw tekst beter en eenvoudiger te lezen.

**Resultaat:**    
Voeg regels toe tussen uw tekst met de Enter-toets.      
Hiermee wordt uw tekst beter en eenvoudiger te lezen.


**Voor beeld 2**

Voeg twee spaties toe vóór het einde van de regel. (spatie, spatie)     
Hiermee voegt u ruimte tussen alinea's toe.

**Daardoor**  
Voeg twee spaties toe vóór het einde van de regel.   

Hiermee voegt u ruimte tussen alinea's toe.
  

## <a name="lists"></a>Certificaatintrekkingslijst

Gerelateerde items ordenen met lijsten. U kunt geordende lijsten met getallen of ongeordende lijsten toevoegen met alleen opsommings tekens.

Geordende lijsten beginnen met een getal gevolgd door een punt voor elk lijst item. Niet-geordende lijsten beginnen met een `*`. Begin elk lijst item op een nieuwe regel. Voer in een bestand of widget van een afkorting twee spaties vóór het regel einde in om een nieuwe alinea te beginnen of Voer twee regel einden opeenvolgend in om een nieuwe alinea te beginnen.   

### <a name="ordered-or-numbered-lists"></a>Geordende of genummerde lijsten

**Hierbij**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Daardoor**

1. Eerste item.
2. Tweede item.
3. Derde item.

### <a name="bullet-lists"></a>Lijst met opsommings tekens

**Hierbij**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Daardoor**

- Item 1
- Item 2
- Item 3

### <a name="nested-lists"></a>Geneste lijsten

**Hierbij**
<pre>

1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3

</pre>

**Daardoor**  

1. Eerste item.

    - Item 1
    - Item 2
    - Item 3
2. Tweede item.
    - Genest item 1
    - Genest item 2
    - Genest item 3


## <a name="links"></a>koppelen

HTTP-en HTTPS-Url's worden automatisch opgemaakt als koppelingen. 

U kunt tekst hyperlinks instellen voor uw URL met behulp van de standaard syntaxis voor de prijs opvolgende koppeling:

```Markdown
[Link Text](Link URL)
```

**Hierbij**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**Daardoor**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>Anker koppelingen

Anker-Id's worden toegewezen aan alle koppen wanneer ze worden gerenderd als HTML. De ID is de koptekst, waarbij de spaties worden vervangen door streepjes (-) en alle kleine letters.

**Hierbij**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Daardoor**

De syntaxis voor een anker koppeling naar een sectie...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
De ID is allemaal in kleine letters en de koppeling is hoofdletter gevoelig. Zorg er dus voor dat u kleine letters gebruikt, ook al gebruikt de kop zelf hoofd letters.


## <a name="tables"></a>Maateenheidgroeptabellen

Gestructureerde gegevens ordenen met tabellen. 

- Plaats elke tabelrij op een eigen regel 
- Afzonderlijke tabel cellen met behulp van het sluis teken `|` 
- De eerste twee regels van een tabel stellen de kolom koppen en de uitlijning van elementen in de tabel in
- Gebruik dubbele punten (`:`) bij het delen van de koptekst en de hoofd tekst van tabellen om de kolom uitlijning op te geven (links, midden, rechts) 
- Als u een nieuwe regel wilt starten, gebruikt u de HTML-code voor opmaak (`<br/>`) (werkt in een wiki, maar niet elders)  
- Zorg ervoor dat u elke rij met een CR of LF beëindigt. 

**Hierbij**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Daardoor**  

| Kop 1 | Kop 2 | Kop 3 |  
|-----------|:---------:|-----------:|  
| Cel a1 | Cel a2 | Cel A3 |  
| Cel B1 | Cel B2 | Cel B3<br/>tweede regel tekst |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Nadruk (vet, cursief, doorhaling)  

U kunt tekst benadrukken door vetgedrukte, cursieve of doorgehaalde tekens toe te passen: 
- Als u cursief wilt Toep assen: rond de tekst met een asterisk `*` of een onderstrepings teken `_`   
- Vet Toep assen: plaats de tekst met een dubbele asterisk `**`.    
- Door halen Toep assen: rondom de tekst met dubbele tilde-tekens `~~`.   

Combi neer deze elementen om meerdere nadruk op tekst toe te passen.    

**Hierbij**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Daardoor**

Gebruik _nadruk_ in opmerkingen om **sterke** adviezen en uitpunt <s>correcties</s>   
**_Vet, cursief tekst_**    
**~~Vetgedrukte tekst door halen~~**  


## <a name="special-characters"></a>Speciale tekens

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Syntaxis</th>
<th width="350px">Voor beeld/notities</th>
</tr>



<tr>
<td>
<p>Als u een van de volgende tekens wilt invoegen, plaatst u een voor voegsel met een back slash:</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>Enkele voor beelden van het invoegen van speciale tekens
<p>```\\``` invoeren om \\ op te halen </p>
<p>Voer ```\_``` in om _ te krijgen </p>
<p>```\#``` invoeren om \# op te halen </p>
<p>```\(``` invoeren om \( op te halen </p>
<p>```\.``` invoeren om \. op te halen </p>
<p>```\!``` invoeren om \! op te halen </p>
</td>
</tr>

</tbody>
</table>
