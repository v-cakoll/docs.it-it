---
title: 'Procedura: calcolare valori intermedi (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: 933a97b2-dfe7-4f4d-94ad-e6e20df84abd
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 033f813bdfa84eda68ac0edd0b38da2bb72158ee
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-calculate-intermediate-values-visual-basic"></a><span data-ttu-id="65c1c-102">Procedura: calcolare valori intermedi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65c1c-102">How to: Calculate Intermediate Values (Visual Basic)</span></span>
<span data-ttu-id="65c1c-103">In questo esempio viene illustrato come calcolare valori intermedi che è possibile usare in operazioni di ordinamento, filtro e selezione.</span><span class="sxs-lookup"><span data-stu-id="65c1c-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65c1c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="65c1c-104">Example</span></span>  
 <span data-ttu-id="65c1c-105">Nell'esempio seguente viene usata la clausola `Let`.</span><span class="sxs-lookup"><span data-stu-id="65c1c-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="65c1c-106">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="65c1c-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim extensions As IEnumerable(Of Decimal) = _  
    From el In root.<Data> _  
    Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
    Where extension > 25 _  
    Order By extension _  
    Select extension  
For Each ex As Decimal In extensions  
    Console.WriteLine(ex)  
Next  
```  
  
 <span data-ttu-id="65c1c-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="65c1c-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="65c1c-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="65c1c-108">Example</span></span>  
 <span data-ttu-id="65c1c-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="65c1c-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="65c1c-110">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="65c1c-110">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="65c1c-111">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: dati numerici in un Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="65c1c-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns="http://www.adatum.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("DataInNamespace.xml")  
        Dim extensions As IEnumerable(Of Decimal) = _  
            From el In root.<Data> _  
            Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
            Where extension > 25 _  
            Order By extension _  
            Select extension  
        For Each ex As Decimal In extensions  
            Console.WriteLine(ex)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="65c1c-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="65c1c-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="65c1c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65c1c-113">See Also</span></span>  
 [<span data-ttu-id="65c1c-114">Query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65c1c-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

