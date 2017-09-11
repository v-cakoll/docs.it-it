---
title: 'Procedura: trovare un elemento con un attributo specifico (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: 59fb7c19-d42f-40eb-8cf8-f1d5b9658eb7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 16c3d06eaae8fb77c0844ac78736692de2bfc6f2
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-find-an-element-with-a-specific-attribute-visual-basic"></a><span data-ttu-id="b2a79-102">Procedura: trovare un elemento con un attributo specifico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2a79-102">How to: Find an Element with a Specific Attribute (Visual Basic)</span></span>
<span data-ttu-id="b2a79-103">In questo argomento viene illustrato come trovare un elemento che include un attributo con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="b2a79-103">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2a79-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2a79-104">Example</span></span>  
 <span data-ttu-id="b2a79-105">Nell'esempio viene illustrato come trovare l'elemento `Address` contenente un attributo `Type` con valore "Billing".</span><span class="sxs-lookup"><span data-stu-id="b2a79-105">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="b2a79-106">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b2a79-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="b2a79-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b2a79-107">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="b2a79-108">Si noti che questo esempio viene utilizzato il [proprietà asse figlio XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), [proprietà axis dell'attributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)e [proprietà Value XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="b2a79-108">Note that this example uses the [XML Child axis property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2a79-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2a79-109">Example</span></span>  
 <span data-ttu-id="b2a79-110">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b2a79-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b2a79-111">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b2a79-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="b2a79-112">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto in un Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b2a79-112">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="b2a79-113">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b2a79-113">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2a79-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2a79-114">See Also</span></span>  
 <span data-ttu-id="b2a79-115"><xref:System.Xml.Linq.XElement.Attribute%2A></xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="b2a79-115"><xref:System.Xml.Linq.XElement.Attribute%2A></span></span>   
 <span data-ttu-id="b2a79-116"><xref:System.Xml.Linq.XContainer.Elements%2A></xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="b2a79-116"><xref:System.Xml.Linq.XContainer.Elements%2A></span></span>   
<span data-ttu-id="b2a79-117"> [Query di base (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="b2a79-117"> [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span></span>  
<span data-ttu-id="b2a79-118"> [Cenni preliminari sugli operatori di Query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b2a79-118"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="b2a79-119"> [Operazioni di proiezione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)</span><span class="sxs-lookup"><span data-stu-id="b2a79-119"> [Projection Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)</span></span>
