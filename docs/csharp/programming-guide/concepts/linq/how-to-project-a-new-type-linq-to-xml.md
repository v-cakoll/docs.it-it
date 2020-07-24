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
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a>Come proiettare un nuovo tipo (LINQ to XML) (C#)

Negli altri esempi di questa sezione sono state illustrate query che restituiscono risultati sotto forma di <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> di `string` e <xref:System.Collections.Generic.IEnumerable%601> di `int`. Si tratta di tipi di risultati comuni, ma non sono appropriati per tutti gli scenari. In molti casi le query dovranno restituire un oggetto <xref:System.Collections.Generic.IEnumerable%601> di un altro tipo.

## <a name="example"></a>Esempio

In questo esempio viene illustrato come creare istanze di oggetti nella clausola `select`. Nel codice viene innanzitutto definita una nuova classe con un costruttore, quindi viene modificata l'istruzione `select` in modo che l'espressione sia una nuova istanza della nuova classe.

Nell'esempio viene usato il documento XML seguente: [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).

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

Questo esempio usa il <xref:System.Xml.Linq.XContainer.Element%2A> metodo introdotto nell'argomento [come recuperare un singolo elemento figlio (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md). Vengono inoltre usati i cast per recuperare i valori degli elementi restituiti dal metodo <xref:System.Xml.Linq.XContainer.Element%2A>.  

Nell'esempio viene prodotto l'output seguente:

```output
Lawnmower:1
Baby Monitor:2
```
