---
title: Ricerca dello stile di paragrafo predefinito (C#)
ms.date: 07/20/2015
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
ms.openlocfilehash: 052accf31007001c0fa0d46870ee6e4cd30f6bb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674076"
---
# <a name="finding-the-default-paragraph-style-c"></a><span data-ttu-id="9e3ee-102">Ricerca dello stile di paragrafo predefinito (C#)</span><span class="sxs-lookup"><span data-stu-id="9e3ee-102">Finding the Default Paragraph Style (C#)</span></span>
<span data-ttu-id="9e3ee-103">La prima attività dell'esercitazione Modifica di informazioni in un documento WordprocessingML consiste nell'individuare lo stile predefinito dei paragrafi del documento.</span><span class="sxs-lookup"><span data-stu-id="9e3ee-103">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e3ee-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e3ee-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9e3ee-105">Description</span><span class="sxs-lookup"><span data-stu-id="9e3ee-105">Description</span></span>  
 <span data-ttu-id="9e3ee-106">Nell'esempio seguente viene aperto un documento WordprocessingML di Office Open XML, vengono individuate le parti del package relative a documento e stile, quindi viene eseguita una query che trova il nome dello stile predefinito.</span><span class="sxs-lookup"><span data-stu-id="9e3ee-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="9e3ee-107">Per informazioni sui pacchetti di documenti Office Open XML e sulle parti da cui sono costituiti, vedere [Dettagli di documenti WordprocessingML Office Open XML (C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="9e3ee-107">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span></span>  
  
 <span data-ttu-id="9e3ee-108">La query cerca un nodo denominato `w:style` che ha un attributo denominato `w:type` con il valore "paragraph" e un attributo denominato `w:default` con il valore "1".</span><span class="sxs-lookup"><span data-stu-id="9e3ee-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="9e3ee-109">Poiché sarà disponibile un solo nodo XML con questi attributi, la query usa l'operatore <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> per convertire una raccolta in un Singleton.</span><span class="sxs-lookup"><span data-stu-id="9e3ee-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="9e3ee-110">Ottiene quindi il valore dell'attributo con il nome `w:styleId`.</span><span class="sxs-lookup"><span data-stu-id="9e3ee-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="9e3ee-111">In questo esempio vengono usate classi dell'assembly WindowsBase</span><span class="sxs-lookup"><span data-stu-id="9e3ee-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="9e3ee-112">e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9e3ee-112">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9e3ee-113">Codice</span><span class="sxs-lookup"><span data-stu-id="9e3ee-113">Code</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship =  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
          docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation =  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
// The following query finds all the paragraphs that have the default style.  
string defaultStyle =   
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
Console.WriteLine("The default style is: {0}", defaultStyle);  
```  
  
### <a name="comments"></a><span data-ttu-id="9e3ee-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="9e3ee-114">Comments</span></span>  
 <span data-ttu-id="9e3ee-115">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="9e3ee-115">This example produces the following output:</span></span>  
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="9e3ee-116">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="9e3ee-116">Next Steps</span></span>  
 <span data-ttu-id="9e3ee-117">Nell'esempio successivo verrà creata una query simile che trova tutti i paragrafi in un documento e i relativi stili:</span><span class="sxs-lookup"><span data-stu-id="9e3ee-117">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
-   [<span data-ttu-id="9e3ee-118">Recupero dei paragrafi e dei relativi stili (C#)</span><span class="sxs-lookup"><span data-stu-id="9e3ee-118">Retrieving the Paragraphs and Their Styles (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a><span data-ttu-id="9e3ee-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e3ee-119">See also</span></span>

- [<span data-ttu-id="9e3ee-120">Esercitazione: Manipolazione di contenuto in un documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="9e3ee-120">Tutorial: Manipulating Content in a WordprocessingML Document</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
