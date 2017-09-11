---
title: 'Procedura: trovare il pari livello immediatamente precedente (XPath-LINQ to XML) (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 3e5c0100ea2a5d4ad3e5f503f2680f946e08e6fd
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="f2821-102">Procedura: trovare il pari livello immediatamente precedente (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2821-102">How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="f2821-103">A volte è necessario trovare l'elemento di pari livello immediatamente precedente a un nodo.</span><span class="sxs-lookup"><span data-stu-id="f2821-103">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="f2821-104">A causa della differenza nella semantica dei predicati di posizione per gli assi di pari livello precedenti in XPath rispetto a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], si tratta di uno dei confronti più interessanti.</span><span class="sxs-lookup"><span data-stu-id="f2821-104">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], this is one of the more interesting comparisons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2821-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2821-105">Example</span></span>  
 <span data-ttu-id="f2821-106">In questo esempio, il [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query utilizza l' <xref:System.Linq.Enumerable.Last%2A>operatore per trovare l'ultimo nodo nella raccolta restituita da <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A> </xref:System.Linq.Enumerable.Last%2A></span><span class="sxs-lookup"><span data-stu-id="f2821-106">In this example, the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="f2821-107">Al contrario, l'espressione XPath utilizza un predicato con valore 1 per trovare l'elemento immediatamente precedente.</span><span class="sxs-lookup"><span data-stu-id="f2821-107">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>  
  
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
  
 <span data-ttu-id="f2821-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="f2821-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Child3 />  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2821-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2821-109">See Also</span></span>  
 [<span data-ttu-id="f2821-110">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2821-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

