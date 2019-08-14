---
title: 'Procedura: Trovare un elemento con un elemento figlio specifico (C#)'
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: a2ff30ebfc8936d351358f77c0655eb584e6d390
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710075"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="2141c-102">Procedura: Trovare un elemento con un elemento figlio specifico (C#)</span><span class="sxs-lookup"><span data-stu-id="2141c-102">How to: Find an Element with a Specific Child Element (C#)</span></span>
<span data-ttu-id="2141c-103">In questo argomento viene illustrato come trovare un determinato elemento che include un elemento figlio con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="2141c-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2141c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2141c-104">Example</span></span>  
 <span data-ttu-id="2141c-105">Nell'esempio viene ricercato l'elemento `Test` contenente un elemento figlio `CommandLine` con valore "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="2141c-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="2141c-106">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: configurazione di test (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2141c-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="2141c-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2141c-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="2141c-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="2141c-108">Example</span></span>  
 <span data-ttu-id="2141c-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2141c-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="2141c-110">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2141c-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="2141c-111">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: configurazione di test in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="2141c-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
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
  
 <span data-ttu-id="2141c-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2141c-112">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="2141c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2141c-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="2141c-114">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="2141c-114">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="2141c-115">Operazioni di proiezione (C#)</span><span class="sxs-lookup"><span data-stu-id="2141c-115">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
