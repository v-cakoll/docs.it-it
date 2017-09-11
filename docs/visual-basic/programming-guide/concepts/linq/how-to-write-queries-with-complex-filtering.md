---
title: 'Procedura: scrivere query con filtri complessi (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: bf286ffc-7990-4b00-a4eb-ee3d70129950
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3f8f6dfc78fb94dcb719ca68841dba54fe92ec75
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-write-queries-with-complex-filtering-visual-basic"></a><span data-ttu-id="30da4-102">Procedura: scrivere query con filtri complessi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30da4-102">How to: Write Queries with Complex Filtering (Visual Basic)</span></span>
<span data-ttu-id="30da4-103">A volte si desidera scrivere query LINQ to XML con filtri complessi.</span><span class="sxs-lookup"><span data-stu-id="30da4-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="30da4-104">Può ad esempio essere necessario trovare tutti gli elementi che hanno un elemento figlio con un determinato nome e valore.</span><span class="sxs-lookup"><span data-stu-id="30da4-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="30da4-105">In questo argomento viene illustrato come scrivere una query di esempio con filtri complessi.</span><span class="sxs-lookup"><span data-stu-id="30da4-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30da4-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="30da4-106">Example</span></span>  
 <span data-ttu-id="30da4-107">Nell'esempio viene illustrato come trovare tutti gli elementi `PurchaseOrder` che includono un elemento figlio `Address` con un attributo `Type` uguale a "Shipping" e un elemento figlio `State` uguale a "NY".</span><span class="sxs-lookup"><span data-stu-id="30da4-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="30da4-108">Viene usata una query annidata nella clausola `Where` e l'operatore `Any` restituisce `True` se la raccolta contiene elementi.</span><span class="sxs-lookup"><span data-stu-id="30da4-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `True` if the collection has any elements in it.</span></span>  
  
 <span data-ttu-id="30da4-109">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="30da4-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="30da4-110">Per ulteriori informazioni sui `Any` operatore, vedere [operazioni del quantificatore (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="30da4-110">For more information about the `Any` operator, see [Quantifier Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("PurchaseOrders.xml")  
Dim purchaseOrders As IEnumerable(Of XElement) = _  
    From el In root.<PurchaseOrder> _  
    Where _  
        (From add In el.<Address> _  
        Where _  
             add.@Type = "Shipping" And _  
             add.<State>.Value = "NY" _  
        Select add) _  
    .Any() _  
    Select el  
For Each el As XElement In purchaseOrders  
    Console.WriteLine(el.@PurchaseOrderNumber)  
Next  
```  
  
 <span data-ttu-id="30da4-111">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="30da4-111">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="30da4-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="30da4-112">Example</span></span>  
 <span data-ttu-id="30da4-113">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="30da4-113">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="30da4-114">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="30da4-114">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="30da4-115">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: più ordini di acquisto in un Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="30da4-115">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim purchaseOrders As IEnumerable(Of XElement) = _  
            From el In root.<aw:PurchaseOrder> _  
            Where _  
                (From add In el.<aw:Address> _  
                Where _  
                     add.@aw:Type = "Shipping" And _  
                     add.<aw:State>.Value = "NY" _  
                Select add) _  
            .Any() _  
            Select el  
        For Each el As XElement In purchaseOrders  
            Console.WriteLine(el.@aw:PurchaseOrderNumber)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="30da4-116">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="30da4-116">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="30da4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30da4-117">See Also</span></span>  
 <span data-ttu-id="30da4-118"><xref:System.Xml.Linq.XElement.Attribute%2A></xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="30da4-118"><xref:System.Xml.Linq.XElement.Attribute%2A></span></span>   
 <span data-ttu-id="30da4-119"><xref:System.Xml.Linq.XContainer.Elements%2A></xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="30da4-119"><xref:System.Xml.Linq.XContainer.Elements%2A></span></span>   
<span data-ttu-id="30da4-120"> [Query di base (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="30da4-120"> [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span></span>  
<span data-ttu-id="30da4-121"> [Proprietà Child Axis XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="30da4-121"> [XML Child Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md) </span></span>  
<span data-ttu-id="30da4-122"> [Proprietà axis dell'attributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="30da4-122"> [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span></span>  
<span data-ttu-id="30da4-123"> [Proprietà Value XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md) </span><span class="sxs-lookup"><span data-stu-id="30da4-123"> [XML Value Property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md) </span></span>  
<span data-ttu-id="30da4-124"> [Operazioni di proiezione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md) </span><span class="sxs-lookup"><span data-stu-id="30da4-124"> [Projection Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md) </span></span>  
<span data-ttu-id="30da4-125"> [Operazioni quantificatore (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)</span><span class="sxs-lookup"><span data-stu-id="30da4-125"> [Quantifier Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)</span></span>
