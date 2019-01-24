---
title: Metodo IGCHost::GetStats
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d9a3775f453cb432ce6b92d067f93ca54c329c06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674180"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="ad7df-102">Metodo IGCHost::GetStats</span><span class="sxs-lookup"><span data-stu-id="ad7df-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="ad7df-103">Ottiene le statistiche per lo stato corrente del sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ad7df-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad7df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad7df-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad7df-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad7df-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="ad7df-106">[in, out] Un puntatore a un [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) struttura che contiene le statistiche per lo stato corrente del sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ad7df-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad7df-107">Note</span><span class="sxs-lookup"><span data-stu-id="ad7df-107">Remarks</span></span>  
 <span data-ttu-id="ad7df-108">Le statistiche possono essere utilizzate da un sistema di assegnazione intelligente per agevolare il sistema di garbage collection di corretto funzionamento.</span><span class="sxs-lookup"><span data-stu-id="ad7df-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="ad7df-109">Ad esempio, il sistema di allocazione può determinare, dopo aver esaminato le statistiche, è necessario aggiungere ulteriore memoria o forzare una raccolta.</span><span class="sxs-lookup"><span data-stu-id="ad7df-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad7df-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad7df-110">Requirements</span></span>  
 <span data-ttu-id="ad7df-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad7df-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad7df-112">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="ad7df-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="ad7df-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ad7df-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad7df-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad7df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad7df-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad7df-115">See also</span></span>
- [<span data-ttu-id="ad7df-116">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="ad7df-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
