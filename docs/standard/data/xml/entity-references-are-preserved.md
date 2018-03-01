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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f5a867d1301355f4c9a77654556229274f96d00c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="entity-references-are-preserved"></a><span data-ttu-id="536f0-102">Riferimenti alle entità conservati</span><span class="sxs-lookup"><span data-stu-id="536f0-102">Entity References are Preserved</span></span>
<span data-ttu-id="536f0-103">Se il riferimento all'entità non viene espanso, ma conservato, il modello DOM (Document Object Model) XML compila un nodo **XmlEntityReference** quando rileva un riferimento all'entità.</span><span class="sxs-lookup"><span data-stu-id="536f0-103">When the entity reference is not expanded, but preserved, the XML Document Object Model (DOM) builds an **XmlEntityReference** node when it encounters an entity reference.</span></span>  
  
 <span data-ttu-id="536f0-104">Usando il seguente codice XML,</span><span class="sxs-lookup"><span data-stu-id="536f0-104">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="536f0-105">il modello DOM compila un nodo **XmlEntityReference** quando rileva il riferimento `&publisher;`.</span><span class="sxs-lookup"><span data-stu-id="536f0-105">the DOM builds an **XmlEntityReference** node when it encounters the `&publisher;` reference.</span></span> <span data-ttu-id="536f0-106">Il nodo **XmlEntityReference** contiene nodi figlio copiati dal contenuto della dichiarazione di entità.</span><span class="sxs-lookup"><span data-stu-id="536f0-106">The **XmlEntityReference** contains child nodes copied from the content in the entity declaration.</span></span> <span data-ttu-id="536f0-107">Nell'esempio di codice precedente è contenuto un testo nella dichiarazione di entità, quindi viene creato un nodo **XmlText** come nodo figlio del nodo del riferimento all'entità.</span><span class="sxs-lookup"><span data-stu-id="536f0-107">The preceding code example contains text in the entity declaration, so an **XmlText** node is created as the child node of the entity reference node.</span></span>  
  
 <span data-ttu-id="536f0-108">![Struttura ad albero per i riferimenti alle entità conservati](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span><span class="sxs-lookup"><span data-stu-id="536f0-108">![Tree structure for preserved entity references](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span></span>  
<span data-ttu-id="536f0-109">Struttura ad albero per i riferimenti alle entità conservati</span><span class="sxs-lookup"><span data-stu-id="536f0-109">Tree structure for entity references that are preserved</span></span>  
  
 <span data-ttu-id="536f0-110">I nodi figlio di **XmlEntityReference** sono copie di tutti i nodi figlio creati dal nodo **XmlEntity** quando è stata rilevata la dichiarazione di entità.</span><span class="sxs-lookup"><span data-stu-id="536f0-110">The child nodes of the **XmlEntityReference** are copies of all the child nodes created from the **XmlEntity** node when the entity declaration was encountered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="536f0-111">I nodi copiati da **XmlEntity** non sono sempre copie esatte dopo che vengono inseriti sotto il nodo del riferimento all'entità.</span><span class="sxs-lookup"><span data-stu-id="536f0-111">The nodes copied from the **XmlEntity** are not always exact copies once placed under the entity reference node.</span></span> <span data-ttu-id="536f0-112">Nell'ambito del nodo del riferimento all'entità possono essere presenti spazi dei nomi che incidono sulla configurazione finale dei nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="536f0-112">There can be namespaces that are in scope at the entity reference node, and that affects the final configuration of the child nodes.</span></span>  
  
 <span data-ttu-id="536f0-113">Per impostazione predefinita, le entità generali, ad esempio `&abc;`, vengono conservate e vengono sempre creati nodi **XmlEntityReference**.</span><span class="sxs-lookup"><span data-stu-id="536f0-113">By default, general entities like `&abc;` are preserved and **XmlEntityReference** nodes always created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="536f0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="536f0-114">See Also</span></span>  
 [<span data-ttu-id="536f0-115">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="536f0-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
