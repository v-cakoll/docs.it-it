---
title: Metodo IGCHost::GetThreadStats
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f86385ba4f4186d14994a2028ee11c42127546
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108349"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="22b7c-102">Metodo IGCHost::GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="22b7c-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="22b7c-103">Ottiene le statistiche per ogni thread di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="22b7c-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22b7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22b7c-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22b7c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="22b7c-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="22b7c-106">[in] Puntatore a un fiber cookie che specifica il thread per il quale recuperare le statistiche.</span><span class="sxs-lookup"><span data-stu-id="22b7c-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="22b7c-107">[in, out] Un puntatore a un [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) struttura che contiene le statistiche di garbage collection per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="22b7c-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22b7c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22b7c-108">Requirements</span></span>  
 <span data-ttu-id="22b7c-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22b7c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22b7c-110">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="22b7c-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="22b7c-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="22b7c-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22b7c-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22b7c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22b7c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22b7c-113">See also</span></span>

- [<span data-ttu-id="22b7c-114">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="22b7c-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
