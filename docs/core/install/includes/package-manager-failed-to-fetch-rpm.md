---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920721"
---

<span data-ttu-id="f9485-101">Quando si installa il pacchetto .NET Core, è possibile che venga visualizzato un errore simile a `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span><span class="sxs-lookup"><span data-stu-id="f9485-101">While installing the .NET Core package, you may see an error similar to `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span></span> <span data-ttu-id="f9485-102">In generale, questo errore indica che il feed del pacchetto per .NET Core viene aggiornato con le versioni più recenti del pacchetto e che è necessario riprovare più tardi.</span><span class="sxs-lookup"><span data-stu-id="f9485-102">Generally speaking, this error means that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="f9485-103">Durante un aggiornamento, il feed del pacchetto non deve essere disponibile per più di 2 ore.</span><span class="sxs-lookup"><span data-stu-id="f9485-103">During an upgrade, the package feed should not be unavailable for more than 2 hours.</span></span> <span data-ttu-id="f9485-104">Se questo errore viene visualizzato continuamente per più di due ore, inviare un problema all'<https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="f9485-104">If you continually receive this error for more than 2 hours, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
