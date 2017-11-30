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
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 459d746ff278ac4affa0318c1fad0aeb6a73e560
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="308db-102">Aggiornamenti dinamici di NodeLists e NamedNodeMaps</span><span class="sxs-lookup"><span data-stu-id="308db-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="308db-103">Poiché il **XmlNodeList** e **XmlNamedNodeMap** contengono un set di nodi, ma il documento XML viene caricato in memoria e viene modificato, il World Wide Web Consortium (W3C) indica che questi oggetti che contengono set di nodi devono essere dinamici.</span><span class="sxs-lookup"><span data-stu-id="308db-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="308db-104">Vale a dire che, se il documento sottostante cambia, anche i dati di questi due oggetti cambiano di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="308db-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="308db-105">Pertanto, se dispone di un **XmlNodeList** che contiene tutti gli elementi figlio di un particolare elemento (ad esempio, l'elemento X), quindi aggiungere un ulteriore elemento, elemento Q, al documento sotto l'elemento X. Il **XmlNodeList** deve essere il nuovo elemento Q aggiunto alla relativa raccolta.</span><span class="sxs-lookup"><span data-stu-id="308db-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="308db-106">Lo stesso vale per il contrario.</span><span class="sxs-lookup"><span data-stu-id="308db-106">The same is true in reverse.</span></span> <span data-ttu-id="308db-107">Se viene aggiunto un nodo di **XmlNodeList**, il documento sottostante viene aggiornato automaticamente anche.</span><span class="sxs-lookup"><span data-stu-id="308db-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="308db-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="308db-108">See Also</span></span>  
 [<span data-ttu-id="308db-109">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="308db-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
