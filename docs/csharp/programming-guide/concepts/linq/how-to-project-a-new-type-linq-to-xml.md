---
title: 'Procedura: Proiettare un nuovo tipo (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: bec4e7c7d87dffb90b49b76aa00a5de093d68436
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593043"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a>Procedura: Proiettare un nuovo tipo (LINQ to XML) (C#)

Negli altri esempi di questa sezione sono state illustrate query che restituiscono risultati sotto forma di <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> di `string` e <xref:System.Collections.Generic.IEnumerable%601> di `int`. Si tratta di tipi di risultati comuni, ma non sono appropriati per tutti gli scenari. In molti casi le query dovranno restituire un oggetto <xref:System.Collections.Generic.IEnumerable%601> di un altro tipo.

## <a name="example"></a>Esempio

In questo esempio viene illustrato come creare istanze di oggetti nella clausola `select`. Nel codice viene innanzitutto definita una nuova classe con un costruttore, quindi viene modificata l'istruzione `select` in modo che l'espressione sia una nuova istanza della nuova classe.

Nell'esempio viene usato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).

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

Nell'esempio viene usato il metodo <xref:System.Xml.Linq.XContainer.Element%2A> illustrato nell'argomento [Procedura: Recuperare un singolo elemento figlio (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md). Vengono inoltre usati i cast per recuperare i valori degli elementi restituiti dal metodo <xref:System.Xml.Linq.XContainer.Element%2A>.  

Questo esempio produce il seguente output:

```console
Lawnmower:1
Baby Monitor:2
```
