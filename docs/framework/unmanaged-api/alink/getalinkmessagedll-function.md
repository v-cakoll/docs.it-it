---
title: Funzione GetALinkMessageDll
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 395dc85ad638e8a790962a4aa38019612c360ce1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402217"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="585d5-102">Funzione GetALinkMessageDll</span><span class="sxs-lookup"><span data-stu-id="585d5-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="585d5-103">Trova e carica la DLL dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="585d5-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="585d5-104">Restituisce 0 se la DLL dei messaggi non è stato disponibile o non caricato.</span><span class="sxs-lookup"><span data-stu-id="585d5-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="585d5-105">La DLL dei messaggi deve essere in una sottodirectory il cui nome è un ID di lingua o nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="585d5-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="585d5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="585d5-106">Syntax</span></span>  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="585d5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="585d5-107">Requirements</span></span>  
 <span data-ttu-id="585d5-108">**Intestazione:** alink.h</span><span class="sxs-lookup"><span data-stu-id="585d5-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="585d5-109">**Libreria**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="585d5-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="585d5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="585d5-110">See Also</span></span>  
 [<span data-ttu-id="585d5-111">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="585d5-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
