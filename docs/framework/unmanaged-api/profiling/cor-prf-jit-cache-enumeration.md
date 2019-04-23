---
title: Enumerazione COR_PRF_JIT_CACHE
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cdbe36403f830926d611ffdc655d82ea25ddeef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144794"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="8c30e-102">Enumerazione COR_PRF_JIT_CACHE</span><span class="sxs-lookup"><span data-stu-id="8c30e-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="8c30e-103">Indica il risultato della ricerca di una funzione memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="8c30e-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c30e-104">`COR_PRF_CACHED_FUNCTION_FOUND` ha un valore pari a zero, pertanto, `COR_PRF_JIT_CACHE` non può essere utilizzato come un surrogato booleano.</span><span class="sxs-lookup"><span data-stu-id="8c30e-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c30e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c30e-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="8c30e-106">Membri</span><span class="sxs-lookup"><span data-stu-id="8c30e-106">Members</span></span>  
  
|<span data-ttu-id="8c30e-107">Member</span><span class="sxs-lookup"><span data-stu-id="8c30e-107">Member</span></span>|<span data-ttu-id="8c30e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c30e-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="8c30e-109">La ricerca ha rilevato la funzione.</span><span class="sxs-lookup"><span data-stu-id="8c30e-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="8c30e-110">La ricerca non ha trovato la funzione.</span><span class="sxs-lookup"><span data-stu-id="8c30e-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c30e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8c30e-111">Requirements</span></span>  
 <span data-ttu-id="8c30e-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c30e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c30e-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8c30e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8c30e-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c30e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c30e-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c30e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c30e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c30e-116">See also</span></span>

- [<span data-ttu-id="8c30e-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="8c30e-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
