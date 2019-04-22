---
title: Recupero dei paragrafi e dei relativi stili (Visual Basic)
ms.date: 07/20/2015
ms.assetid: d9ed2238-d38e-4ad4-b88b-db7859df9bde
ms.openlocfilehash: 3c6554c44c95db13aada0d9edf96cc2df595c6d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816941"
---
# <a name="retrieving-the-paragraphs-and-their-styles-visual-basic"></a><span data-ttu-id="79f9e-102">Recupero dei paragrafi e dei relativi stili (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79f9e-102">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>
<span data-ttu-id="79f9e-103">In questo esempio viene scritta una query che recupera i nodi dei paragrafi da un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="79f9e-103">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="79f9e-104">Viene inoltre identificato lo stile di ciascun paragrafo.</span><span class="sxs-lookup"><span data-stu-id="79f9e-104">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="79f9e-105">Questa query si basa sulla query nell'esempio precedente, [ricerca dello stile di paragrafo predefinito (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), che recupera lo stile predefinito dall'elenco degli stili.</span><span class="sxs-lookup"><span data-stu-id="79f9e-105">This query builds on the query in the previous example, [Finding the Default Paragraph Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="79f9e-106">Queste informazioni sono necessarie per consentire alla query di identificare gli stili dei paragrafi per i quali non è stato impostato uno stile in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="79f9e-106">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="79f9e-107">Gli stili dei paragrafi vengono impostati tramite l'elemento `w:pPr`. Se un paragrafo non contiene tale elemento, verrà formattato con lo stile predefinito.</span><span class="sxs-lookup"><span data-stu-id="79f9e-107">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="79f9e-108">In questo argomento viene spiegata l'importanza di alcune parti della query e quindi viene illustrata la query in un esempio completo e funzionante.</span><span class="sxs-lookup"><span data-stu-id="79f9e-108">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79f9e-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="79f9e-109">Example</span></span>  
 <span data-ttu-id="79f9e-110">L'origine della query per recuperare tutti i paragrafi di un documento e i relativi stili è la seguente:</span><span class="sxs-lookup"><span data-stu-id="79f9e-110">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```vb  
xDoc.Root.<w:body>...<w:p>  
```  
  
 <span data-ttu-id="79f9e-111">Questa espressione è simile all'origine della query nell'esempio precedente, [ricerca dello stile di paragrafo predefinito (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md).</span><span class="sxs-lookup"><span data-stu-id="79f9e-111">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="79f9e-112">La differenza principale è data dall'utilizzo dell'asse <xref:System.Xml.Linq.XContainer.Descendants%2A>, anziché dell'asse <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="79f9e-112">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="79f9e-113">La query usa l'asse <xref:System.Xml.Linq.XContainer.Descendants%2A> perché nei documenti suddivisi in sezioni i paragrafi non saranno elementi figlio diretti dell'elemento del corpo, ma si troveranno due livelli più sotto nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="79f9e-113">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="79f9e-114">Usando l'asse <xref:System.Xml.Linq.XContainer.Descendants%2A>, il codice verrà eseguito correttamente anche se nel documento vengono usate sezioni.</span><span class="sxs-lookup"><span data-stu-id="79f9e-114">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79f9e-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="79f9e-115">Example</span></span>  
 <span data-ttu-id="79f9e-116">La query usa una clausola `Let` per determinare l'elemento che contiene il nodo dello stile.</span><span class="sxs-lookup"><span data-stu-id="79f9e-116">The query uses a `Let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="79f9e-117">Se non è presente nessun elemento, `styleNode` viene impostato su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="79f9e-117">If there is no element, then `styleNode` is set to `Nothing`:</span></span>  
  
```vb  
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()  
```  
  
 <span data-ttu-id="79f9e-118">La clausola `Let` usa dapprima l'asse <xref:System.Xml.Linq.XContainer.Elements%2A> per individuare tutti gli elementi denominati `pPr`, quindi il metodo di estensione <xref:System.Xml.Linq.Extensions.Elements%2A> per individuare tutti gli elementi figlio denominati `pStyle` e infine l'operatore di query standard <xref:System.Linq.Enumerable.FirstOrDefault%2A> per convertire la raccolta in un singleton.</span><span class="sxs-lookup"><span data-stu-id="79f9e-118">The `Let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="79f9e-119">Se la raccolta è vuota, `styleNode` viene impostato su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="79f9e-119">If the collection is empty, `styleNode` is set to `Nothing`.</span></span> <span data-ttu-id="79f9e-120">Si tratta di un idioma utile per cercare il nodo dell'elemento discendente `pStyle`.</span><span class="sxs-lookup"><span data-stu-id="79f9e-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="79f9e-121">Notare che se il nodo figlio `pPr` non esiste, il codice non viene eseguito e viene generata un'eccezione. `styleNode` viene invece impostato su `Nothing`, che corrisponde al comportamento desiderato della clausola `Let`.</span><span class="sxs-lookup"><span data-stu-id="79f9e-121">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `Nothing`, which is the desired behavior of this `Let` clause.</span></span>  
  
 <span data-ttu-id="79f9e-122">La query proietta una raccolta di un tipo anonimo con due membri, `StyleName` e `ParagraphNode`.</span><span class="sxs-lookup"><span data-stu-id="79f9e-122">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79f9e-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="79f9e-123">Example</span></span>  
 <span data-ttu-id="79f9e-124">In questo esempio viene elaborato un documento WordprocessingML, recuperandone i nodi dei paragrafi da un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="79f9e-124">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="79f9e-125">Viene inoltre identificato lo stile di ciascun paragrafo.</span><span class="sxs-lookup"><span data-stu-id="79f9e-125">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="79f9e-126">Questo esempio si basa su esempi precedenti di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="79f9e-126">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="79f9e-127">La nuova query è indicata nei commenti del codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="79f9e-127">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="79f9e-128">È possibile trovare istruzioni per la creazione del documento di origine per questo esempio nella [creando l'origine documento Office Open XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="79f9e-128">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="79f9e-129">In questo esempio vengono usate classi dell'assembly WindowsBase</span><span class="sxs-lookup"><span data-stu-id="79f9e-129">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="79f9e-130">e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="79f9e-130">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
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
  
        ' Following is the new query that finds all paragraphs in the  
        ' document and their styles.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault() _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        For Each p In paragraphs  
            Console.WriteLine("StyleName:{0}", p.StyleName)  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="79f9e-131">In questo esempio produce il seguente output quando viene applicato al documento descritto [creando l'origine documento Office Open XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="79f9e-131">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
```  
StyleName:Heading1  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
```  
  
## <a name="next-steps"></a><span data-ttu-id="79f9e-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="79f9e-132">Next Steps</span></span>  
 <span data-ttu-id="79f9e-133">Nell'argomento successivo [recuperando il testo dei paragrafi (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), si creerà una query per recuperare il testo dei paragrafi.</span><span class="sxs-lookup"><span data-stu-id="79f9e-133">In the next topic, [Retrieving the Text of the Paragraphs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f9e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79f9e-134">See also</span></span>

- [<span data-ttu-id="79f9e-135">Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79f9e-135">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
