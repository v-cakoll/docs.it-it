---
title: Rimozione di elementi, attributi e nodi da un albero XML (C#)
ms.date: 07/20/2015
ms.assetid: 07dd06d6-1117-4077-bf98-9120cf51176e
ms.openlocfilehash: badaa6bab35367d62a73f56c5221cb7d6d4a45f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591266"
---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-c"></a>Rimozione di elementi, attributi e nodi da un albero XML (C#)

È possibile modificare un albero XML, rimuovendo elementi, attributi e altri tipi di nodi.

La rimozione di un singolo elemento o di un singolo attributo da un documento XML è un processo semplice. Tuttavia, quando si rimuovono raccolte di elementi o attributi, è necessario innanzitutto materializzare una raccolta in un elenco e quindi eliminare gli elementi o gli attributi dall'elenco. L'approccio più efficace prevede l'uso del metodo di estensione <xref:System.Xml.Linq.Extensions.Remove%2A>, che consente di ottenere questi risultati.

Il motivo principale per cui scegliere questo approccio è che la maggior parte delle raccolte recuperate da un albero XML viene restituita tramite esecuzione posticipata. Se le raccolte non vengono dapprima materializzate in un elenco o se non vengono usati i metodi di estensione, è possibile riscontrare una determinata categoria di bug. Per altre informazioni, vedere [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (C#)](./mixed-declarative-code-imperative-code-bugs-linq-to-xml.md) (Bug nel codice dichiarativo/imperativo misto (LINQ to XML) (C#)).

I metodi seguenti consentono di rimuovere nodi e attributi da un albero XML.

|Metodo|Descrizione|
|------------|-----------------|
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|Rimuove un oggetto <xref:System.Xml.Linq.XAttribute> dal relativo elemento padre.|
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|Rimuove i nodi figlio da un oggetto <xref:System.Xml.Linq.XContainer>.|
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|Rimuove il contenuto e gli attributi da un oggetto <xref:System.Xml.Linq.XElement>.|
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|Rimuove gli attributi di un oggetto <xref:System.Xml.Linq.XElement>.|
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|Se viene passato `null` come valore, rimuove l'attributo.|
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|Se viene passato `null` come valore, rimuove l'elemento figlio.|
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|Rimuove un oggetto <xref:System.Xml.Linq.XNode> dal relativo elemento padre.|
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|Rimuove ogni attributo o elemento nella raccolta di origine dal relativo elemento padre.|

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

In questo esempio sono illustrati tre approcci per la rimozione di elementi. Con il primo viene rimosso un singolo elemento. Con il secondo viene recuperata una raccolta di elementi, che viene materializzata tramite l'operatore <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> e quindi viene rimossa. Infine, viene recuperata una raccolta di elementi che viene rimossa tramite il metodo di estensione <xref:System.Xml.Linq.Extensions.Remove%2A>.

Per altre informazioni sull'operatore <xref:System.Linq.Enumerable.ToList%2A>, vedere [Conversione di tipi di dati (C#)](./converting-data-types.md).

### <a name="code"></a>Codice

```csharp
XElement root = XElement.Parse(@"<Root>
    <Child1>
        <GrandChild1/>
        <GrandChild2/>
        <GrandChild3/>
    </Child1>
    <Child2>
        <GrandChild4/>
        <GrandChild5/>
        <GrandChild6/>
    </Child2>
    <Child3>
        <GrandChild7/>
        <GrandChild8/>
        <GrandChild9/>
    </Child3>
</Root>");
root.Element("Child1").Element("GrandChild1").Remove();
root.Element("Child2").Elements().ToList().Remove();
root.Element("Child3").Elements().Remove();
Console.WriteLine(root);
```

### <a name="comments"></a>Commenti

L'output del codice è il seguente:

```xml
<Root>
  <Child1>
    <GrandChild2 />
    <GrandChild3 />
  </Child1>
  <Child2 />
  <Child3 />
</Root>
```

Si noti che il primo elemento nipote è stato rimosso da `Child1`. Tutti gli elementi nipote sono stati rimossi da `Child2` e da `Child3`.
