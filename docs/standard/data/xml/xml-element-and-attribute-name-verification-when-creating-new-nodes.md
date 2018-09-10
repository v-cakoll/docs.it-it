---
title: Verifica dei nomi di elementi e di attributi XML durante la creazione di nuovi nodi
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 008cf14e63b8458feebf26eaf27be516bb79f933
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216041"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="cb345-102">Verifica dei nomi di elementi e di attributi XML durante la creazione di nuovi nodi</span><span class="sxs-lookup"><span data-stu-id="cb345-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="cb345-103">La validità dei nomi viene controllata dal modello DOM XML durante la creazione di nuovi nodi di elementi o di attributi.</span><span class="sxs-lookup"><span data-stu-id="cb345-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="cb345-104">Se i nomi contengono caratteri non validi, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cb345-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="cb345-105">Per garantire che i nomi siano validi e codificati correttamente, è necessario usare la classe **XmlConvert** per codificare il nome e decodificarlo nuovamente al livello dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cb345-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="cb345-106">**XmlWriter** dispone di metodi con cui vengono eseguite operazioni aggiuntive per garantire che venga generato un XML in formato corretto.</span><span class="sxs-lookup"><span data-stu-id="cb345-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb345-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb345-107">See also</span></span>

- [<span data-ttu-id="cb345-108">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="cb345-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
