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
ms.openlocfilehash: 69976110a227f95cf157b19b270f25cc3808246e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484108"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="5c6bc-102">Metodo IGCHost2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="5c6bc-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="5c6bc-103">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c6bc-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c6bc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c6bc-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="5c6bc-106">[in] Le dimensioni del segmento usato dal sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="5c6bc-107">[in] La dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c6bc-108">Note</span><span class="sxs-lookup"><span data-stu-id="5c6bc-108">Remarks</span></span>  
 <span data-ttu-id="5c6bc-109">I valori che `SetGCStartupLimitsEx` set possono essere specificati solo prima dell'avvio dell'host.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="5c6bc-110">Questi valori non possono essere modificati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c6bc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c6bc-111">Requirements</span></span>  
 <span data-ttu-id="5c6bc-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c6bc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c6bc-113">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="5c6bc-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5c6bc-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5c6bc-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c6bc-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c6bc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c6bc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c6bc-116">See also</span></span>
- [<span data-ttu-id="5c6bc-117">Interfaccia IGCHost2</span><span class="sxs-lookup"><span data-stu-id="5c6bc-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
