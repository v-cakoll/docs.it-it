---
title: Recupero del testo dei paragrafi (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 095fa0d9-7b1b-4cbb-9c13-e2c9d8923d31
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e26537c9aab97b3e4d77d34d9432078cf4792ef6
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="retrieving-the-text-of-the-paragraphs-visual-basic"></a><span data-ttu-id="3939e-102">Recupero del testo dei paragrafi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3939e-102">Retrieving the Text of the Paragraphs (Visual Basic)</span></span>
<span data-ttu-id="3939e-103">Questo esempio si basa sull'esempio precedente, [recupero i paragrafi e dei relativi stili (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md).</span><span class="sxs-lookup"><span data-stu-id="3939e-103">This example builds on the previous example, [Retrieving the Paragraphs and Their Styles (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md).</span></span> <span data-ttu-id="3939e-104">Questo nuovo esempio consente di recuperare il testo di ciascun paragrafo sotto forma di stringa.</span><span class="sxs-lookup"><span data-stu-id="3939e-104">This new example retrieves the text of each paragraph as a string.</span></span>  
  
 <span data-ttu-id="3939e-105">Per recuperare il testo, nell'esempio viene aggiunta un'ulteriore query che scorre la raccolta di tipi anonimi e proietta una nuova raccolta di un tipo anonimo con l'aggiunta di un nuovo membro `Text`.</span><span class="sxs-lookup"><span data-stu-id="3939e-105">To retrieve the text, this example adds an additional query that iterates through the collection of anonymous types and projects a new collection of an anonymous type with the addition of a new member, `Text`.</span></span> <span data-ttu-id="3939e-106">Usa il <xref:System.Linq.Enumerable.Aggregate%2A>operatore di query standard per concatenare più stringhe in un'unica stringa.</xref:System.Linq.Enumerable.Aggregate%2A></span><span class="sxs-lookup"><span data-stu-id="3939e-106">It uses the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span>  
  
 <span data-ttu-id="3939e-107">Questa tecnica, che prevede dapprima la proiezione di una raccolta di un tipo anonimo e quindi l'uso di questa raccolta per la proiezione in una nuova raccolta di un tipo anonimo, costituisce un idioma comune e utile.</span><span class="sxs-lookup"><span data-stu-id="3939e-107">This technique (that is, first projecting to a collection of an anonymous type, then using this collection to project to a new collection of an anonymous type) is a common and useful idiom.</span></span> <span data-ttu-id="3939e-108">Sarebbe stato possibile scrivere la query senza la proiezione nel primo tipo anonimo,</span><span class="sxs-lookup"><span data-stu-id="3939e-108">This query could have been written without projecting to the first anonymous type.</span></span> <span data-ttu-id="3939e-109">tuttavia, a causa della valutazione lazy, tale tecnica non è più onerosa in termini di potenza di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3939e-109">However, because of lazy evaluation, doing so does not use much additional processing power.</span></span> <span data-ttu-id="3939e-110">L'idioma crea più oggetti temporanei sull'heap, ma senza influire sostanzialmente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3939e-110">The idiom creates more short lived objects on the heap, but this does not substantially degrade performance.</span></span>  
  
 <span data-ttu-id="3939e-111">Sarebbe naturalmente possibile scrivere una singola query che contiene la funzionalità per recuperare i paragrafi, nonché lo stile e il testo di ogni paragrafo.</span><span class="sxs-lookup"><span data-stu-id="3939e-111">Of course, it would be possible to write a single query that contains the functionality to retrieve the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="3939e-112">Tuttavia, è spesso utile suddividere una query più complessa in più query perché il codice risultante è più modulare e più facilmente gestibile.</span><span class="sxs-lookup"><span data-stu-id="3939e-112">However, it often is useful to break up a more complicated query into multiple queries because the resulting code is more modular and easier to maintain.</span></span> <span data-ttu-id="3939e-113">Se inoltre è necessario riutilizzare parte della query, risulta più agevole effettuare il refactoring se le query sono scritte in questo modo.</span><span class="sxs-lookup"><span data-stu-id="3939e-113">Furthermore, if you need to reuse a portion of the query, it is easier to refactor if the queries are written in this manner.</span></span>  
  
 <span data-ttu-id="3939e-114">Queste query, che vengono concatenate, utilizzano il modello di elaborazione esaminato in dettaglio nell'argomento [esercitazione: esecuzione posticipata (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md).</span><span class="sxs-lookup"><span data-stu-id="3939e-114">These queries, which are chained together, use the processing model that is examined in detail in the topic [Tutorial: Deferred Execution (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3939e-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="3939e-115">Example</span></span>  
 <span data-ttu-id="3939e-116">In questo esempio viene elaborato un documento WordprocessingML, determinando il nodo dell'elemento, il nome dello stile e il testo di ciascun paragrafo.</span><span class="sxs-lookup"><span data-stu-id="3939e-116">This example processes a WordprocessingML document, determining the element node, the style name, and the text of each paragraph.</span></span> <span data-ttu-id="3939e-117">Questo esempio si basa su esempi precedenti di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="3939e-117">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="3939e-118">La nuova query è indicata nei commenti del codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3939e-118">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="3939e-119">Per istruzioni sulla creazione del documento di origine per questo esempio, vedere [la creazione di origine documento Office Open XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="3939e-119">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="3939e-120">In questo esempio vengono usate classi dell'assembly WindowsBase</span><span class="sxs-lookup"><span data-stu-id="3939e-120">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="3939e-121">Utilizza i tipi di <xref:System.IO.Packaging?displayProperty=fullName>dello spazio dei nomi.</xref:System.IO.Packaging?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3939e-121">It uses types in the <xref:System.IO.Packaging?displayProperty=fullName> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    ' Following function is required because VB does not support short circuit evaluation  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, _  
                                         ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = _  
          "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    '  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        Dim defaultStyle As String = _  
            ( _  
                From style In styleDoc.Root.<w:style> _  
                Where style.@w:type = "paragraph" And _  
                      style.@w:default = "1" _  
                Select style _  
            ).First().@w:styleId  
  
        ' Find all paragraphs in the document.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        ' Following is the new query that retrieves the text of  
        ' each paragraph.  
        Dim paraWithText = _  
            From para In paragraphs _  
            Select New With { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = para.ParagraphNode.<w:r>.<w:t> _  
                    .Aggregate(New StringBuilder(), _  
                               Function(s As StringBuilder, i As String) s.Append(CStr(i)), _  
                               Function(s As StringBuilder) s.ToString) _  
            }  
  
        For Each p In paraWithText  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text)  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="3939e-122">In questo esempio produce il seguente output quando viene applicato al documento descritto [la creazione di origine documento Office Open XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="3939e-122">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
```  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >Imports System<  
StyleName:Code ><  
StyleName:Code >Class Program<  
StyleName:Code >    Public Shared  Sub Main(ByVal args() As String)<  
StyleName:Code >        Console.WriteLine("Hello World")<  
StyleName:Code >   End Sub<  
StyleName:Code >End Class<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
## <a name="next-steps"></a><span data-ttu-id="3939e-123">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3939e-123">Next Steps</span></span>  
 <span data-ttu-id="3939e-124">Nell'esempio seguente viene illustrato come utilizzare un metodo di estensione, anziché <xref:System.Linq.Enumerable.Aggregate%2A>, per concatenare più stringhe in un'unica stringa.</xref:System.Linq.Enumerable.Aggregate%2A></span><span class="sxs-lookup"><span data-stu-id="3939e-124">The next example shows how to use an extension method, instead of <xref:System.Linq.Enumerable.Aggregate%2A>, to concatenate multiple strings into a single string.</span></span>  
  
-   [<span data-ttu-id="3939e-125">Refactoring tramite un metodo di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3939e-125">Refactoring Using an Extension Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="3939e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3939e-126">See Also</span></span>  
 <span data-ttu-id="3939e-127">[Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) </span><span class="sxs-lookup"><span data-stu-id="3939e-127">[Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) </span></span>  
<span data-ttu-id="3939e-128"> [Esecuzione posticipata e valutazione differita in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="3939e-128"> [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)</span></span>
