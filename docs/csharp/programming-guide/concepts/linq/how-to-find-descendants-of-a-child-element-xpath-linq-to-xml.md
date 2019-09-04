---
title: 'Procedura: Trovare discendenti di un elemento figlio (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: f17d723aa03c45daa4e7e741ea6b14c637537ccf
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253709"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="f027b-102">Procedura: Trovare discendenti di un elemento figlio (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f027b-102">How to: Find Descendants of a Child Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="f027b-103">In questo argomento viene illustrato come ottenere gli elementi discendenti di un elemento figlio con un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="f027b-103">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="f027b-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="f027b-104">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="f027b-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f027b-105">Example</span></span>  
 <span data-ttu-id="f027b-106">In questo esempio sono simulati i problemi di estrazione di testo da una rappresentazione XML di un documento di elaborazione testi.</span><span class="sxs-lookup"><span data-stu-id="f027b-106">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="f027b-107">Vengono dapprima selezionati tutti gli elementi `Paragraph` e quindi tutti gli elementi discendenti `Text` di ogni elemento `Paragraph`.</span><span class="sxs-lookup"><span data-stu-id="f027b-107">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="f027b-108">Gli elementi discendenti `Text` dell'elemento `Comment` non vengono selezionati.</span><span class="sxs-lookup"><span data-stu-id="f027b-108">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root>  
  <Paragraph>  
    <Text>This is the start of</Text>  
  </Paragraph>  
  <Comment>  
    <Text>This comment is not part of the paragraph text.</Text>  
  </Comment>  
  <Paragraph>  
    <Annotation Emphasis='true'>  
      <Text> a sentence.</Text>  
    </Annotation>  
  </Paragraph>  
  <Paragraph>  
    <Text>  This is a second sentence.</Text>  
  </Paragraph>  
</Root>");  
  
// LINQ to XML query  
string str1 =  
    root  
    .Elements("Paragraph")  
    .Descendants("Text")  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
// XPath expression  
string str2 =  
    ((IEnumerable)root.XPathEvaluate("./Paragraph//Text/text()"))  
    .Cast<XText>()  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
if (str1 == str2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(str2);  
```  
  
 <span data-ttu-id="f027b-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="f027b-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  