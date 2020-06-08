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
ms.openlocfilehash: d19d7ed2262db6d3c6e7f15db0e96da52f86db4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500858"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="9a592-102">Enumerazione COR_PRF_JIT_CACHE</span><span class="sxs-lookup"><span data-stu-id="9a592-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="9a592-103">Indica il risultato della ricerca di una funzione memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="9a592-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9a592-104">`COR_PRF_CACHED_FUNCTION_FOUND`ha un valore pari a zero, quindi `COR_PRF_JIT_CACHE` non può essere usato come surrogato booleano.</span><span class="sxs-lookup"><span data-stu-id="9a592-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a592-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a592-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="9a592-106">Membri</span><span class="sxs-lookup"><span data-stu-id="9a592-106">Members</span></span>  
  
|<span data-ttu-id="9a592-107">Membro</span><span class="sxs-lookup"><span data-stu-id="9a592-107">Member</span></span>|<span data-ttu-id="9a592-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a592-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="9a592-109">La ricerca ha rilevato la funzione.</span><span class="sxs-lookup"><span data-stu-id="9a592-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="9a592-110">La ricerca non ha trovato la funzione.</span><span class="sxs-lookup"><span data-stu-id="9a592-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a592-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a592-111">Requirements</span></span>  
 <span data-ttu-id="9a592-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a592-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a592-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9a592-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a592-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a592-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a592-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a592-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a592-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a592-116">See also</span></span>

- [<span data-ttu-id="9a592-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="9a592-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
