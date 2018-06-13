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
ms.openlocfilehash: b7cbc14c1b84ae5605f7aaed688acbedbb51d056
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437131"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="ab251-102">Metodo ICorThreadpool::CorSetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="ab251-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="ab251-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="ab251-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab251-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab251-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ab251-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab251-105">Requirements</span></span>  
 <span data-ttu-id="ab251-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab251-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab251-107">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="ab251-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab251-108">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ab251-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab251-109">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab251-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab251-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab251-110">See Also</span></span>  
 [<span data-ttu-id="ab251-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="ab251-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
