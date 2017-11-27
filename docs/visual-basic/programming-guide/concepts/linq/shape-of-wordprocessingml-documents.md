---
title: Forma dei documenti WordprocessingML (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dfb446b-5a07-4c00-9ab3-a74ba734ff3a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f29ed78062337c7036ada2405fa610ff1f883feb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="shape-of-wordprocessingml-documents-visual-basic"></a><span data-ttu-id="b4505-102">Forma dei documenti WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4505-102">Shape of WordprocessingML Documents (Visual Basic)</span></span>
<span data-ttu-id="b4505-103">In questo argomento viene descritta la forma XML di un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="b4505-103">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="b4505-104">Formati di Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="b4505-104">Microsoft Office Formats</span></span>  
 <span data-ttu-id="b4505-105">Il formato di file nativo per Microsoft Office System 2007 è Office Open XML (più comunemente, Open XML).</span><span class="sxs-lookup"><span data-stu-id="b4505-105">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="b4505-106">Open XML è un formato basato su XML conforme allo standard ECMA e attualmente in approvazione per gli standard ISO-IEC.</span><span class="sxs-lookup"><span data-stu-id="b4505-106">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="b4505-107">Il linguaggio di markup per i file di elaborazione testi all'interno di Open XML è denominato WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="b4505-107">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="b4505-108">In questa esercitazione vengono usati file di origine WordprocessingML come di input per gli esempi.</span><span class="sxs-lookup"><span data-stu-id="b4505-108">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="b4505-109">Se si usa Microsoft Office 2003, possibile salvare i documenti nel formato Office Open XML se è stato installato il pacchetto di compatibilità di Microsoft Office per i formati di file Word, Excel e PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="b4505-109">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="b4505-110">Forma dei documenti WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="b4505-110">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="b4505-111">Il primo aspetto da considerare è la forma dei documenti WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="b4505-111">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="b4505-112">Un documento WordprocessingML contiene un elemento corpo, denominato `w:body`, che contiene i paragrafi del documento.</span><span class="sxs-lookup"><span data-stu-id="b4505-112">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="b4505-113">Ogni paragrafo contiene una o più sequenze di testo, denominate `w:r`.</span><span class="sxs-lookup"><span data-stu-id="b4505-113">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="b4505-114">Ogni sequenza di testo contiene uno o più parti di testo, denominate `w:t`.</span><span class="sxs-lookup"><span data-stu-id="b4505-114">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="b4505-115">Di seguito è riportato un documento WordprocessingML molto semplice:</span><span class="sxs-lookup"><span data-stu-id="b4505-115">The following is a very simple WordprocessingML document:</span></span>  
  
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
  
 <span data-ttu-id="b4505-116">Questo documento contiene due paragrafi.</span><span class="sxs-lookup"><span data-stu-id="b4505-116">This document contains two paragraphs.</span></span> <span data-ttu-id="b4505-117">Entrambi contengono una sola sequenza di testo e ogni sequenza di testo contiene una sola parte di testo.</span><span class="sxs-lookup"><span data-stu-id="b4505-117">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="b4505-118">Il modo più semplice per visualizzare il contenuto di un documento WordprocessingML in formato XML consiste nel crearne uno usando Microsoft Word, salvarlo e quindi eseguire il programma seguente che stampa l'XML nella console.</span><span class="sxs-lookup"><span data-stu-id="b4505-118">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="b4505-119">In questo esempio vengono usate classi dell'assembly WindowsBase</span><span class="sxs-lookup"><span data-stu-id="b4505-119">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="b4505-120">e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b4505-120">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Sub Main()  
        Dim documentRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
  
        Using wdPackage As Package = _  
          Package.Open("SampleDoc.docx", _  
                       FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage _  
                .GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri( _  
                            New Uri("/", UriKind.Relative), _  
                            docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Get the officeDocument part from the package.  
                ' Load the XML in the part into an XDocument instance.  
                Dim xDoc As XDocument = _  
                    XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
                Console.WriteLine(xDoc.Root)  
            End If  
        End Using  
    End Sub  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="b4505-121">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="b4505-121">External Resources</span></span>  
 [<span data-ttu-id="b4505-122">Introduzione ai formati file Office (2007) Open XML</span><span class="sxs-lookup"><span data-stu-id="b4505-122">Introducing the Office (2007) Open XML File Formats</span></span>](http://go.microsoft.com/fwlink/?LinkId=98093)  
  
 <span data-ttu-id="b4505-123">[Overview of WordprocessingML](http://go.microsoft.com/fwlink/?LinkId=98094) (Panoramica di WordprocessingML)</span><span class="sxs-lookup"><span data-stu-id="b4505-123">[Overview of WordprocessingML](http://go.microsoft.com/fwlink/?LinkId=98094)</span></span>  
  
 <span data-ttu-id="b4505-124">[Pagina di download Office 2003: XML Reference Schemas page](http://go.microsoft.com/fwlink/?LinkId=98095) (Schemi di riferimento XML)</span><span class="sxs-lookup"><span data-stu-id="b4505-124">[Office 2003: XML Reference Schemas Download page](http://go.microsoft.com/fwlink/?LinkId=98095)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4505-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4505-125">See Also</span></span>  
 [<span data-ttu-id="b4505-126">Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4505-126">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
