---
title: Rimozione di nodi dal DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be592466627e6ee7b23c608e0defe786548907ad
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46576561"
---
# <a name="removing-nodes-from-the-dom"></a><span data-ttu-id="4e0a3-102">Rimozione di nodi dal DOM</span><span class="sxs-lookup"><span data-stu-id="4e0a3-102">Removing Nodes from the DOM</span></span>
<span data-ttu-id="4e0a3-103">Per rimuovere un nodo specifico dal DOM (Document Object Model) XML, usare il metodo <xref:System.Xml.XmlNode.RemoveChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="4e0a3-103">To remove a node from the XML Document Object Model (DOM), use the <xref:System.Xml.XmlNode.RemoveChild%2A> method to remove a specific node.</span></span> <span data-ttu-id="4e0a3-104">Quando si rimuove un nodo, il metodo rimuove il sottoalbero appartenente al nodo che viene rimosso, purché tale nodo non sia un nodo foglia.</span><span class="sxs-lookup"><span data-stu-id="4e0a3-104">When you remove a node, the method removes the subtree belonging to the node being removed; that is, if it is not a leaf node.</span></span>  
  
 <span data-ttu-id="4e0a3-105">Per rimuovere più nodi dal DOM, usare il metodo <xref:System.Xml.XmlNode.RemoveAll%2A> che consente di rimuovere tutti gli eventuali elementi figlio e attributi del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="4e0a3-105">To remove multiple nodes from the DOM, use the <xref:System.Xml.XmlNode.RemoveAll%2A> method to remove all the children and attributes, if applicable, of the current node.</span></span>  
  
 <span data-ttu-id="4e0a3-106">Se si usa una mappa di nodi <xref:System.Xml.XmlNamedNodeMap>, è possibile rimuovere un nodo usando il metodo <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="4e0a3-106">If you are working with an <xref:System.Xml.XmlNamedNodeMap>, you can remove a node using the <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> method.</span></span>  
  
 <span data-ttu-id="4e0a3-107">Per rimuovere gli attributi, vedere [Rimozione di attributi da un nodo di tipo element nel DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="4e0a3-107">To remove attributes, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0a3-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e0a3-108">See also</span></span>

- [<span data-ttu-id="4e0a3-109">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="4e0a3-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
