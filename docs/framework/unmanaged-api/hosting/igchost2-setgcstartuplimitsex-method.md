---
title: Metodo IGCHost2::SetGCStartupLimitsEx
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e834042c5e00709fcb2198c1496a8a630841d069
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779532"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="2933d-102">Metodo IGCHost2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="2933d-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="2933d-103">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="2933d-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2933d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2933d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2933d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2933d-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="2933d-106">[in] Le dimensioni del segmento usato dal sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="2933d-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="2933d-107">[in] La dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="2933d-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2933d-108">Note</span><span class="sxs-lookup"><span data-stu-id="2933d-108">Remarks</span></span>  
 <span data-ttu-id="2933d-109">I valori che `SetGCStartupLimitsEx` set possono essere specificati solo prima dell'avvio dell'host.</span><span class="sxs-lookup"><span data-stu-id="2933d-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="2933d-110">Questi valori non possono essere modificati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="2933d-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2933d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2933d-111">Requirements</span></span>  
 <span data-ttu-id="2933d-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2933d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2933d-113">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="2933d-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="2933d-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2933d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2933d-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2933d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2933d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2933d-116">See also</span></span>

- [<span data-ttu-id="2933d-117">Interfaccia IGCHost2</span><span class="sxs-lookup"><span data-stu-id="2933d-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
