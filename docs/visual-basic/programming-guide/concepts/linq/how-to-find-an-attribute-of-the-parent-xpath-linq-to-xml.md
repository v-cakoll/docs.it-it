---
title: "Procedura: trovare un attributo dell'elemento padre (XPath-LINQ to XML)"
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: c4cb2f2e52aeaa42fd69b83c19c47fd205d48cbc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352954"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a>Procedura: trovare un attributo dell'elemento padre (XPath-LINQ to XML) (Visual Basic)
In questo argomento viene illustrato come spostarsi all'elemento padre e trovare un relativo attributo.  
  
 L'espressione XPath è:  
  
 `../@id`  
  
## <a name="example"></a>Esempio  
 Viene innanzitutto individuato un elemento `Author`. Quindi, viene individuato l'attributo `id` dell'elemento padre.  
  
 Nell'esempio viene usato il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()  
  
' LINQ to XML query  
Dim att1 As XAttribute = author.Parent.Attribute("id")  
  
' XPath expression  
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _  
    IEnumerable).Cast(Of XAttribute)().First()  
  
If att1 Is att2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(att1)  
```  
  
 Questo esempio produce il seguente output:  
  
```console  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to XML per gli utenti di XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
