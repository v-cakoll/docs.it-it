---
title: Metodo ICorThreadpool::CorGetAvailableThreads
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetAvailableThreads
helpviewer_keywords:
- CorGetAvailableThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetAvailableThreads method [.NET Framework hosting]
ms.assetid: 0b09b750-0b86-4ba4-9621-041857cfe8ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c929b9434507ea7cce936767f2ac72ff98fda7b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215794"
---
# <a name="icorthreadpoolcorgetavailablethreads-method"></a><span data-ttu-id="3fc6d-102">Metodo ICorThreadpool::CorGetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="3fc6d-102">ICorThreadpool::CorGetAvailableThreads Method</span></span>
<span data-ttu-id="3fc6d-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc6d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fc6d-104">Syntax</span></span>  
  
```  
HRESULT CorGetAvailableThreads (  
    [out] DWORD *AvailableWorkerThreads,  
    [out] DWORD *AvailableIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3fc6d-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3fc6d-105">Requirements</span></span>  
 <span data-ttu-id="3fc6d-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fc6d-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fc6d-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fc6d-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fc6d-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3fc6d-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fc6d-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fc6d-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc6d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fc6d-110">See also</span></span>

- [<span data-ttu-id="3fc6d-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="3fc6d-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
