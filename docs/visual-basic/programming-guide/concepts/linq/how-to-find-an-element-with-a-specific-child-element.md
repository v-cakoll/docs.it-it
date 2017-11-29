---
title: 'Procedura: trovare un elemento con un elemento figlio specifico (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0d0a463-6a85-46c3-8453-ad25b0ecf93c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6ddb35e954d709548c6b32475f37454015e0a98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-an-element-with-a-specific-child-element-visual-basic"></a><span data-ttu-id="ecbae-102">Procedura: trovare un elemento con un elemento figlio specifico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecbae-102">How to: Find an Element with a Specific Child Element (Visual Basic)</span></span>
<span data-ttu-id="ecbae-103">In questo argomento viene illustrato come trovare un determinato elemento che include un elemento figlio con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="ecbae-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecbae-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ecbae-104">Example</span></span>  
 <span data-ttu-id="ecbae-105">Nell'esempio viene ricercato l'elemento `Test` contenente un elemento figlio `CommandLine` con valore "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="ecbae-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="ecbae-106">Questo esempio usa il documento XML seguente: [File XML di esempio: configurazione di test (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="ecbae-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="ecbae-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ecbae-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
 <span data-ttu-id="ecbae-108">Si noti che questo esempio viene utilizzato il [proprietà asse figlio XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), [proprietà axis dell'attributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)e [proprietà Value XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="ecbae-108">Note that this example uses the [XML Child axis property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecbae-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="ecbae-109">Example</span></span>  
 <span data-ttu-id="ecbae-110">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ecbae-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="ecbae-111">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="ecbae-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="ecbae-112">Questo esempio usa il documento XML seguente: [File XML di esempio: configurazione di test in uno spazio dei nomi](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="ecbae-112">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="ecbae-113">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ecbae-113">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="ecbae-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecbae-114">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [<span data-ttu-id="ecbae-115">Le query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecbae-115">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="ecbae-116">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecbae-116">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="ecbae-117">Operazioni di proiezione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecbae-117">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
