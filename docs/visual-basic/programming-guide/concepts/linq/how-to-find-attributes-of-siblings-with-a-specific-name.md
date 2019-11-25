---
title: 'Procedura: trovare attributi di pari livello con un nome specifico (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 83b3ddca-830a-4b71-9756-9e4bdf907302
ms.openlocfilehash: ea4492dbbe9dc8e32c675e1a938cda0d10321b7a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343669"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-visual-basic"></a>How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (Visual Basic)
In questo argomento viene illustrato come trovare tutti gli attributi degli elementi di pari livello del nodo di contesto. Nella raccolta vengono restituiti solo gli attributi con un nome specifico.  
  
 L'espressione XPath è:  
  
 `../Book/@id`  
  
## <a name="example"></a>Esempio  
 In questo esempio viene dapprima ricercato un elemento `Book`, quindi tutti gli elementi di pari livello denominati `Book` e infine tutti gli attributi denominati `id`. Il risultato è una raccolta di attributi.  
  
 Questo esempio usa il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
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
  
 Questo esempio produce il seguente output:  
  
```console  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to XML for XPath Users (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
