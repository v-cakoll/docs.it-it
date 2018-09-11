---
title: 'Procedura: Filtrare in base a un elemento facoltativo (C#)'
ms.date: 07/20/2015
ms.assetid: f99e2f93-fca5-403f-8a0c-770761d4905a
ms.openlocfilehash: c781db261dbf673af7a11150971956b4c07da774
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271981"
---
# <a name="how-to-filter-on-an-optional-element-c"></a><span data-ttu-id="2b1e4-102">Procedura: Filtrare in base a un elemento facoltativo (C#)</span><span class="sxs-lookup"><span data-stu-id="2b1e4-102">How to: Filter on an Optional Element (C#)</span></span>
<span data-ttu-id="2b1e4-103">Talvolta si desidera filtrare in base a un elemento anche se non si è certi che esista nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="2b1e4-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="2b1e4-104">La ricerca deve essere eseguita in modo che se l'elemento specifico non include l'elemento figlio, non viene generata un'eccezione di riferimento null quando si applica un filtro sull'elemento.</span><span class="sxs-lookup"><span data-stu-id="2b1e4-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="2b1e4-105">Nell'esempio seguente l'elemento `Child5` non contiene un elemento figlio `Type`, tuttavia la query viene comunque eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="2b1e4-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b1e4-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b1e4-106">Example</span></span>  
 <span data-ttu-id="2b1e4-107">In questo esempio viene usato il metodo di estensione <xref:System.Xml.Linq.Extensions.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b1e4-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
var cList =  
    from typeElement in root.Elements().Elements("Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element("Text");  
foreach(string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="2b1e4-108">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2b1e4-108">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="2b1e4-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b1e4-109">Example</span></span>  
 <span data-ttu-id="2b1e4-110">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2b1e4-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="2b1e4-111">Per altre informazioni, vedere [Utilizzo degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="2b1e4-111">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
XNamespace ad = "http://www.adatum.com";  
var cList =  
    from typeElement in root.Elements().Elements(ad + "Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element(ad + "Text");  
foreach (string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="2b1e4-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2b1e4-112">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b1e4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b1e4-113">See Also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>  
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="2b1e4-114">Query di base (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2b1e4-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
- [<span data-ttu-id="2b1e4-115">Cenni preliminari sugli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="2b1e4-115">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [<span data-ttu-id="2b1e4-116">Operazioni di proiezione (C#)</span><span class="sxs-lookup"><span data-stu-id="2b1e4-116">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
