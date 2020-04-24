---
title: Rimozione di nodi dal DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
ms.openlocfilehash: a34b92abc59215c3cb2b94afd88e2e30405b4e9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710310"
---
# <a name="removing-nodes-from-the-dom"></a>Rimozione di nodi dal DOM
Per rimuovere un nodo specifico dal DOM (Document Object Model) XML, usare il metodo <xref:System.Xml.XmlNode.RemoveChild%2A>. Quando si rimuove un nodo, il metodo rimuove il sottoalbero appartenente al nodo che viene rimosso, purché tale nodo non sia un nodo foglia.  
  
 Per rimuovere più nodi dal DOM, usare il metodo <xref:System.Xml.XmlNode.RemoveAll%2A> che consente di rimuovere tutti gli eventuali elementi figlio e attributi del nodo corrente.  
  
 Se si usa una mappa di nodi <xref:System.Xml.XmlNamedNodeMap>, è possibile rimuovere un nodo usando il metodo <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A>.  
  
 Per rimuovere gli attributi, vedere [Rimozione di attributi da un nodo di tipo element nel DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## <a name="see-also"></a>Vedi anche

- [XML DOM (Document Object Model)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
