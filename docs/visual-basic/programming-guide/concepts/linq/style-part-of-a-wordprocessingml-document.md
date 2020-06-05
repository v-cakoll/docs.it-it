---
title: Parte relativa allo stile di un document2 WordprocessingML
ms.date: 07/20/2015
ms.assetid: 292cc094-9483-4192-ac3b-a5dc51fbac12
ms.openlocfilehash: 0692a9cc3a2ce51851d1b551d49f112fc5e4e41a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406755"
---
# <a name="style-part-of-a-wordprocessingml-document"></a><span data-ttu-id="fead6-102">Parte relativa allo stile di un documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="fead6-102">Style Part of a WordprocessingML Document</span></span>
<span data-ttu-id="fead6-103">In questo argomento è illustrato un esempio della parte di stile del documento WordprocessingML di Office Open XML.</span><span class="sxs-lookup"><span data-stu-id="fead6-103">This topic shows an example of the style part of the Office Open XML WordprocessingML document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fead6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fead6-104">Example</span></span>  
 <span data-ttu-id="fead6-105">Nell'esempio seguente è riportato il codice XML che costituisce la parte di stile di un documento WordprocessingML di Office Open XML.</span><span class="sxs-lookup"><span data-stu-id="fead6-105">The following example is the XML that makes up the style part of an Office Open XML WordprocessingML document.</span></span>  
  
 <span data-ttu-id="fead6-106">Lo stile del paragrafo predefinito ha un elemento con il seguente tag di apertura:</span><span class="sxs-lookup"><span data-stu-id="fead6-106">The default paragraph style has an element with the following opening tag:</span></span>  
  
```xml  
<w:style w:type="paragraph" w:default="1" w:styleId="Normal">  
```  
  
 <span data-ttu-id="fead6-107">Queste informazioni sono necessarie quando si scrive la query per trovare l'identificatore di stile predefinito, in modo che la query possa identificare gli stili dei paragrafi caratterizzati dallo stile predefinito.</span><span class="sxs-lookup"><span data-stu-id="fead6-107">You need to know this information when you write the query to find the default style identifier, so that the query can identify the style of paragraphs that have the default style.</span></span>  
  
 <span data-ttu-id="fead6-108">Si noti che questi documenti sono estremamente semplici rispetto ai tipici documenti generati con Word.</span><span class="sxs-lookup"><span data-stu-id="fead6-108">Note that these documents are very simple when compared to typical documents that Microsoft Word generates.</span></span> <span data-ttu-id="fead6-109">In molti casi, in Word vengono salvate molte informazioni aggiuntive, formattazione aggiuntiva e metadati.</span><span class="sxs-lookup"><span data-stu-id="fead6-109">In many cases, Word saves a great deal of additional information, additional formatting and metadata.</span></span> <span data-ttu-id="fead6-110">Inoltre, in Word le righe non sono formattate per essere facilmente leggibili, come in questo esempio, ma il codice XML viene salvato senza rientro.</span><span class="sxs-lookup"><span data-stu-id="fead6-110">Furthermore, Word does not format the lines to be easily readable as in this example; instead, the XML is saved without indentation.</span></span> <span data-ttu-id="fead6-111">Tuttavia, tutti i documenti WordprocessingML condividono la stessa forma XML di base.</span><span class="sxs-lookup"><span data-stu-id="fead6-111">However, all WordprocessingML documents share the same basic XML shape.</span></span> <span data-ttu-id="fead6-112">Per questo motivo, le query presentate in questa esercitazione potranno essere usate anche con documenti più complicati.</span><span class="sxs-lookup"><span data-stu-id="fead6-112">Because of this, the queries presented in this tutorial will work with more complicated documents.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<w:styles  
    xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
    xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  <w:docDefaults>  
    <w:rPrDefault>  
      <w:rPr>  
        <w:rFonts  
            w:ascii="Times New Roman"  
            w:eastAsia="Times New Roman"  
            w:hAnsi="Times New Roman"  
            w:cs="Times New Roman" />  
        <w:sz w:val="22" />  
        <w:szCs w:val="22" />  
        <w:lang w:val="en-US" w:eastAsia="en-US" w:bidi="ar-SA" />  
      </w:rPr>  
    </w:rPrDefault>  
    <w:pPrDefault />  
  </w:docDefaults>  
  <w:style w:type="paragraph" w:default="1" w:styleId="Normal">  
    <w:name w:val="Normal" />  
    <w:qFormat />  
    <w:rPr>  
      <w:sz w:val="24" />  
      <w:szCs w:val="24" />  
    </w:rPr>  
  </w:style>  
  <w:style w:type="paragraph" w:styleId="Heading1">  
    <w:name w:val="heading 1" />  
    <w:basedOn w:val="Normal" />  
    <w:next w:val="Normal" />  
    <w:link w:val="Heading1Char" />  
    <w:uiPriority w:val="99" />  
    <w:qFormat />  
    <w:rsid w:val="006027C7" />  
    <w:pPr>  
      <w:keepNext />  
      <w:spacing w:before="240" w:after="60" />  
      <w:outlineLvl w:val="0" />  
    </w:pPr>  
    <w:rPr>  
      <w:rFonts w:ascii="Arial" w:hAnsi="Arial" w:cs="Arial" />  
      <w:b />  
      <w:bCs />  
      <w:kern w:val="32" />  
      <w:sz w:val="32" />  
      <w:szCs w:val="32" />  
    </w:rPr>  
  </w:style>  
  <w:style w:type="character" w:default="1" w:styleId="DefaultParagraphFont">  
    <w:name w:val="Default Paragraph Font" />  
    <w:uiPriority w:val="99" />  
    <w:semiHidden />  
  </w:style>  
  <w:style w:type="table" w:default="1" w:styleId="TableNormal">  
    <w:name w:val="Normal Table" />  
    <w:uiPriority w:val="99" />  
    <w:semiHidden />  
    <w:unhideWhenUsed />  
    <w:qFormat />  
    <w:tblPr>  
      <w:tblInd w:w="0" w:type="dxa" />  
      <w:tblCellMar>  
        <w:top w:w="0" w:type="dxa" />  
        <w:left w:w="108" w:type="dxa" />  
        <w:bottom w:w="0" w:type="dxa" />  
        <w:right w:w="108" w:type="dxa" />  
      </w:tblCellMar>  
    </w:tblPr>  
  </w:style>  
  <w:style w:type="numbering" w:default="1" w:styleId="NoList">  
    <w:name w:val="No List" />  
    <w:uiPriority w:val="99" />  
    <w:semiHidden />  
    <w:unhideWhenUsed />  
  </w:style>  
  <w:style w:type="character" w:customStyle="1" w:styleId="Heading1Char">  
    <w:name w:val="Heading 1 Char" />  
    <w:basedOn w:val="DefaultParagraphFont" />  
    <w:link w:val="Heading1" />  
    <w:uiPriority w:val="9" />  
    <w:rsid w:val="009765E3" />  
    <w:rPr>  
      <w:rFonts  
          w:asciiTheme="majorHAnsi"  
          w:eastAsiaTheme="majorEastAsia"  
          w:hAnsiTheme="majorHAnsi"  
          w:cstheme="majorBidi" />  
      <w:b />  
      <w:bCs />  
      <w:kern w:val="32" />  
      <w:sz w:val="32" />  
      <w:szCs w:val="32" />  
    </w:rPr>  
  </w:style>  
  <w:style w:type="paragraph" w:customStyle="1" w:styleId="Code">  
    <w:name w:val="Code" />  
    <w:aliases w:val="c" />  
    <w:uiPriority w:val="99" />  
    <w:rsid w:val="006027C7" />  
    <w:pPr>  
      <w:spacing w:after="60" w:line="300" w:lineRule="exact" />  
    </w:pPr>  
    <w:rPr>  
      <w:rFonts w:ascii="Courier New" w:hAnsi="Courier New" />  
      <w:noProof />  
      <w:color w:val="000080" />  
      <w:sz w:val="20" />  
      <w:szCs w:val="20" />  
    </w:rPr>  
  </w:style>  
</w:styles>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fead6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fead6-113">See also</span></span>

- [<span data-ttu-id="fead6-114">Informazioni dettagliate sui documenti WordprocessingML di Office Open XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fead6-114">Details of Office Open XML WordprocessingML Documents (Visual Basic)</span></span>](details-of-office-open-xml-wordprocessingml-documents.md)
