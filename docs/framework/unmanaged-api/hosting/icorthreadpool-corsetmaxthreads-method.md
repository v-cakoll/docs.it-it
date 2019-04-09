---
title: Metodo ICorThreadpool::CorSetMaxThreads
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48d84d5c45ea8e1af1da44480410692d46162810
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198244"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="e3109-102">Metodo ICorThreadpool::CorSetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="e3109-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="e3109-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="e3109-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3109-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3109-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e3109-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3109-105">Requirements</span></span>  
 <span data-ttu-id="e3109-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3109-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3109-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e3109-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3109-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e3109-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e3109-109">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e3109-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e3109-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3109-110">See also</span></span>

- [<span data-ttu-id="e3109-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="e3109-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
