---
title: 'Procedura: trovare elementi correlati (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 6b0ef058-d704-48a5-98cd-33f00d088af9
ms.openlocfilehash: 24a8f252d0c703cc7883ae1408120b8cae018331
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643172"
---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="8eda5-102">Procedura: trovare elementi correlati (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8eda5-102">How to: Find Related Elements (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="8eda5-103">In questo argomento viene illustrato come ottenere un elemento selezionando un attributo cui viene fatto riferimento dal valore di un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="8eda5-103">This topic shows how to get an element selecting on an attribute that is referred to by the value of another element.</span></span>  
  
 <span data-ttu-id="8eda5-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="8eda5-104">The XPath expression is:</span></span>  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a><span data-ttu-id="8eda5-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="8eda5-105">Example</span></span>  
 <span data-ttu-id="8eda5-106">In questo esempio viene cercato il dodicesimo elemento `Order` e quindi il cliente relativo a tale ordine.</span><span class="sxs-lookup"><span data-stu-id="8eda5-106">This example finds the 12th `Order` element, and then finds the customer for that order.</span></span>  
  
 <span data-ttu-id="8eda5-107">Notare che in .NET l'indicizzazione in un elenco è basata su 'zero'.</span><span class="sxs-lookup"><span data-stu-id="8eda5-107">Note that indexing into a list in .Net is 'zero' based.</span></span> <span data-ttu-id="8eda5-108">L'indicizzazione in una raccolta di nodi di un predicato XPath è basata su 'uno'.</span><span class="sxs-lookup"><span data-stu-id="8eda5-108">Indexing into a collection of nodes in an XPath predicate is 'one' based.</span></span> <span data-ttu-id="8eda5-109">L'esempio rispecchia questa differenza.</span><span class="sxs-lookup"><span data-stu-id="8eda5-109">This example reflects this difference.</span></span>  
  
 <span data-ttu-id="8eda5-110">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: Customers e Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8eda5-110">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim co As XDocument = XDocument.Load("CustomersOrders.xml")  
  
' LINQ to XML query  
Dim customer1 As XElement = ( _  
    From el In co...<Customer> _  
    Where el.@CustomerID = co.<Root>.<Orders>.<Order>. _  
        ToList()(11).<CustomerID>(0).Value _  
    Select el).First()  
  
' An alternate way to write the query that avoids creation  
' of a System.Collections.Generic.List:  
Dim customer2 As XElement = ( _  
    From el In co...<Customer> _  
    Where el.@CustomerID = co.<Root>.<Orders>.<Order>. _  
        Skip(11).First().<CustomerID>(0).Value _  
    Select el).First()  
  
' XPath expression  
Dim customer3 As XElement = co.XPathSelectElement _  
    (".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]")  
  
If customer1 Is customer2 And customer1 Is customer3 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(customer1)  
```  
  
 <span data-ttu-id="8eda5-111">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8eda5-111">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Customer CustomerID="HUNGC">  
  <CompanyName>Hungry Coyote Import Store</CompanyName>  
  <ContactName>Yoshi Latimer</ContactName>  
  <ContactTitle>Sales Representative</ContactTitle>  
  <Phone>(503) 555-6874</Phone>  
  <Fax>(503) 555-2376</Fax>  
  <FullAddress>  
    <Address>City Center Plaza 516 Main St.</Address>  
    <City>Elgin</City>  
    <Region>OR</Region>  
    <PostalCode>97827</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
</Customer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8eda5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8eda5-112">See Also</span></span>  
 [<span data-ttu-id="8eda5-113">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8eda5-113">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
