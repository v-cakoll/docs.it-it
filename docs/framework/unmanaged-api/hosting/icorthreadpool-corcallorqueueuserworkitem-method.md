---
title: Metodo ICorThreadpool::CorCallOrQueueUserWorkItem
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCallOrQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallOrQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorCallOrQueueUserWorkItem method [.NET Framework hosting]
- CorCallOrQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: a2081223-84ca-4331-a8d3-9352f422f3e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7dd4589da9b59d7e701ac641c8d45be3735d0b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199167"
---
# <a name="icorthreadpoolcorcallorqueueuserworkitem-method"></a><span data-ttu-id="a98e6-102">Metodo ICorThreadpool::CorCallOrQueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="a98e6-102">ICorThreadpool::CorCallOrQueueUserWorkItem Method</span></span>
<span data-ttu-id="a98e6-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="a98e6-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a98e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a98e6-104">Syntax</span></span>  
  
```  
HRESULT CorCallOrQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a98e6-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a98e6-105">Requirements</span></span>  
 <span data-ttu-id="a98e6-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a98e6-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a98e6-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a98e6-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a98e6-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a98e6-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a98e6-109">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a98e6-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a98e6-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a98e6-110">See also</span></span>

- [<span data-ttu-id="a98e6-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="a98e6-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
