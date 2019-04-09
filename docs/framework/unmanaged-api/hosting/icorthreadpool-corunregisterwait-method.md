---
title: Metodo ICorThreadpool::CorUnregisterWait
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorUnregisterWait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnregisterWait
helpviewer_keywords:
- CorUnregisterWait method [.NET Framework hosting]
- ICorThreadpool::CorUnregisterWait method [.NET Framework hosting]
ms.assetid: 42c933f1-30a8-4011-bdea-e117f3c3265e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af41a20bcdcbfc44a5a4b0b30947ab9093948291
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122837"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="ecbd1-102">Metodo ICorThreadpool::CorUnregisterWait</span><span class="sxs-lookup"><span data-stu-id="ecbd1-102">ICorThreadpool::CorUnregisterWait Method</span></span>
<span data-ttu-id="ecbd1-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecbd1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ecbd1-104">Syntax</span></span>  
  
```  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ecbd1-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ecbd1-105">Requirements</span></span>  
 <span data-ttu-id="ecbd1-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecbd1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecbd1-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ecbd1-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ecbd1-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ecbd1-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ecbd1-109">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ecbd1-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ecbd1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecbd1-110">See also</span></span>

- [<span data-ttu-id="ecbd1-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="ecbd1-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
