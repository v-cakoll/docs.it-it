---
title: Funzione GetCachePath
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 42bae646b0b1cdd451e01d55ed5b218f3660bb5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429478"
---
# <a name="getcachepath-function"></a><span data-ttu-id="218e8-102">Funzione GetCachePath</span><span class="sxs-lookup"><span data-stu-id="218e8-102">GetCachePath Function</span></span>
<span data-ttu-id="218e8-103">Ottiene il percorso all'assembly memorizzati nella cache, utilizzando i flag specificati.</span><span class="sxs-lookup"><span data-stu-id="218e8-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="218e8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="218e8-104">Syntax</span></span>  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="218e8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="218e8-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="218e8-106">[in] Un [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) valore che indica l'origine dell'assembly memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="218e8-106">[in] An [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="218e8-107">[out] Il puntatore restituito al percorso.</span><span class="sxs-lookup"><span data-stu-id="218e8-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="218e8-108">[in, out] La lunghezza massima richiesta di `pwzCachePath`e al momento della restituzione, la lunghezza effettiva di `pwzCachePath`.</span><span class="sxs-lookup"><span data-stu-id="218e8-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="218e8-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="218e8-109">Requirements</span></span>  
 <span data-ttu-id="218e8-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="218e8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="218e8-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="218e8-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="218e8-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="218e8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="218e8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="218e8-113">See Also</span></span>  
 [<span data-ttu-id="218e8-114">Enumerazione ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="218e8-114">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)  
 [<span data-ttu-id="218e8-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="218e8-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
