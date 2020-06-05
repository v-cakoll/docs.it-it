---
title: 'Procedura: Trovare elementi discendenti (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: e7e2dc9e-bda9-420d-a5b1-4fabf1cca46b
ms.openlocfilehash: ee67a54116a7d91f6cf6af179d6398a4dcece9c4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405235"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-visual-basic"></a>Procedura: trovare elementi discendenti (XPath-LINQ to XML) (Visual Basic)
In questo argomento viene illustrato come ottenere gli elementi discendenti con un determinato nome.  
  
 L'espressione XPath è `//Name`.  
  
## <a name="example"></a>Esempio  
 In questo esempio vengono trovati tutti i discendenti denominati `Name`.  
  
 Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```vb  
      Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = po...<Name>  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("//Name")  
  
If (list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```console
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to XML per gli utenti di XPath (Visual Basic)](linq-to-xml-for-xpath-users.md)
