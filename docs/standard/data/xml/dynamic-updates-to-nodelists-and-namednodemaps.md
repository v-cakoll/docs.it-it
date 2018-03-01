---
title: Aggiornamenti dinamici di NodeLists e NamedNodeMaps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8a7abbb7344530ca993b8d07b774da17e6d0349b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="49978-102">Aggiornamenti dinamici di NodeLists e NamedNodeMaps</span><span class="sxs-lookup"><span data-stu-id="49978-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="49978-103">Poiché in **XmlNodeList** e **XmlNamedNodeMap** è contenuto un set di nodi e il documento XML è già stato caricato in memoria e sottoposto a modifiche, il W3C (World Wide Web Consortium) stabilisce che questi oggetti contenenti set di nodi debbano essere dinamici.</span><span class="sxs-lookup"><span data-stu-id="49978-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="49978-104">Vale a dire che, se il documento sottostante cambia, anche i dati di questi due oggetti cambiano di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="49978-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="49978-105">Se quindi un **XmlNodeList** contiene tutti gli elementi figlio di un particolare elemento (ad esempio l'elemento X), si aggiunge un ulteriore elemento, l'elemento Q, al documento sotto l'elemento X. Nell'elenco **XmlNodeList** deve essere disponibile anche il nuovo elemento Q aggiunto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="49978-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="49978-106">Lo stesso vale per il contrario.</span><span class="sxs-lookup"><span data-stu-id="49978-106">The same is true in reverse.</span></span> <span data-ttu-id="49978-107">Se si aggiunge un nodo a **XmlNodeList**, il documento sottostante viene anch'esso aggiornato.</span><span class="sxs-lookup"><span data-stu-id="49978-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49978-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49978-108">See Also</span></span>  
 [<span data-ttu-id="49978-109">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="49978-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
