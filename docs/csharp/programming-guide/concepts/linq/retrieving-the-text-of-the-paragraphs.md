---
title: Recupero del testo dei paragrafi (C#)
ms.date: 07/20/2015
ms.assetid: 127d635e-e559-408f-90c8-2bb621ca50ac
ms.openlocfilehash: 1d23addb4c4c1ea17343585392fbe08fef08568a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45658509"
---
# <a name="retrieving-the-text-of-the-paragraphs-c"></a><span data-ttu-id="88b2f-102">Recupero del testo dei paragrafi (C#)</span><span class="sxs-lookup"><span data-stu-id="88b2f-102">Retrieving the Text of the Paragraphs (C#)</span></span>
<span data-ttu-id="88b2f-103">Questo esempio si basa sull'esempio precedente, [Recupero dei paragrafi e dei relativi stili (C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md).</span><span class="sxs-lookup"><span data-stu-id="88b2f-103">This example builds on the previous example, [Retrieving the Paragraphs and Their Styles (C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md).</span></span> <span data-ttu-id="88b2f-104">Questo nuovo esempio consente di recuperare il testo di ciascun paragrafo sotto forma di stringa.</span><span class="sxs-lookup"><span data-stu-id="88b2f-104">This new example retrieves the text of each paragraph as a string.</span></span>  
  
 <span data-ttu-id="88b2f-105">Per recuperare il testo, nell'esempio viene aggiunta un'ulteriore query che scorre la raccolta di tipi anonimi e proietta una nuova raccolta di un tipo anonimo con l'aggiunta di un nuovo membro `Text`.</span><span class="sxs-lookup"><span data-stu-id="88b2f-105">To retrieve the text, this example adds an additional query that iterates through the collection of anonymous types and projects a new collection of an anonymous type with the addition of a new member, `Text`.</span></span> <span data-ttu-id="88b2f-106">Viene usato l'operatore di query standard <xref:System.Linq.Enumerable.Aggregate%2A> per concatenare più stringhe in un'unica stringa.</span><span class="sxs-lookup"><span data-stu-id="88b2f-106">It uses the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span>  
  
 <span data-ttu-id="88b2f-107">Questa tecnica, che prevede dapprima la proiezione di una raccolta di un tipo anonimo e quindi l'uso di questa raccolta per la proiezione in una nuova raccolta di un tipo anonimo, costituisce un idioma comune e utile.</span><span class="sxs-lookup"><span data-stu-id="88b2f-107">This technique (that is, first projecting to a collection of an anonymous type, then using this collection to project to a new collection of an anonymous type) is a common and useful idiom.</span></span> <span data-ttu-id="88b2f-108">Sarebbe stato possibile scrivere la query senza la proiezione nel primo tipo anonimo,</span><span class="sxs-lookup"><span data-stu-id="88b2f-108">This query could have been written without projecting to the first anonymous type.</span></span> <span data-ttu-id="88b2f-109">tuttavia, a causa della valutazione lazy, tale tecnica non è più onerosa in termini di potenza di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="88b2f-109">However, because of lazy evaluation, doing so does not use much additional processing power.</span></span> <span data-ttu-id="88b2f-110">L'idioma crea più oggetti temporanei sull'heap, ma senza influire sostanzialmente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="88b2f-110">The idiom creates more short lived objects on the heap, but this does not substantially degrade performance.</span></span>  
  
 <span data-ttu-id="88b2f-111">Sarebbe naturalmente possibile scrivere una singola query che contiene la funzionalità per recuperare i paragrafi, nonché lo stile e il testo di ogni paragrafo.</span><span class="sxs-lookup"><span data-stu-id="88b2f-111">Of course, it would be possible to write a single query that contains the functionality to retrieve the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="88b2f-112">Tuttavia, è spesso utile suddividere una query più complessa in più query perché il codice risultante è più modulare e più facilmente gestibile.</span><span class="sxs-lookup"><span data-stu-id="88b2f-112">However, it often is useful to break up a more complicated query into multiple queries because the resulting code is more modular and easier to maintain.</span></span> <span data-ttu-id="88b2f-113">Se inoltre è necessario riutilizzare parte della query, risulta più agevole effettuare il refactoring se le query sono scritte in questo modo.</span><span class="sxs-lookup"><span data-stu-id="88b2f-113">Furthermore, if you need to reuse a portion of the query, it is easier to refactor if the queries are written in this manner.</span></span>  
  
 <span data-ttu-id="88b2f-114">Queste query, che vengono concatenate, usano il modello di elaborazione esaminato in dettaglio nell'[esercitazione sul concatenamento di query in C#](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).</span><span class="sxs-lookup"><span data-stu-id="88b2f-114">These queries, which are chained together, use the processing model that is examined in detail in the topic [Tutorial: Chaining Queries Together (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88b2f-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="88b2f-115">Example</span></span>  
 <span data-ttu-id="88b2f-116">In questo esempio viene elaborato un documento WordprocessingML, determinando il nodo dell'elemento, il nome dello stile e il testo di ciascun paragrafo.</span><span class="sxs-lookup"><span data-stu-id="88b2f-116">This example processes a WordprocessingML document, determining the element node, the style name, and the text of each paragraph.</span></span> <span data-ttu-id="88b2f-117">Questo esempio si basa su esempi precedenti di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="88b2f-117">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="88b2f-118">La nuova query è indicata nei commenti del codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="88b2f-118">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="88b2f-119">Per istruzioni per la creazione del documento di origine di questo esempio, vedere [Creazione del documento Office Open XML di origine (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="88b2f-119">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="88b2f-120">In questo esempio vengono usate classi dell'assembly WindowsBase</span><span class="sxs-lookup"><span data-stu-id="88b2f-120">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="88b2f-121">e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="88b2f-121">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
  
string defaultStyle =   
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
// Find all paragraphs in the document.  
var paragraphs =  
    from para in xDoc  
                 .Root  
                 .Element(w + "body")  
                 .Descendants(w + "p")  
    let styleNode = para  
                    .Elements(w + "pPr")  
                    .Elements(w + "pStyle")  
                    .FirstOrDefault()  
    select new  
    {  
        ParagraphNode = para,  
        StyleName = styleNode != null ?  
            (string)styleNode.Attribute(w + "val") :  
            defaultStyle  
    };  
  
// Following is the new query that retrieves the text of  
// each paragraph.  
var paraWithText =  
    from para in paragraphs  
    select new  
    {  
        ParagraphNode = para.ParagraphNode,  
        StyleName = para.StyleName,  
        Text = para  
               .ParagraphNode  
               .Elements(w + "r")  
               .Elements(w + "t")  
               .Aggregate(  
                   new StringBuilder(),  
                   (s, i) => s.Append((string)i),  
                   s => s.ToString()  
               )  
    };  
  
foreach (var p in paraWithText)  
    Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
```  
  
 <span data-ttu-id="88b2f-122">Questo esempio consente di ottenere il seguente output quando viene applicato al documento descritto in [Creazione del documento Office Open XML di origine (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="88b2f-122">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
```  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >using System;<  
StyleName:Code ><  
StyleName:Code >class Program {<  
StyleName:Code >    public static void (string[] args) {<  
StyleName:Code >        Console.WriteLine("Hello World");<  
StyleName:Code >    }<  
StyleName:Code >}<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
## <a name="next-steps"></a><span data-ttu-id="88b2f-123">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="88b2f-123">Next Steps</span></span>  
 <span data-ttu-id="88b2f-124">Nell'esempio successivo viene illustrato come usare un metodo di estensione, anziché <xref:System.Linq.Enumerable.Aggregate%2A>, per concatenare più stringhe in un'unica stringa.</span><span class="sxs-lookup"><span data-stu-id="88b2f-124">The next example shows how to use an extension method, instead of <xref:System.Linq.Enumerable.Aggregate%2A>, to concatenate multiple strings into a single string.</span></span>  
  
-   [<span data-ttu-id="88b2f-125">Refactoring usando un metodo di estensione (C#)</span><span class="sxs-lookup"><span data-stu-id="88b2f-125">Refactoring Using an Extension Method (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="88b2f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88b2f-126">See Also</span></span>

- [<span data-ttu-id="88b2f-127">Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="88b2f-127">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)  
- [<span data-ttu-id="88b2f-128">Esecuzione posticipata e valutazione lazy in LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="88b2f-128">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
