---
title: 'Procedura: filtrare i nomi degli elementi (LINQ to XML) (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1437b4a-48aa-4546-834a-d6d3ab015fe1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1dd63c2de233c2b33ce16de6649a5ffecdc7ade7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-filter-on-element-names-linq-to-xml-visual-basic"></a><span data-ttu-id="b5172-102">Procedura: filtrare i nomi degli elementi (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5172-102">How to: Filter on Element Names (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="b5172-103">Quando si chiama uno dei metodi che restituisce l'oggetto <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>, è possibile filtrare in base al nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="b5172-103">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5172-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5172-104">Example</span></span>  
 <span data-ttu-id="b5172-105">In questo esempio viene recuperata una raccolta di discendenti filtrata in maniera tale da includere solo i discendenti con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="b5172-105">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="b5172-106">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b5172-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim items As IEnumerable(Of XElement) = _  
    From el In po...<ProductName> _  
    Select el  
For Each prdName As XElement In items  
    Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
Next  
```  
  
 <span data-ttu-id="b5172-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b5172-107">This code produces the following output:</span></span>  
  
```  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <span data-ttu-id="b5172-108">Gli altri metodi che restituiscono l'oggetto <xref:System.Collections.Generic.IEnumerable%601> delle raccolte <xref:System.Xml.Linq.XElement> sono caratterizzati dallo stesso schema.</span><span class="sxs-lookup"><span data-stu-id="b5172-108">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="b5172-109">Le relative firme sono simili a <xref:System.Xml.Linq.XContainer.Elements%2A> e <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5172-109">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="b5172-110">Di seguito è riportato l'elenco completo dei metodi con firme simili:</span><span class="sxs-lookup"><span data-stu-id="b5172-110">The following is the complete list of methods that have similar method signatures:</span></span>  
  
-   <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a><span data-ttu-id="b5172-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5172-111">Example</span></span>  
 <span data-ttu-id="b5172-112">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b5172-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b5172-113">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b5172-113">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="b5172-114">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: ordine di acquisto tipico in uno spazio dei nomi](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b5172-114">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim items As IEnumerable(Of XElement) = _  
            From el In po...<aw:ProductName> _  
            Select el  
        For Each prdName As XElement In items  
            Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="b5172-115">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b5172-115">This code produces the following output:</span></span>  
  
```  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5172-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5172-116">See Also</span></span>  
 [<span data-ttu-id="b5172-117">Assi LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5172-117">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
