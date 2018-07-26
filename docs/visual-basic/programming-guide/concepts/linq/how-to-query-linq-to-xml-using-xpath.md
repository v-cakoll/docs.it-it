---
title: 'Procedura: eseguire una Query LINQ to XML tramite XPath (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: e1f69a20-1efa-452d-9089-c472fa84b3d5
ms.openlocfilehash: d8f23bd8417c3f59377e5e677b08e403ecc1122d
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244348"
---
# <a name="how-to-query-linq-to-xml-using-xpath-visual-basic"></a><span data-ttu-id="274a7-102">Procedura: eseguire una Query LINQ to XML tramite XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="274a7-102">How to: Query LINQ to XML Using XPath (Visual Basic)</span></span>
<span data-ttu-id="274a7-103">In questo argomento vengono presentati i metodi di estensione che consentono di eseguire una query su un albero XML usando XPath.</span><span class="sxs-lookup"><span data-stu-id="274a7-103">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="274a7-104">Per informazioni dettagliate sull'utilizzo di questi metodi di estensione, vedere <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="274a7-104">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="274a7-105">A meno che non esista un motivo molto specifico per eseguire query tramite XPATH, ad esempio l'uso esteso di codice legacy, è preferibile non usare XPATH con LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="274a7-105">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="274a7-106">Le query XPath non vengono eseguite con le stesse prestazioni delle query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="274a7-106">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="274a7-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="274a7-107">Example</span></span>  
 <span data-ttu-id="274a7-108">Nell'esempio seguente viene creata un piccolo albero XML e viene usato <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> per selezionare un set di elementi.</span><span class="sxs-lookup"><span data-stu-id="274a7-108">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child1>2</Child1>  
        <Child1>3</Child1>  
        <Child2>4</Child2>  
        <Child2>5</Child2>  
        <Child2>6</Child2>  
    </Root>  
  
Dim list As IEnumerable(Of XElement) = root.XPathSelectElements("./Child2")  
For Each el As XElement In list  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="274a7-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="274a7-109">This example produces the following output:</span></span>  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a><span data-ttu-id="274a7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="274a7-110">See Also</span></span>  
 [<span data-ttu-id="274a7-111">Query tecniche avanzate (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="274a7-111">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
