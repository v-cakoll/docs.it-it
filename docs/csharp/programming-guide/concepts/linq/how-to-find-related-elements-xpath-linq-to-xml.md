---
title: 'Procedura: Trovare elementi correlati (XPath-LINQ to XML) (C#)'
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
ms.assetid: 41b386ee-562d-4841-bd6b-e44a7eb69f26
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3cc73ab69adb66fd1158637a8a3c67008d8e8663
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="d843e-102">Procedura: Trovare elementi correlati (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="d843e-102">How to: Find Related Elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="d843e-103">In questo argomento viene illustrato come ottenere un elemento selezionando un attributo cui viene fatto riferimento dal valore di un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="d843e-103">This topic shows how to get an element selecting on an attribute that is referred to by the value of another element.</span></span>  
  
 <span data-ttu-id="d843e-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="d843e-104">The XPath expression is:</span></span>  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a><span data-ttu-id="d843e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d843e-105">Example</span></span>  
 <span data-ttu-id="d843e-106">In questo esempio viene cercato il dodicesimo elemento `Order` e quindi il cliente relativo a tale ordine.</span><span class="sxs-lookup"><span data-stu-id="d843e-106">This example finds the 12th `Order` element, and then finds the customer for that order.</span></span>  
  
 <span data-ttu-id="d843e-107">Notare che in .NET l'indicizzazione in un elenco è basata su 'zero'.</span><span class="sxs-lookup"><span data-stu-id="d843e-107">Note that indexing into a list in .Net is 'zero' based.</span></span> <span data-ttu-id="d843e-108">L'indicizzazione in una raccolta di nodi di un predicato XPath è basata su 'uno'.</span><span class="sxs-lookup"><span data-stu-id="d843e-108">Indexing into a collection of nodes in an XPath predicate is 'one' based.</span></span> <span data-ttu-id="d843e-109">L'esempio rispecchia questa differenza.</span><span class="sxs-lookup"><span data-stu-id="d843e-109">This example reflects this difference.</span></span>  
  
 <span data-ttu-id="d843e-110">Questo esempio usa il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="d843e-110">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XDocument co = XDocument.Load("CustomersOrders.xml");  
  
// LINQ to XML query  
XElement customer1 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .ToList()[11]  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// An alternate way to write the query that avoids creation  
// of a System.Collections.Generic.List:  
XElement customer2 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .Skip(11).First()  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// XPath expression  
XElement customer3 = co.XPathSelectElement(  
  ".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]");  
  
if (customer1 == customer2 && customer1 == customer3)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(customer1);  
```  
  
 <span data-ttu-id="d843e-111">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="d843e-111">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d843e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d843e-112">See Also</span></span>  
 [<span data-ttu-id="d843e-113">LINQ to XML per gli utenti di XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="d843e-113">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

