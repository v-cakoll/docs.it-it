---
title: 'Procedura: trovare un elemento con un elemento figlio specifico (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: b0d0a463-6a85-46c3-8453-ad25b0ecf93c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4adb17ec4bbbe9caf2220a2c9b5bbe207f095350
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-find-an-element-with-a-specific-child-element-visual-basic"></a><span data-ttu-id="3739b-102">Procedura: trovare un elemento con un elemento figlio specifico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3739b-102">How to: Find an Element with a Specific Child Element (Visual Basic)</span></span>
<span data-ttu-id="3739b-103">In questo argomento viene illustrato come trovare un determinato elemento che include un elemento figlio con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="3739b-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3739b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3739b-104">Example</span></span>  
 <span data-ttu-id="3739b-105">Nell'esempio viene ricercato l'elemento `Test` contenente un elemento figlio `CommandLine` con valore "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="3739b-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="3739b-106">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: configurazione di Test (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3739b-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="3739b-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3739b-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
 <span data-ttu-id="3739b-108">Si noti che questo esempio viene utilizzato il [proprietà asse figlio XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), [proprietà axis dell'attributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)e [proprietà Value XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="3739b-108">Note that this example uses the [XML Child axis property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3739b-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="3739b-109">Example</span></span>  
 <span data-ttu-id="3739b-110">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3739b-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="3739b-111">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="3739b-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="3739b-112">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: configurazione di Test in un Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="3739b-112">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="3739b-113">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3739b-113">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="3739b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3739b-114">See Also</span></span>  
 <span data-ttu-id="3739b-115"><xref:System.Xml.Linq.XElement.Attribute%2A></xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="3739b-115"><xref:System.Xml.Linq.XElement.Attribute%2A></span></span>   
 <span data-ttu-id="3739b-116"><xref:System.Xml.Linq.XContainer.Elements%2A></xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="3739b-116"><xref:System.Xml.Linq.XContainer.Elements%2A></span></span>   
<span data-ttu-id="3739b-117"> [Query di base (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="3739b-117"> [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span></span>  
<span data-ttu-id="3739b-118"> [Cenni preliminari sugli operatori di Query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="3739b-118"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="3739b-119"> [Operazioni di proiezione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)</span><span class="sxs-lookup"><span data-stu-id="3739b-119"> [Projection Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)</span></span>
