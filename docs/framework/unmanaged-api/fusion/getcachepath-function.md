---
title: Funzione GetCachePath
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: GetCachePath
helpviewer_keywords: GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 924482bf34d53d3d7144c4bae93a00a8f8d2ad4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="getcachepath-function"></a><span data-ttu-id="b9ae9-102">Funzione GetCachePath</span><span class="sxs-lookup"><span data-stu-id="b9ae9-102">GetCachePath Function</span></span>
<span data-ttu-id="b9ae9-103">Ottiene il percorso all'assembly memorizzati nella cache, utilizzando i flag specificati.</span><span class="sxs-lookup"><span data-stu-id="b9ae9-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ae9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9ae9-104">Syntax</span></span>  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9ae9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9ae9-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="b9ae9-106">[in] Un [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) valore che indica l'origine dell'assembly memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="b9ae9-106">[in] An [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="b9ae9-107">[out] Il puntatore restituito al percorso.</span><span class="sxs-lookup"><span data-stu-id="b9ae9-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="b9ae9-108">[in, out] La lunghezza massima richiesta di `pwzCachePath`e al momento della restituzione, la lunghezza effettiva di `pwzCachePath`.</span><span class="sxs-lookup"><span data-stu-id="b9ae9-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9ae9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9ae9-109">Requirements</span></span>  
 <span data-ttu-id="b9ae9-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9ae9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9ae9-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b9ae9-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b9ae9-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9ae9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ae9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9ae9-113">See Also</span></span>  
 [<span data-ttu-id="b9ae9-114">Enumerazione ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b9ae9-114">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)  
 [<span data-ttu-id="b9ae9-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="b9ae9-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
