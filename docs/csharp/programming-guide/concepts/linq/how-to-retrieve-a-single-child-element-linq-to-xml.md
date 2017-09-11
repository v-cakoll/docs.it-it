---
title: 'Procedura: Recuperare un singolo elemento figlio (LINQ to XML) (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ce37db9e-76fa-46eb-b4cc-e8f32d22ad90
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 11a53104f73325a905ef5144aabddf8c270fd024
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-c"></a><span data-ttu-id="2760a-102">Procedura: Recuperare un singolo elemento figlio (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2760a-102">How to: Retrieve a Single Child Element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="2760a-103">In questo argomento viene illustrato come recuperare un singolo elemento figlio, dato il relativo nome.</span><span class="sxs-lookup"><span data-stu-id="2760a-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="2760a-104">Quando si conosce il nome dell'elemento figlio e si ha la certezza che ne esista solo uno con tale nome, può risultare utile recuperare un singolo elemento, anziché una raccolta.</span><span class="sxs-lookup"><span data-stu-id="2760a-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="2760a-105">Il metodo <xref:System.Xml.Linq.XContainer.Element%2A> restituisce il primo elemento <xref:System.Xml.Linq.XElement> figlio con l'oggetto <xref:System.Xml.Linq.XName> specificato.</span><span class="sxs-lookup"><span data-stu-id="2760a-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="2760a-106">Per recuperare un singolo elemento figlio in Visual Basic, l'approccio più diffuso consiste nell'usare la proprietà XML e quindi recuperare il primo elemento usando la notazione dell'indicizzatore di matrice.</span><span class="sxs-lookup"><span data-stu-id="2760a-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2760a-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="2760a-107">Example</span></span>  
 <span data-ttu-id="2760a-108">Nell'esempio seguente viene illustrato l'uso del metodo <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="2760a-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="2760a-109">Viene ricercato il primo elemento denominato `po` nell'albero XML denominato `Comment`.</span><span class="sxs-lookup"><span data-stu-id="2760a-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="2760a-110">Nell'esempio di Visual Basic viene illustrato l'uso della notazione dell'indicizzatore di matrice per recuperare un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="2760a-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="2760a-111">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="2760a-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
XElement e = po.Element("DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="2760a-112">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="2760a-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="2760a-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="2760a-113">Example</span></span>  
 <span data-ttu-id="2760a-114">Nell'esempio seguente viene illustrato lo stesso codice per XML all'interno di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2760a-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="2760a-115">Per altre informazioni, vedere [Uso degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="2760a-115">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="2760a-116">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: ordine di acquisto tipico in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="2760a-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement e = po.Element(aw + "DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="2760a-117">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="2760a-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2760a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2760a-118">See Also</span></span>  
 [<span data-ttu-id="2760a-119">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2760a-119">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)

