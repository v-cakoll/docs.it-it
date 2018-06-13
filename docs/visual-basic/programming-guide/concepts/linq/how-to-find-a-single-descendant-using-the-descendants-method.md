---
title: 'Procedura: trovare un singolo discendente con il metodo Descendants (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 0c03468c-efc8-4140-98f3-fb67acd9e8e1
ms.openlocfilehash: 5c4e857d28ab4660638198c054cf93bf94a621a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642846"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-visual-basic"></a><span data-ttu-id="e90fa-102">Procedura: trovare un singolo discendente con il metodo Descendants (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e90fa-102">How to: Find a Single Descendant Using the Descendants Method (Visual Basic)</span></span>
<span data-ttu-id="e90fa-103">È possibile usare il metodo <xref:System.Xml.Linq.XContainer.Descendants%2A> dell'asse per scrivere rapidamente codice per trovare un singolo elemento con un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="e90fa-103">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="e90fa-104">Questa tecnica è particolarmente utile quando si desidera trovare un particolare discendente con un nome specifico.</span><span class="sxs-lookup"><span data-stu-id="e90fa-104">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="e90fa-105">È possibile scrivere il codice per spostarsi fino all'elemento desiderato, ma risulta in genere più veloce e semplice scrivere il codice usando l'asse <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="e90fa-105">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e90fa-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e90fa-106">Example</span></span>  
 <span data-ttu-id="e90fa-107">In questo esempio viene usato l'operatore di query standard <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="e90fa-107">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1>GC1 Value</GrandChild1>  
        </Child1>  
        <Child2>  
            <GrandChild2>GC2 Value</GrandChild2>  
        </Child2>  
        <Child3>  
            <GrandChild3>GC3 Value</GrandChild3>  
        </Child3>  
        <Child4>  
            <GrandChild4>GC4 Value</GrandChild4>  
        </Child4>  
    </Root>  
Dim grandChild3 As String = _  
    (From el In root...<GrandChild3> _  
    Select el).First()  
Console.WriteLine(grandChild3)  
```  
  
 <span data-ttu-id="e90fa-108">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="e90fa-108">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="e90fa-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="e90fa-109">Example</span></span>  
 <span data-ttu-id="e90fa-110">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e90fa-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="e90fa-111">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="e90fa-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child1>  
                    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
                </aw:Child1>  
                <aw:Child2>  
                    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
                </aw:Child2>  
                <aw:Child3>  
                    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
                </aw:Child3>  
                <aw:Child4>  
                    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
                </aw:Child4>  
            </aw:Root>  
        Dim grandChild3 As String = _  
            (From el In root...<aw:GrandChild3> _  
            Select el).First()  
        Console.WriteLine(grandChild3)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="e90fa-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="e90fa-112">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="see-also"></a><span data-ttu-id="e90fa-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e90fa-113">See Also</span></span>  
 [<span data-ttu-id="e90fa-114">Le query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e90fa-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
