---
title: Forma dei documenti WordprocessingML (C#)
ms.date: 07/20/2015
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
ms.openlocfilehash: 58c028fed465f45fdcf8f63f2119eb8e8b201e32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76732681"
---
# <a name="shape-of-wordprocessingml-documents-c"></a><span data-ttu-id="67db0-102">Forma dei documenti WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="67db0-102">Shape of WordprocessingML Documents (C#)</span></span>
<span data-ttu-id="67db0-103">In questo argomento viene descritta la forma XML di un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="67db0-103">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="67db0-104">Formati di Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="67db0-104">Microsoft Office Formats</span></span>  
 <span data-ttu-id="67db0-105">Il formato di file nativo per Microsoft Office System 2007 è Office Open XML (più comunemente, Open XML).</span><span class="sxs-lookup"><span data-stu-id="67db0-105">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="67db0-106">Open XML è un formato basato su XML conforme allo standard ECMA e attualmente in approvazione per gli standard ISO-IEC.</span><span class="sxs-lookup"><span data-stu-id="67db0-106">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="67db0-107">Il linguaggio di markup per i file di elaborazione testi all'interno di Open XML è denominato WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="67db0-107">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="67db0-108">In questa esercitazione vengono usati file di origine WordprocessingML come di input per gli esempi.</span><span class="sxs-lookup"><span data-stu-id="67db0-108">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="67db0-109">Se si usa Microsoft Office 2003, è possibile salvare i documenti nel formato Office Open XML se è stato installato Microsoft Office Compatibility Pack per formati di file di Word, Excel e PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="67db0-109">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="67db0-110">Forma dei documenti WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="67db0-110">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="67db0-111">Il primo aspetto da considerare è la forma dei documenti WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="67db0-111">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="67db0-112">Un documento WordprocessingML contiene un elemento corpo, denominato `w:body`, che contiene i paragrafi del documento.</span><span class="sxs-lookup"><span data-stu-id="67db0-112">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="67db0-113">Ogni paragrafo contiene una o più sequenze di testo, denominate `w:r`.</span><span class="sxs-lookup"><span data-stu-id="67db0-113">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="67db0-114">Ogni sequenza di testo contiene uno o più parti di testo, denominate `w:t`.</span><span class="sxs-lookup"><span data-stu-id="67db0-114">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="67db0-115">Di seguito è riportato un documento WordprocessingML molto semplice:</span><span class="sxs-lookup"><span data-stu-id="67db0-115">The following is a very simple WordprocessingML document:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<w:document  
xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
xmlns:o="urn:schemas-microsoft-com:office:office"  
xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
xmlns:v="urn:schemas-microsoft-com:vml"  
xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
xmlns:w10="urn:schemas-microsoft-com:office:word"  
xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is a paragraph.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is another paragraph.</w:t>  
      </w:r>  
    </w:p>  
  </w:body>  
</w:document>  
```  
  
 <span data-ttu-id="67db0-116">Questo documento contiene due paragrafi.</span><span class="sxs-lookup"><span data-stu-id="67db0-116">This document contains two paragraphs.</span></span> <span data-ttu-id="67db0-117">Entrambi contengono una sola sequenza di testo e ogni sequenza di testo contiene una sola parte di testo.</span><span class="sxs-lookup"><span data-stu-id="67db0-117">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="67db0-118">Il modo più semplice per visualizzare il contenuto di un documento WordprocessingML in formato XML consiste nel crearne uno usando Microsoft Word, salvarlo e quindi eseguire il programma seguente che stampa l'XML nella console.</span><span class="sxs-lookup"><span data-stu-id="67db0-118">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="67db0-119">In questo esempio vengono usate classi dell'assembly WindowsBase</span><span class="sxs-lookup"><span data-stu-id="67db0-119">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="67db0-120">e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="67db0-120">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
using (Package wdPackage = Package.Open("SampleDoc.docx", FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship relationship =  
        wdPackage  
        .GetRelationshipsByType(documentRelationshipType)  
        .FirstOrDefault();  
    if (relationship != null)  
    {  
        Uri documentUri =  
            PackUriHelper.ResolvePartUri(  
                new Uri("/", UriKind.Relative),  
                relationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Get the officeDocument part from the package.  
        //  Load the XML in the part into an XDocument instance.  
        XDocument xdoc =  
            XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
        Console.WriteLine(xdoc.Root);  
    }  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="67db0-121">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="67db0-121">External resources</span></span>

- [<span data-ttu-id="67db0-122">Introduzione ai formati file Office (2007) Open XML</span><span class="sxs-lookup"><span data-stu-id="67db0-122">Introducing the Office (2007) Open XML File Formats</span></span>](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205%28v=office.12%29)
- <span data-ttu-id="67db0-123">[Overview of WordprocessingML](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812%28v=office.11%29) (Panoramica di WordprocessingML)</span><span class="sxs-lookup"><span data-stu-id="67db0-123">[Overview of WordprocessingML](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812%28v=office.11%29)</span></span>
- [<span data-ttu-id="67db0-124">Anatomia di un file di WordProcessingML</span><span class="sxs-lookup"><span data-stu-id="67db0-124">Anatomy of a WordProcessingML File</span></span>](http://officeopenxml.com/anatomyofOOXML.php)
- [<span data-ttu-id="67db0-125">Introduzione a WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="67db0-125">Introduction to WordprocessingML</span></span>](https://ericwhite.com/blog/introduction-to-wordprocessingml-series/)

## <a name="see-also"></a><span data-ttu-id="67db0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67db0-126">See also</span></span>

- [<span data-ttu-id="67db0-127">Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="67db0-127">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
