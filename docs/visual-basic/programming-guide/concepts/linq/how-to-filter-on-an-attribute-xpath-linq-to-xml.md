---
title: 'Procedura: Filtrare in un attributo (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: ffefb9d6-45ec-4677-a396-dd9c2b36298f
ms.openlocfilehash: 4ee90e90e1087ffeeeefb475b637f3307a179bff
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250033"
---
# <a name="how-to-filter-on-an-attribute-xpath-linq-to-xml-visual-basic"></a>Procedura: Filtrare in un attributo (XPath-LINQ to XML) (Visual Basic)
In questo argomento viene illustrato come ottenere gli elementi discendente con un nome specificato e con un attributo con un valore specificato.  
  
 L'espressione XPath è:  
  
 `.//Address[@Type='Shipping']`  
  
## <a name="example"></a>Esempio  
 In questo esempio vengono individuati tutti gli elementi discendente il cui nome è `Address` e in cui il valore dell'attributo `Type` è "Shipping".  
  
 Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```vb  
Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    From el In po...<Address> _  
    Where el.@Type = "Shipping" _  
    Select el  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = _  
    po.XPathSelectElements(".//Address[@Type='Shipping']")  
  
If (list1.Count = list2.Count And _  
        list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Questo esempio produce il seguente output:  
  
```console
Results are identical  
<Address Type="Shipping">  
  <Name>Ellen Adams</Name>  
  <Street>123 Maple Street</Street>  
  <City>Mill Valley</City>  
  <State>CA</State>  
  <Zip>10999</Zip>  
  <Country>USA</Country>  
</Address>  
<Address Type="Shipping">  
  <Name>Cristian Osorio</Name>  
  <Street>456 Main Street</Street>  
  <City>Buffalo</City>  
  <State>NY</State>  
  <Zip>98112</Zip>  
  <Country>USA</Country>  
</Address>  
<Address Type="Shipping">  
  <Name>Jessica Arnold</Name>  
  <Street>4055 Madison Ave</Street>  
  <City>Seattle</City>  
  <State>WA</State>  
  <Zip>98112</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to XML per gli utenti di XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
