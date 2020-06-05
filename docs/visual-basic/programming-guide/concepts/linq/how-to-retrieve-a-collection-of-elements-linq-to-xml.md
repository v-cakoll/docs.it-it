---
title: 'Procedura: Recuperare una raccolta di elementi (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2269f9de-8fb9-4666-b8a1-a4e754fa6a81
ms.openlocfilehash: 13aa9ce10df1e23ba5191b523db0272aa52ea581
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397869"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-visual-basic"></a>Procedura: recuperare una raccolta di elementi (LINQ to XML) (Visual Basic)
In questo argomento viene illustrato il metodo <xref:System.Xml.Linq.XContainer.Elements%2A>, che consente di recuperare una raccolta degli elementi figlio di un elemento.  
  
## <a name="example"></a>Esempio  
 In questo esempio vengono scorsi gli elementi figlio dell'elemento `purchaseOrder`.  
  
 Nell'esempio viene usato il documento XML seguente: [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim childElements As IEnumerable(Of XElement)  
childElements = _  
    From el In po.Elements() _  
    Select el  
For Each el As XElement In childElements  
    Console.WriteLine("Name: " & el.Name.ToString())  
Next  
```  
  
 Questo esempio produce il seguente output:  
  
```console  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a>Vedere anche

- [Assi LINQ to XML (Visual Basic)](linq-to-xml-axes.md)
