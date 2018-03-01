---
title: "Influenza dello spazio dei nomi sull'espansione dei riferimenti alle entità per i nuovi nodi contenenti elementi e attributi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9b59f85eb0ef6646345eaef2a409f622c6fe4651
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a><span data-ttu-id="a7fc3-102">Influenza dello spazio dei nomi sull'espansione dei riferimenti alle entità per i nuovi nodi contenenti elementi e attributi</span><span class="sxs-lookup"><span data-stu-id="a7fc3-102">Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes</span></span>
<span data-ttu-id="a7fc3-103">Poiché il contenuto di una dichiarazione di entità può contenere praticamente qualsiasi elemento, è possibile che contenga un elemento quale `<!ENTITY aname "<elem>test</elem>">`.</span><span class="sxs-lookup"><span data-stu-id="a7fc3-103">Because the content of an entity declaration can contain almost anything, there is a possibility that the content could contain an element like `<!ENTITY aname "<elem>test</elem>">`.</span></span>  
  
 <span data-ttu-id="a7fc3-104">Quando il codice XML viene analizzato dal parser, `&aname;` non viene espanso con il contenuto di sostituzione durante l'analisi.</span><span class="sxs-lookup"><span data-stu-id="a7fc3-104">When the XML is parsed, `&aname;` is not expanded with its replacement content at parse time.</span></span> <span data-ttu-id="a7fc3-105">L'espansione del codice XML non viene eseguita in quanto la risoluzione dello spazio dei nomi dell'elemento non può verificarsi fino a quando il nodo non viene posizionato nel documento.</span><span class="sxs-lookup"><span data-stu-id="a7fc3-105">The expansion of the XML is not done because resolution of the namespace for the element cannot occur until the node is placed in the document.</span></span> <span data-ttu-id="a7fc3-106">Fino a quel momento, non è possibile sapere quale spazio dei nomi è incluso nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="a7fc3-106">Until that time, there is no knowledge of what namespace is in scope.</span></span> <span data-ttu-id="a7fc3-107">Quando il nodo viene inserito nel documento, si verifica la risoluzione dello spazio dei nomi e il contenuto dell'entità risultante viene analizzato dal parser nei nodi appropriati.</span><span class="sxs-lookup"><span data-stu-id="a7fc3-107">When the node is put into the document, then the namespace resolution occurs, and the resulting entity content is parsed into its appropriate nodes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7fc3-108">Una volta verificatasi l'espansione su un nodo di riferimento all'entità appena creato, l'espansione non si ripete.</span><span class="sxs-lookup"><span data-stu-id="a7fc3-108">Once the expansion occurs on a newly created entity reference node, it never reoccurs.</span></span> <span data-ttu-id="a7fc3-109">Pertanto gli spazi dei nomi usati nel testo di sostituzione per l'elemento vengono associati nel momento in cui viene impostato il nodo padre.</span><span class="sxs-lookup"><span data-stu-id="a7fc3-109">Therefore, the namespaces used in the replacement text for the element are bound at the time that the parent node is set.</span></span> <span data-ttu-id="a7fc3-110">È tuttavia possibile modificare lo spazio dei nomi nel caso in cui i nodi di riferimento all'entità esistenti vengano rimossi e quindi inseriti in un punto diverso o nel caso di nodi di riferimento all'entità clonati con il metodo **CloneNode**.</span><span class="sxs-lookup"><span data-stu-id="a7fc3-110">However, the namespace can be changed for existing entity reference nodes when you remove and insert them somewhere else, or on entity reference nodes that are cloned with the **CloneNode** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7fc3-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7fc3-111">See Also</span></span>  
 [<span data-ttu-id="a7fc3-112">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="a7fc3-112">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
