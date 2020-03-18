---
title: Proiezione di XML in una forma diversa (C#)
ms.date: 07/20/2015
ms.assetid: 4cb6b14a-32dc-4a2a-813e-bf9368fa8d86
ms.openlocfilehash: 1377df1ce7f54bc9a0f58836d7df5e5b7b54a69a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591529"
---
# <a name="projecting-xml-in-a-different-shape-c"></a><span data-ttu-id="19d11-102">Proiezione di XML in una forma diversa (C#)</span><span class="sxs-lookup"><span data-stu-id="19d11-102">Projecting XML in a Different Shape (C#)</span></span>
<span data-ttu-id="19d11-103">In questo argomento viene illustrato un esempio di proiezione del codice XML in una forma diversa da quella del codice XML di origine.</span><span class="sxs-lookup"><span data-stu-id="19d11-103">This topic shows an example of projecting XML that is in a different shape than the source XML.</span></span>  
  
 <span data-ttu-id="19d11-104">Molte trasformazioni XML tipiche sono costituite da query concatenate, come nel caso di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="19d11-104">Many typical XML transformations consist of chained queries, as in this example.</span></span> <span data-ttu-id="19d11-105">Non è infrequente iniziare con un qualche tipo di codice XML, proiettare i risultati intermedi come raccolte di tipi anonimi o con nome e infine proiettare i risultati nuovamente nel codice XML in una forma completamente diverso rispetto al codice XML di origine.</span><span class="sxs-lookup"><span data-stu-id="19d11-105">It is common to start with some form of XML, project intermediate results as collections of anonymous types or named types, and then finally to project the results back into XML that is in an entirely different shape than the source XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19d11-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="19d11-106">Example</span></span>  
 <span data-ttu-id="19d11-107">In questo esempio viene elaborato un documento WordprocessingML, recuperandone i nodi dei paragrafi da un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="19d11-107">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="19d11-108">Vengono inoltre identificati lo stile e il testo di ciascun paragrafo.</span><span class="sxs-lookup"><span data-stu-id="19d11-108">It also identifies the style and text of each paragraph.</span></span> <span data-ttu-id="19d11-109">Infine il codice XML viene proiettato con una forma diversa.</span><span class="sxs-lookup"><span data-stu-id="19d11-109">Finally, the example projects XML with a different shape.</span></span> <span data-ttu-id="19d11-110">Questo esempio si basa su esempi precedenti di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="19d11-110">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="19d11-111">La nuova istruzione usata per la proiezione è indicata nei commenti del codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="19d11-111">The new statement that does the projection is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="19d11-112">Per istruzioni sulla creazione del documento di origine di questo esempio, vedere [Creazione del documento Office Open XML di origine (C#)](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="19d11-112">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="19d11-113">In questo esempio vengono usate classi dell'assembly WindowsBase</span><span class="sxs-lookup"><span data-stu-id="19d11-113">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="19d11-114">e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="19d11-114">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static string StringConcatenate(this IEnumerable<string> source)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item));  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate(this IEnumerable<string> source, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s).Append(separator);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item)).Append(separator);  
        return sb.ToString();  
    }  
}  
  
class Program  
{  
    public static string ParagraphText(XElement e)  
    {  
        XNamespace w = e.Name.Namespace;  
        return e  
               .Elements(w + "r")  
               .Elements(w + "t")  
               .StringConcatenate(element => (string)element);  
    }  
  
    static void Main(string[] args)  
    {  
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
                    Uri styleUri =  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
                    PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
                    //  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
                }  
            }  
        }  
  
        string defaultStyle =  
            (string)(  
                from style in styleDoc.Root.Elements(w + "style")  
                where (string)style.Attribute(w + "type") == "paragraph" &&  
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
  
        // Retrieve the text of each paragraph.  
        var paraWithText =  
            from para in paragraphs  
            select new  
            {  
                ParagraphNode = para.ParagraphNode,  
                StyleName = para.StyleName,  
                Text = ParagraphText(para.ParagraphNode)  
            };  
  
        // The following is the new code that projects XML in a new shape.  
        XElement root = new XElement("Root",  
            from p in paraWithText  
            select new XElement("Paragraph",  
                new XElement("StyleName", p.StyleName),  
                new XElement("Text", p.Text)  
            )  
        );  
  
        Console.WriteLine(root);  
    }  
}  
```  
  
 <span data-ttu-id="19d11-115">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="19d11-115">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Paragraph>  
    <StyleName>Heading1</StyleName>  
    <Text>Parsing WordprocessingML with LINQ to XML</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text>The following example prints to the console.</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>using System;</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>class Program {</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>    public static void (string[] args) {</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>        Console.WriteLine("Hello World");</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>    }</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>}</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text>This example produces the following output:</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>Hello World</Text>  
  </Paragraph>  
</Root>  
```  
  
## <a name="next-steps"></a><span data-ttu-id="19d11-116">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="19d11-116">Next Steps</span></span>  
 <span data-ttu-id="19d11-117">Nell'esempio successivo viene eseguita una query per individuare tutto il testo in un documento di Word:</span><span class="sxs-lookup"><span data-stu-id="19d11-117">In the next example, you'll query to find all the text in a Word document:</span></span>  
  
- [<span data-ttu-id="19d11-118">Ricerca di testo nei documenti di Word (C#)</span><span class="sxs-lookup"><span data-stu-id="19d11-118">Finding Text in Word Documents (C#)</span></span>](./finding-text-in-word-documents.md)  
  