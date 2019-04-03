---
title: Markdown gebruiken om Microsoft Flow-goedkeuringen op te maken | Microsoft Docs
description: Leer hoe u met Markdown Microsoft Flow-goedkeuringsaanvragen kunt opmaken.
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
ms.openlocfilehash: 7611ccb8bba9f2647402df46753de284016d7cd4
ms.sourcegitcommit: 014f64bcc4aed27794d5c7efc2eca241d271518e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/29/2019
ms.locfileid: "58656126"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Markdown gebruiken in Microsoft Flow-goedkeuringsaanvragen

In dit artikel leert u hoe u de [Markdown](https://en.wikipedia.org/wiki/Markdown)-syntaxis kunt gebruiken om opmaak en tabellen toe te voegen aan uw goedkeuringsaanvragen.

## <a name="headers"></a>Headers

Structureer uw opmerkingen met behulp van headers. Headers zorgen voor een onderverdeling van langere opmerkingen, waardoor ze gemakkelijker te lezen zijn.

Begin een regel met een hash-teken `#` om een kop in te stellen. Orden uw opmerkingen met subkoppen door een regel met extra hash-tekens te laten beginnen, bijvoorbeeld `####`. Er worden maximaal zes niveaus voor koppen ondersteund.

**Voorbeeld:**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Resultaat:**

![Stroom exporteren](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Alinea's en regeleinden

Maak uw tekst gemakkelijker te lezen door deze op te splitsen met alinea's of regeleinden. Voer twee spaties in vóór het regeleinde om met een nieuwe alinea te beginnen of voer twee regeleinden achter elkaar in om met een nieuwe alinea te beginnen.   
   
**Voorbeeld**

Voeg regels tussen uw tekst in met behulp van de Enter-toets.
Dat maakt de tekst overzichtelijker en gemakkelijker te lezen.

**Resultaat:**   
Voeg regels tussen uw tekst in met behulp van de Enter-toets.      
Dat maakt de tekst overzichtelijker en gemakkelijker te lezen.


**Voorbeeld 2**

Voeg twee spaties toe vóór het einde van de regel (spatie, spatie).     
Hiermee wordt ruimte tussen de alinea's gecreëerd.

**Resultaat:**  
Voeg twee spaties toe vóór het einde van de regel.   

Hiermee wordt ruimte tussen de alinea's gecreëerd.
  

## <a name="lists"></a>Lijsten

Deel verwante items in met lijsten. U kunt geordende lijsten met getallen of ongeordende lijsten met alleen opsommingstekens toevoegen.

Geordende lijsten beginnen met een getal gevolgd door een punt voor elk lijstitem. Niet-geordende lijsten beginnen met een `*`. Begin elk lijstitem op een nieuwe regel. Voer in een Markdown-bestand of -widget twee spaties vóór het regeleinde toe om met een nieuwe alinea te beginnen of voer twee regeleinden achter elkaar in om met een nieuwe alinea te beginnen.   

### <a name="ordered-or-numbered-lists"></a>Geordende of genummerde lijsten

**Voorbeeld:**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Resultaat:**

1. Eerste item.
2. Tweede item.
3. Derde item.

### <a name="bullet-lists"></a>Lijsten met opsommingstekens

**Voorbeeld:**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Resultaat:**

- Item 1
- Item 2
- Item 3

### <a name="nested-lists"></a>Geneste lijsten

**Voorbeeld:**
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

**Resultaat:**  

1. Eerste item.

    - Item 1
    - Item 2
    - Item 3
2. Tweede item.
    - Genest item 1
    - Genest item 2
    - Genest item 3


## <a name="links"></a>Koppelingen

HTTP- en HTTPS-URL's worden automatisch opgemaakt als koppelingen. 

U kunt teksthyperlinks instellen voor uw URL met behulp van de syntaxis van de standaard Markdown-koppeling:

```Markdown
[Link Text](Link URL)
```

**Voorbeeld:**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**Resultaat:**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>Ankerkoppelingen

Anker-id's worden toegewezen aan alle koppen die in HTML-indeling worden weergegeven. De id is de koptekst met de spaties vervangen door streepjes (-) en alles in kleine letters.

**Voorbeeld:**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Resultaat:**

De syntaxis voor een ankerkoppeling naar een sectie...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
De id bevat alleen kleine letters en de koppeling is hoofdlettergevoelig. Zorg er dus voor dat u kleine letters gebruikt, ook als in de kop zelf gebruik wordt gemaakt van hoofdletters.


## <a name="tables"></a>Tabellen

Deel gestructureerde gegevens in met tabellen. 

- Geef elke tabelrij een eigen regel 
- Scheid tabelcellen van elkaar met het sluisteken `|` 
- De eerste twee regels van een tabel stellen de kolomkoppen en de uitlijning van elementen in de tabel in
- Gebruik dubbele punten (`:`) om onderscheid te maken tussen koptekst en hoofdtekst van tabellen om kolomuitlijning op te geven (links, midden, rechts) 
- Gebruik de HTML-tag voor eindes (`<br/>`) (werkt binnen een Wiki maar nergens anders) om een nieuwe regel te beginnen  
- Let erop dat u elke rij afsluit met een CR of LF. 

**Voorbeeld:**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Resultaat:**  

| Kop 1 | Kop 2 | Kop 3 |  
|-----------|:---------:|-----------:|  
| Cel A1 | Cel A2 | Cel A3 |  
| Cel B1 | Cel B2 | Cel B3<br/>tweede tekstregel |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Nadruk (vet, cursief, doorhalen)  

U kunt tekst benadrukken door gebruik te maken van vet, cursief of doorhaling: 
- Cursief toepassen: plaats sterretjes `*` of onderstrepingstekens `_` rondom de tekst   
- Vet toepassen: plaats een dubbel sterretje `**` rondom de tekst.    
- Doorhaling toepassen: plaats een dubbele tilde `~~` rondom de tekst.   

Combineer deze elementen om tekst extra te benadrukken.    

**Voorbeeld:**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Resultaat:**

Gebruik _nadruk_ in opmerkingen om een **krachtige** mening en <s>correcties</s>  aan te geven  
**_Vette, cursieve tekst_**   
**~~Vette, doorgehaalde tekst~~**  


## <a name="special-characters"></a>Speciale tekens

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Syntaxis</th>
<th width="350px">Voorbeeld/opmerkingen</th>
</tr>



<tr>
<td>
<p>Als u een van de volgende tekens wilt invoegen, moet u deze vooraf laten gaan door een backslash:</p>

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
<td>Enkele voorbeelden van het invoegen van speciale tekens
<p>Voer ```\\``` in voor \\ </p>
<p>Voer ```\_``` in voor _ </p>
<p>Voer ```\#``` in voor \# </p>
<p>Voer ```\(``` in voor \( </p>
<p>Voer ```\.``` in voor \. </p>
<p>Voer ```\!``` in voor \! </p>
</td>
</tr>

</tbody>
</table>
