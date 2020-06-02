---
title: Tipi di nodo riconosciuti con le query XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
ms.openlocfilehash: b9fc55b11455491406970af2a9232b277160875f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288732"
---
# <a name="node-types-recognized-with-xpath-queries"></a>Tipi di nodo riconosciuti con le query XPath
I tipi di nodi riconosciuti in una query XPath non corrispondono a quelli del DOM (Document Object Model).  
  
## <a name="w3c-xpath-node-types"></a>Tipi di nodo XPath W3C  
 I tipi di nodo riconosciuti in una query XPath non corrispondono a quelli del DOM (Document Object Model). Di seguito sono riportati i tipi di nodo XPath rappresentati dall'enumerazione <xref:System.Xml.XPath.XPathNodeType>.  
  
- <xref:System.Xml.XPath.XPathNodeType.All>  
  
- <xref:System.Xml.XPath.XPathNodeType.Attribute>  
  
- <xref:System.Xml.XPath.XPathNodeType.Comment>  
  
- <xref:System.Xml.XPath.XPathNodeType.Element>  
  
- <xref:System.Xml.XPath.XPathNodeType.Namespace>  
  
- <xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>  
  
- <xref:System.Xml.XPath.XPathNodeType.Root>  
  
- <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>  
  
- <xref:System.Xml.XPath.XPathNodeType.Text>  
  
- <xref:System.Xml.XPath.XPathNodeType.Whitespace>  
  
 Questi tipi di nodo sono basati sul modello dati XPath, dove i nodi derivano dal set di informazioni XML. I tipi di nodo <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> e <xref:System.Xml.XPath.XPathNodeType.Whitespace> sono estensioni Microsoft .NET Framework dei tipi di nodi di base descritti nel modello dati XPath.  
  
 Il tipo di nodo Attribute viene usato in modo diverso nel modello dati XPath rispetto al DOM. Nel modello dati XPath il nodo di tipo element è composto da un set di nodi Attribute a esso correlati e il nodo di tipo element è il padre di ogni nodo Attribute. Nel DOM, tuttavia, il nodo di tipo element è il proprietario e non il padre. In entrambi i modelli, i nodi Attribute e Namespace non sono considerati nodi figlio del nodo di tipo element.  
  
 Il tipo di nodo Namespace è un'aggiunta al modello dati XPath e non è un tipo di nodo DOM riconosciuto.  
  
 Per altre informazioni sulla navigazione dei nodi di elementi, attributi e spazi dei nomi, vedere gli argomenti [Navigazione del set di nodi con XPathNavigator](node-set-navigation-using-xpathnavigator.md) e [Navigazione dei nodi di attributi e dello spazio dei nomi con XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Elaborazione di dati XML con il modello di dati XPath](process-xml-data-using-the-xpath-data-model.md)
- [Selezione di dati XML con XPathNavigator](select-xml-data-using-xpathnavigator.md)
- [Valutazione di espressioni XPath con XPathNavigator](evaluate-xpath-expressions-using-xpathnavigator.md)
- [Corrispondenza di nodi utilizzando XPathNavigator](matching-nodes-using-xpathnavigator.md)
- [Query e spazi dei nomi XPath](xpath-queries-and-namespaces.md)
- [Espressioni XPath compilate](compiled-xpath-expressions.md)
