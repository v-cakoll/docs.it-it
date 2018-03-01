---
title: Metodo ICorThreadpool::CorGetMaxThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorThreadpool.CorGetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetMaxThreads
helpviewer_keywords:
- CorGetMaxThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetMaxThreads method [.NET Framework hosting]
ms.assetid: 2861533a-cda0-47b3-b716-0d363505289b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 066497578f9587da670df5aede4750375c94a7ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="b83fd-102">Metodo ICorThreadpool::CorGetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="b83fd-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="b83fd-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="b83fd-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b83fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b83fd-104">Syntax</span></span>  
  
```  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="b83fd-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b83fd-105">Requirements</span></span>  
 <span data-ttu-id="b83fd-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b83fd-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b83fd-107">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="b83fd-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b83fd-108">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b83fd-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b83fd-109">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b83fd-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b83fd-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b83fd-110">See Also</span></span>  
 [<span data-ttu-id="b83fd-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="b83fd-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
