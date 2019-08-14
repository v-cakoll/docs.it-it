---
title: 'Procedura: Scrivere una query per trovare elementi in base al contesto (C#)'
ms.date: 07/20/2015
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
ms.openlocfilehash: f6fd0a9dc0f2579185f2f72997f1d406a885c636
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710031"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a><span data-ttu-id="255cd-102">Procedura: Scrivere una query per trovare elementi in base al contesto (C#)</span><span class="sxs-lookup"><span data-stu-id="255cd-102">How to: Write a Query that Finds Elements Based on Context (C#)</span></span>
<span data-ttu-id="255cd-103">A volte può essere necessario scrivere una query per selezionare gli elementi in base al contesto.</span><span class="sxs-lookup"><span data-stu-id="255cd-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="255cd-104">In questo caso è anche possibile scegliere un filtro basato sugli elementi di pari livello precedenti o successivi</span><span class="sxs-lookup"><span data-stu-id="255cd-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="255cd-105">oppure sugli elementi figlio o sui predecessori.</span><span class="sxs-lookup"><span data-stu-id="255cd-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="255cd-106">Per ottenere questo risultato, scrivere una query e usare i relativi risultati nella clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="255cd-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="255cd-107">Se è necessario verificare innanzitutto la presenza di valori Null e quindi testare il valore, è preferibile eseguire la query in una clausola `let` e poi usare i risultati nella clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="255cd-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="255cd-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="255cd-108">Example</span></span>  
 <span data-ttu-id="255cd-109">Nell'esempio seguente vengono selezionati tutti gli elementi `p` immediatamente seguiti da un elemento `ul`.</span><span class="sxs-lookup"><span data-stu-id="255cd-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants("p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name.LocalName == "ul"  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="255cd-110">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="255cd-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="255cd-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="255cd-111">Example</span></span>  
 <span data-ttu-id="255cd-112">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="255cd-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="255cd-113">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="255cd-113">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
XNamespace ad = "http://www.adatum.com";  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants(ad + "p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name == ad.GetName("ul")  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="255cd-114">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="255cd-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="255cd-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="255cd-115">See also</span></span>

- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
