---
title: 'Procedura: proiettare un nuovo tipo (LINQ to XML) (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b0e3149ca2fb5e36ebc759421e9489cbfe3dde5f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a><span data-ttu-id="a1ed0-102">Procedura: proiettare un nuovo tipo (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1ed0-102">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="a1ed0-103">Altri esempi in questa sezione sono state illustrate query che restituiscono risultati come <xref:System.Collections.Generic.IEnumerable%601>di <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601>di `string`, e <xref:System.Collections.Generic.IEnumerable%601>di `int`.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a1ed0-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="a1ed0-104">Si tratta di tipi di risultati comuni, ma non sono appropriati per tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="a1ed0-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="a1ed0-105">In molti casi è consigliabile le query dovranno restituire un <xref:System.Collections.Generic.IEnumerable%601>di un altro tipo.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a1ed0-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1ed0-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1ed0-106">Example</span></span>  
 <span data-ttu-id="a1ed0-107">In questo esempio viene illustrato come creare istanze di oggetti nella clausola `Select`.</span><span class="sxs-lookup"><span data-stu-id="a1ed0-107">This example shows how to instantiate objects in the `Select` clause.</span></span> <span data-ttu-id="a1ed0-108">Nel codice viene innanzitutto definita una nuova classe con un costruttore, quindi viene modificata l'istruzione `Select` in modo che l'espressione sia una nuova istanza della nuova classe.</span><span class="sxs-lookup"><span data-stu-id="a1ed0-108">The code first defines a new class with a constructor, and then modifies the `Select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="a1ed0-109">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a1ed0-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Public Class NameQty  
    Public name As String  
    Public qty As Integer  
    Public Sub New(ByVal n As String, ByVal q As Integer)  
        name = n  
        qty = q  
    End Sub  
End Class  
  
Public Class Program  
    Shared Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
  
        Dim nqList As IEnumerable(Of NameQty) = _  
            From n In po...<Item> _  
            Select New NameQty( _  
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))  
  
        For Each n As NameQty In nqList  
            Console.WriteLine(n.name & ":" & n.qty)  
        Next  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="a1ed0-110">Questo esempio viene utilizzato il `M:System.Xml.Linq.XElement.Element` metodo che è stato introdotto nell'argomento [procedura: recuperare un singolo elemento figlio (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a1ed0-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="a1ed0-111">Vengono inoltre usati i cast per recuperare i valori degli elementi restituiti dal metodo `M:System.Xml.Linq.XElement.Element`.</span><span class="sxs-lookup"><span data-stu-id="a1ed0-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="a1ed0-112">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="a1ed0-112">This example produces the following output:</span></span>  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1ed0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1ed0-113">See Also</span></span>  
 [<span data-ttu-id="a1ed0-114">Proiezioni e trasformazioni (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1ed0-114">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
