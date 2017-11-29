---
title: Metodo ICorThreadpool::CorSetMaxThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorThreadpool.CorSetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 384b214ac38eb99ce45bf3050f33f35702813c69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="aed9d-102">Metodo ICorThreadpool::CorSetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="aed9d-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="aed9d-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="aed9d-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aed9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aed9d-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="aed9d-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aed9d-105">Requirements</span></span>  
 <span data-ttu-id="aed9d-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aed9d-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aed9d-107">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="aed9d-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aed9d-108">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aed9d-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aed9d-109">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aed9d-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aed9d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aed9d-110">See Also</span></span>  
 [<span data-ttu-id="aed9d-111">ICorThreadpool (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="aed9d-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
