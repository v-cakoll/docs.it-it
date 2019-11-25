---
title: 'Procedura: trovare il pari livello immediatamente precedente (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
ms.openlocfilehash: b2cb9efba0ef65a1b1ab1d7dadd54759f7d2a26b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344629"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a>How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)

A volte è necessario trovare l'elemento di pari livello immediatamente precedente a un nodo. A causa della differenza nella semantica dei predicati di posizione per gli assi di pari livello precedenti in XPath rispetto a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], si tratta di uno dei confronti più interessanti.

## <a name="example"></a>Esempio

In questo esempio la query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] utilizza l'operatore <xref:System.Linq.Enumerable.Last%2A> per trovare l'ultimo nodo nella raccolta restituita da <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>. Al contrario, l'espressione XPath utilizza un predicato con valore 1 per trovare l'elemento immediatamente precedente.

```vb
Dim root As XElement = _
    <Root>
        <Child1/>
        <Child2/>
        <Child3/>
        <Child4/>
    </Root>
Dim child4 As XElement = root.Element("Child4")

' LINQ to XML query
Dim el1 As XElement = child4.ElementsBeforeSelf().Last()

' XPath expression
Dim el2 As XElement = _
    DirectCast(child4.XPathEvaluate("preceding-sibling::*[1]"),  _
    IEnumerable).Cast(Of XElement)().First()

If el1 Is el2 Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
Console.WriteLine(el1)
```

Questo esempio produce il seguente output:

```console
Results are identical
<Child3 />
```

## <a name="see-also"></a>Vedere anche

- [LINQ to XML for XPath Users (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
