---
title: Rimozione di nodi dal DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec786564e6246f10e10d600f4822442884323557
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568459"
---
# <a name="removing-nodes-from-the-dom"></a><span data-ttu-id="8ac1a-102">Rimozione di nodi dal DOM</span><span class="sxs-lookup"><span data-stu-id="8ac1a-102">Removing Nodes from the DOM</span></span>
<span data-ttu-id="8ac1a-103">Per rimuovere un nodo specifico dal DOM (Document Object Model) XML, usare il metodo <xref:System.Xml.XmlNode.RemoveChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ac1a-103">To remove a node from the XML Document Object Model (DOM), use the <xref:System.Xml.XmlNode.RemoveChild%2A> method to remove a specific node.</span></span> <span data-ttu-id="8ac1a-104">Quando si rimuove un nodo, il metodo rimuove il sottoalbero appartenente al nodo che viene rimosso, purché tale nodo non sia un nodo foglia.</span><span class="sxs-lookup"><span data-stu-id="8ac1a-104">When you remove a node, the method removes the subtree belonging to the node being removed; that is, if it is not a leaf node.</span></span>  
  
 <span data-ttu-id="8ac1a-105">Per rimuovere più nodi dal DOM, usare il metodo <xref:System.Xml.XmlNode.RemoveAll%2A> che consente di rimuovere tutti gli eventuali elementi figlio e attributi del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="8ac1a-105">To remove multiple nodes from the DOM, use the <xref:System.Xml.XmlNode.RemoveAll%2A> method to remove all the children and attributes, if applicable, of the current node.</span></span>  
  
 <span data-ttu-id="8ac1a-106">Se si usa una mappa di nodi <xref:System.Xml.XmlNamedNodeMap>, è possibile rimuovere un nodo usando il metodo <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ac1a-106">If you are working with an <xref:System.Xml.XmlNamedNodeMap>, you can remove a node using the <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> method.</span></span>  
  
 <span data-ttu-id="8ac1a-107">Per rimuovere gli attributi, vedere [Rimozione di attributi da un nodo di tipo element nel DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="8ac1a-107">To remove attributes, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ac1a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ac1a-108">See Also</span></span>  
 [<span data-ttu-id="8ac1a-109">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="8ac1a-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
