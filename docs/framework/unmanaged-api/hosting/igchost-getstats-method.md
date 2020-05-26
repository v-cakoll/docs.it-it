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
ms.openlocfilehash: 67668aa7ff9faf035a047e485a8a3c8a451f45b9
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805243"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="5dd62-102">Metodo IGCHost::GetStats</span><span class="sxs-lookup"><span data-stu-id="5dd62-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="5dd62-103">Ottiene le statistiche per lo stato corrente del sistema di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5dd62-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dd62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5dd62-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dd62-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5dd62-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="5dd62-106">[in, out] Puntatore a una struttura [COR_GC_STATS](cor-gc-stats-structure.md) contenente le statistiche per lo stato corrente del sistema di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5dd62-106">[in, out] A pointer to a [COR_GC_STATS](cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dd62-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5dd62-107">Remarks</span></span>  
 <span data-ttu-id="5dd62-108">Le statistiche possono essere utilizzate da un sistema di allocazione intelligente per consentire il funzionamento del sistema Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5dd62-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="5dd62-109">Ad esempio, il sistema di allocazione può determinare, dopo aver esaminato le statistiche, che è necessario aggiungere altra memoria o forzare una raccolta.</span><span class="sxs-lookup"><span data-stu-id="5dd62-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dd62-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5dd62-110">Requirements</span></span>  
 <span data-ttu-id="5dd62-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dd62-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dd62-112">**Intestazione:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="5dd62-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5dd62-113">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5dd62-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5dd62-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dd62-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd62-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dd62-115">See also</span></span>

- [<span data-ttu-id="5dd62-116">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="5dd62-116">IGCHost Interface</span></span>](igchost-interface.md)
