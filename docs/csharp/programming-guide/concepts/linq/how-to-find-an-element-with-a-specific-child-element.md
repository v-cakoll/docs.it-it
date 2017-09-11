---
title: 'Procedura: Trovare un elemento con un elemento figlio specifico (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: dcbfe8efb16dd5e672deeac2fffea109689dacc5
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="beacf-102">Procedura: Trovare un elemento con un elemento figlio specifico (C#)</span><span class="sxs-lookup"><span data-stu-id="beacf-102">How to: Find an Element with a Specific Child Element (C#)</span></span>
<span data-ttu-id="beacf-103">In questo argomento viene illustrato come trovare un determinato elemento che include un elemento figlio con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="beacf-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="beacf-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="beacf-104">Example</span></span>  
 <span data-ttu-id="beacf-105">Nell'esempio viene ricercato l'elemento `Test` contenente un elemento figlio `CommandLine` con valore "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="beacf-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="beacf-106">Questo esempio usa il documento XML seguente: [File XML di esempio: configurazione di test (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="beacf-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="beacf-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="beacf-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="beacf-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="beacf-108">Example</span></span>  
 <span data-ttu-id="beacf-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="beacf-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="beacf-110">Per altre informazioni, vedere [Uso degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="beacf-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="beacf-111">Questo esempio usa il documento XML seguente: [File XML di esempio: configurazione di test in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="beacf-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
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
  
 <span data-ttu-id="beacf-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="beacf-112">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="beacf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="beacf-113">See Also</span></span>  
 <span data-ttu-id="beacf-114"><xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="beacf-114"><xref:System.Xml.Linq.XElement.Attribute%2A></span></span>   
 <span data-ttu-id="beacf-115"><xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="beacf-115"><xref:System.Xml.Linq.XContainer.Elements%2A></span></span>   
 <span data-ttu-id="beacf-116">[Query di base (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="beacf-116">[Basic Queries (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span></span>  
 <span data-ttu-id="beacf-117">[Panoramica degli operatori query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="beacf-117">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="beacf-118">Operazioni di proiezione (C#)</span><span class="sxs-lookup"><span data-stu-id="beacf-118">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)

