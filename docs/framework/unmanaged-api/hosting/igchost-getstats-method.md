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
ms.openlocfilehash: c86786a34ff236fb57a1ea6bc4d00b9cd5c4a717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134891"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="d5b2b-102">Metodo IGCHost::GetStats</span><span class="sxs-lookup"><span data-stu-id="d5b2b-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="d5b2b-103">Ottiene le statistiche per lo stato corrente del sistema di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d5b2b-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b2b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5b2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5b2b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d5b2b-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="d5b2b-106">[in, out] Puntatore a una struttura [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) che contiene le statistiche per lo stato corrente del sistema di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d5b2b-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5b2b-107">Note</span><span class="sxs-lookup"><span data-stu-id="d5b2b-107">Remarks</span></span>  
 <span data-ttu-id="d5b2b-108">Le statistiche possono essere utilizzate da un sistema di allocazione intelligente per consentire il funzionamento del sistema Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d5b2b-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="d5b2b-109">Ad esempio, il sistema di allocazione può determinare, dopo aver esaminato le statistiche, che è necessario aggiungere altra memoria o forzare una raccolta.</span><span class="sxs-lookup"><span data-stu-id="d5b2b-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5b2b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d5b2b-110">Requirements</span></span>  
 <span data-ttu-id="d5b2b-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5b2b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5b2b-112">**Intestazione:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="d5b2b-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="d5b2b-113">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d5b2b-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5b2b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5b2b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b2b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5b2b-115">See also</span></span>

- [<span data-ttu-id="d5b2b-116">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="d5b2b-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
