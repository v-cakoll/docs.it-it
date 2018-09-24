---
title: 'Procedura: Creare una gerarchia tramite raggruppamento (C#)'
ms.date: 07/20/2015
ms.assetid: 0213d59e-5f76-438c-9cab-4bf11f7b971d
ms.openlocfilehash: 8fa384ced04a90002f8f721266f163c874d6e0ff
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46585560"
---
# <a name="how-to-create-hierarchy-using-grouping-c"></a><span data-ttu-id="19bbe-102">Procedura: Creare una gerarchia tramite raggruppamento (C#)</span><span class="sxs-lookup"><span data-stu-id="19bbe-102">How to: Create Hierarchy Using Grouping (C#)</span></span>
<span data-ttu-id="19bbe-103">In questo esempio viene illustrato come raggruppare dati e quindi generare codice XML basato sul raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="19bbe-103">This example shows how to group data, and then generate XML based on the grouping.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19bbe-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="19bbe-104">Example</span></span>  
 <span data-ttu-id="19bbe-105">In questo esempio vengono prima raggruppati i dati in base a una categoria, quindi viene generato un nuovo file XML in cui la gerarchia XML riflette il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="19bbe-105">This example first groups data by a category, then generates a new XML file in which the XML hierarchy reflects the grouping.</span></span>  
  
 <span data-ttu-id="19bbe-106">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="19bbe-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement doc = XElement.Load("Data.xml");  
var newData =  
    new XElement("Root",  
        from data in doc.Elements("Data")  
        group data by (string)data.Element("Category") into groupedData  
        select new XElement("Group",  
            new XAttribute("ID", groupedData.Key),  
            from g in groupedData  
            select new XElement("Data",  
                g.Element("Quantity"),  
                g.Element("Price")  
            )  
        )  
    );  
Console.WriteLine(newData);  
```  
  
 <span data-ttu-id="19bbe-107">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="19bbe-107">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="19bbe-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19bbe-108">See Also</span></span>

- <span data-ttu-id="19bbe-109">[Advanced Query Techniques (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md) (Tecniche di query avanzate (LINQ to XML) in C#)</span><span class="sxs-lookup"><span data-stu-id="19bbe-109">[Advanced Query Techniques (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)</span></span>
