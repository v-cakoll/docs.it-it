---
title: 'Procedura: recuperare un singolo elemento figlio (LINQ to XML) (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 006a6afbb07ceea64b8fcc6cdab1d4fd31ae3c87
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a><span data-ttu-id="eaf80-102">Procedura: recuperare un singolo elemento figlio (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eaf80-102">How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="eaf80-103">In questo argomento viene illustrato come recuperare un singolo elemento figlio, dato il relativo nome.</span><span class="sxs-lookup"><span data-stu-id="eaf80-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="eaf80-104">Quando si conosce il nome dell'elemento figlio e si ha la certezza che ne esista solo uno con tale nome, può risultare utile recuperare un singolo elemento, anziché una raccolta.</span><span class="sxs-lookup"><span data-stu-id="eaf80-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="eaf80-105">Il <xref:System.Xml.Linq.XContainer.Element%2A>metodo restituisce il primo figlio <xref:System.Xml.Linq.XElement>con specificato <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Element%2A></span><span class="sxs-lookup"><span data-stu-id="eaf80-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="eaf80-106">Per recuperare un singolo elemento figlio in Visual Basic, l'approccio più diffuso consiste nell'usare la proprietà XML e quindi recuperare il primo elemento usando la notazione dell'indicizzatore di matrice.</span><span class="sxs-lookup"><span data-stu-id="eaf80-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaf80-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="eaf80-107">Example</span></span>  
 <span data-ttu-id="eaf80-108">Nell'esempio seguente viene illustrato l'utilizzo di <xref:System.Xml.Linq.XContainer.Element%2A>(metodo).</xref:System.Xml.Linq.XContainer.Element%2A></span><span class="sxs-lookup"><span data-stu-id="eaf80-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="eaf80-109">Viene ricercato il primo elemento denominato `po` nell'albero XML denominato `Comment`.</span><span class="sxs-lookup"><span data-stu-id="eaf80-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="eaf80-110">Nell'esempio di Visual Basic viene illustrato l'uso della notazione dell'indicizzatore di matrice per recuperare un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="eaf80-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="eaf80-111">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="eaf80-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim e As XElement = po.<DeliveryNotes>(0)  
Console.WriteLine(e)  
```  
  
 <span data-ttu-id="eaf80-112">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="eaf80-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="eaf80-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="eaf80-113">Example</span></span>  
 <span data-ttu-id="eaf80-114">Nell'esempio seguente viene illustrato lo stesso codice per XML all'interno di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="eaf80-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="eaf80-115">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="eaf80-115">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="eaf80-116">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto in un Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="eaf80-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim e As XElement = po.<aw:DeliveryNotes>(0)  
        Console.WriteLine(e)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="eaf80-117">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="eaf80-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eaf80-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eaf80-118">See Also</span></span>  
 [<span data-ttu-id="eaf80-119">Assi LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eaf80-119">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)

