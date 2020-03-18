---
title: Recupero dei paragrafi e dei relativi stili (C#)
ms.date: 07/20/2015
ms.assetid: c2f767f8-57b1-4b4b-af04-89ffb1f7067d
ms.openlocfilehash: 47127b6f1d6bfaa0d8d93333882a0d0b59f1bae6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168297"
---
# <a name="retrieving-the-paragraphs-and-their-styles-c"></a><span data-ttu-id="654de-102">Recupero dei paragrafi e dei relativi stili (C#)</span><span class="sxs-lookup"><span data-stu-id="654de-102">Retrieving the Paragraphs and Their Styles (C#)</span></span>
<span data-ttu-id="654de-103">In questo esempio viene scritta una query che recupera i nodi dei paragrafi da un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="654de-103">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="654de-104">Viene inoltre identificato lo stile di ciascun paragrafo.</span><span class="sxs-lookup"><span data-stu-id="654de-104">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="654de-105">Questa query si basa sulla query dell'esempio precedente, [Ricerca dello stile di paragrafo predefinito (C#)](./finding-the-default-paragraph-style.md), che recupera lo stile predefinito dall'elenco degli stili.</span><span class="sxs-lookup"><span data-stu-id="654de-105">This query builds on the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="654de-106">Queste informazioni sono necessarie per consentire alla query di identificare gli stili dei paragrafi per i quali non è stato impostato uno stile in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="654de-106">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="654de-107">Gli stili dei paragrafi vengono impostati tramite l'elemento `w:pPr`. Se un paragrafo non contiene tale elemento, verrà formattato con lo stile predefinito.</span><span class="sxs-lookup"><span data-stu-id="654de-107">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="654de-108">In questo argomento viene spiegata l'importanza di alcune parti della query e quindi viene illustrata la query in un esempio completo e funzionante.</span><span class="sxs-lookup"><span data-stu-id="654de-108">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="654de-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="654de-109">Example</span></span>  
 <span data-ttu-id="654de-110">L'origine della query per recuperare tutti i paragrafi di un documento e i relativi stili è la seguente:</span><span class="sxs-lookup"><span data-stu-id="654de-110">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```csharp  
xDoc.Root.Element(w + "body").Descendants(w + "p")  
```  
  
 <span data-ttu-id="654de-111">Questa espressione è simile all'origine della query dell'esempio precedente, [Ricerca dello stile di paragrafo predefinito (C#)](./finding-the-default-paragraph-style.md).</span><span class="sxs-lookup"><span data-stu-id="654de-111">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="654de-112">La differenza principale è data dall'utilizzo dell'asse <xref:System.Xml.Linq.XContainer.Descendants%2A>, anziché dell'asse <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="654de-112">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="654de-113">La query usa l'asse <xref:System.Xml.Linq.XContainer.Descendants%2A> perché nei documenti suddivisi in sezioni i paragrafi non saranno elementi figlio diretti dell'elemento del corpo, ma si troveranno due livelli più sotto nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="654de-113">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="654de-114">Usando l'asse <xref:System.Xml.Linq.XContainer.Descendants%2A>, il codice verrà eseguito correttamente anche se nel documento vengono usate sezioni.</span><span class="sxs-lookup"><span data-stu-id="654de-114">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="654de-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="654de-115">Example</span></span>  
 <span data-ttu-id="654de-116">La query usa una clausola `let` per determinare l'elemento che contiene il nodo dello stile.</span><span class="sxs-lookup"><span data-stu-id="654de-116">The query uses a `let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="654de-117">Se non è presente nessun elemento, `styleNode` viene impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="654de-117">If there is no element, then `styleNode` is set to `null`:</span></span>  
  
```csharp  
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()  
```  
  
 <span data-ttu-id="654de-118">La clausola `let` usa dapprima l'asse <xref:System.Xml.Linq.XContainer.Elements%2A> per individuare tutti gli elementi denominati `pPr`, quindi il metodo di estensione <xref:System.Xml.Linq.Extensions.Elements%2A> per individuare tutti gli elementi figlio denominati `pStyle` e infine l'operatore di query standard <xref:System.Linq.Enumerable.FirstOrDefault%2A> per convertire la raccolta in un singleton.</span><span class="sxs-lookup"><span data-stu-id="654de-118">The `let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="654de-119">Se la raccolta è vuota, `styleNode` viene impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="654de-119">If the collection is empty, `styleNode` is set to `null`.</span></span> <span data-ttu-id="654de-120">Si tratta di un idioma utile per cercare il nodo dell'elemento discendente `pStyle`.</span><span class="sxs-lookup"><span data-stu-id="654de-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="654de-121">Notare che se il nodo figlio `pPr` non esiste, il codice non viene eseguito e viene generata un'eccezione. `styleNode` viene invece impostato su `null`, che corrisponde al comportamento desiderato della clausola `let`.</span><span class="sxs-lookup"><span data-stu-id="654de-121">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `null`, which is the desired behavior of this `let` clause.</span></span>  
  
 <span data-ttu-id="654de-122">La query proietta una raccolta di un tipo anonimo con due membri, `StyleName` e `ParagraphNode`.</span><span class="sxs-lookup"><span data-stu-id="654de-122">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="654de-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="654de-123">Example</span></span>  
 <span data-ttu-id="654de-124">In questo esempio viene elaborato un documento WordprocessingML, recuperandone i nodi dei paragrafi da un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="654de-124">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="654de-125">Viene inoltre identificato lo stile di ciascun paragrafo.</span><span class="sxs-lookup"><span data-stu-id="654de-125">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="654de-126">Questo esempio si basa su esempi precedenti di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="654de-126">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="654de-127">La nuova query è indicata nei commenti del codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="654de-127">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="654de-128">Per istruzioni per la creazione del documento di origine di questo esempio, vedere [Creazione del documento Office Open XML di origine (C#)](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="654de-128">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="654de-129">In questo esempio vengono usate classi dell'assembly WindowsBase</span><span class="sxs-lookup"><span data-stu-id="654de-129">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="654de-130">e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="654de-130">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative), docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
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
  
// Following is the new query that finds all paragraphs in the  
// document and their styles.  
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
  
foreach (var p in paragraphs)  
    Console.WriteLine("StyleName:{0}", p.StyleName);  
```  
  
 <span data-ttu-id="654de-131">Questo esempio consente di ottenere il seguente output quando viene applicato al documento descritto in [Creazione del documento Office Open XML di origine (C#)](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="654de-131">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
```output  
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
  
## <a name="next-steps"></a><span data-ttu-id="654de-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="654de-132">Next Steps</span></span>  
 <span data-ttu-id="654de-133">Nell'argomento successivo, [Recupero del testo dei paragrafi (C#)](./retrieving-the-text-of-the-paragraphs.md), verrà creata una query per recuperare il testo dei paragrafi.</span><span class="sxs-lookup"><span data-stu-id="654de-133">In the next topic, [Retrieving the Text of the Paragraphs (C#)](./retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="654de-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="654de-134">See also</span></span>

- [<span data-ttu-id="654de-135">Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="654de-135">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
