---
title: 'Procedura: Trovare un attributo dell''elemento padre (XPath-LINQ to XML) (C#)'
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
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 612baa54e125a5559cc1416bf78d19862ce5d082
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="fea33-102">Procedura: Trovare un attributo dell'elemento padre (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fea33-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="fea33-103">In questo argomento viene illustrato come spostarsi all'elemento padre e trovare un relativo attributo.</span><span class="sxs-lookup"><span data-stu-id="fea33-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="fea33-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="fea33-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="fea33-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="fea33-105">Example</span></span>  
 <span data-ttu-id="fea33-106">Viene innanzitutto individuato un elemento `Author`.</span><span class="sxs-lookup"><span data-stu-id="fea33-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="fea33-107">Quindi, viene individuato l'attributo `id` dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="fea33-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="fea33-108">Questo esempio usa il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="fea33-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement author =   
    books  
    .Root  
    .Element("Book")  
    .Element("Author");  
  
// LINQ to XML query  
XAttribute att1 =  
    author  
    .Parent  
    .Attribute("id");  
  
// XPath expression  
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();  
  
if (att1 == att2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(att1);  
```  
  
 <span data-ttu-id="fea33-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="fea33-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="fea33-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fea33-110">See Also</span></span>  
 [<span data-ttu-id="fea33-111">LINQ to XML per gli utenti di XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="fea33-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

