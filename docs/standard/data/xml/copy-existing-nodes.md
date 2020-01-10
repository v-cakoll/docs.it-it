---
title: Copia di nodi esistenti
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: fb9ccd7b16d00355ba87bb32f5447906feeecd94
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711064"
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="c36b6-102">Copia di nodi esistenti</span><span class="sxs-lookup"><span data-stu-id="c36b6-102">Copy Existing Nodes</span></span>
<span data-ttu-id="c36b6-103">Nel DOM (Document Object Model) XML sono disponibili molti metodi e proprietà che è possibile usare per selezionare un nodo, ad esempio **SelectSingleNode**, **ChildNodes[int i]** e **Attributes[int i]** .</span><span class="sxs-lookup"><span data-stu-id="c36b6-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="c36b6-104">Una volta selezionato il nodo, è possibile inserirlo nell'albero mediante uno dei metodi di inserimento applicabili a quel determinato tipo di nodo.</span><span class="sxs-lookup"><span data-stu-id="c36b6-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="c36b6-105">L'unica restrizione all'inserimento di un nodo nell'albero è che il documento deve conservare un formato corretto dopo l'inserimento del nodo.</span><span class="sxs-lookup"><span data-stu-id="c36b6-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="c36b6-106">Quando un nodo esistente viene inserito nell'albero DOM, viene rimosso dalla posizione originale e aggiunto alla posizione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c36b6-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36b6-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c36b6-107">See also</span></span>

- [<span data-ttu-id="c36b6-108">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="c36b6-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
