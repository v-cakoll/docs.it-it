---
title: 'Procedura: calcolare valori intermedi (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 933a97b2-dfe7-4f4d-94ad-e6e20df84abd
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eaedaf15318ea9ae521cc070e7cd9a267decf330
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-calculate-intermediate-values-visual-basic"></a><span data-ttu-id="180a0-102">Procedura: calcolare valori intermedi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="180a0-102">How to: Calculate Intermediate Values (Visual Basic)</span></span>
<span data-ttu-id="180a0-103">In questo esempio viene illustrato come calcolare valori intermedi che è possibile usare in operazioni di ordinamento, filtro e selezione.</span><span class="sxs-lookup"><span data-stu-id="180a0-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="180a0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="180a0-104">Example</span></span>  
 <span data-ttu-id="180a0-105">Nell'esempio seguente viene usata la clausola `Let`.</span><span class="sxs-lookup"><span data-stu-id="180a0-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="180a0-106">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="180a0-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="180a0-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="180a0-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="180a0-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="180a0-108">Example</span></span>  
 <span data-ttu-id="180a0-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="180a0-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="180a0-110">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="180a0-110">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="180a0-111">Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici in uno spazio dei nomi](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="180a0-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="180a0-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="180a0-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="180a0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="180a0-113">See Also</span></span>  
 [<span data-ttu-id="180a0-114">Le query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="180a0-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
