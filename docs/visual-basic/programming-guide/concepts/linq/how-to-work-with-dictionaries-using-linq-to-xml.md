---
title: 'Procedura: utilizzare dizionari tramite LINQ to XML (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 6cb3f969-1986-414a-b850-87418712edea
ms.openlocfilehash: b6e41f61358563472f49b22df389df00e721503e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644823"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-visual-basic"></a><span data-ttu-id="9fa38-102">Procedura: utilizzare dizionari tramite LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fa38-102">How to: Work with Dictionaries Using LINQ to XML (Visual Basic)</span></span>
<span data-ttu-id="9fa38-103">Spesso risulta utile eseguire la conversione in XML di varie strutture dati e la riconversione di altre strutture dati in XML.</span><span class="sxs-lookup"><span data-stu-id="9fa38-103">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="9fa38-104">In questo argomento è illustrata un'implementazione specifica di questo approccio generale con la conversione di un oggetto <xref:System.Collections.Generic.Dictionary%602> in XML e viceversa.</span><span class="sxs-lookup"><span data-stu-id="9fa38-104">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fa38-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="9fa38-105">Example</span></span>  
 <span data-ttu-id="9fa38-106">Questo esempio Usa valori letterali XML e una query in un'espressione incorporata.</span><span class="sxs-lookup"><span data-stu-id="9fa38-106">This example uses XML literals and a query in an embedded expression.</span></span> <span data-ttu-id="9fa38-107">La query proietta nuovi <xref:System.Xml.Linq.XElement> oggetti, che quindi diventano il nuovo contenuto per il `Root` <xref:System.Xml.Linq.XElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="9fa38-107">The query projects new <xref:System.Xml.Linq.XElement> objects, which then become the new content for the `Root` <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```vb  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)()  
dict.Add("Child1", "Value1")  
dict.Add("Child2", "Value2")  
dict.Add("Child3", "Value3")  
dict.Add("Child4", "Value4")  
Dim root As XElement = _  
    <Root>  
        <%= From keyValue In dict _  
            Select New XElement(keyValue.Key, keyValue.Value) %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="9fa38-108">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="9fa38-108">This code produces the following output:</span></span>  
  
```xml  
          <Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="9fa38-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="9fa38-109">Example</span></span>  
 <span data-ttu-id="9fa38-110">Nel codice seguente viene creato un dizionario da XML.</span><span class="sxs-lookup"><span data-stu-id="9fa38-110">The following code creates a dictionary from XML.</span></span>  
  
```vb  
Dim root As XElement = _  
        <Root>  
            <Child1>Value1</Child1>  
            <Child2>Value2</Child2>  
            <Child3>Value3</Child3>  
            <Child4>Value4</Child4>  
        </Root>  
  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)  
For Each el As XElement In root.Elements  
    dict.Add(el.Name.LocalName, el.Value)  
Next  
For Each str As String In dict.Keys  
    Console.WriteLine("{0}:{1}", str, dict(str))  
Next  
```  
  
 <span data-ttu-id="9fa38-111">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="9fa38-111">This code produces the following output:</span></span>  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fa38-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fa38-112">See Also</span></span>  
 [<span data-ttu-id="9fa38-113">Proiezioni e trasformazioni (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fa38-113">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
