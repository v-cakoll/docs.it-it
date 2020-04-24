---
title: Corrispondenza di nodi utilizzando XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
ms.openlocfilehash: f0988c3a112fefc351175de02c790dc25fe6e94a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710687"
---
# <a name="matching-nodes-using-xpathnavigator"></a>Corrispondenza di nodi utilizzando XPathNavigator
La classe <xref:System.Xml.XPath.XPathNavigator> fornisce il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> per determinare se un nodo corrisponde a un'espressione XPath. Il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> accetta un'espressione XPath come input e restituisce un oggetto <xref:System.Boolean> che indica se il nodo corrente corrisponde all'espressione XPath o all'oggetto <xref:System.Xml.XPath.XPathExpression> compilato fornito.  
  
## <a name="matching-nodes"></a>Corrispondenza di nodi  
 Il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> restituisce `true` se il nodo corrente corrisponde all'espressione XPath specificata. Ad esempio, nel seguente esempio di codice, il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> restituirà `true` se il nodo corrente è l'elemento `b` e se l'elemento `b` presenta un attributo `c`.  
  
> [!NOTE]
> Il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> non influisce sullo stato del tipo <xref:System.Xml.XPath.XPathNavigator>.  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Elaborazione di dati XML con il modello di dati XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Selezione di dati XML con XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [Valutazione di espressioni XPath con XPathNavigator](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [Tipi di nodo riconosciuti con le query XPath](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [Query e spazi dei nomi XPath](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [Espressioni XPath compilate](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
