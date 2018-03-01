---
title: Raccolte di nodi in NamedNodeMaps e NodeLists
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 025954b8-7aa8-47c5-a1c1-f81064fb4d65
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ff327c1a450e9ce712d496bdca2cd2ebbff6adda
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="node-collections-in-namednodemaps-and-nodelists"></a><span data-ttu-id="61cae-102">Raccolte di nodi in NamedNodeMaps e NodeLists</span><span class="sxs-lookup"><span data-stu-id="61cae-102">Node Collections in NamedNodeMaps and NodeLists</span></span>
<span data-ttu-id="61cae-103">È possibile recuperare un set di nodi e inserirlo in una raccolta ordinata o non ordinata.</span><span class="sxs-lookup"><span data-stu-id="61cae-103">You can retrieve a set of nodes and put it in an ordered or unordered collection.</span></span> <span data-ttu-id="61cae-104">Quando si inserisce un set di nodi in una raccolta non ordinata, tale set viene chiamato NamedNodeMap dal W3C; in questo tipo di raccolta è possibile recuperare i dati in base al nome o all'indice.</span><span class="sxs-lookup"><span data-stu-id="61cae-104">When putting a set of nodes into an unordered collection, the set is called a NamedNodeMap by the World Wide Web Consortium (W3C); you can retrieve the data by name or index in this type of collection.</span></span> <span data-ttu-id="61cae-105">L'inserimento di un set di nodi in una raccolta ordinata viene denominato NodeList dal W3C e i dati possono essere recuperati tramite un indice con base zero.</span><span class="sxs-lookup"><span data-stu-id="61cae-105">Putting a set of nodes in an ordered collection is called a NodeList by the W3C, and the data can be retrieved by a zero-based index.</span></span> <span data-ttu-id="61cae-106">NamedNodeMaps e NodeLists sono descritti dal W3C.</span><span class="sxs-lookup"><span data-stu-id="61cae-106">NamedNodeMaps and NodeLists are described by the W3C.</span></span> <span data-ttu-id="61cae-107">Le implementazioni in Microsoft .NET Framework per NamedNodeMap sono **XmlNamedNodeMap** e NodeList viene implementato da **XmlNodeList**.</span><span class="sxs-lookup"><span data-stu-id="61cae-107">The implementations in the Microsoft .NET Framework for the NamedNodeMap is the **XmlNamedNodeMap**, and the NodeList is implemented by the **XmlNodeList**.</span></span>  
  
 <span data-ttu-id="61cae-108">Per informazioni sulle raccolte non ordinate, vedere [Recupero di nodi non ordinati in base al nome o all'indice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="61cae-108">For information on the unordered collection, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span> <span data-ttu-id="61cae-109">Per informazioni sulle raccolte ordinate, vedere [Recupero di nodi ordinati in base all'indice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="61cae-109">For information on the ordered collection, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cae-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61cae-110">See Also</span></span>  
 [<span data-ttu-id="61cae-111">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="61cae-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
