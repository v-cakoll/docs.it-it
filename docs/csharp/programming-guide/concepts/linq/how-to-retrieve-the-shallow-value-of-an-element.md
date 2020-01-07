---
title: Come recuperare il valore superficiale di un elemento (C#)
ms.date: 07/20/2015
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
ms.openlocfilehash: b9b69b5a18106f82d13cb54208c2362f8239711e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347443"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a><span data-ttu-id="7b369-102">Come recuperare il valore superficiale di un elemento (C#)</span><span class="sxs-lookup"><span data-stu-id="7b369-102">How to retrieve the shallow value of an element (C#)</span></span>
<span data-ttu-id="7b369-103">In questo argomento viene illustrato come ottenere il valore superficiale di un elemento.</span><span class="sxs-lookup"><span data-stu-id="7b369-103">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="7b369-104">Per valore superficiale si intende un valore che appartiene solo all'elemento specifico, a differenza del valore completo che include i valori di tutti gli elementi discendenti concatenati in una singola stringa.</span><span class="sxs-lookup"><span data-stu-id="7b369-104">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>  
  
 <span data-ttu-id="7b369-105">Quando si recupera il valore di un elemento eseguendo il cast o usando la proprietà <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>, si ottiene il valore completo.</span><span class="sxs-lookup"><span data-stu-id="7b369-105">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property, you retrieve the deep value.</span></span> <span data-ttu-id="7b369-106">Per recuperare il valore superficiale, è possibile usare il metodo di estensione `ShallowValue`, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7b369-106">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the following example.</span></span> <span data-ttu-id="7b369-107">Il recupero del valore superficiale risulta utile quando si desidera selezionare gli elementi in base al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="7b369-107">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>  
  
 <span data-ttu-id="7b369-108">Nell'esempio seguente viene dichiarato un metodo di estensione che recupera il valore superficiale di un elemento.</span><span class="sxs-lookup"><span data-stu-id="7b369-108">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="7b369-109">Questo metodo di estensione viene quindi usato in una query per elencare tutti gli elementi che contengono un valore calcolato.</span><span class="sxs-lookup"><span data-stu-id="7b369-109">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b369-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b369-110">Example</span></span>  
 <span data-ttu-id="7b369-111">Il file di testo seguente, Report.xml, è l'origine di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="7b369-111">The following text file, Report.xml, is the source for this example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```csharp  
public static class MyExtensions  
{  
    public static string ShallowValue(this XElement xe)  
    {  
        return xe  
               .Nodes()  
               .OfType<XText>()  
               .Aggregate(new StringBuilder(),  
                          (s, c) => s.Append(c),  
                          s => s.ToString());  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement root = XElement.Load("Report.xml");  
  
        IEnumerable<XElement> query = from el in root.Descendants()  
                                      where el.ShallowValue().StartsWith("=")  
                                      select el;  
  
        foreach (var q in query)  
        {  
            Console.WriteLine("{0}{1}{2}",  
                q.Name.ToString().PadRight(8),  
                q.Attribute("Name").ToString().PadRight(20),  
                q.ShallowValue());  
        }  
    }  
}  
```  
  
 <span data-ttu-id="7b369-112">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="7b369-112">This example produces the following output:</span></span>  
  
```output  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b369-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b369-113">See also</span></span>

- [<span data-ttu-id="7b369-114">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="7b369-114">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
