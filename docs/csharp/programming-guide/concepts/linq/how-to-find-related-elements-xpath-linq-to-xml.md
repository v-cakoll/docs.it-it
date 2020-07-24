---
title: Come trovare elementi correlati (XPath-LINQ to XML) (C#)
description: In questo esempio di C# viene confrontato XPath con LINQ to XML come ottenere un elemento selezionando un attributo a cui fa riferimento il valore di un altro elemento.
ms.date: 07/20/2015
ms.assetid: 41b386ee-562d-4841-bd6b-e44a7eb69f26
ms.openlocfilehash: 4423e7d719d39e71bcbcc9e88d052c6aff4ffb05
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105257"
---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="0d84c-103">Come trovare elementi correlati (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0d84c-103">How to find related elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="0d84c-104">In questo argomento viene illustrato come ottenere un elemento selezionando un attributo cui viene fatto riferimento dal valore di un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="0d84c-104">This topic shows how to get an element selecting on an attribute that is referred to by the value of another element.</span></span>  
  
 <span data-ttu-id="0d84c-105">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="0d84c-105">The XPath expression is:</span></span>  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a><span data-ttu-id="0d84c-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d84c-106">Example</span></span>  
 <span data-ttu-id="0d84c-107">In questo esempio viene cercato il dodicesimo elemento `Order` e quindi il cliente relativo a tale ordine.</span><span class="sxs-lookup"><span data-stu-id="0d84c-107">This example finds the 12th `Order` element, and then finds the customer for that order.</span></span>  
  
 <span data-ttu-id="0d84c-108">Notare che in .NET l'indicizzazione in un elenco è basata su "zero".</span><span class="sxs-lookup"><span data-stu-id="0d84c-108">Note that indexing into a list in .NET is 'zero' based.</span></span> <span data-ttu-id="0d84c-109">L'indicizzazione in una raccolta di nodi di un predicato XPath è basata su 'uno'.</span><span class="sxs-lookup"><span data-stu-id="0d84c-109">Indexing into a collection of nodes in an XPath predicate is 'one' based.</span></span> <span data-ttu-id="0d84c-110">L'esempio rispecchia questa differenza.</span><span class="sxs-lookup"><span data-stu-id="0d84c-110">This example reflects this difference.</span></span>  
  
 <span data-ttu-id="0d84c-111">Questo esempio usa il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="0d84c-111">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
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
  
 <span data-ttu-id="0d84c-112">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="0d84c-112">This example produces the following output:</span></span>  
  
```output  
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
