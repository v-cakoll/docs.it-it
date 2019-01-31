---
title: 'Procedura: Eseguire una query in LINQ to XML tramite XPath (C#)'
ms.date: 07/20/2015
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
ms.openlocfilehash: a3e9cb29b9ba027cfc70eeb0cd163b24834dff83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564107"
---
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a><span data-ttu-id="acd03-102">Procedura: Eseguire una query in LINQ to XML tramite XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="acd03-102">How to: Query LINQ to XML Using XPath (C#)</span></span>
<span data-ttu-id="acd03-103">In questo argomento vengono presentati i metodi di estensione che consentono di eseguire una query su un albero XML usando XPath.</span><span class="sxs-lookup"><span data-stu-id="acd03-103">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="acd03-104">Per informazioni dettagliate sull'utilizzo di questi metodi di estensione, vedere <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="acd03-104">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="acd03-105">A meno che non esista un motivo molto specifico per eseguire query tramite XPATH, ad esempio l'uso esteso di codice legacy, è preferibile non usare XPATH con LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="acd03-105">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="acd03-106">Le query XPath non vengono eseguite con le stesse prestazioni delle query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acd03-106">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acd03-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="acd03-107">Example</span></span>  
 <span data-ttu-id="acd03-108">Nell'esempio seguente viene creata un piccolo albero XML e viene usato <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> per selezionare un set di elementi.</span><span class="sxs-lookup"><span data-stu-id="acd03-108">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child1", 2),  
    new XElement("Child1", 3),  
    new XElement("Child2", 4),  
    new XElement("Child2", 5),  
    new XElement("Child2", 6)  
);  
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");  
foreach (XElement el in list)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="acd03-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="acd03-109">This example produces the following output:</span></span>  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a><span data-ttu-id="acd03-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acd03-110">See also</span></span>

- <span data-ttu-id="acd03-111">[Advanced Query Techniques (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md) (Tecniche di query avanzate (LINQ to XML) in C#)</span><span class="sxs-lookup"><span data-stu-id="acd03-111">[Advanced Query Techniques (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)</span></span>
