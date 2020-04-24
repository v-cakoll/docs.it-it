---
title: Aggiornamenti dinamici di NodeLists e NamedNodeMaps
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
ms.openlocfilehash: 58dfde94c2f37b0a09ee795b9df20296c9f86da6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710973"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="72fe3-102">Aggiornamenti dinamici di NodeLists e NamedNodeMaps</span><span class="sxs-lookup"><span data-stu-id="72fe3-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="72fe3-103">Poiché in **XmlNodeList** e **XmlNamedNodeMap** è contenuto un set di nodi e il documento XML è già stato caricato in memoria e sottoposto a modifiche, il W3C (World Wide Web Consortium) stabilisce che questi oggetti contenenti set di nodi debbano essere dinamici.</span><span class="sxs-lookup"><span data-stu-id="72fe3-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="72fe3-104">Vale a dire che, se il documento sottostante cambia, anche i dati di questi due oggetti cambiano di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="72fe3-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="72fe3-105">Se quindi un **XmlNodeList** contiene tutti gli elementi figlio di un particolare elemento (ad esempio l'elemento X), si aggiunge un ulteriore elemento, l'elemento Q, al documento sotto l'elemento X. Nell'elenco **XmlNodeList** deve essere disponibile anche il nuovo elemento Q aggiunto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="72fe3-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="72fe3-106">Lo stesso vale per il contrario.</span><span class="sxs-lookup"><span data-stu-id="72fe3-106">The same is true in reverse.</span></span> <span data-ttu-id="72fe3-107">Se si aggiunge un nodo a **XmlNodeList**, il documento sottostante viene anch'esso aggiornato.</span><span class="sxs-lookup"><span data-stu-id="72fe3-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72fe3-108">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="72fe3-108">See also</span></span>

- [<span data-ttu-id="72fe3-109">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="72fe3-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
