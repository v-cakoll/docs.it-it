---
title: Ricerca dello stile di paragrafo predefinito (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 834654837b5c7fc747b0df1ee9dc645664a77351
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="finding-the-default-paragraph-style-c"></a><span data-ttu-id="4f23a-102">Ricerca dello stile di paragrafo predefinito (C#)</span><span class="sxs-lookup"><span data-stu-id="4f23a-102">Finding the Default Paragraph Style (C#)</span></span>
<span data-ttu-id="4f23a-103">La prima attività dell'esercitazione Modifica di informazioni in un documento WordprocessingML consiste nell'individuare lo stile predefinito dei paragrafi del documento.</span><span class="sxs-lookup"><span data-stu-id="4f23a-103">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f23a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f23a-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="4f23a-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f23a-105">Description</span></span>  
 <span data-ttu-id="4f23a-106">Nell'esempio seguente viene aperto un documento WordprocessingML di Office Open XML, vengono individuate le parti del package relative a documento e stile, quindi viene eseguita una query che trova il nome dello stile predefinito.</span><span class="sxs-lookup"><span data-stu-id="4f23a-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="4f23a-107">Per informazioni sui pacchetti di documenti Office Open XML e sulle parti da cui sono costituiti, vedere [Dettagli di documenti WordprocessingML Office Open XML (C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="4f23a-107">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span></span>  
  
 <span data-ttu-id="4f23a-108">La query cerca un nodo denominato `w:style` che ha un attributo denominato `w:type` con il valore "paragraph" e un attributo denominato `w:default` con il valore "1".</span><span class="sxs-lookup"><span data-stu-id="4f23a-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="4f23a-109">Poiché sarà disponibile un solo nodo XML con questi attributi, la query usa l'operatore <xref:System.Linq.Enumerable.First%2A?displayProperty=fullName> per convertire una raccolta in un Singleton.</span><span class="sxs-lookup"><span data-stu-id="4f23a-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=fullName> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="4f23a-110">Ottiene quindi il valore dell'attributo con il nome `w:styleId`.</span><span class="sxs-lookup"><span data-stu-id="4f23a-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="4f23a-111">In questo esempio vengono usate classi dell'assembly WindowsBase</span><span class="sxs-lookup"><span data-stu-id="4f23a-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="4f23a-112">e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4f23a-112">It uses types in the <xref:System.IO.Packaging?displayProperty=fullName> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4f23a-113">Codice</span><span class="sxs-lookup"><span data-stu-id="4f23a-113">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="4f23a-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="4f23a-114">Comments</span></span>  
 <span data-ttu-id="4f23a-115">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4f23a-115">This example produces the following output:</span></span>  
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="4f23a-116">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4f23a-116">Next Steps</span></span>  
 <span data-ttu-id="4f23a-117">Nell'esempio successivo verrà creata una query simile che trova tutti i paragrafi in un documento e i relativi stili:</span><span class="sxs-lookup"><span data-stu-id="4f23a-117">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
-   [<span data-ttu-id="4f23a-118">Recupero dei paragrafi e dei relativi stili (C#)</span><span class="sxs-lookup"><span data-stu-id="4f23a-118">Retrieving the Paragraphs and Their Styles (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a><span data-ttu-id="4f23a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f23a-119">See Also</span></span>  
 [<span data-ttu-id="4f23a-120">Esercitazione: manipolazione di contenuto in un documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="4f23a-120">Tutorial: Manipulating Content in a WordprocessingML Document</span></span>](http://msdn.microsoft.com/library/2696355e-4f83-4eaf-91b2-baa721f42fb4)

