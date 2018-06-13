---
title: Individuare lo stile del paragrafo predefinito (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9d094a4a-ec8c-41b0-b7ab-a3deb2a01d45
ms.openlocfilehash: 77e6e6db321b5f8ef338706e5f938daa02d115eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642041"
---
# <a name="finding-the-default-paragraph-style-visual-basic"></a><span data-ttu-id="3faa2-102">Individuare lo stile del paragrafo predefinito (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3faa2-102">Finding the Default Paragraph Style (Visual Basic)</span></span>
<span data-ttu-id="3faa2-103">La prima attività dell'esercitazione Modifica di informazioni in un documento WordprocessingML consiste nell'individuare lo stile predefinito dei paragrafi del documento.</span><span class="sxs-lookup"><span data-stu-id="3faa2-103">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3faa2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3faa2-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="3faa2-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3faa2-105">Description</span></span>  
 <span data-ttu-id="3faa2-106">Nell'esempio seguente viene aperto un documento WordprocessingML di Office Open XML, vengono individuate le parti del package relative a documento e stile, quindi viene eseguita una query che trova il nome dello stile predefinito.</span><span class="sxs-lookup"><span data-stu-id="3faa2-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="3faa2-107">Per informazioni sui pacchetti di documento Office Open XML e le parti sono costituite da, vedere [dettagli di Office Open XML documenti WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="3faa2-107">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span></span>  
  
 <span data-ttu-id="3faa2-108">La query cerca un nodo denominato `w:style` che ha un attributo denominato `w:type` con il valore "paragraph" e un attributo denominato `w:default` con il valore "1".</span><span class="sxs-lookup"><span data-stu-id="3faa2-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="3faa2-109">Poiché sarà disponibile un solo nodo XML con questi attributi, la query usa l'operatore <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> per convertire una raccolta in un Singleton.</span><span class="sxs-lookup"><span data-stu-id="3faa2-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="3faa2-110">Ottiene quindi il valore dell'attributo con il nome `w:styleId`.</span><span class="sxs-lookup"><span data-stu-id="3faa2-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="3faa2-111">In questo esempio vengono usate classi dell'assembly WindowsBase</span><span class="sxs-lookup"><span data-stu-id="3faa2-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="3faa2-112">e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3faa2-112">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3faa2-113">Codice</span><span class="sxs-lookup"><span data-stu-id="3faa2-113">Code</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
  
    Sub Main()  
  
        Const fileName As String = "SampleDoc.docx"  
  
        Const documentRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Const stylesRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If docPackageRelationship IsNot Nothing Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                ' Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If styleRelation IsNot Nothing Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    ' Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        ' The following query finds all the paragraphs that have the default style.  
        Dim defParas As IEnumerable(Of XElement) = _  
            From style In styleDoc.Root.<w:style> _  
            Where style.@w:type.Equals("paragraph") And _  
                   style.@w:default.Equals("1") _  
            Select style  
        ' Then find the style of the first.  
        Dim defaultStyle As String = defParas.First().@w:styleId  
  
        Console.WriteLine("The default style is: " & defaultStyle)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="3faa2-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="3faa2-114">Comments</span></span>  
 <span data-ttu-id="3faa2-115">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="3faa2-115">This example produces the following output:</span></span>  
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="3faa2-116">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3faa2-116">Next Steps</span></span>  
 <span data-ttu-id="3faa2-117">Nell'esempio successivo verrà creata una query simile che trova tutti i paragrafi in un documento e i relativi stili:</span><span class="sxs-lookup"><span data-stu-id="3faa2-117">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
-   [<span data-ttu-id="3faa2-118">Recupero dei paragrafi e gli stili (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3faa2-118">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a><span data-ttu-id="3faa2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3faa2-119">See Also</span></span>  
 [<span data-ttu-id="3faa2-120">Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3faa2-120">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
