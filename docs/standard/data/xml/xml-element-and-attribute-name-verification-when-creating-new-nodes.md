---
title: Verifica dei nomi di elementi e di attributi XML durante la creazione di nuovi nodi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c041d5d2830222f3fae09a39f1ea10eb08772388
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="48c03-102">Verifica dei nomi di elementi e di attributi XML durante la creazione di nuovi nodi</span><span class="sxs-lookup"><span data-stu-id="48c03-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="48c03-103">La validità dei nomi viene controllata dal modello DOM XML durante la creazione di nuovi nodi di elementi o di attributi.</span><span class="sxs-lookup"><span data-stu-id="48c03-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="48c03-104">Se i nomi contengono caratteri non validi, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="48c03-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="48c03-105">Per garantire che i nomi siano validi e codificati correttamente, è necessario utilizzare il **XmlConvert** classe per codificare il nome e decodificarlo nuovamente al livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="48c03-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="48c03-106">Il **XmlWriter** dispone di metodi che eseguono operazioni aggiuntive per assicurarsi che verrà generato XML ben formato.</span><span class="sxs-lookup"><span data-stu-id="48c03-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c03-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48c03-107">See Also</span></span>  
 [<span data-ttu-id="48c03-108">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="48c03-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
