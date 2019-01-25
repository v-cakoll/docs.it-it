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
ms.openlocfilehash: 632f19e0ead57d5508265fece578bb22f18ba54a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722725"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="8764e-102">Funzione GetALinkMessageDll</span><span class="sxs-lookup"><span data-stu-id="8764e-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="8764e-103">Trova e carica la DLL dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="8764e-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="8764e-104">Restituisce 0 se non è stato possibile che si trova o caricare la DLL dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="8764e-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="8764e-105">La DLL dei messaggi deve essere in una sottodirectory il cui nome è un ID di lingua, o nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="8764e-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8764e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8764e-106">Syntax</span></span>  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="8764e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8764e-107">Requirements</span></span>  
 <span data-ttu-id="8764e-108">**Intestazione:** alink.h</span><span class="sxs-lookup"><span data-stu-id="8764e-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="8764e-109">**Libreria**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="8764e-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8764e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8764e-110">See also</span></span>
- [<span data-ttu-id="8764e-111">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="8764e-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
