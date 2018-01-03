---
title: "La chiave del Registro di sistema specificata non è valida perché contiene due o più barre rovesciate consecutive"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 0d78b6f7-5759-45b4-8c37-c6902ada76ff
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94cf205a00260768ec4b7a458e89b81b20aaab2e
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="specified-registry-key-is-not-valid-because-it-contains-two-or-more-consecutive-backslashes"></a><span data-ttu-id="cb5e8-102">La chiave del Registro di sistema specificata non è valida perché contiene due o più barre rovesciate consecutive</span><span class="sxs-lookup"><span data-stu-id="cb5e8-102">Specified registry key is not valid because it contains two or more consecutive backslashes</span></span>
<span data-ttu-id="cb5e8-103">Una chiave del Registro di sistema specificata con un percorso contiene due o più barre rovesciate consecutive.</span><span class="sxs-lookup"><span data-stu-id="cb5e8-103">A registry key specified with a path contains two or more consecutive backslashes.</span></span> <span data-ttu-id="cb5e8-104">Può verificarsi se si combinano più stringhe per formare il percorso e si include inavvertitamente un numero eccessivo di barre rovesciate.</span><span class="sxs-lookup"><span data-stu-id="cb5e8-104">This may be a result of combining several strings to form the path and inadvertently including too many backslashes.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cb5e8-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="cb5e8-105">To correct this error</span></span>  
  
-   <span data-ttu-id="cb5e8-106">Esaminare la chiave del Registro di sistema specificata per determinare dove e perché vengono inserite le barre rovesciate in eccesso.</span><span class="sxs-lookup"><span data-stu-id="cb5e8-106">Examine the registry key being specified to determine where and why the extra backslashes are being inserted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb5e8-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb5e8-107">See Also</span></span>  
 [<span data-ttu-id="cb5e8-108">Procedura: analizzare percorsi di file</span><span class="sxs-lookup"><span data-stu-id="cb5e8-108">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [<span data-ttu-id="cb5e8-109">Registry</span><span class="sxs-lookup"><span data-stu-id="cb5e8-109">My.Computer.Registry</span></span>](xref:Microsoft.VisualBasic.MyServices.RegistryProxy)
