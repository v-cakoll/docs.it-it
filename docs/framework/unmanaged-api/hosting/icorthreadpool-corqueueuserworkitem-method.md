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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700085"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="cbdd1-102">Metodo ICorThreadpool::CorQueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="cbdd1-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>
<span data-ttu-id="cbdd1-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="cbdd1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbdd1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbdd1-104">Syntax</span></span>  
  
```  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cbdd1-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cbdd1-105">Requirements</span></span>  
 <span data-ttu-id="cbdd1-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbdd1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbdd1-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cbdd1-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cbdd1-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cbdd1-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cbdd1-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbdd1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbdd1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbdd1-110">See also</span></span>

- [<span data-ttu-id="cbdd1-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="cbdd1-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
