---
title: Confronto tra XPath e LINQ to XML
description: Informazioni sulle analogie e sulle differenze di funzionalità tra XPath e LINQ to XML in C#. È possibile utilizzare entrambi per eseguire una query su un albero XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 87d361b1-daa9-4fd4-a53a-cbfa40111ad3
ms.openlocfilehash: e2f34903b20a53dea6e5ff4858d4fadaebd9c37a
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104004"
---
# <a name="comparison-of-xpath-and-linq-to-xml"></a>Confronto tra XPath e LINQ to XML
XPath e LINQ to XML offrono alcune funzionalità analoghe. Entrambi possono essere usati per eseguire query su un albero XML, restituendo risultati quali una raccolta di elementi, una raccolta di attributi, una raccolta di nodi o il valore di un elemento o di un attributo. Esistono tuttavia alcune differenze.  
  
## <a name="differences-between-xpath-and-linq-to-xml"></a>Differenze tra XPath e LINQ to XML  
 XPath non consente la proiezione di nuovi tipi. Può restituire solo raccolte di nodi dall'albero, mentre tramite LINQ to XML può eseguire una query e proiettare un oggetto grafico o un albero XML in una nuova forma. Le query LINQ to XML includono molte più funzionalità e sono molto più efficaci delle espressioni XPath.  
  
 Le espressioni XPath esistono in isolamento all'interno di una stringa. Il compilatore C# non consente di analizzare l'espressione XPath in fase di compilazione. Al contrario, le query LINQ to XML vengono analizzate e compilate tramite il compilatore C#. Il compilatore è in grado di intercettare molti errori di query.  
  
 I risultati di XPath non sono fortemente tipizzati. In diverse circostanze il risultato della valutazione di un'espressione XPath è un oggetto e spetta allo sviluppatore determinare il tipo appropriato ed eseguire il cast del risultato secondo necessità. Al contrario, le proiezioni di una query LINQ to XML sono fortemente tipizzate.  
  
## <a name="result-ordering"></a>Ordinazione di risultati  
 Nella raccomandazione XPath 1.0 si afferma che una raccolta corrispondente al risultato della valutazione di un'espressione XPath non è ordinata.  
  
 Tuttavia, quando si esegue l'iterazione di una raccolta restituita da un metodo dell'asse XPath LINQ to XML, i nodi della raccolta vengono restituiti nell'ordine del documento. Ciò è vero anche quando si accede a assi XPath in cui i predicati sono espressi in termini di ordine inverso del documento, ad esempio `preceding` e `preceding-sibling`.  
  
 Al contrario, la maggior parte degli assi LINQ to XML restituisce le raccolte nell'ordine del documento, ma due di essi, <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A> e <xref:System.Xml.Linq.XNode.Ancestors%2A>, restituiscono le raccolte nell'ordine inverso del documento. Nella tabella seguente sono enumerati gli assi e viene indicato l'ordine delle raccolte per ognuno di essi:  
  
|Asse LINQ to XML|Ordering|  
|----------------------|--------------|  
|XContainer.DescendantNodes|Ordine del documento|  
|XContainer.Descendants|Ordine del documento|  
|XContainer.Elements|Ordine del documento|  
|XContainer.Nodes|Ordine del documento|  
|XContainer.NodesAfterSelf|Ordine del documento|  
|XContainer.NodesBeforeSelf|Ordine del documento|  
|XElement.AncestorsAndSelf|Ordine inverso del documento|  
|XElement.Attributes|Ordine del documento|  
|XElement.DescendantNodesAndSelf|Ordine del documento|  
|XElement.DescendantsAndSelf|Ordine del documento|  
|XNode.Ancestors|Ordine inverso del documento|  
|XNode.ElementsAfterSelf|Ordine del documento|  
|XNode.ElementsBeforeSelf|Ordine del documento|  
|XNode.NodesAfterSelf|Ordine del documento|  
|XNode.NodesBeforeSelf|Ordine del documento|  
  
## <a name="positional-predicates"></a>Predicati di posizione  
 All'interno di un'espressione XPath, i predicati di posizione vengono espressi in termini di ordine del documento per molti assi, mentre sono espressi in ordine inverso del documento per gli assi inversi, che sono `preceding`, `preceding-sibling`, `ancestor` e `ancestor-or-self`. Ad esempio, l'espressione XPath `preceding-sibling::*[1]` restituisce l'elemento di pari livello immediatamente precedente. Ciò è vero anche se il set di risultati finale è presentato nell'ordine del documento.  
  
 Al contrario, tutti i predicati di posizione di LINQ to XML sono sempre espressi in termini di ordine dell'asse. Ad esempio, `anElement.ElementsBeforeSelf().ElementAt(0)` restituisce il primo elemento figlio del padre dell'elemento sottoposto a query, non l'elemento di pari livello immediatamente precedente. Un altro esempio: `anElement.Ancestors().ElementAt(0)` restituisce l'elemento padre.  
  
 Se si vuole trovare l'elemento immediatamente precedente in LINQ to XML, scrivere l'espressione seguente:  
  
```csharp
ElementsBeforeSelf().Last()
```
  
```vb
ElementsBeforeSelf().Last()
```
  
## <a name="performance-differences"></a>Differenze di prestazioni  
 Le query XPath che usano la funzionalità XPath in LINQ to XML non garantiscono le stesse prestazioni delle query LINQ to XML.  
  
## <a name="comparison-of-composition"></a>Confronto di composizione  
 La composizione di una query LINQ to XML è parallela a quella di un'espressione XPath, anche se molto diversa nella sintassi.  
  
 Se ad esempio una variabile denominata `customers` contiene un elemento e si desidera trovare un elemento nipote denominato `CompanyName` sotto tutti gli elementi figlio denominati `Customer`, è necessario scrivere la seguente espressione XPath:  
  
```csharp  
customers.XPathSelectElements("./Customer/CompanyName")
```  
  
```vb
customers.XPathSelectElements("./Customer/CompanyName")
```

 L'equivalente di una query LINQ to XML è:  
  
```csharp  
customers.Elements("Customer").Elements("CompanyName")
```  
  
```vb
customers.Elements("Customer").Elements("CompanyName")
```  

 Esistono paralleli analoghi per ogni asse XPath.  
  
|Asse XPath|Asse LINQ to XML|  
|----------------|----------------------|  
|child (asse predefinito)|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|  
|Parent (..)|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=nameWithType>|  
|attribute (@)|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType><br /><br /> oppure<br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|  
|asse ancestor|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|  
|asse ancestor-or-self|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|  
|asse descendant (//)|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType><br /><br /> oppure<br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=nameWithType>|  
|descendant-or-self|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType><br /><br /> oppure<br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=nameWithType>|  
|following-sibling|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType><br /><br /> oppure<br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=nameWithType>|  
|preceding-sibling|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType><br /><br /> oppure<br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=nameWithType>|  
|following|Nessun equivalente diretto.|  
|preceding|Nessun equivalente diretto.|  
  