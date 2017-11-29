---
title: Enumerazione COR_PRF_JIT_CACHE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_JIT_CACHE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_JIT_CACHE
helpviewer_keywords: COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 08fe81321e958d61c1aae86ae366077b563dba3e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="7b3f0-102">Enumerazione COR_PRF_JIT_CACHE</span><span class="sxs-lookup"><span data-stu-id="7b3f0-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="7b3f0-103">Indica il risultato della ricerca di una funzione memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="7b3f0-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b3f0-104">`COR_PRF_CACHED_FUNCTION_FOUND`ha un valore pari a zero, pertanto `COR_PRF_JIT_CACHE` non può essere utilizzato come un surrogato booleano.</span><span class="sxs-lookup"><span data-stu-id="7b3f0-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b3f0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b3f0-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="7b3f0-106">Membri</span><span class="sxs-lookup"><span data-stu-id="7b3f0-106">Members</span></span>  
  
|<span data-ttu-id="7b3f0-107">Membro</span><span class="sxs-lookup"><span data-stu-id="7b3f0-107">Member</span></span>|<span data-ttu-id="7b3f0-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b3f0-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="7b3f0-109">La funzione è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="7b3f0-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="7b3f0-110">La ricerca non ha trovato la funzione.</span><span class="sxs-lookup"><span data-stu-id="7b3f0-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b3f0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b3f0-111">Requirements</span></span>  
 <span data-ttu-id="7b3f0-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b3f0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b3f0-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7b3f0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7b3f0-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b3f0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b3f0-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b3f0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b3f0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b3f0-116">See Also</span></span>  
 [<span data-ttu-id="7b3f0-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="7b3f0-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
