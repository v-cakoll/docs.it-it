---
title: "Creazione di nuovi riferimenti alle entità"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22e9b66f58275141cf9da154573ca43a0b90affc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-entity-references"></a><span data-ttu-id="3f2de-102">Creazione di nuovi riferimenti alle entità</span><span class="sxs-lookup"><span data-stu-id="3f2de-102">Creating New Entity References</span></span>
<span data-ttu-id="3f2de-103">Il **CreateEntityReference** crea un nuovo metodo **XmlEntityReference** nodo.</span><span class="sxs-lookup"><span data-stu-id="3f2de-103">The **CreateEntityReference** method creates a new **XmlEntityReference** node.</span></span> <span data-ttu-id="3f2de-104">Il modello DOM XML cerca di vedere se il nome dell'entità a cui si fa riferimento è già stato dichiarato.</span><span class="sxs-lookup"><span data-stu-id="3f2de-104">The XML Document Object Model (DOM) looks to see if the entity name being referenced has already been declared.</span></span> <span data-ttu-id="3f2de-105">In caso affermativo, i nodi figlio del **XmlEntityReference** nodo vengono copiati dal nodo della dichiarazione di entità.</span><span class="sxs-lookup"><span data-stu-id="3f2de-105">If it has, the child nodes of **XmlEntityReference** node are copied from the entity declaration node.</span></span> <span data-ttu-id="3f2de-106">Se non vi è alcuna dichiarazione di entità corrispondente, viene associato un nodo di testo vuoto come unico figlio del nodo del riferimento all'entità.</span><span class="sxs-lookup"><span data-stu-id="3f2de-106">If there is no entity declaration that matches, an empty text node is attached as the only child of the entity reference node.</span></span> <span data-ttu-id="3f2de-107">Poiché i nodi figlio del **XmlEntityReference** nodo sono copie di altri nodi, questi nodi figlio sono di sola lettura e non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="3f2de-107">Because the child nodes of the **XmlEntityReference** node are copies of other nodes, these child nodes are read-only and cannot be modified.</span></span>  
  
 <span data-ttu-id="3f2de-108">Dopo aver copiato i nodi, è probabile che vi sia uno spazio dei nomi nell'area di validità nel punto del riferimento all'entità.</span><span class="sxs-lookup"><span data-stu-id="3f2de-108">When the nodes are copied, there may be a namespace in scope at the point of the entity reference.</span></span> <span data-ttu-id="3f2de-109">Tale spazio dei nomi incide sulla configurazione di qualsiasi nodo di elemento o di attributo generato.</span><span class="sxs-lookup"><span data-stu-id="3f2de-109">This namespace affects the configuration of any element or attribute nodes generated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f2de-110">Il DOM aggiunge i nodi figlio per il **EntityReference** solo quando si inserisce il **EntityReference** nodo nel documento.</span><span class="sxs-lookup"><span data-stu-id="3f2de-110">The DOM adds child nodes to the **EntityReference** only when you insert the **EntityReference** node to the document.</span></span> <span data-ttu-id="3f2de-111">Appena creato **EntityReference** nodi non hanno nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="3f2de-111">Newly created **EntityReference** nodes have no child nodes.</span></span>  
  
 <span data-ttu-id="3f2de-112">Anche se il **XmlDataDocument** è una classe derivata del **XmlDocument**, **XmlDataDocument** non supporta la creazione di riferimenti a entità.</span><span class="sxs-lookup"><span data-stu-id="3f2de-112">Even though the **XmlDataDocument** is a derived class of the **XmlDocument**, the **XmlDataDocument** does not support the creation of entity references.</span></span> <span data-ttu-id="3f2de-113">In questo modo **EntityReference** gli elementi figlio sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="3f2de-113">This is because **EntityReference** children are read-only.</span></span> <span data-ttu-id="3f2de-114">Gli elementi figlio di un **EntityReference** nodo può estendersi su più aree.</span><span class="sxs-lookup"><span data-stu-id="3f2de-114">The children of an **EntityReference** node can span more than one region.</span></span> <span data-ttu-id="3f2de-115">In questo caso, parte di una riga associata con l'area che contiene una parte di un **EntityReference** sarà di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="3f2de-115">In this case, part of a row associated with the region that contains a part of an **EntityReference** will be read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f2de-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f2de-116">See Also</span></span>  
 [<span data-ttu-id="3f2de-117">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="3f2de-117">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
