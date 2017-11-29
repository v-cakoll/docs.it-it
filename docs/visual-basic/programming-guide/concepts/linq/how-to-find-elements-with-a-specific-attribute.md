---
title: 'Procedura: trovare elementi con un attributo specifico (XPath-LINQ to XML) (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bb38d2c-bc7c-4196-8909-aaf41fb86b28
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c4904ef70b2c978d73514302e726aba8f14fc20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="9bd03-102">Procedura: trovare elementi con un attributo specifico (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bd03-102">How to: Find Elements with a Specific Attribute (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="9bd03-103">Talvolta si desidera individuare tutti gli elementi con un attributo specifico.</span><span class="sxs-lookup"><span data-stu-id="9bd03-103">Sometimes you want to find all elements that have a specific attribute.</span></span> <span data-ttu-id="9bd03-104">Il contenuto dell'attributo non è rilevante</span><span class="sxs-lookup"><span data-stu-id="9bd03-104">You are not concerned about the contents of the attribute.</span></span> <span data-ttu-id="9bd03-105">perché si desidera solo individuare gli elementi in cui tale attributo è presente.</span><span class="sxs-lookup"><span data-stu-id="9bd03-105">Instead, you want to select based on the existence of the attribute.</span></span>  
  
 <span data-ttu-id="9bd03-106">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="9bd03-106">The XPath expression is:</span></span>  
  
 `./*[@Select]`  
  
## <a name="example"></a><span data-ttu-id="9bd03-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="9bd03-107">Example</span></span>  
 <span data-ttu-id="9bd03-108">Nel codice seguente vengono selezionati solo gli elementi con attributo `Select`.</span><span class="sxs-lookup"><span data-stu-id="9bd03-108">The following code selects just the elements that have the `Select` attribute.</span></span>  
  
```vb  
Dim doc As XElement = _   
    <Root>  
        <Child1>1</Child1>  
        <Child2 Select='true'>2</Child2>  
        <Child3>3</Child3>  
        <Child4 Select='true'>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    From el In doc.Elements() _  
    Where el.@Select <> Nothing _  
    Select el  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = DirectCast(doc.XPathEvaluate _  
    ("./*[@Select]"), IEnumerable).Cast(Of XElement)()  
  
If list1.Count() = list2.Count() And _  
    list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="9bd03-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="9bd03-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bd03-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bd03-110">See Also</span></span>  
 [<span data-ttu-id="9bd03-111">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bd03-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
