---
title: 'Procedura: trovare pari livello (XPath-LINQ to XML) precedenti (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59055718-d0a7-4db3-8901-18dd33587703
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 54d70c1bfb3f1c2d3882b7582f6a11682eea46a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-visual-basic"></a>Procedura: trovare pari livello (XPath-LINQ to XML) precedenti (Visual Basic)
Questo argomento confronta l'asse `preceding-sibling` XPath con l'asse <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> dell'elemento figlio di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 L'espressione XPath è:  
  
 `preceding-sibling::*`  
  
 Notare che i risultati di <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> e <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>, sono espressi nell'ordine dei documenti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene cercato l'elemento `FullAddress` e quindi vengono recuperati gli elementi precedenti usando l'asse `preceding-sibling`.  
  
 Questo esempio usa il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
```vb  
Dim co As XElement = XElement.Load("CustomersOrders.xml")  
Dim add As XElement = co.<Customers>.<Customer>. _  
        <FullAddress>.FirstOrDefault  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = add.ElementsBeforeSelf()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = add.XPathSelectElements("preceding-sibling::*")  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list2  
    Console.WriteLine(el)  
Next  
```  
  
 Questo esempio produce il seguente output:  
  
```  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ to XML per gli utenti di XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
