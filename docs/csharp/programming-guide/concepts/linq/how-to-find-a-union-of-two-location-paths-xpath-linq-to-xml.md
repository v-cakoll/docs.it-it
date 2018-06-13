---
title: "Procedura: Trovare un'unione di due percorsi (XPath-LINQ to XML) (C#)"
ms.date: 07/20/2015
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
ms.openlocfilehash: cd98c1da2f2f8653c5db36f89a63dfdc7a7ab691
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333297"
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a>Procedura: Trovare un'unione di due percorsi (XPath-LINQ to XML) (C#)
In XPath è possibile trovare l'unione dei risultati di due percorsi di posizione XPath.  
  
 L'espressione XPath è:  
  
 `//Category|//Price`  
  
 È possibile ottenere gli stessi risultati usando l'operatore di query standard <xref:System.Linq.Enumerable.Concat%2A>.  
  
## <a name="example"></a>Esempio  
 In questo esempio vengono trovati tutti gli elementi `Category` e tutti gli elementi `Price`, che vengono concatenati in un'unica raccolta. Si noti che la query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] chiama <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> per ordinare i risultati. Anche i risultati della valutazione dell'espressione di XPath sono nell'ordine del documento.  
  
 Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).  
  
```csharp  
XDocument data = XDocument.Load("Data.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    data  
    .Descendants("Category")  
    .Concat(  
        data  
        .Descendants("Price")  
    )  
    .InDocumentOrder();  
  
// XPath expression  
IEnumerable<XElement> list2 = data.XPathSelectElements("//Category|//Price");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Questo esempio produce il seguente output:  
  
```  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ to XML per gli utenti di XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
