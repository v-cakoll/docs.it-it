---
title: "Procedura: Trovare un attributo dell'elemento padre (XPath-LINQ to XML) (Visual Basic)"
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: 15752805f35b145514d25208b6de44a7ed8ade47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580538"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="84fcc-102">Procedura: Trovare un attributo dell'elemento padre (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84fcc-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="84fcc-103">In questo argomento viene illustrato come spostarsi all'elemento padre e trovare un relativo attributo.</span><span class="sxs-lookup"><span data-stu-id="84fcc-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="84fcc-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="84fcc-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="84fcc-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="84fcc-105">Example</span></span>  
 <span data-ttu-id="84fcc-106">Viene innanzitutto individuato un elemento `Author`.</span><span class="sxs-lookup"><span data-stu-id="84fcc-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="84fcc-107">Quindi, viene individuato l'attributo `id` dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="84fcc-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="84fcc-108">Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: Libri (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="84fcc-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()  
  
' LINQ to XML query  
Dim att1 As XAttribute = author.Parent.Attribute("id")  
  
' XPath expression  
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _  
    IEnumerable).Cast(Of XAttribute)().First()  
  
If att1 Is att2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(att1)  
```  
  
 <span data-ttu-id="84fcc-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="84fcc-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="84fcc-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84fcc-110">See also</span></span>
- [<span data-ttu-id="84fcc-111">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84fcc-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
