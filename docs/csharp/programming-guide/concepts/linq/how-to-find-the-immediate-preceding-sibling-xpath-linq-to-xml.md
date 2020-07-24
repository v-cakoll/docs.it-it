---
title: Come trovare l'elemento di pari livello immediatamente precedente (XPath-LINQ to XML) (C#)
description: In questo esempio di C# viene confrontato XPath con LINQ to XML per individuare l'elemento di pari livello immediatamente precedente a un nodo.
ms.date: 07/20/2015
ms.assetid: 74c06201-0b1b-4b5e-b3ac-0092980614e6
ms.openlocfilehash: eaee7f1205ce0d0b2a9c2c41d96ba532573a1384
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105206"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-c"></a><span data-ttu-id="4f3cc-103">Come trovare l'elemento di pari livello immediatamente precedente (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="4f3cc-103">How to find the immediate preceding sibling (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="4f3cc-104">A volte è necessario trovare l'elemento di pari livello immediatamente precedente a un nodo.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-104">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="4f3cc-105">A causa della differenza nella semantica dei predicati di posizione per gli assi di pari livello precedenti in XPath rispetto a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], si tratta di uno dei confronti più interessanti.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-105">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f3cc-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f3cc-106">Example</span></span>  
 <span data-ttu-id="4f3cc-107">In questo esempio la query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] utilizza l'operatore <xref:System.Linq.Enumerable.Last%2A> per trovare l'ultimo nodo nella raccolta restituita da <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-107">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="4f3cc-108">Al contrario, l'espressione XPath utilizza un predicato con valore 1 per trovare l'elemento immediatamente precedente.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-108">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
    @"<Root>  
    <Child1/>  
    <Child2/>  
    <Child3/>  
    <Child4/>  
</Root>");  
XElement child4 = root.Element("Child4");  
  
// LINQ to XML query  
XElement el1 =  
    child4  
    .ElementsBeforeSelf()  
    .Last();  
  
// XPath expression  
XElement el2 =  
    ((IEnumerable)child4  
                 .XPathEvaluate("preceding-sibling::*[1]"))  
                 .Cast<XElement>()  
                 .First();  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 <span data-ttu-id="4f3cc-109">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="4f3cc-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Child3 />  
```  
