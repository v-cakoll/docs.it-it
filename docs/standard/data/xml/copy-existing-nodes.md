---
title: Copia di nodi esistenti
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c026d9f825375d74d53d5cc46969ff0f713bab1c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="edb4b-102">Copia di nodi esistenti</span><span class="sxs-lookup"><span data-stu-id="edb4b-102">Copy Existing Nodes</span></span>
<span data-ttu-id="edb4b-103">Nel DOM (Document Object Model) XML sono disponibili molti metodi e proprietà che è possibile usare per selezionare un nodo, ad esempio **SelectSingleNode**, **ChildNodes[int i]** e **Attributes[int i]**.</span><span class="sxs-lookup"><span data-stu-id="edb4b-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="edb4b-104">Una volta selezionato il nodo, è possibile inserirlo nell'albero mediante uno dei metodi di inserimento applicabili a quel determinato tipo di nodo.</span><span class="sxs-lookup"><span data-stu-id="edb4b-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="edb4b-105">L'unica restrizione all'inserimento di un nodo nell'albero è che il documento deve conservare un formato corretto dopo l'inserimento del nodo.</span><span class="sxs-lookup"><span data-stu-id="edb4b-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="edb4b-106">Quando un nodo esistente viene inserito nell'albero DOM, viene rimosso dalla posizione originale e aggiunto alla posizione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="edb4b-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb4b-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edb4b-107">See Also</span></span>  
 [<span data-ttu-id="edb4b-108">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="edb4b-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
