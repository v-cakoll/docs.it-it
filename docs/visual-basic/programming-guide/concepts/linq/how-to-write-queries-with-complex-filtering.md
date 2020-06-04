---
title: 'Procedura: Scrivere query con filtro complesso'
ms.date: 07/20/2015
ms.assetid: bf286ffc-7990-4b00-a4eb-ee3d70129950
ms.openlocfilehash: 18ed4379b7ec9c8007cc3c189fc45571b5161911
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397622"
---
# <a name="how-to-write-queries-with-complex-filtering-visual-basic"></a><span data-ttu-id="405cc-102">Procedura: scrivere query con filtri complessi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="405cc-102">How to: Write Queries with Complex Filtering (Visual Basic)</span></span>
<span data-ttu-id="405cc-103">A volte si desidera scrivere query LINQ to XML con filtri complessi.</span><span class="sxs-lookup"><span data-stu-id="405cc-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="405cc-104">Può ad esempio essere necessario trovare tutti gli elementi che hanno un elemento figlio con un determinato nome e valore.</span><span class="sxs-lookup"><span data-stu-id="405cc-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="405cc-105">In questo argomento viene illustrato come scrivere una query di esempio con filtri complessi.</span><span class="sxs-lookup"><span data-stu-id="405cc-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="405cc-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="405cc-106">Example</span></span>  
 <span data-ttu-id="405cc-107">Nell'esempio viene illustrato come trovare tutti gli elementi `PurchaseOrder` che includono un elemento figlio `Address` con un attributo `Type` uguale a "Shipping" e un elemento figlio `State` uguale a "NY".</span><span class="sxs-lookup"><span data-stu-id="405cc-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="405cc-108">Viene usata una query annidata nella clausola `Where` e l'operatore `Any` restituisce `True` se la raccolta contiene elementi.</span><span class="sxs-lookup"><span data-stu-id="405cc-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `True` if the collection has any elements in it.</span></span>  
  
 <span data-ttu-id="405cc-109">Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="405cc-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="405cc-110">Per ulteriori informazioni sull' `Any` operatore, vedere [operazioni del quantificatore (Visual Basic)](quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="405cc-110">For more information about the `Any` operator, see [Quantifier Operations (Visual Basic)](quantifier-operations.md).</span></span>  
  
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
  
 <span data-ttu-id="405cc-111">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="405cc-111">This code produces the following output:</span></span>  
  
```console  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="405cc-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="405cc-112">Example</span></span>  
 <span data-ttu-id="405cc-113">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="405cc-113">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="405cc-114">Per ulteriori informazioni, vedere [Cenni preliminari sugli spazi dei nomi (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="405cc-114">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="405cc-115">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: più ordini di acquisto in uno spazio dei nomi](sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="405cc-115">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="405cc-116">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="405cc-116">This code produces the following output:</span></span>  
  
```console  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="405cc-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="405cc-117">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="405cc-118">Query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="405cc-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)
- [<span data-ttu-id="405cc-119">XML Child Axis Property</span><span class="sxs-lookup"><span data-stu-id="405cc-119">XML Child Axis Property</span></span>](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="405cc-120">XML Attribute Axis Property</span><span class="sxs-lookup"><span data-stu-id="405cc-120">XML Attribute Axis Property</span></span>](../../../language-reference/xml-axis/xml-attribute-axis-property.md)
- [<span data-ttu-id="405cc-121">Proprietà Value XML</span><span class="sxs-lookup"><span data-stu-id="405cc-121">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="405cc-122">Operazioni di proiezione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="405cc-122">Projection Operations (Visual Basic)</span></span>](projection-operations.md)
- [<span data-ttu-id="405cc-123">Operazioni del quantificatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="405cc-123">Quantifier Operations (Visual Basic)</span></span>](quantifier-operations.md)
