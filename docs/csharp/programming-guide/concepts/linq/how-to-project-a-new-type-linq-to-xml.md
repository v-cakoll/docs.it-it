---
title: 'Procedura: Proiettare un nuovo tipo (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: eefe645f376f8f52a94b94cdd49640e165a69aae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636625"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="fbbff-102">Procedura: Proiettare un nuovo tipo (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fbbff-102">How to: Project a New Type (LINQ to XML) (C#)</span></span>
<span data-ttu-id="fbbff-103">Negli altri esempi di questa sezione sono state illustrate query che restituiscono risultati sotto forma di <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> di `string` e <xref:System.Collections.Generic.IEnumerable%601> di `int`.</span><span class="sxs-lookup"><span data-stu-id="fbbff-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="fbbff-104">Si tratta di tipi di risultati comuni, ma non sono appropriati per tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="fbbff-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="fbbff-105">In molti casi le query dovranno restituire un oggetto <xref:System.Collections.Generic.IEnumerable%601> di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="fbbff-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbbff-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbbff-106">Example</span></span>  
 <span data-ttu-id="fbbff-107">In questo esempio viene illustrato come creare istanze di oggetti nella clausola `select`.</span><span class="sxs-lookup"><span data-stu-id="fbbff-107">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="fbbff-108">Nel codice viene innanzitutto definita una nuova classe con un costruttore, quindi viene modificata l'istruzione `select` in modo che l'espressione sia una nuova istanza della nuova classe.</span><span class="sxs-lookup"><span data-stu-id="fbbff-108">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="fbbff-109">Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="fbbff-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
class NameQty {  
    public string name;  
    public int qty;  
    public NameQty(string n, int q)  
    {  
        name = n;  
        qty = q;  
    }  
};  
  
class Program {  
    public static void Main() {  
        XElement po = XElement.Load("PurchaseOrder.xml");  
  
        IEnumerable<NameQty> nqList =  
            from n in po.Descendants("Item")  
            select new NameQty(  
                    (string)n.Element("ProductName"),  
                    (int)n.Element("Quantity")  
                );  
  
        foreach (NameQty n in nqList)  
            Console.WriteLine(n.name + ":" + n.qty);  
    }  
}  
```  
  
 <span data-ttu-id="fbbff-110">Nell'esempio viene usato il metodo `M:System.Xml.Linq.XElement.Element` illustrato nell'argomento [Procedura: Recuperare un singolo elemento figlio (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="fbbff-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="fbbff-111">Vengono inoltre usati i cast per recuperare i valori degli elementi restituiti dal metodo `M:System.Xml.Linq.XElement.Element`.</span><span class="sxs-lookup"><span data-stu-id="fbbff-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="fbbff-112">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="fbbff-112">This example produces the following output:</span></span>  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="fbbff-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbbff-113">See also</span></span>

- <span data-ttu-id="fbbff-114">[Projections and Transformations (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md) (Proiezioni e trasformazioni (LINQ to XML) in C#)</span><span class="sxs-lookup"><span data-stu-id="fbbff-114">[Projections and Transformations (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)</span></span>
