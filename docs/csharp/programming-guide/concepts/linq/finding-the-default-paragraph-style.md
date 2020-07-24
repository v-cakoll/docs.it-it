---
title: Ricerca dello stile di paragrafo predefinito (C#)
description: Informazioni su come elaborare un documento WordprocessingML con LINQ in C#. In questo esempio viene trovato lo stile predefinito dei paragrafi nel documento.
ms.date: 07/20/2015
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
ms.openlocfilehash: e18bbbdbd5b2627c9ff4c3c3eedd84d7cb166a62
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103818"
---
# <a name="finding-the-default-paragraph-style-c"></a><span data-ttu-id="89005-104">Ricerca dello stile di paragrafo predefinito (C#)</span><span class="sxs-lookup"><span data-stu-id="89005-104">Finding the Default Paragraph Style (C#)</span></span>
<span data-ttu-id="89005-105">La prima attività dell'esercitazione Modifica di informazioni in un documento WordprocessingML consiste nell'individuare lo stile predefinito dei paragrafi del documento.</span><span class="sxs-lookup"><span data-stu-id="89005-105">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89005-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="89005-106">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="89005-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89005-107">Description</span></span>  
 <span data-ttu-id="89005-108">Nell'esempio seguente viene aperto un documento WordprocessingML di Office Open XML, vengono individuate le parti del package relative a documento e stile, quindi viene eseguita una query che trova il nome dello stile predefinito.</span><span class="sxs-lookup"><span data-stu-id="89005-108">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="89005-109">Per informazioni sui pacchetti di documenti Office Open XML e sulle parti da cui sono costituiti, vedere [Dettagli di documenti WordprocessingML Office Open XML (C#)](./wordprocessingml-document-with-styles.md).</span><span class="sxs-lookup"><span data-stu-id="89005-109">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (C#)](./wordprocessingml-document-with-styles.md).</span></span>  
  
 <span data-ttu-id="89005-110">La query cerca un nodo denominato `w:style` che ha un attributo denominato `w:type` con il valore "paragraph" e un attributo denominato `w:default` con il valore "1".</span><span class="sxs-lookup"><span data-stu-id="89005-110">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="89005-111">Poiché sarà disponibile un solo nodo XML con questi attributi, la query usa l'operatore <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> per convertire una raccolta in un Singleton.</span><span class="sxs-lookup"><span data-stu-id="89005-111">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="89005-112">Ottiene quindi il valore dell'attributo con il nome `w:styleId`.</span><span class="sxs-lookup"><span data-stu-id="89005-112">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="89005-113">In questo esempio vengono usate classi dell'assembly WindowsBase</span><span class="sxs-lookup"><span data-stu-id="89005-113">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="89005-114">e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89005-114">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="89005-115">Codice</span><span class="sxs-lookup"><span data-stu-id="89005-115">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="89005-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="89005-116">Comments</span></span>  
 <span data-ttu-id="89005-117">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="89005-117">This example produces the following output:</span></span>  
  
```output  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="89005-118">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="89005-118">Next Steps</span></span>  
 <span data-ttu-id="89005-119">Nell'esempio successivo verrà creata una query simile che trova tutti i paragrafi in un documento e i relativi stili:</span><span class="sxs-lookup"><span data-stu-id="89005-119">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
- [<span data-ttu-id="89005-120">Recupero dei paragrafi e dei relativi stili (C#)</span><span class="sxs-lookup"><span data-stu-id="89005-120">Retrieving the Paragraphs and Their Styles (C#)</span></span>](./retrieving-the-paragraphs-and-their-styles.md)  
