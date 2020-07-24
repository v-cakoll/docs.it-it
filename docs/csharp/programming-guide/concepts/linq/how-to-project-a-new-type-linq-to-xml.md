---
title: Come proiettare un nuovo tipo (LINQ to XML) (C#)
description: Informazioni su come creare query in LINQ to XML in C# che restituiscono IEnumerable <T> di tipi oltre a XElement, String o int, descritti in altri esempi.
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 013ea852a64b77c04ac583b4d9b71e8006cd4976
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104641"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="b0347-103">Come proiettare un nuovo tipo (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b0347-103">How to project a new type (LINQ to XML) (C#)</span></span>

<span data-ttu-id="b0347-104">Negli altri esempi di questa sezione sono state illustrate query che restituiscono risultati sotto forma di <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> di `string` e <xref:System.Collections.Generic.IEnumerable%601> di `int`.</span><span class="sxs-lookup"><span data-stu-id="b0347-104">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="b0347-105">Si tratta di tipi di risultati comuni, ma non sono appropriati per tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="b0347-105">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="b0347-106">In molti casi le query dovranno restituire un oggetto <xref:System.Collections.Generic.IEnumerable%601> di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="b0347-106">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>

## <a name="example"></a><span data-ttu-id="b0347-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0347-107">Example</span></span>

<span data-ttu-id="b0347-108">In questo esempio viene illustrato come creare istanze di oggetti nella clausola `select`.</span><span class="sxs-lookup"><span data-stu-id="b0347-108">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="b0347-109">Nel codice viene innanzitutto definita una nuova classe con un costruttore, quindi viene modificata l'istruzione `select` in modo che l'espressione sia una nuova istanza della nuova classe.</span><span class="sxs-lookup"><span data-stu-id="b0347-109">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>

<span data-ttu-id="b0347-110">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="b0347-110">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>

```csharp
class NameQty
{
    public string name;
    public int qty;
    public NameQty(string n, int q)
    {
        name = n;
        qty = q;
    }
};

class Program {
    public static void Main()
    {
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

<span data-ttu-id="b0347-111">Questo esempio usa il <xref:System.Xml.Linq.XContainer.Element%2A> metodo introdotto nell'argomento [come recuperare un singolo elemento figlio (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b0347-111">This example uses the <xref:System.Xml.Linq.XContainer.Element%2A> method that was introduced in the topic [How to retrieve a single child element (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="b0347-112">Vengono inoltre usati i cast per recuperare i valori degli elementi restituiti dal metodo <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="b0347-112">It also uses casts to retrieve the values of the elements that are returned by the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  

<span data-ttu-id="b0347-113">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="b0347-113">This example produces the following output:</span></span>

```output
Lawnmower:1
Baby Monitor:2
```
