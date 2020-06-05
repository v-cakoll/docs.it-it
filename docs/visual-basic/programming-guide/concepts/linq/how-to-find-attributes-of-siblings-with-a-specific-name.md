---
title: 'Procedura: Trovare attributi di elementi di pari livello con un nome specifico (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 83b3ddca-830a-4b71-9756-9e4bdf907302
ms.openlocfilehash: 0317e03de6f671991d6d0a4247ca2e9c172439b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405274"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="d50db-102">Procedura: trovare attributi di elementi di pari livello con un nome specifico (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d50db-102">How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="d50db-103">In questo argomento viene illustrato come trovare tutti gli attributi degli elementi di pari livello del nodo di contesto.</span><span class="sxs-lookup"><span data-stu-id="d50db-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="d50db-104">Nella raccolta vengono restituiti solo gli attributi con un nome specifico.</span><span class="sxs-lookup"><span data-stu-id="d50db-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="d50db-105">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="d50db-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="d50db-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d50db-106">Example</span></span>  
 <span data-ttu-id="d50db-107">In questo esempio viene dapprima ricercato un elemento `Book`, quindi tutti gli elementi di pari livello denominati `Book` e infine tutti gli attributi denominati `id`.</span><span class="sxs-lookup"><span data-stu-id="d50db-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="d50db-108">Il risultato è una raccolta di attributi.</span><span class="sxs-lookup"><span data-stu-id="d50db-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="d50db-109">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d50db-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books as XDocument = XDocument.Load("Books.xml")  
Dim book As XElement = books.Root.<Book>(0)  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XAttribute) = _  
    From el In book.Parent.<Book> _  
    Select el.Attribute("id")  
  
' XPath expression  
Dim list2 As IEnumerable(Of XAttribute) = DirectCast(book. _  
    XPathEvaluate("../Book/@id"), IEnumerable).Cast(Of XAttribute)()  
  
If list1.Count() = list2.Count() And _  
        (list1.Intersect(list2)).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XAttribute In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="d50db-110">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="d50db-110">This example produces the following output:</span></span>  
  
```console  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a><span data-ttu-id="d50db-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d50db-111">See also</span></span>

- [<span data-ttu-id="d50db-112">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d50db-112">LINQ to XML for XPath Users (Visual Basic)</span></span>](linq-to-xml-for-xpath-users.md)
