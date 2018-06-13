---
title: 'Procedura: creare una gerarchia tramite il raggruppamento (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 4eb3ca6b-1aed-43de-b8b9-41c769c993f8
ms.openlocfilehash: 9df85a52d63c4d7dbffb99a47378d3a1efc10cca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33639324"
---
# <a name="how-to-create-hierarchy-using-grouping-visual-basic"></a><span data-ttu-id="01e54-102">Procedura: creare una gerarchia tramite il raggruppamento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01e54-102">How to: Create Hierarchy Using Grouping (Visual Basic)</span></span>
<span data-ttu-id="01e54-103">In questo esempio viene illustrato come raggruppare dati e quindi generare codice XML basato sul raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="01e54-103">This example shows how to group data, and then generate XML based on the grouping.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01e54-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="01e54-104">Example</span></span>  
 <span data-ttu-id="01e54-105">In questo esempio vengono prima raggruppati i dati in base a una categoria, quindi viene generato un nuovo file XML in cui la gerarchia XML riflette il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="01e54-105">This example first groups data by a category, then generates a new XML file in which the XML hierarchy reflects the grouping.</span></span>  
  
 <span data-ttu-id="01e54-106">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="01e54-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim doc As XElement = XElement.Load("Data.xml")  
Dim newData As XElement = _  
    <Root>  
        <%= _  
            From data In doc.<Data> _  
            Group By category = data.<Category>(0).Value _  
            Into groupedData = Group _  
            Select <Group ID=<%= category %>>  
                       <%= _  
                           From g In groupedData _  
                           Select _  
                           <Data>  
                               <%= g.<Quantity>(0) %>  
                               <%= g.<Price>(0) %>  
                           </Data> _  
                       %>  
                   </Group> _  
        %>  
    </Root>  
Console.WriteLine(newData)  
```  
  
 <span data-ttu-id="01e54-107">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="01e54-107">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Group ID="A">  
    <Data>  
      <Quantity>3</Quantity>  
      <Price>24.50</Price>  
    </Data>  
    <Data>  
      <Quantity>5</Quantity>  
      <Price>4.95</Price>  
    </Data>  
    <Data>  
      <Quantity>3</Quantity>  
      <Price>66.00</Price>  
    </Data>  
    <Data>  
      <Quantity>15</Quantity>  
      <Price>29.00</Price>  
    </Data>  
  </Group>  
  <Group ID="B">  
    <Data>  
      <Quantity>1</Quantity>  
      <Price>89.99</Price>  
    </Data>  
    <Data>  
      <Quantity>10</Quantity>  
      <Price>.99</Price>  
    </Data>  
    <Data>  
      <Quantity>8</Quantity>  
      <Price>6.99</Price>  
    </Data>  
  </Group>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01e54-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01e54-108">See Also</span></span>  
 [<span data-ttu-id="01e54-109">Tecniche di Query (LINQ to XML) avanzate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01e54-109">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
