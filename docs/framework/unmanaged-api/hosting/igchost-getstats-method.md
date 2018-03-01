---
title: Metodo IGCHost::GetStats
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8d105b0aed9c47d5e2d8ad664744e6424db63961
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="3f54b-102">Metodo IGCHost::GetStats</span><span class="sxs-lookup"><span data-stu-id="3f54b-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="3f54b-103">Ottiene le statistiche per lo stato corrente del sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="3f54b-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f54b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f54b-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f54b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f54b-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="3f54b-106">[in, out] Un puntatore a un [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) struttura che contiene le statistiche per lo stato corrente del sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="3f54b-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f54b-107">Note</span><span class="sxs-lookup"><span data-stu-id="3f54b-107">Remarks</span></span>  
 <span data-ttu-id="3f54b-108">Le statistiche possono essere utilizzate da un sistema intelligente di allocazione per agevolare il sistema di garbage collection di funzionamento.</span><span class="sxs-lookup"><span data-stu-id="3f54b-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="3f54b-109">Ad esempio, può determinare il sistema di allocazione, dopo aver esaminato le statistiche, è necessario aggiungere ulteriore memoria o forzare una raccolta.</span><span class="sxs-lookup"><span data-stu-id="3f54b-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f54b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f54b-110">Requirements</span></span>  
 <span data-ttu-id="3f54b-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f54b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f54b-112">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="3f54b-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="3f54b-113">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f54b-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f54b-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f54b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f54b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f54b-115">See Also</span></span>  
 [<span data-ttu-id="3f54b-116">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="3f54b-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
