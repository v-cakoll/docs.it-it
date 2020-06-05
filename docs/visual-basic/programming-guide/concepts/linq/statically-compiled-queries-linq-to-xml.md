---
title: Query compilate in modo statico (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
ms.openlocfilehash: f020c1ed8627df8c8386a059f0cea372e8df363e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406768"
---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a>Query compilate in modo statico (LINQ to XML) (Visual Basic)

Uno dei più importanti vantaggi a livello di prestazioni di LINQ to XML, rispetto a <xref:System.Xml.XmlDocument>, consiste nel fatto che le query in LINQ to XML sono compilate in modo statico, mentre le query XPath devono essere interpretate in fase di esecuzione. Questa funzionalità è incorporata in LINQ to XML, pertanto non è necessario eseguire passaggi aggiuntivi per sfruttarla, ma è utile capire la distinzione per saper scegliere tra le due tecnologie. In questo argomento viene illustrata la differenza

## <a name="statically-compiled-queries-vs-xpath"></a>Confronto tra query compilate in modo statico e XPath

Nell'esempio seguente viene illustrato come ottenere gli elementi discendenti con un nome specificato e con un attributo con un valore specificato.

Di seguito è riportata l'espressione XPath equivalente:

```vb
//Address[@Type='Shipping']
```

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = From el In po.Descendants("Address")
            Where el.@Type = "Shipping"

For Each el In list1
    Console.WriteLine(el)
Next
```

L'espressione di query di questo esempio viene scritta di nuovo dal compilatore nella sintassi delle query basate su metodo. L'esempio seguente, scritto nella sintassi delle query basate su metodo, produce gli stessi risultati del precedente:

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

Il metodo <xref:System.Linq.Enumerable.Where%2A> è un metodo di estensione. Per altre informazioni, vedere [Metodi di estensione](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md). Poiché <xref:System.Linq.Enumerable.Where%2A> è un metodo di estensione, la query precedente è compilata come se fosse scritta come indicato di seguito:

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

Questo esempio produce esattamente gli stessi risultati dei due esempi precedenti. Questo illustra il fatto che le query sono compilate efficacemente in chiamate ai metodi collegate in modo statico. Questo fatto, insieme alla semantica di esecuzione posticipata degli iteratori, consente un miglioramento delle prestazioni. Per ulteriori informazioni sulla semantica di esecuzione posticipata degli iteratori, vedere [esecuzione posticipata e valutazione lazy in LINQ to XML (Visual Basic)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).

> [!NOTE]
> Questi esempi rappresentano il codice che potrebbe venire scritto dal compilatore. L'implementazione effettiva potrebbe differire leggermente da questi esempi, ma le prestazioni saranno la stesse o simili.

## <a name="executing-xpath-expressions-with-xmldocument"></a>Esecuzione di espressioni XPath con XmlDocument

Nell'esempio seguente viene usato <xref:System.Xml.XmlDocument> per ottenere gli stessi risultati degli esempi precedenti:

```vb
Dim reader = Xml.XmlReader.Create("PurchaseOrders.xml")
Dim doc As New Xml.XmlDocument()
doc.Load(reader)
Dim nl As Xml.XmlNodeList = doc.SelectNodes(".//Address[@Type='Shipping']")
For Each n As Xml.XmlNode In nl
    Console.WriteLine(n.OuterXml)
Next
reader.Close()
```

Questa query restituisce lo stesso output degli esempi che usano LINQ to XML. L'unica differenza consiste nel fatto che in LINQ to XML viene applicato un rientro al codice XML stampato, mentre in <xref:System.Xml.XmlDocument> no.

L'utilizzo di <xref:System.Xml.XmlDocument> non garantisce tuttavia lo stesso livello di prestazioni di LINQ to XML, in quanto il metodo <xref:System.Xml.XmlNode.SelectNodes%2A> deve eseguire internamente le operazioni seguenti ogni volta che viene chiamato:

- Analisi della stringa che contiene l'espressione XPath, suddividendo la stringa in token.

- Convalida dei token per assicurarsi che l'espressione XPath sia valida.

- Conversione dell'espressione in un albero delle espressioni interno.

- Iterazione nei nodi, selezionando in modo appropriato i nodi per il set di risultati in base alla valutazione dell'espressione.

Queste operazioni sono in numero significativamente maggiore rispetto a quelle eseguite dalla query LINQ to XML corrispondente. La differenza di prestazioni specifica varia per tipi diversi di query, ma in generale le query LINQ to XML comportano un lavoro minore, e pertanto prestazioni migliori, rispetto alla valutazione di espressioni XPath tramite <xref:System.Xml.XmlDocument>.

## <a name="see-also"></a>Vedere anche

- [Prestazioni (LINQ to XML) (Visual Basic)](performance-linq-to-xml.md)
