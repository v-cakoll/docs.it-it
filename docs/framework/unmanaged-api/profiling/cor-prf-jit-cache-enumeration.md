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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144794"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="0bb6a-102">Enumerazione COR_PRF_JIT_CACHE</span><span class="sxs-lookup"><span data-stu-id="0bb6a-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="0bb6a-103">Indica il risultato della ricerca di una funzione memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="0bb6a-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  `COR_PRF_CACHED_FUNCTION_FOUND` <span data-ttu-id="0bb6a-104">ha un valore pari a zero, pertanto, `COR_PRF_JIT_CACHE` non può essere utilizzato come un surrogato booleano.</span><span class="sxs-lookup"><span data-stu-id="0bb6a-104">has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bb6a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0bb6a-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="0bb6a-106">Membri</span><span class="sxs-lookup"><span data-stu-id="0bb6a-106">Members</span></span>  
  
|<span data-ttu-id="0bb6a-107">Member</span><span class="sxs-lookup"><span data-stu-id="0bb6a-107">Member</span></span>|<span data-ttu-id="0bb6a-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0bb6a-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="0bb6a-109">La ricerca ha rilevato la funzione.</span><span class="sxs-lookup"><span data-stu-id="0bb6a-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="0bb6a-110">La ricerca non ha trovato la funzione.</span><span class="sxs-lookup"><span data-stu-id="0bb6a-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bb6a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0bb6a-111">Requirements</span></span>  
 <span data-ttu-id="0bb6a-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bb6a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bb6a-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0bb6a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0bb6a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bb6a-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0bb6a-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0bb6a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0bb6a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bb6a-116">See also</span></span>

- [<span data-ttu-id="0bb6a-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="0bb6a-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
