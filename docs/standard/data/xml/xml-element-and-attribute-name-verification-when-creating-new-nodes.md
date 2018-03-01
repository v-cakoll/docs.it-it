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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 36b9761cefb1dba47c88d053773c89e4312dee9d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="1a355-102">Verifica dei nomi di elementi e di attributi XML durante la creazione di nuovi nodi</span><span class="sxs-lookup"><span data-stu-id="1a355-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="1a355-103">La validità dei nomi viene controllata dal modello DOM XML durante la creazione di nuovi nodi di elementi o di attributi.</span><span class="sxs-lookup"><span data-stu-id="1a355-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="1a355-104">Se i nomi contengono caratteri non validi, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1a355-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="1a355-105">Per garantire che i nomi siano validi e codificati correttamente, è necessario usare la classe **XmlConvert** per codificare il nome e decodificarlo nuovamente al livello dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1a355-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="1a355-106">**XmlWriter** dispone di metodi con cui vengono eseguite operazioni aggiuntive per garantire che venga generato un XML in formato corretto.</span><span class="sxs-lookup"><span data-stu-id="1a355-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a355-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a355-107">See Also</span></span>  
 [<span data-ttu-id="1a355-108">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="1a355-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
