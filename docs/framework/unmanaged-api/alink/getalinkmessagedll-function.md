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
ms.openlocfilehash: 41e79a4c9587e3e738039cbf6a84087a2e7fc9b1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741951"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="ed079-102">Funzione GetALinkMessageDll</span><span class="sxs-lookup"><span data-stu-id="ed079-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="ed079-103">Trova e carica la DLL dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ed079-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="ed079-104">Restituisce 0 se non è stato possibile che si trova o caricare la DLL dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ed079-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="ed079-105">La DLL dei messaggi deve essere in una sottodirectory il cui nome è un ID di lingua, o nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="ed079-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed079-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed079-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="ed079-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed079-107">Requirements</span></span>  
 <span data-ttu-id="ed079-108">**Intestazione:** alink.h</span><span class="sxs-lookup"><span data-stu-id="ed079-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="ed079-109">**Libreria**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="ed079-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed079-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed079-110">See also</span></span>

- [<span data-ttu-id="ed079-111">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="ed079-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
