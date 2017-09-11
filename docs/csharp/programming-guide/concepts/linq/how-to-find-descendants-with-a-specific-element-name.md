---
title: 'Procedura: Trovare discendenti con un nome di elemento specifico (C#)'
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
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 72659358a50d3ae1de9c699bff0bdd9f4ac4f383
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="af3d1-102">Procedura: Trovare discendenti con un nome di elemento specifico (C#)</span><span class="sxs-lookup"><span data-stu-id="af3d1-102">How to: Find Descendants with a Specific Element Name (C#)</span></span>
<span data-ttu-id="af3d1-103">Talvolta si desidera individuare tutti i discendenti con un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="af3d1-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="af3d1-104">È possibile scrivere codice per scorrere tutti i discendenti, tuttavia è più agevole usare l'asse <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="af3d1-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af3d1-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="af3d1-105">Example</span></span>  
 <span data-ttu-id="af3d1-106">Nell'esempio seguente è illustrato come individuare discendenti in base al nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="af3d1-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
IEnumerable<string> textSegs =  
    from seg in root.Descendants("t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="af3d1-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="af3d1-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="af3d1-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="af3d1-108">Example</span></span>  
 <span data-ttu-id="af3d1-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="af3d1-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="af3d1-110">Per altre informazioni, vedere [Uso degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="af3d1-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root xmlns='http://www.adatum.com'>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<string> textSegs =  
    from seg in root.Descendants(ad + "t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="af3d1-111">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="af3d1-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="af3d1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af3d1-112">See Also</span></span>  
 <span data-ttu-id="af3d1-113"><xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="af3d1-113"><xref:System.Xml.Linq.XContainer.Descendants%2A></span></span>   
 [<span data-ttu-id="af3d1-114">Query di base (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="af3d1-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

