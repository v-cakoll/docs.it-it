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
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 39110a9b44e6efbe7ad0331cfdb4fbe6078e7cfc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a><span data-ttu-id="fab71-102">Influenza dello spazio dei nomi sull'espansione dei riferimenti alle entità per i nuovi nodi contenenti elementi e attributi</span><span class="sxs-lookup"><span data-stu-id="fab71-102">Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes</span></span>
<span data-ttu-id="fab71-103">Poiché il contenuto di una dichiarazione di entità può contenere praticamente qualsiasi elemento, è possibile che contenga un elemento quale `<!ENTITY aname "<elem>test</elem>">`.</span><span class="sxs-lookup"><span data-stu-id="fab71-103">Because the content of an entity declaration can contain almost anything, there is a possibility that the content could contain an element like `<!ENTITY aname "<elem>test</elem>">`.</span></span>  
  
 <span data-ttu-id="fab71-104">Quando il codice XML viene analizzato dal parser, `&aname;` non viene espanso con il contenuto di sostituzione durante l'analisi.</span><span class="sxs-lookup"><span data-stu-id="fab71-104">When the XML is parsed, `&aname;` is not expanded with its replacement content at parse time.</span></span> <span data-ttu-id="fab71-105">L'espansione del codice XML non viene eseguita in quanto la risoluzione dello spazio dei nomi dell'elemento non può verificarsi fino a quando il nodo non viene posizionato nel documento.</span><span class="sxs-lookup"><span data-stu-id="fab71-105">The expansion of the XML is not done because resolution of the namespace for the element cannot occur until the node is placed in the document.</span></span> <span data-ttu-id="fab71-106">Fino a quel momento, non è possibile sapere quale spazio dei nomi è incluso nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="fab71-106">Until that time, there is no knowledge of what namespace is in scope.</span></span> <span data-ttu-id="fab71-107">Quando il nodo viene inserito nel documento, si verifica la risoluzione dello spazio dei nomi e il contenuto dell'entità risultante viene analizzato dal parser nei nodi appropriati.</span><span class="sxs-lookup"><span data-stu-id="fab71-107">When the node is put into the document, then the namespace resolution occurs, and the resulting entity content is parsed into its appropriate nodes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fab71-108">Una volta verificatasi l'espansione su un nodo di riferimento all'entità appena creato, l'espansione non si ripete.</span><span class="sxs-lookup"><span data-stu-id="fab71-108">Once the expansion occurs on a newly created entity reference node, it never reoccurs.</span></span> <span data-ttu-id="fab71-109">Pertanto gli spazi dei nomi usati nel testo di sostituzione per l'elemento vengono associati nel momento in cui viene impostato il nodo padre.</span><span class="sxs-lookup"><span data-stu-id="fab71-109">Therefore, the namespaces used in the replacement text for the element are bound at the time that the parent node is set.</span></span> <span data-ttu-id="fab71-110">Tuttavia, lo spazio dei nomi può essere modificato per i nodi di riferimento di entità esistenti quando si rimuove e inserirli in un'altra posizione o in nodi di riferimento all'entità clonati con il **CloneNode** metodo.</span><span class="sxs-lookup"><span data-stu-id="fab71-110">However, the namespace can be changed for existing entity reference nodes when you remove and insert them somewhere else, or on entity reference nodes that are cloned with the **CloneNode** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab71-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fab71-111">See Also</span></span>  
 [<span data-ttu-id="fab71-112">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="fab71-112">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
