---
title: 'Procedura: Trovare un elemento con un attributo specifico (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 59fb7c19-d42f-40eb-8cf8-f1d5b9658eb7
ms.openlocfilehash: d4af129cdb7e9049be747b9eb29aaa26ef5d8188
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855621"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-visual-basic"></a><span data-ttu-id="b15e3-102">Procedura: Trovare un elemento con un attributo specifico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b15e3-102">How to: Find an Element with a Specific Attribute (Visual Basic)</span></span>
<span data-ttu-id="b15e3-103">In questo argomento viene illustrato come trovare un elemento che include un attributo con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="b15e3-103">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b15e3-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b15e3-104">Example</span></span>  
 <span data-ttu-id="b15e3-105">Nell'esempio viene illustrato come trovare l'elemento `Address` contenente un attributo `Type` con valore "Billing".</span><span class="sxs-lookup"><span data-stu-id="b15e3-105">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="b15e3-106">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b15e3-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("PurchaseOrder.xml")  
Dim address As IEnumerable(Of XElement) = _  
    From el In root.<Address> _  
    Where el.@Type = "Billing" _  
    Select el  
For Each el As XElement In address  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="b15e3-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b15e3-107">This code produces the following output:</span></span>  
  
```xml  
          <Address Type="Billing">  
  <Name>Tai Yee</Name>  
  <Street>8 Oak Avenue</Street>  
  <City>Old Town</City>  
  <State>PA</State>  
  <Zip>95819</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
 <span data-ttu-id="b15e3-108">Si noti che questo esempio Usa la [proprietà asse figlio XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), il [proprietà axis dell'attributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)e il [proprietà Value XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="b15e3-108">Note that this example uses the [XML Child axis property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b15e3-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="b15e3-109">Example</span></span>  
 <span data-ttu-id="b15e3-110">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b15e3-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b15e3-111">Per altre informazioni, vedere [uso di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b15e3-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="b15e3-112">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto in uno spazio dei nomi](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b15e3-112">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim address As IEnumerable(Of XElement) = _  
            From el In root.<aw:Address> _  
            Where el.@aw:Type = "Billing" _  
            Select el  
        For Each el As XElement In address  
            Console.WriteLine(el)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="b15e3-113">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b15e3-113">This code produces the following output:</span></span>  
  
```xml  
<aw:Address aw:Type="Billing" xmlns:aw="http://www.adventure-works.com">  
  <aw:Name>Tai Yee</aw:Name>  
  <aw:Street>8 Oak Avenue</aw:Street>  
  <aw:City>Old Town</aw:City>  
  <aw:State>PA</aw:State>  
  <aw:Zip>95819</aw:Zip>  
  <aw:Country>USA</aw:Country>  
</aw:Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b15e3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b15e3-114">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="b15e3-115">Query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b15e3-115">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [<span data-ttu-id="b15e3-116">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b15e3-116">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="b15e3-117">Operazioni di proiezione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b15e3-117">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
