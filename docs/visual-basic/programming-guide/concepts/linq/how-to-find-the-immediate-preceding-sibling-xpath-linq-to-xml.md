---
title: "Procedura: trovare l'elemento di pari livello immediatamente precedente (XPath-LINQ to XML) (Visual Basic)"
ms.date: 07/20/2015
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
ms.openlocfilehash: bc54239d2ddaafcc46413ed13c274449daaba0c7
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320596"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="4d13d-102">Procedura: trovare l'elemento di pari livello immediatamente precedente (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d13d-102">How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="4d13d-103">A volte è necessario trovare l'elemento di pari livello immediatamente precedente a un nodo.</span><span class="sxs-lookup"><span data-stu-id="4d13d-103">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="4d13d-104">A causa della differenza nella semantica dei predicati di posizione per gli assi di pari livello precedenti in XPath rispetto a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], si tratta di uno dei confronti più interessanti.</span><span class="sxs-lookup"><span data-stu-id="4d13d-104">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d13d-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d13d-105">Example</span></span>  
 <span data-ttu-id="4d13d-106">In questo esempio la query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] utilizza l'operatore <xref:System.Linq.Enumerable.Last%2A> per trovare l'ultimo nodo nella raccolta restituita da <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d13d-106">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="4d13d-107">Al contrario, l'espressione XPath utilizza un predicato con valore 1 per trovare l'elemento immediatamente precedente.</span><span class="sxs-lookup"><span data-stu-id="4d13d-107">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>  
  
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
  
 <span data-ttu-id="4d13d-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4d13d-108">This example produces the following output:</span></span>  
  
```console
Results are identical  
<Child3 />  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d13d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d13d-109">See also</span></span>

- [<span data-ttu-id="4d13d-110">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d13d-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
