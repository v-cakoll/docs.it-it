---
title: Come trovare elementi con un attributo specifico (XPath-LINQ to XML) (C#)
description: In questo esempio di C# viene confrontato XPath con LINQ to XML per individuare gli elementi con un attributo specifico.
ms.date: 07/20/2015
ms.assetid: daed00dd-923a-43be-8a90-eee406f6f574
ms.openlocfilehash: eb0b5c27fb3993b487c5e8d70c6562c1d0562860
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105262"
---
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-c"></a><span data-ttu-id="3f9f6-103">Come trovare elementi con un attributo specifico (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-103">How to find elements with a specific attribute (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="3f9f6-104">Talvolta si desidera individuare tutti gli elementi con un attributo specifico.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-104">Sometimes you want to find all elements that have a specific attribute.</span></span> <span data-ttu-id="3f9f6-105">Il contenuto dell'attributo non è rilevante</span><span class="sxs-lookup"><span data-stu-id="3f9f6-105">You are not concerned about the contents of the attribute.</span></span> <span data-ttu-id="3f9f6-106">perché si desidera solo individuare gli elementi in cui tale attributo è presente.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-106">Instead, you want to select based on the existence of the attribute.</span></span>  
  
 <span data-ttu-id="3f9f6-107">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="3f9f6-107">The XPath expression is:</span></span>  
  
 `./*[@Select]`  
  
## <a name="example"></a><span data-ttu-id="3f9f6-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f9f6-108">Example</span></span>  
 <span data-ttu-id="3f9f6-109">Nel codice seguente vengono selezionati solo gli elementi con attributo `Select`.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-109">The following code selects just the elements that have the `Select` attribute.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(  
@"<Root>  
    <Child1>1</Child1>  
    <Child2 Select='true'>2</Child2>  
    <Child3>3</Child3>  
    <Child4 Select='true'>4</Child4>  
    <Child5>5</Child5>  
</Root>");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    from el in doc.Elements()  
    where el.Attribute("Select") != null  
    select el;  
  
// XPath expression  
IEnumerable<XElement> list2 =  
    ((IEnumerable)doc.XPathEvaluate("./*[@Select]")).Cast<XElement>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="3f9f6-110">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="3f9f6-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  