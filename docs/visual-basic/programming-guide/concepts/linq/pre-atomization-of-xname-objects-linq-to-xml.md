---
title: Pre-atomizzazione di oggetti XName (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
ms.openlocfilehash: c0e75afa797d2b20f32fc55e6c19d0c1593d174c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740787"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a>Pre-atomizzazione di oggetti XName (LINQ to XML) (Visual Basic)

Per migliorare le prestazioni in LINQ to XML, è possibile pre-atomizzare gli oggetti <xref:System.Xml.Linq.XName>. Con la pre-atomizzazione si intende assegnare una stringa a un oggetto <xref:System.Xml.Linq.XName> prima di creare l'albero XML usando i costruttori delle classi <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XAttribute>. Anziché passare una stringa al costruttore, che utilizzerebbe la conversione implicita da stringa a <xref:System.Xml.Linq.XName>, è possibile passare l'oggetto <xref:System.Xml.Linq.XName> inizializzato.

Questa operazione consente di migliorare le prestazioni quando si crea un albero XML di grandi dimensioni in cui sono ripetuti nomi specifici. A tale scopo, è necessario dichiarare e inizializzare gli oggetti <xref:System.Xml.Linq.XName> prima di costruire l'albero XML, quindi usare gli oggetti <xref:System.Xml.Linq.XName> anziché specificare le stringhe per i nomi di elementi e attributi. Questa tecnica può consentire un miglioramento significativo delle prestazioni se si crea un numero elevato di elementi (o attributi) con lo stesso nome.

Se si decide di usare la pre-atomizzazione, è prima necessario testarla nel proprio scenario.

## <a name="example"></a>Esempio

Questo concetto è illustrato nell'esempio seguente:

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

Questo esempio produce il seguente output:

```xml
<Root>
  <Data ID="1">4,100,000</Data>
  <Data ID="2">3,700,000</Data>
  <Data ID="3">1,150,000</Data>
</Root>
```

Nell'esempio seguente è illustrata la stessa tecnica per un documento XML in uno spazio dei nomi:

```vb
Dim aw As XNamespace = "http://www.adventure-works.com"
Dim root1 As XName = aw + "Root"
Dim data As XName = aw + "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XAttribute(XNamespace.Xmlns + "aw", aw),
                          New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

Questo esempio produce il seguente output:

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Data ID="1">4,100,000</aw:Data>
  <aw:Data ID="2">3,700,000</aw:Data>
  <aw:Data ID="3">1,150,000</aw:Data>
</aw:Root>
```

L'esempio seguente è più simile a quello che potrebbe verificarsi in un caso reale. In questo esempio il contenuto dell'elemento viene fornito da una query:

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"
  
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root2 As New XElement(root1, From i In Enumerable.Range(1, 100000)
                                 Select New XElement(data, New XAttribute(ID, i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```  

L'esempio precedente offre prestazioni migliori rispetto all'esempio seguente, in cui i nomi non sono pre-atomizzati:

```vb
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root As New XElement("Root", From i In Enumerable.Range(1, 100000)
                                 Select New XElement("Data", New XAttribute("ID", i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```

## <a name="see-also"></a>Vedere anche

- [Prestazioni (LINQ to XML) (Visual Basic)](performance-linq-to-xml.md)
- [Oggetti XName e XNamespace atomizzati (LINQ to XML) (Visual Basic)](atomized-xname-and-xnamespace-objects-linq-to-xml.md)
