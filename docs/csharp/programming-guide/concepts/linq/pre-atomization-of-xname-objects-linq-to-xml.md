---
title: Pre-atomizzazione di oggetti XName (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: e84fbbe7-f072-4771-bfbb-059d18e1ad15
ms.openlocfilehash: 2fd754a352bd2988e52ec9c67a9915a8e587b107
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591490"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-c"></a>Pre-atomizzazione di oggetti XName (LINQ to XML) (C#)
Per migliorare le prestazioni in LINQ to XML, è possibile pre-atomizzare gli oggetti <xref:System.Xml.Linq.XName>. Questa operazione consiste nell'assegnare una stringa a un oggetto <xref:System.Xml.Linq.XName> prima di creare l'albero XML usando i costruttori delle classi <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XAttribute>. Anziché passare una stringa al costruttore, che utilizzerebbe la conversione implicita da stringa a <xref:System.Xml.Linq.XName>, è possibile passare l'oggetto <xref:System.Xml.Linq.XName> inizializzato.  
  
 Questa operazione consente di migliorare le prestazioni quando si crea un albero XML di grandi dimensioni in cui sono ripetuti nomi specifici. A tale scopo, è necessario dichiarare e inizializzare gli oggetti <xref:System.Xml.Linq.XName> prima di costruire l'albero XML, quindi usare gli oggetti <xref:System.Xml.Linq.XName> anziché specificare le stringhe per i nomi di elementi e attributi. Questa tecnica può consentire un miglioramento significativo delle prestazioni se si crea un numero elevato di elementi (o attributi) con lo stesso nome.  
  
 Se si decide di usare la pre-atomizzazione, è prima necessario testarla nel proprio scenario.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra questa operazione.  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 Nell'esempio seguente è illustrata la stessa tecnica per un documento XML in uno spazio dei nomi:  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XName Root = aw + "Root";  
XName Data = aw + "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XAttribute(XNamespace.Xmlns + "aw", aw),  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 L'esempio seguente è più simile a quello che potrebbe verificarsi in un caso reale. In questo esempio il contenuto dell'elemento viene fornito da una query:  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
DateTime t1 = DateTime.Now;  
XElement root = new XElement(Root,  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement(Data,  
        new XAttribute(ID, i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
 L'esempio precedente offre prestazioni migliori rispetto all'esempio seguente, in cui i nomi non sono pre-atomizzati:  
  
```csharp  
DateTime t1 = DateTime.Now;  
XElement root = new XElement("Root",  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement("Data",  
        new XAttribute("ID", i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti XName e XNamespace atomizzati (LINQ to XML) (C#)](./atomized-xname-and-xnamespace-objects-linq-to-xml.md)
