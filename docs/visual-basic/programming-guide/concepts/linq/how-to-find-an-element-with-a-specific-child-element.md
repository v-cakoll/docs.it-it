---
title: 'Procedura: Trovare un elemento con un elemento figlio specifico (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b0d0a463-6a85-46c3-8453-ad25b0ecf93c
ms.openlocfilehash: 4df2f8f55a516665c02d12c3bdf6569601db30c2
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "72249905"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-visual-basic"></a><span data-ttu-id="a67c8-102">Procedura: Trovare un elemento con un elemento figlio specifico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a67c8-102">How to: Find an Element with a Specific Child Element (Visual Basic)</span></span>
<span data-ttu-id="a67c8-103">In questo argomento viene illustrato come trovare un determinato elemento che include un elemento figlio con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="a67c8-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a67c8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a67c8-104">Example</span></span>  
 <span data-ttu-id="a67c8-105">Nell'esempio viene ricercato l'elemento `Test` contenente un elemento figlio `CommandLine` con valore "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="a67c8-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="a67c8-106">Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: configurazione di test (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a67c8-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("TestConfig.xml")  
Dim tests As IEnumerable(Of XElement) = _  
    From el In root.<Test> _  
    Where el.<CommandLine>.Value = "Examp2.EXE" _  
    Select el  
For Each el as XElement In tests  
    Console.WriteLine(el.@TestId)  
Next  
```  
  
 <span data-ttu-id="a67c8-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a67c8-107">This code produces the following output:</span></span>  
  
```console  
0002  
0006  
```  
  
 <span data-ttu-id="a67c8-108">Si noti che in questo esempio vengono utilizzate la proprietà [Axis Child XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), la [Proprietà Axis attribute XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)e la [proprietà Value XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="a67c8-108">Note that this example uses the [XML Child axis property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a67c8-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a67c8-109">Example</span></span>  
 <span data-ttu-id="a67c8-110">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a67c8-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="a67c8-111">Per ulteriori informazioni, vedere [Cenni preliminari sugli spazi dei nomi (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a67c8-111">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="a67c8-112">Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: configurazione di test in uno spazio dei nomi](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="a67c8-112">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("TestConfigInNamespace.xml")  
        Dim tests As IEnumerable(Of XElement) = _  
            From el In root.<Test> _  
            Where el.<CommandLine>.Value = "Examp2.EXE" _  
            Select el  
        For Each el As XElement In tests  
            Console.WriteLine(el.@TestId)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="a67c8-113">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a67c8-113">This code produces the following output:</span></span>  
  
```console  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="a67c8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a67c8-114">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="a67c8-115">Query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a67c8-115">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [<span data-ttu-id="a67c8-116">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a67c8-116">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="a67c8-117">Operazioni di proiezione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a67c8-117">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
