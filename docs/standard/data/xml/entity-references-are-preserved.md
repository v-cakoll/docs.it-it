---
title: "Riferimenti alle entità conservati"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 770c714e8f5942ea733c417ae9b06f69e4acf1a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-preserved"></a><span data-ttu-id="7ea3d-102">Riferimenti alle entità conservati</span><span class="sxs-lookup"><span data-stu-id="7ea3d-102">Entity References are Preserved</span></span>
<span data-ttu-id="7ea3d-103">Quando il riferimento all'entità non è espanso, ma conservato, l'oggetto modello DOM (Document XML) viene compilato un **XmlEntityReference** nodo quando viene rilevato un riferimento all'entità.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-103">When the entity reference is not expanded, but preserved, the XML Document Object Model (DOM) builds an **XmlEntityReference** node when it encounters an entity reference.</span></span>  
  
 <span data-ttu-id="7ea3d-104">Usando il seguente codice XML,</span><span class="sxs-lookup"><span data-stu-id="7ea3d-104">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="7ea3d-105">il modello DOM compila un **XmlEntityReference** nodo quando viene rilevato il `&publisher;` riferimento.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-105">the DOM builds an **XmlEntityReference** node when it encounters the `&publisher;` reference.</span></span> <span data-ttu-id="7ea3d-106">Il **XmlEntityReference** contiene nodi figlio copiati dal contenuto della dichiarazione di entità.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-106">The **XmlEntityReference** contains child nodes copied from the content in the entity declaration.</span></span> <span data-ttu-id="7ea3d-107">Esempio di codice precedente contiene il testo nella dichiarazione di entità, pertanto un **XmlText** nodo viene creato come nodo figlio del nodo di riferimento di entità.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-107">The preceding code example contains text in the entity declaration, so an **XmlText** node is created as the child node of the entity reference node.</span></span>  
  
 <span data-ttu-id="7ea3d-108">![Struttura per i riferimenti alle entità conservati](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span><span class="sxs-lookup"><span data-stu-id="7ea3d-108">![Tree structure for preserved entity references](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span></span>  
<span data-ttu-id="7ea3d-109">Struttura ad albero per i riferimenti alle entità conservati</span><span class="sxs-lookup"><span data-stu-id="7ea3d-109">Tree structure for entity references that are preserved</span></span>  
  
 <span data-ttu-id="7ea3d-110">I nodi figlio del **XmlEntityReference** sono copie di tutti gli elementi figlio di nodi creati dal **XmlEntity** nodo quando è stata rilevata la dichiarazione di entità.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-110">The child nodes of the **XmlEntityReference** are copies of all the child nodes created from the **XmlEntity** node when the entity declaration was encountered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ea3d-111">I nodi copiati dal **XmlEntity** non sono sempre copie esatte una volta posizionate sotto il nodo di riferimento di entità.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-111">The nodes copied from the **XmlEntity** are not always exact copies once placed under the entity reference node.</span></span> <span data-ttu-id="7ea3d-112">Nell'ambito del nodo del riferimento all'entità possono essere presenti spazi dei nomi che incidono sulla configurazione finale dei nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-112">There can be namespaces that are in scope at the entity reference node, and that affects the final configuration of the child nodes.</span></span>  
  
 <span data-ttu-id="7ea3d-113">Per impostazione predefinita, le entità generali quali `&abc;` vengono mantenuti e **XmlEntityReference** vengono sempre creati nodi.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-113">By default, general entities like `&abc;` are preserved and **XmlEntityReference** nodes always created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea3d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ea3d-114">See Also</span></span>  
 [<span data-ttu-id="7ea3d-115">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="7ea3d-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
