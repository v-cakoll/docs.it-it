---
title: Metodo ICorThreadpool::CorQueueUserWorkItem
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 249571cbe49fdce720630e31d2da1641aa979624
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218693"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="3b727-102">Metodo ICorThreadpool::CorQueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="3b727-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>
<span data-ttu-id="3b727-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="3b727-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b727-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b727-104">Syntax</span></span>  
  
```  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3b727-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3b727-105">Requirements</span></span>  
 <span data-ttu-id="3b727-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b727-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b727-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3b727-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b727-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3b727-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3b727-109">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3b727-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3b727-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b727-110">See also</span></span>

- [<span data-ttu-id="3b727-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="3b727-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
