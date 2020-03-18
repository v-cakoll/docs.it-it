---
title: Come trovare un elemento con un elemento figlio specifico (c'è)How to find an element with a specific child element (C
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 0536b1b92d4d7fc18b5d406bbcd24aefc6a840c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141151"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="113b3-102">Come trovare un elemento con un elemento figlio specifico (c'è)How to find an element with a specific child element (C</span><span class="sxs-lookup"><span data-stu-id="113b3-102">How to find an element with a specific child element (C#)</span></span>
<span data-ttu-id="113b3-103">In questo argomento viene illustrato come trovare un determinato elemento che include un elemento figlio con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="113b3-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="113b3-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="113b3-104">Example</span></span>  
 <span data-ttu-id="113b3-105">Nell'esempio viene ricercato l'elemento `Test` contenente un elemento figlio `CommandLine` con valore "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="113b3-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="113b3-106">Questo esempio usa il documento XML seguente: [File XML di esempio: configurazione di test (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="113b3-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="113b3-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="113b3-107">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="113b3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="113b3-108">Example</span></span>  
 <span data-ttu-id="113b3-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="113b3-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="113b3-110">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="113b3-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="113b3-111">Questo esempio usa il documento XML seguente: [File XML di esempio: configurazione di test in uno spazio dei nomi](./sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="113b3-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](./sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="113b3-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="113b3-112">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="113b3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="113b3-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- <span data-ttu-id="113b3-114">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)</span><span class="sxs-lookup"><span data-stu-id="113b3-114">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="113b3-115">Operazioni di proiezione (C#)</span><span class="sxs-lookup"><span data-stu-id="113b3-115">Projection Operations (C#)</span></span>](./projection-operations.md)
