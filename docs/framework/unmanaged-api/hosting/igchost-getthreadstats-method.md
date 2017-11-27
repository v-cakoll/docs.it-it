---
title: Metodo IGCHost::GetThreadStats
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.GetThreadStats
api_location: mscoree.dll
api_type: COM
f1_keywords: GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7bfd6b89c3220e071a477e0c5b85e4ee57289762
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="3fa89-102">Metodo IGCHost::GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="3fa89-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="3fa89-103">Ottiene le statistiche per ogni thread di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="3fa89-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fa89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fa89-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fa89-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3fa89-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="3fa89-106">[in] Puntatore a un fiber cookie che specifica il thread per il quale recuperare le statistiche.</span><span class="sxs-lookup"><span data-stu-id="3fa89-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="3fa89-107">[in, out] Un puntatore a un [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) struttura che contiene le statistiche di garbage collection per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="3fa89-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fa89-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3fa89-108">Requirements</span></span>  
 <span data-ttu-id="3fa89-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fa89-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fa89-110">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="3fa89-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="3fa89-111">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3fa89-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fa89-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fa89-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa89-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fa89-113">See Also</span></span>  
 [<span data-ttu-id="3fa89-114">IGCHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3fa89-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
