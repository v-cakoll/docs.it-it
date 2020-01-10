---
title: Rimozione del contenuto di un nodo nel DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
ms.openlocfilehash: f5086bdea8ff1f0ee5329f347223ebb4a6bd71da
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710336"
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="81b5b-102">Rimozione del contenuto di un nodo nel DOM</span><span class="sxs-lookup"><span data-stu-id="81b5b-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="81b5b-103">Per i tipi di nodo che ereditano da <xref:System.Xml.XmlCharacterData>, ossia <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace> e <xref:System.Xml.XmlSignificantWhitespace>, è possibile rimuovere i caratteri usando il metodo <xref:System.Xml.XmlCharacterData.DeleteData%2A>, che consente di rimuovere una serie di caratteri dal nodo.</span><span class="sxs-lookup"><span data-stu-id="81b5b-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="81b5b-104">Per rimuovere l'intero contenuto di un nodo, è necessario rimuovere il nodo stesso.</span><span class="sxs-lookup"><span data-stu-id="81b5b-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="81b5b-105">Per mantenere il nodo, anche se il contenuto non è corretto, è necessario modificare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="81b5b-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="81b5b-106">Per informazioni sulla modifica del contenuto di un nodo, vedere [Modifica di nodi, contenuto e valori in un documento XML](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="81b5b-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b5b-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81b5b-107">See also</span></span>

- [<span data-ttu-id="81b5b-108">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="81b5b-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
