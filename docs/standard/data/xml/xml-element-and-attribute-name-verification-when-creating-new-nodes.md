---
title: Verifica dei nomi di elementi e di attributi XML durante la creazione di nuovi nodi
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
ms.openlocfilehash: 1da893261b35c6b57c4f08eb53b7701ec1d81fae
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289850"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="984af-102">Verifica dei nomi di elementi e di attributi XML durante la creazione di nuovi nodi</span><span class="sxs-lookup"><span data-stu-id="984af-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="984af-103">La validità dei nomi viene controllata dal modello DOM XML durante la creazione di nuovi nodi di elementi o di attributi.</span><span class="sxs-lookup"><span data-stu-id="984af-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="984af-104">Se i nomi contengono caratteri non validi, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="984af-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="984af-105">Per garantire che i nomi siano validi e codificati correttamente, è necessario usare la classe **XmlConvert** per codificare il nome e decodificarlo nuovamente al livello dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="984af-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="984af-106">**XmlWriter** dispone di metodi con cui vengono eseguite operazioni aggiuntive per garantire che venga generato un XML in formato corretto.</span><span class="sxs-lookup"><span data-stu-id="984af-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="984af-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="984af-107">See also</span></span>

- [<span data-ttu-id="984af-108">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="984af-108">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
