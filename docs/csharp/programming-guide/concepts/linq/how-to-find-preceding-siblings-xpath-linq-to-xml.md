---
title: Come trovare elementi di pari livello precedenti (XPath-LINQ to XML) (C#)
description: In questo esempio C# viene confrontato l'asse di pari livello XPath preceding con l'asse LINQ to XML figlio XNode. ElementsBeforeSelf.
ms.date: 07/20/2015
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
ms.openlocfilehash: 4150c94fe1e30e7a72bb53b4c6c12481ee0bad19
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103462"
---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-c"></a>Come trovare elementi di pari livello precedenti (XPath-LINQ to XML) (C#)
Questo argomento confronta l'asse `preceding-sibling` XPath con l'asse <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> dell'elemento figlio di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 L'espressione XPath è:  
  
 `preceding-sibling::*`  
  
 Notare che i risultati di <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> e <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>, sono espressi nell'ordine dei documenti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene cercato l'elemento `FullAddress` e quindi vengono recuperati gli elementi precedenti usando l'asse `preceding-sibling`.  
  
 Questo esempio usa il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
  
XElement add = co.Element("Customers").Element("Customer").Element("FullAddress");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = add.ElementsBeforeSelf();  
  
// XPath expression  
IEnumerable<XElement> list2 = add.XPathSelectElements("preceding-sibling::*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list2)  
    Console.WriteLine(el);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```output  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
